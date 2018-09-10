---
layout: post
title:  "iOS 新規環境用にでビルドする"
date:   2017-03-30 00:00:00
categories: swift xcode
blog: true
---


BuildSettings → Swift Compiler → Other Swift Flags → DEBUGに「-D DEBUG」、Releaseに「-D RELEASE」を指定する。

![](https://d2mxuefqeaa7sj.cloudfront.net/s_858DEC0D7A4F8F9AC7CA410BBA79C0AD71A287328F695AA5E66A1A7DFCB6682E_1490923941658_Screenshot+2017-03-31+10.32.08.png)

<br/>

左上の スキーマ → Manage Schemes... → 対象プロジェクトを選択して Edit → Run → Infoタブの Build Configuration を DEBUG/RELEASE に切り替える。

![](https://d2mxuefqeaa7sj.cloudfront.net/s_858DEC0D7A4F8F9AC7CA410BBA79C0AD71A287328F695AA5E66A1A7DFCB6682E_1490924040080_Screenshot+2017-03-31+10.33.41.png)

![](https://d2mxuefqeaa7sj.cloudfront.net/s_858DEC0D7A4F8F9AC7CA410BBA79C0AD71A287328F695AA5E66A1A7DFCB6682E_1490924076837_Screenshot+2017-03-31+10.34.20.png)

<br/>

Cocoapods を使用している場合は、さらに設定が必要。
Pods → Info → Configurations で「Staging」を追加

![](https://d2mxuefqeaa7sj.cloudfront.net/s_858DEC0D7A4F8F9AC7CA410BBA79C0AD71A287328F695AA5E66A1A7DFCB6682E_1490924247107_Screenshot+2017-03-31+10.37.06.png)


Build Settings → Apple LLVM 6.1 → Preprocessor Macros で Staging を「STAGING=1」に設定。

![](https://d2mxuefqeaa7sj.cloudfront.net/s_858DEC0D7A4F8F9AC7CA410BBA79C0AD71A287328F695AA5E66A1A7DFCB6682E_1490924373651_Screenshot+2017-03-31+10.39.25.png)


### 環境別コンパイル

{% highlight swift %}
#if DEBUG
let env = "デバッグ環境"
#elseif STAGING
let env = "ステージング環境"
#else
let env = "リリース環境"
#endif
{% endhighlight %}


## Special Thanks
[http://qiita.com/merrill/items/079999aa064f0df9baf7#%E7%92%B0%E5%A2%83%E3%81%94%E3%81%A8%E3%81%AB%E5%87%A6%E7%90%86%E3%82%92%E5%88%86%E3%81%91%E3%82%8B](http://qiita.com/merrill/items/079999aa064f0df9baf7#%E7%92%B0%E5%A2%83%E3%81%94%E3%81%A8%E3%81%AB%E5%87%A6%E7%90%86%E3%82%92%E5%88%86%E3%81%91%E3%82%8B)
