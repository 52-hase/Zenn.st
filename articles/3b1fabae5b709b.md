---
title: "DOMについて"
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


# DOMとは？
- Document Object Model の略称です。
- DOM は JavaScript 言語の一部ではなく、ウェブサイトを構築するために使用される Web API の 1 つです。


# DOMツリー
```
<!DOCTYPE html>
<html>①
  <head>②
    <title>サンプルページ</title>③
  </head>
  <body>④
    <h1>Hello, World!</h1>⑤
    <p>これはサンプルページです。</p>⑥
  </body>
</html>
```

```
Document
 ├── html①
 │   ├── head②
 │   │   └── title③
 │   └── body④
 │       ├── h1⑤
 │       └── p⑥

```
