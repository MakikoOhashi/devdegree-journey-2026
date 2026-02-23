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
