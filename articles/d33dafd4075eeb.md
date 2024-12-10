---
title: "paizaまとめ"
emoji: "📚"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: [paiza]
published: false
---
### 開発環境
- macOS
- VSCode
- Rails 7.1.3.3
- ruby-3.2.3
- PostgreSQL 16.2
- Heroku

<br>
<br>
<br>

# まとめ
・末尾の改行を取り除く
```
chomp
```

・文字列や数値型オブジェクトを整数（Integer）型に変換
```
to_i
```
:::details 例
```
"123".to_i    # => 123
"45abc".to_i  # => 45 （先頭の数字部分だけを取得）
"abc".to_i    # => 0 （数字がない場合は 0）
nil.to_i      # => 0 （nil は 0 になります）
```
:::

・繰り返し処理を行う
```
n.times do
  # 繰り返したい処理
end
```
:::details 例
5.times do
  puts "こんにちは！"
end
# 出力:
# こんにちは！
# こんにちは！
# こんにちは！
# こんにちは！
# こんにちは！
:::

・入力文字列を（ ）の内容で配列に変換
```
split(" ")
```
:::details 例
```
"aaa bbb ccc" → ["aaa", "bbb", "ccc"]
```
:::

・カンマ区切りで文字列を配列に分割 / 先頭からN個を取得
```
split(',')[0, N]
```



・式
```
"#{A / B} #{A % B}"
```
:::details 解説
・#{} は式展開の記法
・{} 内の式が評価され、結果が文字列に埋め込まれる
・A / B は商
・A % B は余り
:::

・()と 2乗の計算
```
((a+b)×c)2乗　

((a + b) * c) ** 2
```

・変数の初期化 / 変数に足した値を代入

```
# 変数 N を 0 で初期化
N = 0

# N に 3,286 を足した値を N へ代入
N += 3286

# N に 4,736 をかけた値を N へ代入
N *= 4736

# N を 12,312 で割った余りを N へ代入
N %= 12312

```


・gets.chomp と gets.split の違い
（そちらもNを取得し出力）

```
N = gets.chomp

Hello World Ruby

入力された内容がそのまま1つの文字列として扱われ出力もそのまま表示される。
```
```
N = gets.split

Hello
World
Ruby

入力文字列をスペースやタブ文字で区切り配列として扱う。
```

・mapの使い方
```
A, B = gets.split.map(&:to_i)

入力を取得 ⇨ 入力文字列を空白で区切り配列に変換 ⇨ 配列の各要素を整数に変換する
```
<br>
<br>
<br>