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

### 2026-03-30
- `Apply Transform Over Each Element in Array` に着手
- 学び:
  - `function map(arr: number[], fn: (n: number, i: number) => number): number[]` が言っているのは、型の形だけ
  - `n` と `i` は引数名で、名前自体は仮のもの
  - `n` が値で `i` が index になるのは、型だけではなく `map` の仕様と実際の呼び出し方で決まる
  - `fn` は各要素に適用するために外から渡される関数
  - `push` は配列に値を追加するためのメソッド
  - `return` がないと、材料が渡されても結果の配列は返らない
  - まだ自力で書ける感覚は薄いが、`型 / 文脈 / 実装` を分けて考える練習になった

### 2026-03-31
- `Filter Elements from Array` を Submit
- 学び:
  - `filter` は `map` と違って、各要素を変換するのではなく「残すかどうか」を判定する
  - `if (fn(arr[i], i))` は、`fn` の結果が truthy ならその元の値 `arr[i]` を残す、という意味
  - `result.push(arr[i])` で入れているのは index ではなく元の値
  - `fn` があるだけで filter になるのではなく、`if` で条件判定として使っているから filter と分かる
  - まだ自力で書ける感覚は薄いが、`map` と `filter` の違いは少し見えてきた

### 2026-04-01
- `Array Reduce Transformation` を実施
- URL: https://leetcode.com/problems/array-reduce-transformation/submissions/1965310915/?envType=study-plan-v2&envId=30-days-of-javascript
- 学び:
  - `init` は型だけでは意味が決まらず、実際の呼び出しで渡される開始値
  - `let result = init;` は、その開始値から累積結果を始めるという意味
  - `i` は index、`nums[i]` はその index に入っている値
  - `fn(result, nums[i])` は「前回までの答え」と「今の値」を使って次の答えを作る
  - `reduce` は配列を最終的に1つの値にたたむ処理

### 2026-04-02
- `Function Composition` に着手
- 学び:
  - `function compose(functions: F[]): F` だけでは右から左は決まらず、問題の仕様としてそう実装する必要がある
  - `compose` は外側で関数を返し、実際の `for` ループは返された内側の関数の中に入る
  - `for (let i = functions.length - 1; i >= 0; i--)` は、右端の関数から順に result を更新するための書き方
  - 実装は1つではなく、`for` / `reduceRight` / 再帰など複数ありうる
  - 今の段階では「自分で一発で書けること」より「いろんな書き方を見ても意味が読めること」が大事だと整理

### 2026-04-03
- `Return Length of Arguments Passed` を実施
- URL: https://leetcode.com/problems/return-length-of-arguments-passed/submissions/1967213570/?envType=study-plan-v2&envId=30-days-of-javascript
- 学び:
  - `...args` は可変長引数で、渡された引数が配列 `args` にまとまる
  - 今回数えるのは `JSONValue` の中身ではなく、引数の個数
  - `.length` は「最初から最後まで」ではなく、配列に入っている要素数
  - 今回は `return args.length;` だけでよかった

### 2026-04-08
- Promise / sleep 問題に着手
- `resolve` は型ではなく、Promise が渡してくる引数だと整理
- `Promise<void>` は値を返さず、完了だけを表す Promise だと理解
- `new Promise(...)` は新しい Promise を作って返す、という入り口を確認

### 2026-04-09
- `cancellable` 問題を提出
- `setTimeout` で予約し、`clearTimeout` で取り消す基本を確認
- `clearTimeout` は自分で定義するものではなく、JavaScript の組み込み機能だと理解
- Promise / timer 系は、最初から知っている前提の知識が多く、つらさが出やすいと実感
