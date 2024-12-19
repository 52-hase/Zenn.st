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
# ・末尾の改行を取り除く
```
chomp
```

# ・文字列や数値型オブジェクトを整数（Integer）型に変換
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

# ・繰り返し処理を行う
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

# ・入力文字列を（ ）の内容で配列に変換
```
split(" ")
```
:::details 例
```
"aaa bbb ccc" → ["aaa", "bbb", "ccc"]
```
:::

# ・カンマ区切りで文字列を配列に分割 / 先頭からN個を取得
```
split(',')[0, N]
```

# ・式
```
"#{A / B} #{A % B}"
```
:::details 解説
・#{} は式展開の記法
・{} 内の式が評価され、結果が文字列に埋め込まれる
・A / B は商
・A % B は余り
:::

# ・()と 2乗の計算
```
((a+b)×c)2乗　

((a + b) * c) ** 2
```

# ・変数の初期化 / 変数に足した値を代入
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


# ・gets.chomp と gets.split の違い
（どちらもNを取得し出力）

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

# ・mapの使い方
```
A, B = gets.split.map(&:to_i)

入力を取得 ⇨ 入力文字列を空白で区切り配列に変換 ⇨ 配列の各要素を整数に変換する
```

# ・半角スペース区切りで文字列にする
```
puts "#{D} #{P}"
```

# ・範囲を生成とループで出力
```
n = gets.to_i

# 1 から N まで順に出力
(1..n).each do |i|
  puts i
end
```

# ・分岐
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
・回数を入力から受け取る
Q = gets.to_i

・Q回繰り返す
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

# ・N が 3 けたになるよう数値の前に半角スペースを埋める / 0で埋める

```
N = gets.to_i
puts "%3d" % N
```
:::details 解説
```
・入力から自然数を取得
N = gets.to_i

# 3桁の幅で右詰め、値Nの残りを半角スペースで埋める
# %3d: 3桁の幅で整数を表示、足りない桁は左側にスペースを挿入
puts "%3d" % N

# 3桁の幅で右詰め、値Nの残りを0で埋める
puts "%03d" % N
```
:::

# ・文字列から指定した範囲を取得する
https://www.javadrive.jp/ruby/string_class/index5.html#section2
```
・文字列sが program の場合

s = gets.chomp
puts(s[0..2])

> pro

# program
# 0123456　の数字で範囲取得
```

# ・配列と等しい要素かの確認をする
https://docs.ruby-lang.org/ja/latest/method/Array/i/include=3f.html
```
A = gets.chomp # 問題の値を取得

menu = gets.split # メニュー名を単語ごとに分割して配列に格納

# menuにAの要素が含まれているか確認する
if menu.include?(A)
  puts "YES" # 一致する単語があれば 
else
  puts "NO"  # なければ
end
```

# ・条件を満たす要素を抽出して新しいコレクションを返す
https://docs.ruby-lang.org/ja/latest/method/Array/i/filter.html
```
A, B = gets.split.map(&:to_i)
prices = gets.split.map(&:to_i)
coupon = prices.select { |price| price >= B }

if coupon.any?
    max_price = coupon.max
    prices[prices.index(max_price)] /= 2
end

puts prices.sum
```
:::details 解説
```
# A: 商品の数, B: クーポンが適用される条件の価格
# 標準入力から2つの整数を取得し、それぞれAとBに代入
A, B = gets.split.map(&:to_i)

# 標準入力から商品価格リストを取得し、数値配列としてpricesに格納
prices = gets.split.map(&:to_i)

# クーポンが適用可能な商品の価格を抽出 (価格がB以上のもの)
# selectメソッドで条件を満たす価格のみを新しい配列(coupon)として返す
coupon = prices.select { |price| price >= B }

# クーポン適用可能な商品が存在する場合
if coupon.any?
    # クーポン適用可能商品の中で最も高い価格を取得
    max_price = coupon.max

    # その価格に対応する要素を元の配列(prices)内で見つけ、その値を半額に更新
    # prices.index(max_price) で最も高い価格のインデックスを取得
    prices[prices.index(max_price)] /= 2
end

# 商品価格の合計を計算し出力
puts prices.sum
```
:::

・文字列の置換
https://www.sejuku.net/blog/14685
```
A = gets.chomp
result = A.gsub(/-+/, '-')
puts result
```
:::details 解説
```
文字列.gsub(/正規表現/, '変換後の文字')
```
# ・-+ の詳細な構造と意味
```
[-]
ハイフン自体を意味します。
正規表現では、- は特殊文字ではないため、そのまま書くと「ハイフン」という文字そのものを意味します。

[+]
直前のパターン（この場合は -）が 1回以上 繰り返される部分を表します。
例えば:
-+ は、「ハイフンが1回以上繰り返される部分」にマッチします。
-- や --- など、ハイフンが複数連続している部分に対応します。
```
:::

# ・文字列の最初と最後を指定して取得する

```
(0...n-1).each do |i|
    # 現在の単語の末尾と次の単語の先頭が異なる場合
    if words[i][-1] != words[i+1][0]

        # しりとりが成立していないため、不一致の文字を記録
        # words[i][-1] は現在の単語の最後の文字
        # words[i+1][0] は次の単語の最初の文字
        result = "#{words[i][-1]} #{words[i+1][0]}"
        
        # ループを抜ける（最初に見つかった不一致で終了）
        break
    end 
end
```

# ・文字列を選択して置き換える
```
# 母音の文字列を定義
v = "aiueoAIUEO"  # 小文字と大文字の母音を一つの文字列で定義

# 文字列を配列に分解して、母音以外の文字を選択
name = s.chars.select { |char| !v.include?(char) }.join
# s.chars は文字列を一文字ずつの配列に変換
# select で母音を除外して、残りの子音を選ぶ
# join で選ばれた子音を一つの文字列に連結
```