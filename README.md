# dance-plan

ダンサポ（Android アプリ）が読みに来る、月間トレーニングプランの配信元です。

## 使い方

`plan.json` を書き換えて push すると、次にアプリを開いたときに反映されます。
アプリの再ビルドもインストールもいりません。新しい月が届くと通知が1本出ます。

```bash
cd ~/karin-posters/dance-plan
# plan.json を編集
git add plan.json && git commit -m "10月のメニュー" && git push
```

配信URL: `https://raw.githubusercontent.com/kiyamac-oss/dance-plan/main/plan.json`

## 書くときの決まりごと

- **`updatedAt` を必ず新しくする。** ここが前回と同じだとアプリは更新をスキップします
- **項目の `id` は変えない。** 変えると、それまでの実行記録がその項目に紐づかなくなります
- `status` は `active`（今やる月）か `preview`（予告だけ／チェック不可）
- `color` は壁に貼っている紙と意味をそろえる
  - `mint` = リズム / `pink` = 動きの質・アイソレーション / `violet` = グルーヴ / `gold` = 仕上げ
- **このリポジトリは公開です。** 本名・学校・練習場所・スケジュールは書かないこと

## 壊れた JSON を push したら

アプリは検証に通らない JSON を読み込みません。前に受け取った内容を表示したままになるので、
娘さんの画面が真っ白になることはありません。直して push し直せば復旧します。
