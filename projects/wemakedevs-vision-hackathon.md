# WeMakeDevs Vision Hackathon メモ

## 2026-02-23

### 参加情報
- 登録: https://www.wemakedevs.org/hackathons/vision/resources
- 着手予定: 2026-02-24 から

### テーマ（現時点）
- Visionを使った学習支援
- OCR中心はやめる
- iPad + Apple Pencil前提
- 子どもが「書けていない部分」を検知し、`困ってる？ ここみて！` のようにマーキングするアプリ

### 技術方針
- Swiftで開始
- ClaudeCodeの活用を検討
- Python要素も入れて経験を作る（GSoC応募先の広がりを意識）
- リポジトリは未作成

### 依存関係と順序
- Ruidaichan完了後にWAKARUMADEのSwift化を進める案
- 理由: Xcodeの同時運用が重く、作業が分散しやすいため
- まずはVisionテーマの最小形を早く決める

### 進路メモ
- MLH: SpringBは不採用
- 次: Summerに応募

### VPS学習メモ（今日の気づき）
1. 広がるのは責任範囲
- プロセス障害、再起動影響、ログ監視、秘密情報管理、夜間障害責任を自分で設計する視点が得られる

2. 広がるのは抽象化理解
- PaaS/Serverlessが「楽なもの」ではなく「責任をどこまで肩代わりする抽象化か」で見える
- AI運用判断（推論場所、バッチ/常駐、メモリ不足時の方針）に直結する

### 一言
- VPS理解は「所有しない設計」を選ぶための前提知識になる

## 2026-02-25

### 進捗
- ハッカソン要件確認: https://www.wemakedevs.org/hackathons/vision/rules
- iPadアプリを立ち上げ
- リポジトリ作成: https://github.com/MakikoOhashi/pencil-stuck-marker

### 実装到達点
- Xcodeを起動して実装開始
- Simulator上で描画を確認
- 描画停止を10秒で検知
- 停止した箇所を黄色アノテーションするところまで実装

### テーマ確認
- Visionを使う
- Pythonも使ってみる（GSoC応募の選択肢拡張のため）

## 提出ロードマップ（2026-02-26 -> 2026-03-02 05:00 JST）

### 戦略
- ストア提出は対象外。`動くデモ + README + 短い動画` に集中
- 勝ち筋は「詰まり検知 -> 声かけ -> 空間アノテーション」を明確に見せること

### やらないこと
- OCR
- 正解提示
- 本格チャット
- 複数問題対応
- 審査提出向けのiOS配布対応

### やること
- Vision Agentが「介入してよいか」を判断
- Pythonが「何を表示するか」を決定
- その流れを2-3分動画で伝える

### Day 1（2/26）
- Swift側: 詰まり検知（stall / oscillation）を関数分離
- Vision Agent呼び出しを1箇所に集約（`verify_intervention`）
- Python最小APIを接続（region情報 -> 表示メッセージJSON）
- 到達点: Swift -> Vision Agent -> Python -> Swift が1回通る

### Day 2（2/27）
- UI最小仕上げ（黄色ハイライト、吹き出し、dismiss/強調）
- READMEでVision Agents SDKの役割とPythonの役割を明記
- 到達点: 第三者が見て「介入の意図」が分かる状態

### Day 3（2/28）
- デモ動画撮影（2-3分）
- 構成: 読込 -> 書く -> 停止 -> 吹き出し -> 強調 -> 再開
- 字幕/ナレーションに以下を含める:
  - No OCR
  - No answers
  - Behavior-based intervention
  - Vision Agent verifies before interrupting
- 到達点: 提出可能な動画1本

### Day 4（3/1）
- README最終チェック
- 動画URL確定
- 提出フォーム入力
- 直すのは致命的不具合のみ（UI微調整はしない）

### 判断基準
- その作業は「動画で一発で伝わるか」
  - YES: やる
  - NO: やらない
