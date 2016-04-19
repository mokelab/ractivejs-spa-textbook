---
layout: page
title: Step 4 データを紐付けてみよう(3)
---

[Step 3](../step3/)では、テンプレートに配列を渡す方法を学びました。

JavaScriptには、配列の他にもう1つ重要なデータ構造がありましたね。

```
var moke = {
  name : 'モケラ',
  organization: 'モケラボ'
};
console.log(moke.name); // 'モケラ' がコンソールに表示される
```

もちろん、このオブジェクトも`data`に渡すことができます。

```javascript
var r = new Ractive({
  el : '#container',
  template : '#myTemplate',
  data : {
    moke : {
      name : 'モケラ',
      organization : 'モケラボ'
    }
  }
});
```

テンプレートでは、通常のオブジェクトと同様に`.フィールド名`でアクセスできます。

```xml
<script id="myTemplate" type="text/ractive">
    <p>名前：{{ "{{moke.name"}}}}</p>
    <p>所属：{{ "{{moke.organization"}}}}</p>
</script>
```

## 課題

次のHTMLの`<!-- -->`の部分を埋めて、`screen_name`とフォロワー数を表示してみましょう。

```xml
<!DOCTYPE html>
<html>
<body>
  <section id="container"></section>
  
  <script id="myTemplate" type="text/ractive">
    <!-- この部分を埋めよう-->
  </script>

  <script src="https://cdnjs.cloudflare.com/ajax/libs/ractive/0.7.3/ractive.js"></script>

  <script type="text/javascript">
    var r = new Ractive({
      el : '#container',
      template : '#topTemplate',
      data : {
        user : {
          'screen_name' : 'mokelab',
          'followers_count' : 72,
          'friends_count' : 10
        }
      }
    });
  </script>
</body>
</html>
```


