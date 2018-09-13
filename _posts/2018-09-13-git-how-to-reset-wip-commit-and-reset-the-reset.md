---
layout: post
title: '[Git] How to reset WIP commit and reset the reset'
categories: git
---
## 直前コミットを取り消して、その内容ベースでやりなおしたい

```
git reset --soft HEAD^
```

## リセット自体をやめたい

```
git reset --hard ORIG_HEAD
```
