# ruidaichan / ruidaichan-api: Daily Decision & Failure Log

面接・振り返り用に、日次で「何を実装したか / 何を判断したか / 何を除外したか / 完了条件」を残すログ。

---

## 2026-02-20

### Summary
式問題（例: `4 mm = □ cm`）への対応と、成功件数が少ない場合のリトライ実装を実施。  
対象範囲を小学1-3年の図を使わない算数に絞る方針を決定。

### Repositories
- https://github.com/MakikoOhashi/ruidaichan
- https://github.com/MakikoOhashi/ruidaichan-api

### What I Did
- `4 mm = □ cm` のような単位変換の式問題に対応
- 成功件数が少ないケースでのリトライ処理を実装

### Decision
- まずは以下ソースの1-3年問題で成立確認を優先
  - https://www.print365.net/2gakkimadekeisan1nen/
  - https://sukiruma.net/sandrill/
- 判定軸: 「図を使わない算数問題」に集中して品質を上げる

### Scope In
- 小学1-3年の図を使わない算数問題
- 写真1枚またはOCRテキストからの類題生成
- 類題5問をA4で即印刷可能な出力

### Scope Out（現時点で除外）
- 図を使って考える問題
- グラフ・表の読み取り
- 作図（円・球）
- ものさしの読み方（実物操作）
- 計算ピラミッド（図配置）
- 百ます計算（UI別物）
- 筆算

### Acceptance Criteria
- 図を使わない算数問題の**8割以上**で成立すること
- 入力（写真1枚 or OCRテキスト）から類題5問を生成できること
- A4で即印刷可能な形で出力できること

### Next Gate
- 上記チェックが通過したらREADME整備
- README整備後にUI作成フェーズへ移行
