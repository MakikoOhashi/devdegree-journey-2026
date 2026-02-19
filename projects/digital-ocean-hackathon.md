# Digital Ocean Hackathon

## 概要
- **時期:** 2026年2月
- **内容:** AIの出力評価（制御）による試験問題類題作成プロダクト
- **提出物リポジトリ:** https://github.com/MakikoOhashi/deterministic-ai-control-engine
- **現状:** 提出準備中
- **提出期限:** 2月末

## コンセプト
AIの出力を評価・制御することで質の高い試験問題の類題を自動生成

## 提出物サマリー（2026-02-19時点）

### 1. Guided Reading v1 フロー整理
- フロントから `POST /ocr/structure` 前処理呼び出しを削除
- 入力は軽量クライアント正規化（trim/改行/空白）に変更
- Guided Readingに不要な空欄補充系 state/ロジックを `frontend/app/page.tsx` から削除

### 2. Static Siteデプロイ対応
- `frontend/next.config.js` に `output: "export"` を追加
- `frontend` ビルドで `out/` 生成を確認
- DO Static Site 前提（source=`frontend`, output=`out`）と整合

### 3. README整備（実装整合 + 運用）
- パイプライン説明を現状へ更新（`/ocr/structure` 非依存）
- DO Backend/Frontendの設定手順を追記
- `NEXT_PUBLIC_API_BASE` 注意点（パスprefix必要ケース、再デプロイ必須）を追記
- Live Demo / Status / v1スコープ説明を強化

### 4. Generation providerをGradient専用化
- `backend/src/providers/gradient.generate.provider.ts` を追加（chat/completions）
- `backend/src/index.ts` のgeneration providerをGradient専用へ変更
- Gemini generationフォールバックを削除
- 既定値をDO Inference向けに設定
  - `GRADIENT_BASE_URL=https://inference.do-ai.run/v1`
  - `GRADIENT_MODEL=llama3.3-70b-instruct`（envで上書き可）

### 5. EmbeddingはGemini維持（ハイブリッド）
- 生成はGradient、評価用embeddingはGeminiの構成を維持
- embedding providerは抽象化済みで、将来交換可能

### 6. 品質確認
- `npm run typecheck:v1` を実行し通過

### 7. トラブル切り分け（運用知見）
- `difficulty/weights 404` の原因を `NEXT_PUBLIC_API_BASE` のベースパス不一致と特定
- `GRADIENT_MODEL` は表示名ではなく `/v1/models` の `id` 指定が必要
- `llama3-8b-instruct` が有効IDであることを確認

## 設計判断（面接用）
- 機能追加より、依存削減・運用整合・切り分け可能性を優先
- provider切替は実装だけでなく、設定/ドキュメントまで同時更新
- 失敗を再現可能な運用知見として固定（404の原因分解）

## 技術スタック
- Frontend: Next.js
- Backend: Node.js / TypeScript
- Generation: Gradient (DO Inference)
- Embedding: Gemini
- Deploy: DigitalOcean (Backend + Static Site)

## 進捗
- [ ] プロダクト完成
- [ ] 提出
- [ ] 3月: プロダクト化 → 実評価獲得

## 関連ログ
- /Users/makiko/Documents/Documents - makiko’s MacBook Air/dev/devdegree-journey-2026/projects/deterministic-ai-control-engine-dev-log.md
