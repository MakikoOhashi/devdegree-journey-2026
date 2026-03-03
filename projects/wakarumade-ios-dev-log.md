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
