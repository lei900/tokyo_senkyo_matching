### サービス名：東京選挙マッチング

### 行政課題
若者の政治関心度&投票率が低い現状がある。
理由の一つに政党による違いがわからない若者が多くいると考えている。

### 解決策
質問に答えてもらうことで自分の考えに近い政党を判定でき、その人に合ったYouTube動画、SNS媒体をおすすめすることで政治への関心を向上させたい。

ターゲット層（どのようなユーザーに向けて作る予定か)
選挙に行く意思はあるけど、どの党を選べばいいのか決め手がなくて困っている人々。

### 作成するサービスDemo

- [東京選挙マッチング Demo](https://tokyo-senkyo-matching.herokuapp.com/)

### サービスの流れ

-  政治に関する質問が複数あって、ユーザーは選択肢（超賛成、賛成、無関心、反対）から議題に対しての賛成か反対かを選ぶ。
-  質問に政党が紐づいていて、質問に対する賛成か反対かによってその議題に紐づいた政党に相性ポイントが入る仕組みになっている。
-  最終的に相性ポイント順に政党をランキングづけする。
-  ランキングが一番高かった政党がユーザーにマッチした政党と判定する。

### アプリの機能概要

- ユーザー登録機能
  - ユーザー認証
  - ユーザー情報登録項目

- 政策アンケート（質問）表示機能
  - 政党政策をアンケート項目として表示する

- 政策アンケート(質問)回答機能
  - ユーザーはアンケートに回答できる
  - 回答選択肢：超賛成、賛成、反対、無関心

- 政党マッチング結果表示機能
  - 政党との相性度結果ランキングを表示する

- 情報源おすすめ機能
    - 投票について、ユーザの関心傾向を確認するアンケートを表示
    - ユーザーはアンケートに回答できる
    - 回答結果に基づいて、最適な情報源を表示する

### 相性ポイントの計算方法

質問開始と同時にユーザーと全部の政党を紐づける。

質問に答える時にユーザーと質問を紐づける。
質問の回答は中間テーブルに保存する。

また、質問は政党にも紐づいている。
政党は紐づいた質問に対して賛成か反対かの立場を持っている。

ユーザーが回答した時に、「回答」と「政党の立場」を参照して以下の判定方法で政党との相性度を集計する。

- ユーザー選択が超賛成の議題に対して、政党意見が
  - 賛成の場合、該当政党との相性度+2点
  - 反対の場合、相性度-1点
- ユーザー選択が賛成の議題に対して、政党意見が
  - 賛成の場合、政党との相性度+1点
  - 反対の場合、相性度-1点
- ユーザー選択が反対の議題に対して、政党意見が
  - 賛成の場合、該当政党との相性度-1点
  - 反対の場合、相性度+1点
- ユーザー選択が無関心の議題に対して、政党との相性度が加減しない


判定したポイントをユーザーと政党の中間テーブルに保存する。

### 画面遷移図
https://www.figma.com/file/6nxgo4iLligzPZgFsq2Xyh/%E6%94%BF%E5%85%9A%E6%8A%95%E7%A5%A8%E3%83%9E%E3%83%83%E3%83%81%E3%83%B3%E3%82%B0?node-id=0%3A1

### ER図の作成
![スクリーンショット 2022-08-15 18 46 06](https://user-images.githubusercontent.com/64511596/184649336-b90e6632-dd08-4d30-9e3f-5ac01e227f3e.png)

### チームメンバ
武田喜一
王蕾
岩木俊幸
武田凌也

### ミーティングの議事録
https://resilient-raver-ce1.notion.site/3dbe6445578c4e40a159a2deb730cdb2?v=1bb4473ec16241f38a8e0f2261a9d910
### 振り返り
https://resilient-raver-ce1.notion.site/c52d33c2e85840388221ca5757f6ff3e
