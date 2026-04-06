# TracktoInventory Dev Log

## 2026-04-03
- `TracktoInventory` の update 方針を整理。
- `2026-02` に別ストアでダウンロード履歴が一度あったが、すぐに消えていた。
- 仮説:
  - `Render` のコールドスタートで初回体験が悪く、離脱された可能性が高い。
- 対応方針:
  - UI を `Cloudflare` 側へ移動する。
  - バックエンドは `Render` のまま維持する。
  - 先に UI に到達してもらい、その間に `Render` を起こす構成へ作り替える。
- 追加で進めること:
  - `Remix` から `React Router` への移行も同時に進める。

## 2026-04-05
- `TTI` アプリを `Cloudflare front + Render back` 構成へリファクタし、`main` に無事マージ。
- ひとまずこのリファクタは一区切り。
- 長く詰まった Shopify ナビ問題の原因メモ:
  - `workers.dev` を preview 扱いしていて、公式ナビではなくフォールバック表示に入っていた
  - ナビリンクで `host` が落ちて、embedded app の文脈が維持できていなかった
  - `s-app-nav` 表示前に App Bridge 周りの初期化が噛み合っていなかった
- いちばん効いた対処:
  - `/Users/makiko/Documents/Documents - makiko’s MacBook Air/dev/track-to-inventory/apps/web/app/root.jsx` の `<head>` に `app-bridge.js` を静的に置いたこと
  - これで App Bridge の読み込みが安定し、ナビが出る状態になった
- まとめ:
  - `preview` 判定のズレ
  - `host` の取り回し不足
  - App Bridge の読み込みタイミング
  の複合問題だった

## 2026-04-06
- `TracktoInventory` の名前を `Inbound Tracking` に改名。
- 提出用スライドをすべて修正。
- 英語リスティングを提出。
