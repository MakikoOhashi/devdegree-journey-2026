# Azure Hackathon - Shelf: Dev Log

## 2026-05-07
- Shelf リポの方向性を整理
- 過去の貿易（繊維商社）実務の痛み・論点を「プロダクトの問題定義」として扱う方針に寄せて README を固めた
- 目標: “AIで何か作る”ではなく「自分だけが解像度を持つ現場課題」を構造化して差別化する

## 2026-05-08
- UI 改善
  - 本棚（Shelf）の挙動を改善
  - Human in the loop の「どこで人が判断するか」を UI で理解できる見え方に寄せた

## 2026-05-09
- Decision Context Engine の方向性を整理
  - AIが自動で判断するプロダクトではなく、「人間が判断する前に必要な根拠・過去事例・バランス情報」を右側に即提示する設計に寄せた
  - Human Decision を押す前に、担当者が判断材料をすぐ確認できることを優先

## 2026-05-10
- UI を 2026-05-13 までに固める方針を決定（機能追加より「見せ方の固定」を優先）
- Shipment Workspace / SI Workspace の進捗グラフ準備を開始

## 2026-05-11
- Resolution Decision Tree を「分岐型確認フロー」として読みやすい FLOW 図へ修正

## 2026-05-12
- GitHub的UIに決定して全体を再設計（Shelf / Issues（AI承認センター）/ Documents / Settings）
- 「変更・確認依頼」で AI エージェントと営業が直接やりとりできる導線へ更新

## 2026-05-13
- 活動ログページを新設（AIがどこまで受信し、どう整理し、どこへ流したかを見える化）
- 入力受信→整理→Issue化→Human確認のフローをMOCKで確認
- Azure アカウント作成と AI 連携まで完了（概念からシステムへ進める前提が整った）

## 2026-05-14
- AI の責務を分離（Orchestrator / Processor）
  - Processor: 分類 / 抽出 / 紐付け / 提案
  - Orchestrator: 入力受信→Processor呼び出し→Issue化→Human承認→ログ出力の統制
- 変更依頼→承認センター→活動ログの見え方を整理（連番・並びの一貫性を優先）
- 設計メモを `projects/agent-processors.md` に固定

## 2026-05-15
- UI を見直し（不要なナビゲーションとページを削除して認知負荷を削減）
- Action Planner の前に Intake Resolver を追加
  - AI 実行の前に「入力を業務単位へ整理する入口レイヤ」を挟む設計に寄せた
