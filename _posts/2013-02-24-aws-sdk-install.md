---
layout: post
title: "AWS-SDK インストールから簡単なデモ表示まで"
description: "AWS-SDK install memo"
category: 
tags: [AWS] [PHP] [PEAR]
---
{% include JB/setup %}

** インストール
 ~/libs以下にPEARをインストールするところから
<pre><code>
mkdir libs
cd libs
# グローバルを汚したくないのでローカル設定ファイルを作成
pear  config-create `pwd` .pearrc
pear -c .pearrc install PEAR
pear -c .pearrc channel-discover pear.amazonwebservices.com
# 依存するライブラリもまとめて入れる
pear -c .pearrc -D auto_discover=1 install aws/sdk
</code></pre>

** AWSのバケット指定
