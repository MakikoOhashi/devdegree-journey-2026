# Devdegree 2026 再挑戦記録

## 📊 現状 (Updated: 2026-04-13)

### 基本情報
- **前回結果:** DevDegree は不合格、ただしリアルプロダクト本線とレイヤーの見せ方を再整理中
- **次回出願:** 2026年12月
- **現在:** 社会人（独立開発フェーズ / DevDegree 再挑戦準備）
- **Portfolio:** https://makikoohashi.github.io/

### プロジェクト進行状況
| プロジェクト | ステータス | ノート | リンク |
|------------|----------|------|------|
| WAKARUMADE iOS | 公開済み / Shorts運用継続 | LPとYouTube Shortsを毎日運用 | [詳細](projects/wakarumade-ios-dev-log.md) |
| Ruidaichan | 課金プラン追加 / 再提出 | StoreKit 対応を進めつつ審査待ち | [詳細](projects/ruidaichan-dev-log.md) |
| Inbound Tracking | 英語リスティング提出済み | Cloudflare front + Render back へ整理済み | [詳細](projects/tracktoinventory-dev-log.md) |
| Tango Shuukan | Twilio導入 / 再提出中 | SMS 学習導線の成立性を検証中 | [詳細](projects/tango-shuukan-dev-log.md) |
| Coaching Company | 商品部分を磨き込み / next repo 作成 | 収益化候補として再検討中 | [詳細](projects/coaching-company-dev-log.md) |

### 学習進捗
- **Duolingo English Test:** 写真描写の短文完結を継続
- **LSAT Logic Games:** BrainBashers で毎朝継続
- **LeetCode:** 低優先で維持しつつ、朝ルーティンに残す

### 直近の優先順位
- [ ] Tango Shuukan / Ruidaichan の審査対応を前に進める
- [ ] Shopify 構築支援の受託対応を継続する
- [ ] LP 統合と横断サイトの導線を整える
- [ ] VPS 上 Codex の使いどころを絞って、週次で使い続けられる形にする

## 🎯 Core Theme / 開発思想

**人間の判断・不安・確認コストを、AIによる「予測と根拠提示」で事前に消し、Product / Platform / Systems をつなぐ**

### 最重要テーマ
> **人間の判断・不安・確認コストをAIによる“予測と根拠提示”で事前に消し、Product / Platform / Systems をつなぐ。**

My work focuses on reducing human decision-making anxiety and verification costs through AI-driven prediction with clear, explainable reasoning.

Across tax, inventory, education, and operational workflows, I design systems where AI helps people decide faster with confidence.

I am especially interested in moving between product surfaces, shared platforms, and systems that make repeated operations scalable.

重要なのは、AIを使うこと自体が目的ではないこと。  
AIはあくまで、やりたいことを解決するために部分的に導入している手段であり、本質は「不安・調整コスト・確認コストを減らす設計」にある。

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

### AIは手段であって目的ではない
- AIを前面に出したいわけではない
- 目的は、詰まる瞬間・確認の手間・判断の不安を減らすこと
- AIは、そのために必要な部分だけ導入する
- 価値の中心は「AIを使っていること」ではなく、「ちょうどよく制御された体験・運用・導線」にある

### 外向きの二本軸
外向きには、現在の活動は次の二本軸で整理する。

これは単なる「2プロダクト」ではなく、`toC` と `toB` の両方で実課題を解いてきたという **2つの市場理解** を示す。  
DevDegree に対しては「私は toC と toB の両方で実課題を解いてきた」というメッセージになる。  
補助メモ: [Two-Market Thesis](strategy-two-axes.md)

#### 1. to C
- 教育文面
- 親子の詰まり
- 子どもの学習
- 資格 / 学習の習慣化
- `WAKARUMADE`
- `Ruidaichan`
- `たんご習慣`
- `Coaching Company`
- チャネル:
  - ネイティブアプリ
  - YouTube

ここは **痛み -> 共感 -> ちょうどいい解決** で進める軸。

#### 2. to B
- Shopify app
- 輸入商品管理
- ERP代替
- 在庫 / 進捗 / 運用負荷削減
- 商社 / 貿易 / EC
- `Forecast to Inventory`
- `eBay sync`
- `Inbound Tracking（旧 Track to Inventory）`
- `trade-shelf-agent`
- チャネル:
  - LinkedIn
  - ポートフォリオ
  - 実務文脈

ここは **業務の無駄削減 / 予測 / 管理の簡素化** で進める軸。

#### 二本軸に分ける意味
- 発信先がぶれない
- 文体が混ざらない
- 何をどこで話すか決めやすい
- 将来的にポートフォリオでも整理しやすい

ただし、この二本は内側では共通テーマでつながっている。

- 調整コストを減らす
- 不確実性を減らす
- AIをちょうどよく制御する

外向きには二本軸、内側の思想は一本、という構造で持つ。

### 発信と数字の扱い方
- マーケは主戦場にしない
- 基本方針は **置く・整える・少し見る**
- Shorts は毎日淡々と出す
- 数字は週1回だけ確認する
- 目的は「反応を追うこと」ではなく、「見つけてもらえる状態を静かに増やすこと」

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
- 単発の作品ではなく、Product Layer から Platform Layer、Systems / Org Leverage Layer へ視座を上げられる人
- ハッカソン量産ではなく、共通設計思想で複数プロダクトを接続して示す

### 実行優先順位（2026上半期）
1. Geminiを完成させて提出（現実課題への接続を示す）
2. DETは制御エンジンとして最小プロトタイプ化（生成制御の技術抽象度を示す）
3. 2つの共通アーキテクチャ思想を文章化・図示（再現性と将来性を示す）

### 重要ドキュメント（思想の固定化）
- [AI Output Governance Engine](projects/ai-output-governance-engine.md)
- [思想の原点（2026-01）](references/2026-01-origin-thesis.md)
- [Two-Market Thesis](strategy-two-axes.md)
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
- 2026-04-13: 現状セクションを最新化（Tango Shuukan / Ruidaichan / Inbound Tracking / VPS 導入）
