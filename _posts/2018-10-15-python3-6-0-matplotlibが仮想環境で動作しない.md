---
layout: post
title: Python3.6.0 Matplotlibが仮想環境で動作しない
categories: python
---
## 原因
`virtualenv`を使っていたこと

## 解決策
`venv`を使用すればいい

## 詳細
[Working with Matplotlib on OSX](https://matplotlib.org/faq/osx_framework.html)によると、

> On OSX, two different types of Python builds exist: a regular build and a framework build. In order to interact correctly with OSX through the native GUI frameworks, you need a framework build of Python.

`Python`には`regular`と`framework` buildが存在していて、`OSX native GUI framework`を使用するためには`framework build`が必要になる。

> In a virtualenv, a non-framework build is used even when the environment is created from a framework build (virtualenv bug #54, virtualenv bug #609).

`virtualenv`が作成する仮想環境では、それが`framwork build`から作成された場合であっても、`non-framework build`のPythonが使用されてしまう。

## 参考
[Working with Matplotlib on OSX](https://matplotlib.org/faq/osx_framework.html)
