+++
categories = ['備忘録']
tags = ['hugo','papermod']
title = 'ブログ作った備忘録'
date = 2024-09-28T19:46:11+09:00
slug = 'daily_blog_note'
draft = true
+++

今このブログを書くのに使ってるHugoとPaperMod(テーマの一つ)についての備忘録。素人がふわっと書いた備忘録なので、きちんとした情報は公式ドキュメント等を参照してください。
<!--more-->
<br>
<br>
<br>

2023年年末に、それまで使っていたWordPressのブログからHugoのブログに乗り換えました。
モチベーションは私のブログの更新頻度にムラがあってWordPress本体やプラグインなどの更新対応が追い付かないことが多いこと、エディタが使いにくいと感じたこと、数年前？そこそこ前から静的ブログジェネレータというものをちらちら見かけていて興味を持っていたこと、Gitを使ってドキュメントのリビジョン管理やってみたいと思っていたこと……です。

<br>

[Hugo公式サイト](https://gohugo.io/)

<br>

その中でHugoの、PaperModというテーマでやってみようと決めたのは、ざっくり検索してみてドキュメントやいろんな方が書かれた備忘録的記事が多く、私のような素人でもそういう情報を見てなんとかできるんじゃないかと思えたからです。
現時点で、Hugo　ブログ　で検索すると下記のような記事がヒットします。めっちゃ先人たちの肩に乗れる…。

<br>

[【Hugo】ブログを作りたい？...5分もあれば十分だ](https://zenn.dev/rivine/articles/2023-06-12-create-hugo-blog)
[Hugo で静的なサイト・ブログを構築しよう](https://qiita.com/peaceiris/items/ef38cc2a4b5565d0dd7c)
[hugoを使って爆速でブログを作成する](https://zenn.dev/harachan/articles/a043e9a756cae4)
[Hugoでブログを始める](https://hn-carter.sakura.ne.jp/posts/get-started-hugo/)
[Hugoでブログを作った](https://catengineer.net/created-blog/)
[]()
[]()

<br>

lastmod設定は下記記事をそのまま使った…
https://www.jacksonlucky.net/posts/use-lastmod-with-papermod/

そのほか、下記も参考にしたが、そのままではうまくいかなかった
https://k-kaz-git.github.io/post/hugo-custom-theme-pagermod/

公式
https://gohugo.io/methods/page/gitinfo/

<br>

lastmod設定の際に、深く考えずに(！)hugo.toml内でpublishdateの設定を

> publishDate = ['publishdate', 'pubdate', 'published']

…と変更していて、このままだとArchiveページに何も表示されなくなる。(ArchiveページではPublishdateを引用しているが、現状のページごとのfrontmatterでは'publishdate', 'pubdate', 'published'を指定していないから)。

> publishDate = ['date', 'publishdate', 'pubdate', 'published']

とすると、各ページ中のfrontmatterで設定されたdateを引用してページを生成するため問題解消される（date以外の指定って要らないのでは…）