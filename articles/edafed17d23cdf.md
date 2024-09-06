---
title: "独自のドメインを取得し設定する"
emoji: "📚"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: []
published: false
---
### 開発環境
- macOS
- VSCode
- Rails 7.1.3.3
- ruby-3.2.3
- PostgreSQL 16.2

### 行いたいこと
- Herokuの無料プランでデプロイした場合URLは、`https://⚪︎⚪︎⚪︎.herokuapp.com`のようなドメインになっているので独自のドメインに変更したい。


<br>
<br>
<br>

# 独自のドメインを取得する
・お名前.comで簡単に取得できます。（クレジットカードの登録が必要です）
（ドメインの取得サイトは他にもあるので）
https://navi.onamae.com/login

:::details 取得の手順
`アカウントの作成` ⇨ `＋ドメイン登録` ⇨ `検索欄に作成したいドメイン名を入力（小文字）（アンダーバーは不可）` 
⇨ `.com 0円〜 を選択` ⇨ `ブログ・ホームページ` ⇨ `今回レンタルサーバーは不要なので削除` 
⇨ `支払い方法を入力` ⇨ `完了`
:::
<br>

※今回レンタルサーバーは不要なので以下を削除しました。
[![Image from Gyazo](https://i.gyazo.com/3e465b9f1f0ae2510e4f1d4f7f89eb96.png)](https://gyazo.com/3e465b9f1f0ae2510e4f1d4f7f89eb96)
::::


# Herokuに取得したドメインを設定する
・Herokuのダッシュボードの`Settings`から直接設定することもできますが、今回はターミナルからコマンドで設定しました。
・今回取得したドメインは`live-fes.com`なので、頭に`www.`をつけて`www.live-fes.com`で登録する。
```:ターミナル
$ heroku domains:add www.live-fes.com
```
・ドメインが正しく登録されているか確認するコマンドです。
```
$ heroku domains
```

# CloudflareでドメインをSSL対応させる設定
・まず`Start for free`から登録する。
https://www.cloudflare.com
:::details 設定の手順
・`ホーム` ⇨ `＋ドメインを追加する`

・ドメインを追加すると、`追加したドメインの画面` ⇨ `DNS（レコード）`から`Cloudflare ネームサーバー`が
2つ確認できる。（これを`お名前.comのネームサーバー`に登録する）

・お名前.comの`ご利用中のサービス`から登録したドメインを選択 ⇨ `ネームサーバーの変更`を選択
⇨ `その他のサービス`を選択 → `Cloudflare ネームサーバー`の2つをコピペする。
<br>
（参考画像）
[![Image from Gyazo](https://i.gyazo.com/83e01e45c47f785ca4e201888b3623dd.png)](https://gyazo.com/83e01e45c47f785ca4e201888b3623dd)
:::






# CNAMEの設定






<br>
<br>
<br>




