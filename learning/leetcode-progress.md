# LeetCode 学習記録

## 目標
- 最低限Loopくらいは書けるレベル
- 3ヶ月で100問達成
- Rating 1400+

## 進捗
- 解いた問題数: 3
- 目標: 基本的なループ実装
- 現在Rating: -（未計測）

## CoderPad選択式論理テスト向け位置づけ
- LeetCode（Easy/Medium）でアルゴリズム思考を英語で訓練
- コード実装力と論理整理を同時強化
- 外部評価: LeetCode Rating / 問題解決数

## 無料・有料メモ
- LeetCode: 基本機能は無料、Rating取得も無料
- LeetCode Premium（目安: 月$35）は頻出問題アクセス向けで必須ではない
- Codeforces: 参加・Rating取得とも完全無料（英語長文読解の補助として併用）

## 運用方針
- 主軸はLeetCode（毎日継続）
- Codeforcesは補助枠として物語調・長文問題の読解耐性を強化
- Devdegree対策では、無料範囲でRatingと解答数を積み上げる

## 学習ログ
### 2026-02-11
- [記載予定]

### 2026-03-24
- `30 Days of JavaScript` を開始
- `Create Hello World Function` を Accepted
- 学び:
  - `args` は関数に渡される引数
  - `return function(...args): string { ... }` は「引数をいくつでも受け取り、文字列を返す関数を返す」という意味
  - 今回は中身は `return "Hello World";` だけでよかった

### 2026-03-25
- `Counter` を Accepted
- URL: https://leetcode.com/problems/counter/submissions/1958239744/?envType=study-plan-v2&envId=30-days-of-javascript
- 学び:
  - 毎回1ずつ変わる処理は、まず `increment` を考える
  - `return n++;` は「今の値を返してから増やす」
  - `return n = n + 1;` は文法上はありだが、返る値が1つ先に進むので今回の期待とは違う

### 2026-03-26
- `To Be Or Not To Be` に着手
- 学び:
  - `type ToBeOrNotToBe = { ... }` は、`toBe` と `notToBe` を持つオブジェクトの形を定義している
  - `expect` は定型語ではなく、ここで定義される関数名
  - `other` は比較相手として後から渡される引数名で、名前自体は何でもよい
  - `const` は新しく変数を作る時に必要で、関数の引数には不要
  - 今回は `return false` ではなく、失敗時に `throw new Error(...)` が必要
  - `toBe` と `notToBe` は両方をまとめたオブジェクトとして返す

### 2026-03-27
- `Counter II` を Accepted
- URL: https://leetcode.com/problems/counter-ii/submissions/1960374080/?envType=study-plan-v2&envId=30-days-of-javascript
- 学び:
  - `Counter` 型は `number` を返す関数を持つオブジェクトの形
  - `createCounter` は数値ではなく `increment / decrement / reset` を持つオブジェクトを返す
  - `=>` の1行式は暗黙の return になる
  - `reset` のように `{}` で書く場合は明示的な `return` が必要
