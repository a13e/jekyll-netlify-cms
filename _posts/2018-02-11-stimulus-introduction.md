---
layout: post
title:  "Stimulus Introduction"
date:   2018-02-11 00:00:01
categories: Stimulus JavaScript
blog: true
---

[Stimulus Introduction](https://stimulusjs.org/handbook/introduction)の感想・メモ。

## 全体としての感想

- 全体としてStimulusはバックエンドアプリケーションが生成したHTML DOMに対する操作をする機能のためのライブラリとしてデザインされており小さくシンプルであるのが印象的。
- 生成済みDOMへの操作のみが使用用途であることが事前にわかりきっているケースであれば、jQueryで自前のDOM手術をするよりもはるかに保守性を高くコストを抑えてプロダクト開発ができると感じた。
- SPAをつくるための機能が一切ないので、チーム開発においては開発方針が絞れる意味でも良いと感じた。(一部メンバーが非同期処理で暴れるみたいなことを防ぎやすい)
- データ追加系に関しては下記に記載のようにもう少しサポートしてもよいのではないかと感じた。

## 非同期ロードからの要素追加に関して

> There are cases where you’d want Stimulus to create new DOM elements, and you’re definitely free to do that. We might even add some sugar to make it easier in the future. But it’s the minority use case. The focus is on manipulating, not creating elements.

これは[DHHさんが書いたMedium](https://m.signalvnoise.com/stimulus-1-0-a-modest-javascript-framework-for-the-html-you-already-have-f04307009130)からの抜粋だが、この一文がどういうことなのかが、Introduction内のこの章ではっきりとした。
現行仕様では、データに応じて、要素を増やすには下記のような形で、直接DOMをユーザー側で操作する必要が出てしまう。(Welcome to DOM surgery party!)

```
import { Controller } from "stimulus"

export default class extends Controller {
  connect() {
    this.load()
  }

  load() {
    fetch(this.data.get("url"))
      .then(response => response.text())
      .then(html => {
        this.element.innerHTML = html
      })
  }
}
```

個人的にはStimulusを使用するケース(管理画面等)においても、リスト型のデータに新しい要素をユーザー起因のイベントで追加して、画面更新するような用途は多いので、アップデートが期待される。
