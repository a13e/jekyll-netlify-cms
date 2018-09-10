---
layout: post
title:  "Swift3 Xcode UITextField Keyboard Typeを設定する"
date:   2017-03-30 00:00:00
categories: swift xcode
blog: true
---

メールアドレス入力フォーム用のTextFieldに変更する

{% highlight swift %}
self.emailField.keyboardType = UIKeyboardType.emailAddress
{% endhighlight %}

他にも色々あるらしい。
詳しくは参考URLにある。

## 参考
http://qiita.com/BlueRoyInc/items/07338e3f04c2509641ac
http://www.globalnerdy.com/2013/02/18/the-iphones-virtual-keyboards-a-visual-catalogue/
http://swift-nyumon.info/uitextfield_number_keyboard
