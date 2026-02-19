# deterministic-ai-control-engine: Daily Decision & Failure Log

面接・振り返り用に、日次で「何をしたか / なぜそうしたか / 何が失敗したか / どう切り分けたか」を残すログ。

---

## 2026-02-19

### Summary
FrontendをStatic Site化してDOで動作させ、Generation APIをDOのGradientに切替。EmbeddingはGradient非対応のためGeminiを維持。

### Decisions
- FrontendはStatic Siteとして運用する
- GenerationはDO Gradientを採用する
- EmbeddingはGeminiを継続する（Gradientでは不可）

### What I Did
- FrontendをStatic Site化してデプロイ（DOで動作確認）
- GenerationのAI APIをDO Gradientへ変更
- EmbeddingはGeminiを残す構成へ調整

### Learning
- Static Site運用はこのプロダクト要件と相性が良い
- EmbeddingはGradientで代替できないため、現時点ではGemini併用が現実解

### Interview-ready Takeaway
- 「全置換」ではなく、使える層だけ置換して動く構成を作る判断ができた
- 技術選定を机上で終わらせず、デプロイ可能性で最終判断した
