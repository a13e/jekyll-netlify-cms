---
layout: post
title:  "Lisp Macros"
date:   2018-01-07 00:00:01
categories: Lisp
blog: true
---

Lisp Macrosについてメモ

## Macros (マクロ)

マクロを使うと標準的なLispの文法を拡張することができる
技術的には、マクロはS式を引数にとり、`Lisp form`を返却する関数で、それが評価されるものとなる。

## マクロを定義する

`defmacro`というマクロでマクロを定義することができる
下記がマクロの文法

```
(defmacro macro-name (parameter-list))
"Optional documentation string."
body-form
```

下記例では`setTo10`という名前の、数値の引数をとり、その変数を10へ上書きするマクロを定義する

```
(defmacro setTo10(num)
(setq num 10)(print num))
(setq x 25)
(print x)
(setTo10 x)
```

実行すると下記が表示される

```
25
10
```

## 参考
[https://www.tutorialspoint.com/lisp/lisp_macros.htm](https://www.tutorialspoint.com/lisp/lisp_macros.htm)
