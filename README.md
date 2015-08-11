# GroupSite

森島研究室ダンス班のウェブサイトを作成するジェネレータです。

## 動作確認環境
Hugo Static Site Generator v0.15-DEV
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

GOPATHを設定して、binをPATHに通しておく。@~/zshrc

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

## デプロイ方法
サイトのホスティングにはgithub pagesを使っています。
GroupSite/publicディレクトリがgithub pagesを実際に持つアカウントのサブモジュールになっています。
アカウントを変更したい場合は、一旦punlicフォルダのサブモジュールをはずして、変更したいアカウントの.github.ioリポジトリを再度publicとしてサブモジュール登録してください。
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
newsのようなモーダルある系の記事はGroupSite/news以下にあるyamlファイルで管理をしているのでそれをコピーして編集します。
ただし、最新記事の順番にソートさせるにはファイル名の頭の採番を一個ずつ減らして新しいファイルを作っていく必要があります。理由はhugoのバグでmapの降順sortが機能しなかったため。

yamlが参照している画像はimg/news以下に設置しています。ファイル名は任意でOKです。
ファイルサイズは650x350pxが推奨です。

### Projectsの編集
Newsとほぼ同じ

### Peopleの編集
パラメータはGroupSite/config.tomlを編集すればOKです。画像はGroupSite/peopleを参照して下さい。
200x200px推奨

### Topの背景を変えたい
gifがGroupSite/unnamed.gifにあります。これを差し替えればOKです。


