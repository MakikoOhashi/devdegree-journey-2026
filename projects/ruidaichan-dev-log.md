# ruidaichan / ruidaichan-api: Daily Decision & Failure Log

面接・振り返り用に、日次で「何を実装したか / 何を判断したか / 何を除外したか / 完了条件」を残すログ。

運用手順: /Users/makiko/Documents/Documents - makiko’s MacBook Air/dev/devdegree-journey-2026/references/daily-progress-logging-process.md

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

### Addendum: README方針更新（2026-02-20）

1. README主軸変更
- CHANGE: READMEの主軸を `/extract` 中心から `/micro/generate_from_ocr` 中心に変更
- WHY: Phase0では「抽出精度」より「1枚の類題プリント生成体験」を最優先したため

2. 入力例・スキーマ追加
- CHANGE: `/micro/generate_from_ocr` の入力例・出力スキーマ例を追加
- WHY: 単位変換（例: `10cm = ◻︎m`）を文章題ではなく計算問題として扱うため

3. 旧エンドポイント整理
- CHANGE: `/extract*`, `/micro/generate` を legacy/aux 扱いに整理
- WHY:
  - ルールベース制約では自然な類題生成が難しいため
  - 正確性だけでなく「そのまま印刷できるプリント体験」を母親目線で優先したため
  - ChatGPTより1アクション少ない体験を目指すため

4. Timeout / partial_success 方針追加
- CHANGE: Timeout / partial_success の方針をREADMEに追加
- WHY:
  - 10問指定で3問だけ返る体験を避けるため
  - 軽い再試行で安定性を上げつつ、待ち時間増加を抑えるため

5. ロードマップ基準リンク追加
- CHANGE: ロードマップ基準リンクを追加
- WHY:
  - Phase0完了条件を明確化するため
  - 機能拡張よりUI磨き・審査提出に進む判断軸を固定するため

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

## 2026-02-22

- `/micro/generate_from_ocr`の入力例・出力スキーマ例を追加（問題タイプは増えても、入出力の枠は固定のための試行錯誤）

## 2026-02-23

- difficulty（`easy` / `same` / `hard`）機能整備
