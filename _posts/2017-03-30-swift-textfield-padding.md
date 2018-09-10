---
layout: post
title:  "Swift3 TextField Paddingを設定する"
date:   2017-03-30 00:00:00
categories: swift xcode
blog: true
---

メールアドレスフォームにpadding-leftを追加するコード

{% highlight swift %}
self.emailField.leftView = UIView(frame: CGRect(x: 0, y: 0, width: 10, height: self.emailField.frame.size.height))
self.emailField.leftViewMode = UITextFieldViewMode.always
{% endhighlight %}
