---
title: canvas-download
date: 2018-04-09 14:21:25
tags:
---

# 遭遇狀況

需要將 canvas 轉成圖片並讓使用者點擊某個地方後可以把圖片下載至本地端

# canvas 轉圖片

使用 [`HTMLCanvasElement.toDataURL()`](https://developer.mozilla.org/zh-TW/docs/Web/API/HTMLCanvasElement/toDataURL) 將 canvas 元素轉為 base64 的 dataUrl

```javascript
let canvas = document.getElementsByTagName('canvas')[0] //抓取canvas元素
let dataUrl = canvas.toDataURL() //回傳base64
```

# 下載功能

```javascript
function clickToDownload(e) {
    e.preventDefault() // 消除連結原有功能
    let link = document.querySelector('.link') //指定連結元素
    link.setAttribute('href', dataUrl) // 設定連結為剛剛canvas轉的dataurl
    link.setAttribute('download', fileName) // 設定下載之檔案名稱
    link.click() // 模擬點擊連結
}
```
