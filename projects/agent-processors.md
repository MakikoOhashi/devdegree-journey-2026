# Agent Processors (Orchestrator / Processor 分離)

Azure Hackathon - Shelf の「入力→整理→Issue→承認→ログ」を壊れにくくするための設計メモ。

## 目的
- 単一LLMの“なんでも屋”化を避け、責務を固定して品質と再現性を上げる
- Human approval を前提に、判断材料の整理とログ可視化を主戦場にする

## 全体像
- **Orchestrator LLM**
  - 入力を受け取り、必要な Processor を選び、結果を統合して Issue を作る
  - Human 承認ステップを挟み、最終適用（または却下）までの状態遷移を統制する
  - 活動ログ（何を受け取り、どのProcessorを呼び、何が出て、どう判断されたか）を出力する
- **Processor LLMs（役割別）**
  - 1つの Processor は 1つの責務に集中し、入出力を固定する

## Processor の責務（最小セット）
1. **分類（Classifier）**
   - 入力を「どのドメイン/ワークスペース/論点か」に分類する
   - 例: shipment / SI / docs / issue-type（質問/変更依頼/確認依頼/エスカレーション）
2. **抽出（Extractor）**
   - 入力から事実・要件・制約・期限・関係者を抽出する
   - “解釈”ではなく“拾う”を優先し、抜けの質問（clarifying questions）も列挙する
3. **紐付け（Linker）**
   - 既存の Shelf / Issues / Documents / 過去ログ へ関連付け候補を出す
   - 例: 既存Issueの重複検知、関連ドキュメント候補、影響範囲候補
4. **提案（Proposer）**
   - 具体的な次アクション案を複数提示する（案A/B/C）
   - それぞれに: 期待効果 / リスク / 必要な確認 / 最小実行手順 を付ける

## データフロー（状態遷移）
1. Input 受信
2. Orchestrator が Processor を選択して順次実行
3. 統合して Issue（判断単位）を作成
4. Human approval（承認/差し戻し/却下）
5. Apply（反映）または Close
6. 活動ログに出力（再現可能な履歴）

## ログ（最低限ほしい項目）
- `event_id`（連番/一意ID）
- `received_at`（受信時刻）
- `input_source`（メール/フォーム/Slack等）
- `orchestrator_decision`（どのProcessorを呼んだか、順序）
- `processor_outputs`（要約＋主要フィールド）
- `issue_id`（作成/紐付け先）
- `human_decision`（承認/差し戻し/却下）
- `applied_changes`（実際に反映した内容）

## 守るルール（運用のための制約）
- Processor は「文章をうまくする」より「構造を揃える」を優先
- Orchestrator は “勝手に確定” しない（Human approval を通す）
- 迷ったら Processor を増やすより、入出力スキーマを締める

