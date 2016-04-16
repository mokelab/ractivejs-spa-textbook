---
layout: page
title: Step 1 指定した位置にレイアウトをいれてみよう
---

まずは、Ractive.jsに慣れるところからはじめましょう。Ractive.jsとは、データバインドに特化したUIライブラリです。これを使うと、画面の制御をかなり楽に行うことができます。

Ractive.jsは他ライブラリへの依存がなく、単独で利用可能です。CDNでホストされているので、これから作成するWebアプリのhtmlファイルに、次の1行を追加するだけで使いはじめることができます。

```
<script src="https://cdnjs.cloudflare.com/ajax/libs/ractive/0.7.3/ractive.js"></script>
```

Ractive.jsの基本的な考え方は、「指定した位置に、指定したレイアウトを貼り付ける」という考え方です。`new Ractive()`で`Ractive`オブジェクトを作ることで、実際にレイアウトを貼り付けます。

次の例は、idが`container`という場所に、`myTemplate`というidをもつレイアウトを貼り付ける例です。

```
<!DOCTYPE html>
<html>
<body>
  <section id="container"></section>
  
  <script id="myTemplate" type="text/ractive">
    <h1>Hello Ractive.js World!</h1>
  </script>

  <script src="https://cdnjs.cloudflare.com/ajax/libs/ractive/0.7.3/ractive.js"></script>

  <script type="text/javascript">
    var r = new Ractive({
      el : '#container', // どこに貼り付ける？
      template : '#myTemplate' // どのレイアウトを貼り付ける？
    });
  </script>
</body>
</html>
```

Ractive.jsのルールは次の2つです。

- レイアウト(テンプレート)は、`<script>`タグにidをつけ、その中に記述します。
- newで`Ractive`オブジェクトを作る際、`el`と`template`で場所と、どのレイアウトかを指定します。

[ここ](./demo.html)で、実際に動いているものを確認してみましょう。

## 課題

次のHTMLの`/* */`の部分を埋めて、指定したレイアウトを表示してみましょう。

```
<!DOCTYPE html>
<html>
<body>
  <section id="mainBox"></section>
  
  <script id="topTemplate" type="text/ractive">
    <h1>トップページ！</h1>
  </script>

  <script src="https://cdnjs.cloudflare.com/ajax/libs/ractive/0.7.3/ractive.js"></script>

  <script type="text/javascript">
    var r = new Ractive(
    /* ここを埋めてみよう */
    );
  </script>
</body>
</html>
```