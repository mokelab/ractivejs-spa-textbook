---
layout: page
title: Step 2 データを紐付けてみよう
---

[Step 1](../step1/)では、指定した位置に指定したレイアウトを貼り付けるところまでを学びました。Step 2以降では、貼り付けるものを「テンプレート」と呼ぶことにします。なぜテンプレートと呼ぶかはこのStepを学ぶとわかります。

`Ractive`オブジェクトをnewで作る際、データを渡すことができます。データは、`new Ractive()`で渡すオブジェクトの`data`フィールドにkey-value形式で指定します。

```javascript
var r = new Ractive({
  el : '#container',
  template : '#myTemplate',
  data : {
    name : 'モケラ'
  }
});
```

ここでは、`name = 'モケラ'`というデータを指定しました。ここで指定したデータを表示するには、テンプレートで`{{データ名}}`をいれます。`<p>`の中身に先ほど指定した`name`というデータを指定するには、次のように記述します。

```xml
<script id="myTemplate" type="text/ractive">
  <p>{{ "{{name"}}}}</p>
</script>
```

もちろん、`data`に渡すのはオブジェクトなので、複数指定することもできます。課題で確認してみましょう。

## 課題

次のHTMLの`/* */`と`<!-- -->`の部分を埋めて、`data`で指定した名前と所属を表示してみましょう。

```xml
<!DOCTYPE html>
<html>
<body>
  <section id="container"></section>
  
  <script id="topTemplate" type="text/ractive">
    <p>名前：{{ "{{name"}}}}</p>
    <p>所属：<!-- 所属を表示させよう--></p>
  </script>

  <script src="https://cdnjs.cloudflare.com/ajax/libs/ractive/0.7.3/ractive.js"></script>

  <script type="text/javascript">
    var r = new Ractive({
      el : '#container',
      template : '#topTemplate',
      data : {
       /* 名前：モケラ となるようにここを埋めよう */
        organization : 'モケラボ'
      }
    });
  </script>
</body>
</html>
```


