---
layout: post
title:  "React Native Tutorial Day1"
date:   2018-02-11 00:00:02
categories: ReactNative
blog: true
---

[React Native](https://facebook.github.io/react-native/docs/getting-started.html)の学習メモ

## Expo

[Expo](https://expo.io/)がすごくて早速テンションが上がった

[create-react-native-app](https://github.com/react-community/create-react-native-app)をローカルに落として、立ち上げると、QRコードが表示され、Expoアプリで読み取るだけで、HMRができる優れもの。

まだ全体像が見えてないので、わからないことだらけだが、下記のようなWeb開発をしていれば見慣れたES6コードを書くだけでモバイルアプリが開発できるのは学習コストの面で良さそうな印象を実際に触ってそのまま感じ取れた。

```
import React, { Component } from 'react';
import { AppRegistry, Text } from 'react-native';

export default class HelloWorldApp extends Component {
  render() {
    return (
      <Text>Hello world!</Text>
    );
  }
}

// skip this line if using Create React Native App
AppRegistry.registerComponent('AwesomeProject', () => HelloWorldApp);

```

## まとめ

React Native, Expoをはじめて使った高揚感でフェアに捉えきれてない感じはある。魔法のアイテムにすら感じてしまっている。
iOS/Android掛け持ちの辛さ等があるはずなので、もう少し触ってメリデメを実際に感じとっていきたい。
