---
layout: post
title: "AWSで簡単なCDNサーバを作る"
description: "AWS S3 Startup with CloudFront"
category: 
tags: AWS S3 CloudFront
---
{% include JB/setup %}

## 流れ
1. S3バケット作成
    CloudFrontはS3経由でファイルを取得するので
2. CloudFront用のバケット設定
3. CloudFrontのディストリビューション作成
4. ドメインを割り振り、独自ドメインで運用してみる

## S3バケット作成 ~ CloudFront用のバケット設定
- AWS Consoleの`S3`をクリック
- `Create Bucket`からバケット作成
    Bucket Name　はドメイン名がいいと思う
- 作成したバケットを選択して右上の`Properties`から`Permissions`を押す
- `Edit bucket policy`からJSON形式のポリシールールを定義（指定のバケット以下の読み込み権限を自動的に付与）
    {
    "Statement": [
        {
            "Sid": "st.szyn.jp-PublicReadAcl",
            "Effect": "Allow",
            "Principal": {
                "AWS": "*"
            },
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::st.szyn.jp/*"
        }
    ]
    }
- 試しにファイルをアップロードして閲覧できることを確認


### CloudFrontのディストリビューション作成 ~ ドメイン設定
- `Create distribution`を押して作成
    `Cnames`で割り当てるドメインをセット
- 作成されたディストリビューションの`i`を押して`Domain name`確認
- cname sub xxxx.cloudfront.net. みたいな感じでCNAMEセット
