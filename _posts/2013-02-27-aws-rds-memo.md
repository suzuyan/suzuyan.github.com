---
layout: post
title: "AWS RDSを試してみた"
description: ""
category: 
tags: AWS RDS MySQL
---
{% include JB/setup %}


## Instance作成
- AWS Console のRDSをクリック
- `Launch DB Instance`をクリック
- 特に難しいところはないのでポチポチ押していく

## 外部接続できるようにする
- `DB Security Groups`の`default`を選択
- `CIDR/IP`に`0.0.0.0/0`を登録（どのIPからも接続OK）
