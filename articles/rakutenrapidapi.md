---
title: "Rakuten RapidAPIの登録方法"
emoji: "🌟"
type: "idea" # tech: 技術記事 / idea: アイデア
topics: [RapidAPI,RakutenRapidAPI]
published: true
---
# はじめに
先日、base64をGIF加工してくれるAPIがないかなと探していたところ、RakutenRapidAPIというサービスを見つけました。最終的に自分でそのAPIを作って公開したのですが、あまり日本語での情報がないようでしたので記事を作りました。

# 想定読者
- RakutenRapidAPIに興味を持っている人
- 公開手順の感じを知りたい人

# RakutenRapidAPIとは
自分の管理しているAPIを登録して公開したり、世界中の人が作成した便利なAPIを利用することができるサービスです。
面白い部分としてAPI公開者はこのサービスを通じて**収益**を得ることができます。
さらに収益モデルを**API作成者自身が設定**でき、API利用者は利用状況に応じて料金を払います。

ちなみにRakutenRapidAPIサービス提供側は発生した利用料から20%(2022年1月現在)の手数料を受け取ります。
プランはかなり自由に設定できます。こちらは筆者が設定したプランですが各数値は自分で決めることができました。
![](/images/rakutenrapidapi/rakuten1.png)

このサービスの特徴として、自分が公開しているAPIの入り口は利用者から秘匿化されることも利点の1つだと思います。RakutenRapidAPI上の入り口を経由して自身のAPIがリクエストされます。

より詳細な情報はこちらをご覧ください。
https://api.rakuten.net/api-providers

# 公開手順
## 1. API準備
まずは公開するAPIを用意する必要があります。記事の目的から外れていくのでここは省略しますが、自分の場合はAWSを使ってAPIGateway＋Lambda構成で用意しています。

## 2. RakutenRapidAPIへの登録
こちらのページからユーザ登録します。たまにページがとても重くなるときがあります。あなたのせいじゃないです。辛抱強く待ちましょう。

## 3. API作成
### 3.1 API追加
ログインしたらプロバイダボードからAPI追加を選択します。
![](/images/rakutenrapidapi/rakuten6.png)

### 3.2 APIの宛先の設定
最初のステップとして「BaseURLを追加」→「設定」項目からAPIのベースURLを登録します
![](/images/rakutenrapidapi/rakuten2.png)

### 3.3 エンドポイントの設定
次に「エンドポイント」項目からエンドポイントの作成を選択します
![](/images/rakutenrapidapi/rakuten3.png)

### 3.4 APIの宛先の設定
次に「エンドポイント」項目からエンドポイントの作成を選択します
エンドポイントの説明やパラメータの説明などを行います。
![](/images/rakutenrapidapi/rakuten4.png)
POSTリクエストであれば、パラメータの例を入力します。
ポイントとして、ここで入力したパラメータは利用を迷っている人がAPIをテストするときに使用されるので、APIの有用性が分かるような値を設定できると良いと思います。
また、リクエストの言語ごとの例のような項目はRakutenRapidAPIが自動で用意してくれるので自分で何かをする必要はありません。
![](/images/rakutenrapidapi/rakuten5.png)

### 3.5 API説明情報の設定
「画像を追加」項目からAPIについての説明を記述します
自分は全世界向けにしたかったので英語で書いてみました。日本語でも大丈夫です。（一部のAPIを見ると自動翻訳されていそうです）
ポイントとして、あまり多くは記入できなさそうに見える「概要」欄がAPIを検索したときに見える部分なので実は大事です。ここの記述を頑張るのが良さそうです。
![](/images/rakutenrapidapi/rakuten7.png)

### 3.6 API説明情報の設定
最後に「APIを公開する」ページで公開を行います。これでAPIの公開については完了です。
![](/images/rakutenrapidapi/rakuten8.png)

## 4. 料金プランの設定
プロバイダボードから料金プランを選択します
![](/images/rakutenrapidapi/rakuten9.png)

プランの追加を選択して料金プランについて設定していきます
他の方の作成したAPIを見ると、BASICプラントして基本料無料で日別に上限を設けたフリーミアプランを作り、このプランでテストをしてもらって、気に入った人にはPROプラン以降のサブスク契約をしてもらうというパターンが多いように思います。例で出している自分のプランもそれを真似しています。
![](/images/rakutenrapidapi/rakuten10.png)

## 5. 公開状況の確認
こちらのページから自分のAPIが検索でヒットするかや、見た目や説明がおかしいところがないかを確認しましょう。
https://api.rakuten.net/

# 最後に
Rakuten RapidAPIを使ったAPIの公開手順について紹介させて頂きました。

最後に宣伝です。
今回紹介したサービスを使って、画像のbase64データからGIF画像を作成するAPIを公開しています。機会があればぜひ使ってみて下さい。(テストで格闘したので2022年1月のエラー率が異常ですが..)
https://api.rakuten.net/teteeee/api/base64images2gif

また、APIのイメージ画像でも使用しているロゴのようなものですが、自作のスマホアプリで作成しました。
こちらも機会があればぜひ使ってみて下さい。
https://play.google.com/store/apps/details?id=com.kenbon.liverToy
