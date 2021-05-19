# 1.WSLのインストール
## ⑴Windowsの設定を開いて、「アプリ」を選択

<img src="https://i.imgur.com/fI559aW.png">

## ⑵「プログラムと機能」を選択。

<img src="https://i.imgur.com/ZQAdILz.png">

## ⑶「Windowsの機能の有効化または、無効化」

<img src="https://i.imgur.com/zHTbXSd.png">

⑷[Linux用Widowsサブシステム]のチェックボックスにチェックを入れて「OK」を選択。

<img src="https://i.imgur.com/tAAQmwF.png">

## ⑸WSLのインストールが始まり、インストール後「今すぐ再起動」を選択

※Zoom中などの場合に気を付ける。
  先生に許可をもらう。

<br>
<hr>
<br>

# 2.Ubuntuのインストール
## ⑴Microsoft Storeを開く。

<img src="https://i.imgur.com/iKUl6Oo.png">

## ⑵「Ubunutu」と検索する。

<img src="https://i.imgur.com/LvQGdGi.png">

## ⑶「Ubuntu 20.04 LTS」を選択。

<img src="https://i.imgur.com/Xmpnr8r.png">

## ⑷「入手」を選択。ダウンロードが自動的に始まるので待機。

<img src="https://i.imgur.com/lKLEHeS.png">

## ⑸「起動」を選択。

<img src="https://i.imgur.com/joig3r9.png">

## ⑹起動をして少し待つと、ユーザーネームの設定が出るので、任意のユーザーネームを設定する。

(ここでは[makomako])

<img src="https://i.imgur.com/DQUFyll.png">

## ⑺次にパスワードを設定する。

※ここで、打ち込んでも表示されないが、実際は打ち込まれているころに注意する。

<img src="https://i.imgur.com/iShDekS.png">

## ⑻確認のため、もう一度入力する必要があるのでもう一度入力。

<img src="https://i.imgur.com/6SoQNYR.png">

## ⑼次のように表示されたらOK。

<img src="https://i.imgur.com/28rdwyP.png">

<br>
<hr>
<br>

# 3.VScodeに「Remote - WSL」という拡張機能を入れる。
<img src="https://i.imgur.com/WNbzanl.png">

<br>
<hr>
<br>

# 4.Ruby環境の構築
## ⑴VScodeを開き、左のメニューから「リモートエクスプローラー」を選択

<img src="https://i.imgur.com/Pt9Ifj9.png">

## ⑵Ubuntuのインストールの時に入力したユーザーネームの部分を右クリックし、「Open Folder in WSL」を選択

<img src="https://i.imgur.com/N5gdZEk.png">

## ⑶ターミナルが出ていることを確認。(ユーザーネーム@パソコン名:~$となっている。)

※出ていない場合はCtrl+@

<img src="https://i.imgur.com/S1RCFl7.png">

## ⑷環境を最新にする。<br>
ターミナルの部分で
```
$ sudo apt-get update
```
```
$ sudo apt-get upgrade
```
を実行する。

パスワードを入力するように言われるので、入力する(以後、省略。)

<img src="https://i.imgur.com/pDbLsrS.png">

<!-- update実行後
<img src="https://i.imgur.com/w644FNI.png"> -->

upgrade実行時、Y/nと聴かれるのでyを打ち込んでEnter
<img src="https://i.imgur.com/sQFSTEY.png">

<!-- upgrade実行後
<img src="https://i.imgur.com/c0mDrNb.png"> -->

## ⑸各種ライブラリを入れる。
```
$ sudo apt-get install make
```
```
$ sudo apt-get install gcc
```
```
$ sudo apt-get install -y libssl-dev libreadline-dev zlib1g-dev
```

<!-- <img src="https://i.imgur.com/zEnsWHH.png">
<img src="https://i.imgur.com/xdGL1Fj.png">
<img src="https://i.imgur.com/SNrA7Cn.png"> -->


## ⑹Node.jsを入れる

Node.jsのインストール
```
$ sudo apt-get install npm
```
<!-- <img src="https://i.imgur.com/CkRFvgW.png"> -->

Nodeのバージョン管理を行うnのインストール
```
$ sudo npm install -g n
$ sudo n stable
```
<!-- <img src="https://i.imgur.com/6BHLPLW.png">
<img src="https://i.imgur.com/IukN1UJ.png"> -->

## ⑺rbenvを入れる。
rbenvをインストール
```
$ git clone https://github.com/sstephenson/rbenv.git ~/.rbenv
```
<!-- <img src="https://i.imgur.com/c45WlTd.png"> -->

rbenvのパスを通す。
```
＄ echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
```

rbenvの設定を行う
```
 $ ~/.rbenv/bin/rbenv init
 ```
上のコマンドを実行すると、次のように表示される。
<img src="https://i.imgur.com/13YnLoa.png">

左のワークスペースから.bashrcを開く。

<img src="https://i.imgur.com/AJNbTZb.png">

ファイルの一番下の、
```
export PATH="$HOME/.rbenv/bin:$PATH"
```
の下に、
```
eval "$(rbenv init -)"を追加する。
```
<img src="https://i.imgur.com/3GNlEne.png">

最後に
```
$ source ~/.bashrc
```
を実行して、環境変数の反映をさせる。

## ⑻ruby-buildを入れる。

ruby-buildのインストール
```
＄ git clone https://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build
```
<img src="https://i.imgur.com/fqEu310.png">

## ⑼Rubyを入れる。

任意のバージョンのRubyを入れる。
```
$ rbenv install 〇.〇.〇
```
※ここめちゃ時間かかる。

<img src="https://i.imgur.com/ffaAnJe.png">

```
$ rbenv rehash
```
```
$ rbenv global 〇.〇.〇
```

Rubyのバージョン確認
```
ruby -v
```

# 5.Railsの開発を開始する。

⑴任意のディレクトリを作成する

```
$ mkdir mako-app
```

⑵ディレクトリに移動
```
$ cd mako-app
```
⑶Gemfileを作成。
```
$ bundle init
```

⑷Gemfileの中身を編集<br>
(コメントアウトされているgem "rails"をアンコメント)

<img src="https://i.imgur.com/lc9ZSDI.png">

⑸Railsをインストール
```
$ bundle install --path vendor/bundle
```
この時に--path vendor/bundleを忘れずにつけること。
このオプションを付けることによって、プロジェクトのvendor/bundle以下にgemが格納されます。
<img src="https://i.imgur.com/e52NmoN.png">

⑹Railsプロジェクトを作成。
```
bundle exec rails new .
```
※プロジェクトを作成する際、様々なオプションがある。
```
bundle exec rails new -h
```
で調べることができる。

⑺必要なgemを入れる。

⑻.gitignoreを[https://www.gitignore.io/]のrails用に編集する。
