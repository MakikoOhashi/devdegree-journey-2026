# Devdegree 2026 再挑戦記録

## 🎯 Core Theme / 開発思想

**人間の判断・不安・確認コストを、AIによる「予測と根拠提示」で事前に消す**

### 最重要テーマ
> **人間の判断・不安・確認コストをAIによる“予測と根拠提示”で事前に消す。**

My work focuses on reducing human decision-making anxiety and verification costs by using AI-driven prediction with clear, explainable reasoning.

Across tax, inventory, education, and operational workflows, I design systems where AI does not replace humans, but helps them decide faster and with confidence.

### 統合テーマ
> **私はAIの不確実性を制御する基盤を設計しています。**
> **人間とAIが一緒に責任を取るためのインフラを設計しています。**

- AIをForecastに使う
- 不安を減らす
- 無駄な業務を消す
- 生成を制御する

この4点は別テーマではなく、共通して**不確実性の制御**を目指す。

- 税務: 監査リスクの不確実性
- DET: 出題偏りの不確実性
- 生成AI: 出力品質の不確実性

### なぜこの軸か
- **背景:** 10年以上の実務で「人間の不安が業務を止める瞬間」を何度も見た
- **AI時代の本質:** 正解を出すより、安心して決断できる材料を揃える
- **一貫性:** すべてのプロジェクトがこの思想を異なるドメインで検証している

### DevDegreeでの勝ち筋
審査で重視されると考えている軸:

- 技術理解
- 問題定義の深さ
- 将来性（拡張可能性）
- 一貫した思想

狙う見せ方:
- 「AIを使ったアプリ開発者」ではなく「AI制御レイヤーを設計できる人」
- ハッカソン量産ではなく、共通設計思想で複数プロダクトを接続して示す

### 実行優先順位（2026上半期）
1. Geminiを完成させて提出（現実課題への接続を示す）
2. DETは制御エンジンとして最小プロトタイプ化（生成制御の技術抽象度を示す）
3. 2つの共通アーキテクチャ思想を文章化・図示（再現性と将来性を示す）

### 重要ドキュメント（思想の固定化）
- [AI Output Governance Engine](projects/ai-output-governance-engine.md)
- [思想の原点（2026-01）](references/2026-01-origin-thesis.md)
- [日次進捗ログ手順](references/daily-progress-logging-process.md)
- 目的: 「何を作るか」ではなく「どんな状態を作るか」を短く固定して、判断基準のぶれを防ぐ

### AI中心時代の設計前提
旧世界（人間中心）:
Human -> UI -> App -> DB/API

新世界（AI中心）:
Human -> AI Agent -> API/Backend/System of Record -> Execution & Evidence

この変化では、UIは主戦場ではなく交換可能レイヤーになる。  
評価対象は、AIが直接利用できるAPI設計・データ意味・処理正当性・証跡設計。

### フロントを作らないサービス戦略
今後の中核価値は以下の4系統:

1. 判断を返す（Forecast / Risk estimation / Scoring）
2. 記録を保証する（監査証跡 / 履歴固定 / 差分管理）
3. 実行を担う（決済 / 発注 / 申請 / 更新）
4. 意味変換する（生データ -> 判定可能な構造）

狙いは「人間向け画面の最適化」ではなく、  
**AIが連続的に叩いても破綻しない、説明責任を返せるバックエンド**を作ること。

### Forecast × 説明責任
このリポジトリの実質テーマは、予測精度の競争だけではない。  
テーマは **「予測に基づく意思決定の正当性を残すこと」**。

- Forecast to Inventory: 予測外れが在庫コストに直結するため、根拠が必要
- Forecast Expense（Gemini）: 税務・監査観点で「なぜその判断か」の説明が必要

目指すのは、単一回答の提示ではなく:
- 根拠の分解
- 過去比較
- 不確実性の明示
- 代替シナリオ提示

天気予報と同じく、価値は「当て続けること」だけではない。  
確率・根拠・不確実性を明示し、外れた場合も判断過程を説明できることが重要。  
つまり、**「その時点で合理的な判断だった」と示せる責任構造**を設計する。

これは分析ツールではなく、  
**人間とAIが共同で責任を取るための意思決定インフラ**として設計する。

## 📊 現状 (Updated: 2026-03-11)

### 基本情報
- **前回結果:** CoderPad論理テスト不合格
- **次回出願:** 2026年12月
- **現在:** 社会人（独立開発フェーズ）
- **Portfolio:** https://makikoohashi.github.io/

### プロジェクト進行状況
| プロジェクト | ステータス | ノート | リンク |
|------------|----------|------|------|
| WAKARUMADE iOS | 公開済み / 1.0.2提出済み | LPとYouTube Shorts運用開始 | [詳細](projects/wakarumade-ios-dev-log.md) |
| Ruidaichan | App Review継続中 | `Ready for Review`で返答待ち | [詳細](projects/ruidaichan-dev-log.md) |
| eBay Catalog Bridge | 立ち上げ完了 / 連携作業中 | 外部アカウント準備のブロッカーあり | https://github.com/MakikoOhashi/ebay-catalog-bridge |
| GSoC 2026 | 取り組み先決定 | `json-schema-org/community#980` Qualification Taskを進行予定 | [詳細](projects/gsoc-dev-log.md) |

### 学習進捗
- **Duolingo English Test:** Writing強化中（写真描写の短文完結を重点）
- **LSAT Logic Games:** 22/50（品質の低い問題は不成立として切り分け）
- **LeetCode:** 低優先で維持

### 直近の優先順位
- [ ] GSoC #980 Qualification Task（POC + 既存コード評価）
- [ ] eBay Catalog Bridge の外部ブロッカー解除
- [ ] WAKARUMADE Shortsの日次運用継続
- [ ] DET Writing（4-5短文を毎回完結）

---

## 📁 ディレクトリ構成
```
├── projects/        # プロジェクト詳細
├── learning/        # 学習記録
├── weekly/          # 週次ログ
├── references/      # 思想メモ・原点ログ
├── timeline.md      # 月次計画
└── references.md    # 参考情報・ベンチマーク
```

## 🔄 更新履歴
- 2026-02-11: リポジトリ作成
- 2026-02-12: Core Themeを「不確実性の制御」軸で推敲、DevDegree向け勝ち筋と優先順位を追記
- 2026-02-12: AI中心時代の設計前提、フロントレス戦略、Forecast × 説明責任を追記
- 2026-02-12: AI Output Governance Engineの抽出版ドキュメントを追加
- 2026-02-12: 思想の原点メモ（2026-01）を references/ に追加
- 2026-03-11: 現状セクションを最新化（iOS公開/審査状況/GSoC方針/学習進捗）
