# Tango Shuukan Dev Log

## 2026-04-08
- `tango-shuukan` の立ち上げを開始
- UI の初期実装を進めた
- バックエンドを `common-ai-api` に入れるために、Common 側の整備も進めた

## 2026-04-09
- `TangoShuukan` を App Store 審査まで提出
- 初の有料 iOS アプリ審査
- 前日から作り始めて翌日に提出まで進められ、立ち上げから提出までの速度が少し上がってきた感覚あり

## 2026-05-01
- ストア公開を実施
- 課金設定ミスを修正（Pricing and Availability を誤って有料にして初期課金になっていた → `¥0` に戻し、IAP / Subscription で課金する設計へ）
