---
layout: post
title: "git filter branch"
description: ""
category: 
tags: []
---
{% include JB/setup %}

github で複数アカウント持っていて色々使い分けてるんですが、 authered がアカウントに紐付いていないアカウントになってしまっていて困ったので調べてみた<br>
どうやら <b>git filter-branch</b> というコマンドで設定できるようだ

## git filter-branch
[git-filter-branch(1) Manual Page][1]
<code><pre>
git filter-branch --commit-filter '
    GIT_AUTHOR_NAME="アカウント名"
    GIT_AUTHOR_EMAIL="メールアドレス"
    GIT_COMMITTER_NAME="アカウント名"
    GIT_COMMITTER_EMAIL="メールアドレス"
    git commit-tree "$@"
' HEAD
</pre></code>

<b>git filter-branch</b> で一度コミットした内容を消したりもできるようです<br>
[git最強のオプション filter-branch - CubicLouve][2]

git はコマンド多すぎていまいち使いこなせている感じしないｗ

[1]: https://www.kernel.org/pub/software/scm/git/docs/git-filter-branch.html
[2]: http://spring-mt.tumblr.com/post/25934691482/git-filter-branch
