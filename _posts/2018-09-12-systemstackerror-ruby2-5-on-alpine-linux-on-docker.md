---
layout: post
title: 'SystemStackError, Ruby2.5 on Alpine Linux on Docker'
---
## 発生した問題
開発用に使用している`ruby:2.5.1-alpine`をベースとしたDockerイメージにて、`Rspec`内にて `factory_bot`を用いて`fixtures`をリストで生成する箇所にて`SystemStackError`が発生する問題に直面した。

## 原因

[こちら](https://bugs.ruby-lang.org/issues/14387#note-19)をみるに、`Ruby2.5`と`alpine`の組み合わせに起因しているよう。尚詳細は理解できていない。

## 対応
Dockerイメージのベースを`ruby:2.5.1`へ変更し、関連箇所を併せて修正(`apk` -> `apt-get`等)することで問題を解消した。


## References
[https://bugs.ruby-lang.org/issues/14387#note-19](https://bugs.ruby-lang.org/issues/14387#note-19)
