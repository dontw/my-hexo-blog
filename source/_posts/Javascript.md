---
title: Copying Array in Javascript
date: 2018-04-03 15:37:14
tags: javascript
---

# 遭遇狀況

用 map 修改 array 內 object 的 property 值時，發現更動值會直接動到原本 object，所以需要先複製一個陣列來讓我做修改。

# 複製方式

![array clone type](https://i.stack.imgur.com/OnwBf.png)

淺層複製:

```javascript
arr.slice()
arr.concat()
arr.splice(0)
```

深層複製(複製 object, array 內的 primitive 值):

```javascript
arr1 = JSON.parse(JSON.stringify(arr))
```

超深層複製(連 object, array 內的 function 都複製 **要用插件**):

```javascript
arr2 = $.extend(true, [], arr1) // jQuery.js needed
arr2 = _.extend(arr1) // Underscore.js needed
arr2 = _.cloneDeep(arr1) // Lo-dash.js needed
```
