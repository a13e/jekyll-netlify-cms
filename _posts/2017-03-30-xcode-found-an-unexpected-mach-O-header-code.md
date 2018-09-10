---
layout: post
title:  "Found an unexpected Mach-O header code: * in XCode 6"
date:   2017-03-30 00:00:00
categories: swift xcode
blog: true
---

`organizer`で`Export`したらタイトルのエラーが発生して困った
下記を参考にしたらうまく動作した。

![](https://i.stack.imgur.com/nhWxm.png)

> Somehow pods appeared to become an embedded binary. So I had to remove it, pod install once more, and the issue disappeared.

## 参考
[http://stackoverflow.com/questions/26559948/found-an-unexpected-mach-o-header-code-1918975009-in-xcode-6](http://stackoverflow.com/questions/26559948/found-an-unexpected-mach-o-header-code-1918975009-in-xcode-6)
