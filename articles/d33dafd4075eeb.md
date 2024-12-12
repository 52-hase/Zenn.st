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

・半角スペース区切りで文字列にする
```
puts "#{D} #{P}"
```

・範囲を生成とループで出力
```
n = gets.to_i

# 1 から N まで順に出力
(1..n).each do |i|
  puts i
end
```

・分岐

```
(1..100).each do |i|
    if i % 3 == 0 && i % 5 == 0
        puts "FizzBuzz"
    elsif i % 3 == 0
        puts "Fizz"
    elsif i % 5 == 0
        puts "Buzz"
    else
        puts i
    end
end
```
:::details 解説
```
・(1..100) で1から100までの範囲を作成
・each メソッドで各数字を順に処理

条件分岐で以下を判定
・3と5の両方で割り切れる場合は "FizzBuzz"
・3のみで割り切れる場合は "Fizz"
・5のみで割り切れる場合は "Buzz"
・どちらでも割り切れない場合はその数字

・puts で各結果を改行付きで出力
```
:::

・

```
Q = gets.to_i
Q.times do
    N, M = gets.split.map(&:to_f)
    
    rounded = (N * (10 ** M)).round / (10 ** M)
    printf("%.*f\n", M, rounded)
end
```
:::details 解説
```
# 質問の回数を入力から受け取る
Q = gets.to_i

# Q回繰り返す
Q.times do
   # 入力から数値Nと丸める桁数Mを取得
   # split: 入力文字列を空白で分割
   # map(&:to_f): 文字列を浮動小数点数に変換
   N, M = gets.split.map(&:to_f)
   
   # 丸め処理の仕組み:
   # 1. 10^M を掛けて桁を移動
   # 2. round() で四捨五入
   # 3. 10^M で割って元の桁に戻す
   rounded = (N * (10 ** M)).round / (10 ** M)
   
   # 指定の小数位まで出力
   # %.*f: 動的に小数点以下の桁数を指定
   # \n: 改行
   printf("%.*f\n", M, rounded)
end
```
:::


<br>
<br>
<br>