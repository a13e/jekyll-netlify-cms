---
layout: post
title:  "オフィス利用状況把握システム"
description: オフィス移転後、利用状況に応じてオフィス配置等を変えたいという小話を耳にしたのと、当時機械学習で何かしたかったことがあり、作成したシステム。
image: being_image_1.png
date:   2017-07-01 00:00:01
categories: works being
blog: true
---
<div style="width:200px">
  <img style="border:1px solid #dcdcdc;margin:10px 0;object-fit: cover;" src="/assets/images/being_image_1.png" width="100%"/>
</div>

オフィス移転後、利用状況に応じてオフィス配置等を変えたいという小話を耳にしたのと、当時機械学習で何かしたかったことがあり、作成したシステム。

2017/07 ~ 2017/09

大きく下記3つの構成になっている。

- 定期撮影 & S3へ画像アップロードするiOSアプリ
- S3上の画像をインプットにして、画像解析及びデータを記録するスクリプト
- データ閲覧用のRedash

## 共同で開発した[ozw](https://qiita.com/ozw)さんによるqiita記事

[機械学習で共有スペース利用状況の解析](https://qiita.com/ozw/items/ac50ee4c0ad893ac3dd6)
