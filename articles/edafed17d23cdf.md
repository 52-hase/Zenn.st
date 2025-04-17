---
title: "独自のドメインを取得しHerokuに設定する"
emoji: "🌐"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: [ドメイン, domain, Cloudflare]
published: true
---
### 開発環境
- macOS
- VSCode
- Rails 7.1.3.3
- ruby-3.2.3
- PostgreSQL 16.2
- Heroku

### 行いたいこと
- `Heroku`の無料プランでデプロイした場合URLは、`https://◯◯◯.herokuapp.com`のようなドメインになっているので独自のドメインに変更したい。
- 本来Herokuで独自ドメインを設定するためには、`ドメインをSSL化`するために`月額7$`の有料プラン（Hobby）に入会する必要がありますが、今回は`Cloudflare`を使用し`ドメインのSSL化`に対応していきます。

<br>
<br>
<br>

# 独自のドメインを取得する
・`お名前.com`で簡単に取得できます。
（今回の手順では料金は発生しませんが、クレジットカードの登録が必要です）
（ドメインの取得サイトは他にもあります）
https://navi.onamae.com/login

:::details 取得の手順
`アカウントの作成`⇨`＋ドメイン登録`⇨`検索欄に作成したいドメイン名を入力（小文字)(アンダーバーは不可）` 
⇨ `.com （今回は0円〜）を選択` ⇨ `ブログ・ホームページ` ⇨ `今回レンタルサーバーは不要なので削除` 
⇨ `支払い方法を入力` ⇨ `完了`
:::
<br>

※今回レンタルサーバーは不要なので以下を削除しました。
[![Image from Gyazo](https://i.gyazo.com/3e465b9f1f0ae2510e4f1d4f7f89eb96.png)](https://gyazo.com/3e465b9f1f0ae2510e4f1d4f7f89eb96)

<br>

# Herokuに取得したドメインを設定する
・Herokuのダッシュボードの`Settings`から直接設定することもできますが、今回はターミナルからコマンドで設定しました。
・今回取得したドメインは`live-fes.com`なので、頭に`www.`をつけて`www.live-fes.com`で登録する。
```:ターミナル
$ heroku domains:add www.live-fes.com
```
・ドメインが正しく登録されているか確認するコマンドです。
```:ターミナル
$ heroku domains
```
<br>

# CloudflareでドメインをSSL対応させる設定
・まず`Start for free`から無料プランで登録する。
https://www.cloudflare.com
:::details 設定の手順
### [Cloudflare側]
・`ホーム` ⇨ `＋ドメインを追加する`

・ドメインを追加すると、`追加したドメインの画面`⇨`DNS（レコード)`から`Cloudflare ネームサーバー`が`2つ`確認できる。（これを`お名前.comのネームサーバー`に登録する）
<br>
　　　　　　　　　　　　　　　(参考画像)
[![Image from Gyazo](https://i.gyazo.com/f46ee3dcd98834e6892ee830fcb0fb56.png)](https://gyazo.com/f46ee3dcd98834e6892ee830fcb0fb56)

### [お名前.com側]
・お名前.comの`ご利用中のサービス`から登録したドメインを選択 ⇨ `ネームサーバーの変更`を選択
⇨ `その他のサービス`を選択 → `Cloudflare ネームサーバー`の2つをコピペする。
<br>
（参考画像）
[![Image from Gyazo](https://i.gyazo.com/83e01e45c47f785ca4e201888b3623dd.png)](https://gyazo.com/83e01e45c47f785ca4e201888b3623dd)
:::

<br>

# Cloudflare で 独自ドメイン経由でアクセスできる様に設定する
・`追加したドメインの画面` ⇨ `DNS（レコード）` → `DNS管理` → `編集`
・`タイプ`、`名前（必須）`、`ターゲット（必須）`を入力する。（他はデフォルト）
(タイプは`CNAME`、名前は`www`、ターゲットは`元のHerokuのドメイン`を入力します。)
[![Image from Gyazo](https://i.gyazo.com/254c1aacd9f807ad14566764df17aabc.png)](https://gyazo.com/254c1aacd9f807ad14566764df17aabc)
:::details Herokuの "DNS Target" について
・`Heroku`に独自ドメインを登録した際に、ターゲット入力用の`DNS Target`が発行されますが、それを使用したところ上手くい反映されなかったため、今回は直接元のドメインを入力しました。
:::

<br>

# SSL化の設定確認
・`SSL/TLS（概要）` ⇨ `SSL/TLS 暗号化`の現在の暗号化モードが`フル`になっていることを確認
[![Image from Gyazo](https://i.gyazo.com/cc97990c870a479bafda210124585d3c.png )](https://gyazo.com/cc97990c870a479bafda210124585d3c)

<br>

・正しく設定できていれば、URLが独自のドメインに変更されています。
[![Image from Gyazo](https://i.gyazo.com/43b0ce9b6e00f5b8d3f8aa0a19008af2.png =800x)](https://gyazo.com/43b0ce9b6e00f5b8d3f8aa0a19008af2)

<br>
:::message
実装や外部ツールで、元のHerokuのドメイン設定をして場合は、ドメインの修正や追加をする。
(`README`, `OGP`, `Google認証` など)
:::

<br>

### 以上で独自ドメインの取得から設定は完了です。


<br>
<br>
<br>




