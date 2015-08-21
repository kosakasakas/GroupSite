# GroupSite

森島研究室ダンス班のウェブサイトを作成するジェネレータです。

## 動作確認環境
Hugo Static Site Generator v0.15-DEV<br>
OS X Yosemite (10.10.3)

## インストール方法
以下はYosemiteを想定した環境の構築方法です。

### Hugoをインストール
homebrewでインストールできます。(homebrewがわからない場合はぐぐってね)

    brew install hugo

ただ、hugoのバージョンは0.14以上じゃないと最新のテーマが動かないため、インストールしたhugoのバージョンは確認しておいてください。

    hugo version  #Hugo Static Site Generator v0.14-DEVとか出ればOK

自分の環境ではhomebrewからのインストールだとv0.13しかインストールできなかったため、一旦アンインストールして手動で再インストールしました。
やりかたは、まずgoをインストール

    brew install go

GOPATHを設定して、binをPATHに通しておく。@~/.zshrc

    export GOPATH=$HOME/go
    export PATH=$HOME/go/bin:$PATH

これでgoが使えるようになるので、hugoをインストール

　　go get -u -v github.com/spf13/hugo

バージョンが0.14以上であることを確認してください。

### リポジトリのセットアップ
GroupSiteリポジトリをローカルに落として使えるようにする方法です。
まず作業ディレクトリにgit cloneしてくる。

    git clone git@github.com:kosakasakas/GroupSite.git

リポジトリに入ってサブモジュールを更新

    cd GroupSite
    git submodule update --init --recursive

以上でセットアップ完了です。

## プレビューしたい
デプロイする前にチェックする場合、以下のコマンドでローカルサーバーを起動します

    hugo server --watch -t creative --buildDrafts

コマンドラインでこれを打った後、ブラウザで以下のURLに繋げば見れると思います。

    http://127.0.0.1:1313/

## デプロイ方法
サイトのホスティングにはgithub pagesを使っています。
GroupSite/publicディレクトリがgithub pagesを実際に持つアカウントの.github.ioリポジトリのサブモジュールになっています。
アカウントを変更したい場合は、一旦publicフォルダのサブモジュールをはずして、変更したいアカウントの.github.ioリポジトリを再度publicディレクトリとしてサブモジュール登録してください。
この辺の細かい流れはHugoのドキュメントに書いてあるっぽいです。http://gohugo.io/tutorials/github-pages-blog/

また、アカウントを変更した場合、新しいデプロイ先のURLを GroupSite/config.tomlに記述しておく必要があります。
これをしないと、cssやらimageやら見つからなくてページが崩れます。

    baseurl = "http://kosakasakastest.github.io/" ## この部分を自分のサイトURLに置き換える

これができたらデプロイします。

    cd Groupsite
    ./deploy.sh

以上でgithub pagesにサイトがデプロイされます。

## サイトの編集方法
### 主な文言の修正
基本的なパラメータは全てGroupSite/config.tomlに記載されているのでそれをいじってください。

### Newsの編集
Newsを新しくPostする場合は、GroupSite以下で以下のコマンドを打ってください。

    hugo new jp-news/newest-your-news.md ##好きなファイル名でOKです

このとき、jp-newsがSection名になるので、JPのニュースを投稿する時はjp-newsを指定ディレクトリとして生成するようにしてください。
このコマンドを打った後はGroupSite/content/jp-newsにmdファイルが生成されるので、それを随時編集してください。
マークダウンで記述することができます。
以下はヘッダに書かれているパラメータの説明です。

    date  ## ポストした時の時刻が自動的に記述されます。また、この時間順で記事がオーダーされます。
    title ## 記事のタイトル。主にカルーセルで表示されます。
    description  ## 今のところ使っていない
    image ## サムネイル。512x512が推奨。カルーセルで表示します。
    draft ## 下書きかどうか。本番デプロイする際はこれを削除してください。


### Projectsの編集
Newsとほぼ同じ。postの際はjp-projectsを指定してください。

### Peopleの編集
パラメータはGroupSite/config.tomlを編集すればOKです。画像はGroupSite/peopleを参照して下さい。
200x200px推奨。
urlパラメータを指定することで、アイコンをクリックした際に指定した個人サイトに飛ばすことができるようになっています。

### Topの背景を変えたい
トップはHTML5で動画を再生しています。動画はGroupSite/img/movie/以下にある、opening.mp4とopening.webmを差し替えれば動きます。
また、ローディング中に表示するための画像として、動画の0フレーム目の画像を0_frame.jpg、HTML5のvideoタグに対応していないブラウザ用にdefault.jpgを合わせて用意してmovie以下に設置してください。
推奨サイズは720pで、ビットレート1Mくらいに抑えることをお勧めします。


## 構造など

    GroupSite/config.toml #パラメータ全般が書かれたファイル
    GroupSite/data # モーダル系の設定ファイル
    GroupSite/img # 画像は全てここ。thema/creative/static/imageのシンボリックリンク
    GroupSite/themas # 改造テーマのサブモジュール
    Groupsite/public # 実際にデプロイするデータ群。自動生成される。github pagesのアカウントのリポジトリ
    Groupsite/deploy # デプロイする時はこれを叩くとpunlicにファイルがはかれてpushされる

## 使用しているライブラリなど

* [slick](https://github.com/kenwheeler/slick)
* [share-button](http://syncer.jp/how-to-setting-share-button)
