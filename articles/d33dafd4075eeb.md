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
・
```

```

<br>
<br>
<br>