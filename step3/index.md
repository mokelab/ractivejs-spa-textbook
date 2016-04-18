---
layout: page
title: Step 3 データを紐付けてみよう(2)
---

[Step 2](../step2/)では、テンプレートに渡すデータを`data`フィールドにkey-value形式で指定する方法を学びました。このStepではもう少し高度なデータの紐付けを学びましょう。

復習です。テンプレートの`{{ "{{name"}}}}`にデータを渡すには、次のように`Ractive`オブジェクトを作りました。

```javascript
var r = new Ractive({
  el : '#container',
  template : '#myTemplate',
  data : {
    name : 'モケラ'
  }
});
```

もし、表示する名前が複数あった場合はどのようにすればよいでしょうか？答えを見る前にすこし考えてみてください。


たとえば次のように番号をつけるという方法がありますね。

```xml
<script id="myTemplate" type="text/ractive">
  <p>こんにちは！{{ "{{name1"}}}}さん！</p>
  <p>こんにちは！{{ "{{name2"}}}}さん！</p>
</script>

<script type="text/javascript">
  var r = new Ractive({
    el : '#container',
    template : '#myTemplate',
    data : {
      name1 : '赤モケラ',
      name2 : '青モケラ',
    }
  });
</script>
```

しかしこの方法だと、名前が増えるたびに`data`フィールドに追加する必要がありますし、個数がそもそも事前にわからない場合は扱いづらそうです。

そういえばJavaScriptには「配列」というデータ構造がありました。次のように、先頭から何番目のデータを取り出せといった命令ができるデータ構造でしたね。

```javascript
var names = ['赤モケラ', '青モケラ'];
console.log(names[0]); // '赤モケラ' がコンソールに表示される
```

順番は0から始まる点に注意しましょう。この配列は`data`に次のように渡すことができます。

```javascript
var r = new Ractive({
  el : '#container',
  template : '#myTemplate',
  data : {
    names : ['赤モケラ', '青モケラ']
  }
});
```

テンプレートでは、通常の配列のように`[]`で先頭からの位置を指定します。

```xml
<script id="myTemplate" type="text/ractive">
  <p>こんにちは！{{ "{{name[0]"}}}}さん！</p>
  <p>こんにちは！{{ "{{name[1]"}}}}さん！</p>
</script>
```

## 課題

次のHTMLの`<!-- -->`の部分を埋めて、「こんにちは！白モケラさん！」と表示されるようにしましょう。

```xml
<!DOCTYPE html>
<html>
<body>
  <section id="container"></section>
  
  <script id="myTemplate" type="text/ractive">
    <p>こんにちは！<!-- この部分を埋めよう-->さん！</p>
  </script>

  <script src="https://cdnjs.cloudflare.com/ajax/libs/ractive/0.7.3/ractive.js"></script>

  <script type="text/javascript">
    var r = new Ractive({
      el : '#container',
      template : '#topTemplate',
      data : {
        names : ['赤モケラ', '青モケラ', '白モケラ']
      }
    });
  </script>
</body>
</html>
```


