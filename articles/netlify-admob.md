---
title: "【無料&簡単に】AdMobの app-ads.txt に対応する【Netlify使用】"
emoji: "🏃"
type: "idea" # tech: 技術記事 / idea: アイデア
topics: ['Admob','スマホアプリ','Netlify','広告']
published: true
---
# はじめに
筆者は個人でスマホアプリを開発しています。
先日、Googleの広告をアプリ内に組み込むのに苦戦したので備忘を兼ねて本記事を書きました。

# 想定読者
- 自身のWebページをまだ持っていない個人開発者
- 無料でAdmobのapp-ads.txtに対応するやり方を探している人
- Netlifyというサービスを知らなかった人

# Admobのapp-ads.txtとは
スマホアプリを作成し、GoogleのAdmobを使ってアプリ内に広告をつける際に必要となるファイルです。広告の不正利用を防ぐための確認に使われます。

# Netlifyとは
静的なwebサイトを無料で簡単に公開できるサービスです。
本記事では初めてNetlifyを使う方を想定して公開までの手順を解説したいと思います。

# 自身のWebページの作成と公開
ここから本題です。
Netlifyを使用したwebページの作成とapp-ads.txtの配置について解説します

## 1. GitHubに公開するサイトのリポジトリを作成
説明をシンプルにするため、以下ではGitHubでサイトを公開する前提で話を進めます。
公開するサイトのリポジトリとファイルをGitHubに準備して下さい。
慣れていない方は階層などで戸惑うかもしれませんので、一例として[私のページ階層](https://github.com/teteeee/myhomepage)を公開します。
(リポジトリはpublic設定にする必要はないのでprivateで作成して大丈夫です。)
## 2. Netlifyへの登録
NetlifyへSign Upしてアカウントを作成してください。
執筆時点でのサイトはこちらです。
https://www.netlify.com/

アカウント作成後、GitHubとの連携を行います。
こちらのサイトの「Gitリポジトリと連携」というトピックの情報が分かりやすいです。
https://rightcode.co.jp/blog/information-technology/netlify-github-up

無事に連携ができたらサイトのURLを分かりやすい文字列に変更しましょう。
ドメインを所有していれば、自分の持っているカスタムドメインに設定することもできます。
![](/images/netlify-admob/2.png)

ここまでで自分のWebページ作成と公開が完了です。
無料ですし想像よりも簡単だったのではないかと思います。

# app-ads.txtの作成と公開

## 1. app-ads.txtの作成
Admobの画面から、「アプリ」→「すべてのアプリを表示」→「APP-ADS.TXTの設定」で表示されるコードをコピーしてapp-ads.txtを作成します。
![](/images/netlify-admob/3.png =250x)
![](/images/netlify-admob/4.png)

[筆者の場合](https://github.com/teteeee/myhomepage/blob/main/app-ads.txt)は対象のレコードが一行だけのファイルになっています。
作成したapp-ads.txtはGitHubのリポジトリ直下に配置します。

## 2. ストアへのWebページの登録
Androidの場合はアプリページ内の「ストアの設定」から「ウェブサイト」という箇所で設定します。
![](/images/netlify-admob/1.png)


iOSの場合はストアの掲載情報のマーケティングURL欄に設定します。
(後でスクショ貼る)

# 最後に
以上の手順でAdmobの設定は完了です。自動的に設定が正しいか判定されるので、1日ほど待つと対応完了という扱いになります。

最後に宣伝です。
SlackやMattermostでカスタム絵文字を作成するスマホアプリを開発しました。クスッとするような身内ネタの文字や画像を作ってみて下さい。
https://play.google.com/store/apps/details?id=com.kenbon.liverToy


### それでは、良き開発ライフを！