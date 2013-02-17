---
layout: post
title: "install jekyll memo"
description: "Make github page by jekyll memo."
category: github ruby
tags: jekyll
---
{% include JB/setup %}

## github上にリポジトリを作成する

[<img src="/assets/jekyll_install_memo01.png" alt="github page 01" class="aligncenter size-medium wp-image-80" />][1]

＊github pageを利用するには**アカウント名.github.com**でリポジトリを作る

## jekyllのインストール

<pre># 一般ユーザ権限でインストールしたいので--user-installオプションをつける
gem install jekyll --user-install
</pre>

## jekyll bootstrapのインストール

jekyll bootstrapなるものがあり、サクサクっと上げるにはチョー便利 http://jekyllbootstrap.com/

<pre>git clone https://github.com/plusjade/jekyll-bootstrap.git USERNAME.github.com
cd USERNAME.github.com
# サンプルの投稿はいらないので削除しておく
rm -rf _posts/core-samples/
</pre>

## ローカルで確認

jekyll起動時にローカル環境で確認できるようサーバ起動させる

### vi _config.yml

<pre># 追記
server: true
</pre>

## jekyll起動

<pre>jekyll
# PATH通ってなかったら(bashrcとかに書いておくといいでっす)
export PATH=$PATH:~/.gem/ruby/1.8/bin
</pre>

デフォルトのportは4000なのでhttp://localhost:4000にアクセスしてみてページが表示されればOK！

## gitにpushする

<pre>git remote set-url origin git@github.com:USERNAME/USERNAME.github.com.git
git push origin master
</pre>

## 記事追加していく

<pre># ページ追加
rake post title="ページタイトル"
# _post以下に%Y-%m-%d-ページタイトル.md ファイルができているのでmarkdownでガシガシ書いていく
</pre>

こことか見ながら進めると色々捗る http://jekyllbootstrap.com/usage/jekyll-quick-start.html

 [1]: http://blog.szyn.jp/wp-content/uploads/2013/02/b6af95929ed2ee94e306e44e0c70b539.png
