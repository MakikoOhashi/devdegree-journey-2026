# wakarumade-ios: Dev Log

## 2026-03-03

### 進捗
- UIまでざっくりFIX完了
- 残タスクは類題作成まわりと細かな修正
- 追加機能（進捗ログなど）の要否・優先度を検討中

### 実装方針（今回）
- 既存のWeb（Vercel）側APIを再利用してiOSから叩く構成にした
- 別サーバーを新規で用意せずに進められ、開発が軽くなった

### 次の設計着想
- `common-ai-api`（Vercel / Next.js）を共通基盤として用意し、複数アプリで再利用

エンドポイント例:
- `POST /chat`
- `POST /parse`
- `POST /similar`
- `POST /log`

共通ヘッダー:
- `x-app-id: wakarumade-ios`
- `x-guest-id: ...`

想定環境変数:
- `GEMINI_API_KEY`
- `SUPABASE_SERVICE_ROLE_KEY`
- `SUPABASE_URL`

## 2026-03-04

### 進捗
- バックエンド接続を、Web(Vercel)の個別エンドポイント呼び出し構成から `common-ai-api` に完全移行
- iOS側の利用先を一本化し、運用・拡張時の管理ポイントを削減

### 判断
- アプリごとのAPI分散をやめ、共通基盤への集約を優先
- 今後の機能追加は `common-ai-api` 側で吸収し、iOS側変更を最小化する方針

## 2026-03-05

### 今日の目標
- WAKARUMADE iOS を審査提出
- 提出フォーム: https://www.tfaforms.com/4956119

### 実績
- WAKARUMADE iOS をひとまず審査提出完了

## 2026-03-08

### 実績
- WAKARUMADE iOS 公開完了

## 2026-03-09

### 実績
- WAKARUMADE iOS `1.0.2` を審査提出
- 変更内容: 英語版対応、Bug Fix ほか
- WAKARUMADE LPを作成・公開
  - URL: https://wakarumade-app.vercel.app/
  - Repository: https://github.com/MakikoOhashi/v0-wakarumade-landing-page

## 2026-03-10

### 実績
- WAKARUMADE AppのYouTube Shortsを初投稿
  - URL: https://www.youtube.com/shorts/drcE4hPdPUI

### 運用方針
- 今日から毎朝、WAKARUMADEのYouTube Shortsを1本投稿する

## 2026-03-11

### 状況
- App Store Connect: `iOS 1.0.3 Waiting for Review`

### 方針
- マーケティング仮説としてインド市場を優先候補に設定
- Android版（展開可否・実装方式）を検討開始

### 実績
- YouTube Shortsを投稿（日課継続）

## 2026-03-12

### 状況
- App Store Connect: `iOS 1.0.3 Waiting for Review`（待ち継続）

### 実績
- YouTube Shortsを投稿（日課継続）
  - URL: https://youtube.com/shorts/61psYii-Afs

## 2026-03-13

### 状況
- App Store Connect: `iOS 1.0.3 In Review`
- App Store Connect: `iOS 1.0.3 Ready for Distribution`

### 実績
- YouTube Shortsを投稿（日課継続）
  - URL: https://youtube.com/shorts/FD4bD4Bn2XQ?feature=share

## 2026-03-14

### 実績
- YouTube Shortsを投稿（日課継続）
  - URL: https://youtube.com/shorts/IjVkc2e0rbM
