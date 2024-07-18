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


```
document.addEventListener('DOMContentLoaded', function() {
  const input = document.getElementById('chat-input');
  const imageInput = document.getElementById('chat-image');
  const button = document.getElementById('button');
  const chatImageLabel = document.getElementById('chat-image-label');

  // 画像が選択されたときにラベルを更新する
  imageInput.addEventListener('change', function() {
    if (imageInput.files.length > 0) {
      chatImageLabel.textContent = '画像が添付されています';
    } 
  });

  button.addEventListener('click', function() {
    const content = input.value;
    const file = imageInput.files[0];

    if (file) {
      const reader = new FileReader();
      reader.onload = function(event) {
        const base64String = event.target.result.split(',')[1];
        App.room.speak(content, base64String);
      };
      reader.readAsDataURL(file);
    } else {
      App.room.speak(content);
    }

    input.value = '';
    imageInput.value = '';
    chatImageLabel.textContent = '画像';  // 入力をクリアした後、ラベルを画像に戻す
  });
});

```

- DOMContentLoaded イベント
・ページのコンテンツがすべて読み込まれた後に実行する処理を設定します。
```
document.addEventListener('DOMContentLoaded', function() { ... });
```

- 要素の取得
・getElementById メソッドを使って、HTML要素を取得します。
```
const input = document.getElementById('chat-input');
  const imageInput = document.getElementById('chat-image');
  const button = document.getElementById('button');
  const chatImageLabel = document.getElementById('chat-image-label');
```

- イベントリスナーの追加
・addEventListener メソッドを使って、要素にイベントリスナーを追加します。
```
imageInput.addEventListener('change', function() { ... });
```

- ファイル選択時の処理
・ファイルが選択されたときに、ラベルのテキストを更新します。
```
chatImageLabel.textContent = '画像が添付されています';
```

- ボタンがクリックされたときの処理
テキストと画像を処理し、送信する処理を定義します。
ファイルが選択されている場合、FileReader を使ってファイルを読み込み、Base64形式に変換します。
ファイルがない場合は、テキストのみを送信します。

- 入力フィールドのリセット
送信後、入力フィールドとファイル入力をクリアし、ラベルを元に戻します。
```
input.value = '';
```