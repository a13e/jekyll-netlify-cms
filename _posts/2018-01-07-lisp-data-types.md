---
layout: post
title:  "Lisp Data Types"
date:   2018-01-07 00:00:00
categories: Lisp
blog: true
---

[https://www.tutorialspoint.com/lisp/lisp_data_types.htm](https://www.tutorialspoint.com/lisp/lisp_data_types.htm)

## typep

オブジェクトが指定したタイプに属するかどうかを判定する関数

```
(typep 12 'integer) ; return T
(typep 12 'string) ; return NIL
```

## type-of

オブジェクトのデータタイプを返す関数

```
(defvar x 10)
(print (type-of x))
```

## defstruct

自分でデータタイプを新たに定義することができる

## setq

変数を設定する

```
(setq n 4)
```

は

```
(set (quote n) 4)
```

と同義

## defvar

setqと同様だが、変数が定義されていないときだけ使用するのが異なる。
