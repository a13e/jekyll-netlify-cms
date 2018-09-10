---
layout: post
title:  "Lisp Basic Syntax"
date:   2018-01-06 00:00:00
categories: Lisp
blog: true
---

[https://www.tutorialspoint.com/lisp/lisp_basic_syntax.htm](https://www.tutorialspoint.com/lisp/lisp_basic_syntax.htm)を参考にして学んだことをまとめる。

## Hello, World

```
(write-line "Hello, World")
```

## Basic Syntax - 基本構文

Lispプログラムは`atom`, `list`, `string`3つの基本ブロックで構築されている

### atom

`atom`は数値もしくは、文字列のこと。特殊記号も含む。

下記が例

```
hello-from-tutorials-point
name
123008907
*hello*
Block#221
abc123
```

### list

`list`は`atom`と他のカッコで囲われた`list`で構成されるもの。

下記が例

```
( i am a list )
(a ( a b c ) d e fgh )
( father tom ( susan bill joe ) )
( sum mon tue wed thur fri sat )
( )
```

### string

`string`はダブルクォート記号で囲われた文字列のグループ

下記が例

```
" I am a string"
"a ba c d efg #$%^&!"
"Please enter the following details :"
"Hello from 'Tutorials Point'! "
```

## コメント

行頭に `;` を使うことで、その行のあとをコメントとして扱うことができる

```
(write-line "Hello, World") ; greet the world

; tell them your whereabouts

(write-line "I am at 'Tutorials Point'! Learning Lisp")
```

## 注意点

- 基本数値演算子は `+`, `-`, `*`, and `/`
- Lispでは`f(x)`を`(f x)`と表す。例えば`cos(45)`は`cos 45`として記述する
- Lispは大文字/小文字を区別しないので、`cos 45` と `COS 45`は同様に扱う
- Lispは関数の引数を含めて、すべてを評価しようとします。下記3つのタイプの要素のみが定数であり、これらは常に自身の値を返します。
  - 数値
  - 文字列`t`
    - 論理的な`true`を表す
  - `nil`
    - 空のリストと同様に、論理的な`false`を表す

## Lispの評価プロセス

- `reader`が文字列をLispオブジェクトか`s-expression (S式)`に変換する
- `evaluator`がS式から構築される`Lips forms`文法を定義する。この評価の第2レベルでどのS式が`Lisp forms`であるかの文法を定義する。
- `Lisp forms`は下記になりうる
  - `atom`
  - `empty` or `non-list`
  - 第一要素としての、symbolを持つリスト

`evaluator`は引数としての正しい`Lisp form`を受け、値を返す関数として動作する。
これがLispをカッコで囲んで記載する理由で、こうすることで、Lispの式及びform全体を`evaluator`の引数として渡すことができている。

## 評価させず文字列として扱う

シングルクォートを使用することで, 関数評価をせず、その部分を文字列として扱うことができる

```
(write '(* 2 3)) ; returns (* 2 3) -> not evaluated
(write (* 2 3)) ; returns 6 -> evaluated
```
