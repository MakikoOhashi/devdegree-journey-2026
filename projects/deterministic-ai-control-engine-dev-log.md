# deterministic-ai-control-engine: Daily Decision & Failure Log

面接・振り返り用に、日次で「何をしたか / なぜそうしたか / 何が失敗したか / どう切り分けたか」を残すログ。

---

## 2026-02-19

### Summary
Guided Reading v1のフロー整理、Static Siteデプロイ整合、README運用情報強化、Generation providerをGradient専用化、運用トラブル切り分けまで実施。

### Changes
1. Guided Reading v1 フロー整理
- フロントから `POST /ocr/structure` 前処理呼び出しを削除
- 入力は軽量クライアント正規化（trim / 改行 / 空白）へ変更
- Guided Readingに不要な空欄補充系 state / ロジックを `frontend/app/page.tsx` から削除

2. Static Site デプロイ対応
- `frontend/next.config.js` に `output: "export"` を追加
- `frontend` ビルドで `out/` 生成を確認
- DO Static Site設定（source=`frontend`, output=`out`）と整合

3. README更新（実装整合 + 運用）
- パイプラインを現状に合わせて更新（`/ocr/structure` 非依存）
- DO Backend / Frontendの設定手順を追記
- `NEXT_PUBLIC_API_BASE` の注意点（パスprefix必要ケース、再デプロイ必須）を追記
- Live Demo / Status / v1スコープ説明を強化

4. Generation providerをGradientへ切替
- `backend/src/providers/gradient.generate.provider.ts` を追加（chat/completions）
- `backend/src/index.ts` のgeneration providerをGradient専用化
- Gemini generationフォールバックを削除
- デフォルト値をDO Inference向けに設定
  - `GRADIENT_BASE_URL=https://inference.do-ai.run/v1`
  - `GRADIENT_MODEL=llama3.3-70b-instruct`（envで上書き可）

5. EmbeddingはGemini維持（ハイブリッド）
- 生成はGradient、評価用embeddingはGeminiの構成を維持
- READMEに設計理由を明記（embedding providerは抽象化済みで交換可能）

6. 型安全チェック
- `npm run typecheck:v1` 実行、通過確認

### Decisions
- Guided Reading v1は「前処理依存を減らす」方向で簡素化
- Generationは運用の明確化を優先してGradient専用化
- Embeddingは評価安定性を優先してGemini継続（交換可能設計は維持）

### Failures / Issues
- `difficulty/weights` が404
- Manhattan-styleの「設定は正しいはず」状態で実際はベースパス不一致

### Debug Notes
- `NEXT_PUBLIC_API_BASE` のベースパス不一致が404原因
- `GRADIENT_MODEL` は表示名ではなく `/v1/models` の `id` を指定する必要あり
- `llama3-8b-instruct` が有効IDであることを確認

### Interview-ready Takeaway
- 「機能追加」ではなく「依存削減・運用整合・切り分け可能性」を優先
- Provider切替は実装だけでなく、運用パラメータとドキュメントを同時更新
- 失敗（404）を環境変数・パス・モデルIDの3点で切り分け、再現可能な知見として固定
