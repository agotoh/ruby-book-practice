# [プロを目指す人の為の Ruby 入門](http://gihyo.jp/book/2017/978-4-7741-9397-7)の勉強メモ

## 内容

あとで

## Ruby 環境構築手順

Mac に rbenv で Ruby 環境を構築する

### 前提

- OS: macOS Mojave 10.14.2
- Ruby の version 管理には rbenv を利用する
- Gem は Bundler で管理　今回は Bundler のインストールまで実施する

### rbenv, ruby のインストール

#### 現在インストールされている version 等確認

```bash:
which ruby
#/usr/bin/ruby
ruby -v
#ruby 2.3.7p456 (2018-03-28 revision 63024) [universal.x86_64-darwin18]
```

#### rbenv インストール

[rbenv 公式](https://github.com/rbenv/rbenv/blob/master/README.md)の手順で Homebrew でインストール

```bash:
brew install rbenv
rbenv init
echo 'eval "$(rbenv init -)"' >> ~/.zshrc
source ~/.zshrc
```

#### rbenv で ruby をインストール

global は最新の stable 2.6.0 、 local は 2.4.5 をインストールする手順

##### インストール可能な ruby の version 一覧を表示

```bash:
rbenv install -l
```

2.4.5 ,2.6.0 がリストに存在する事確認

##### 現在インストールされている ruby バージョンの一覧を表示

```bash:
rbenv versions
```

まだインストールしてないので、system のみ表示される事確認

##### 2.6.0 と 2.4.5 をインストール （結構時間かかるよ）

```bash:
rbenv install 2.4.5
rbenv install 2.6.0
rbenv versions
```

2.4.5,2.6.0 が表示されるのを確認

##### grobal に 2.6.0 を設定

```bash:
rbenv global 2.6.0
```

##### local に 2.4.5 を設定

対象のフォルダに cd した上で

```bash:
rbenv local 2.4.5
```

### Bundler インストール

```bash:
gem install bundler
gem env home
```

gem env home で gem env が rbenv で指定した ruby の version になっていることを確認

bundle init
で Gemfile ができることを確認。
今後コマンドは
bundle exec をつける
