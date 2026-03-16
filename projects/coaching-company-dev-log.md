# Coaching Company Dev Log

## 2026-03-16

### Repository
- https://github.com/MakikoOhashi/coaching-company

### Summary
- 「導入問題 -> 問題回答 -> コーチ介入 -> 次の問題へ進む」1セッションの骨格をかなり具体化
- LINE と Coaching Company の役割分担を整理し、Company 側は自社問題バンクで進める方針を固めた

### What I Did
1. 問題バンク方針の整理
- LINE は固定問題 + 習慣化
- Coaching Company は過去問レベルの自社問題バンクを使う

2. データ基盤の追加
- Supabase に `coaching` スキーマを作成
- `company_questions` と `question_exposures` の土台を作成

3. API 実装
- `common-ai-api` 側に Company 専用の問題取得 / 回答送信 endpoint を追加
- `coaching.company_questions` から問題を取得
- `question_exposures` に出題履歴を保存

4. フロント接続
- `coaching-company` 側の Question panel を Company 問題バンクへ接続
- 問題表示 -> 回答 -> 採点 -> 解説表示まで通した

5. Coach intervention の追加
- 誤答時: 最大3ターンまで短く整理を補助しつつ、常に次へ進めるように調整
- 正解時: 1回だけ意味確認をして、その後は自然に次へ進むように調整

6. UI 調整
- Question panel を「導入問題」として位置づけ
- 導入コメントと実際の設問文を分けて表示
- 誤答整理用の入力欄は必要時のみ表示
- 通常はコーチの締めのあと5秒で自動的に次の問題へ進む
- 「ここをもう少し確認する」リンクで自動遷移を止め、通常チャットへ戻れる導線を追加

### Takeaway
- Coaching Company は単なるチャットや問題アプリではなく、「導入問題でつまずきを確認し、コーチが短く介入しながら本題へ進める」プロダクトとして骨格が見えてきた
