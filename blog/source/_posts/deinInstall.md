---
title: dein + vim-markdown Install
date: 2017-05-26 14:46:04
tags:
- vim
- dein
- install
---
# dein入れてみました
出遅れた感すごいですがdein入れてみました

まずはコマンドラインで以下を実行してください
specify the installation directoryの所はその名の通りインストールする場所を決めてください
僕の場合は`.vim/`にしました

```
curl https://raw.githubusercontent.com/Shougo/dein.vim/master/bin/installer.sh > installer.sh
sh ./installer.sh {specify the installation directory}
```

すると以下のようなコードが出てきます
ここに書いてあるpathは先ほどインストールを指定したフォルダの場所などで変わるのでしたのコードをコピペしても動かないと思います
(コピペしたらなぜか上下に4行の空きがありました助けてください)

```
"dein Scripts-----------------------------
if &compatible
  set nocompatible               " Be iMproved
endif

" Required:
set runtimepath+=/Users/master/.vim//repos/github.com/Shougo/dein.vim

" Required:
if dein#load_state('/Users/master/.vim/')
  call dein#begin('/Users/master/.vim/')
  " Let dein manage dein
  " Required:
  call dein#add('/Users/master/.vim//repos/github.com/Shougo/dein.vim')

  " Add or remove your plugins here:
  call dein#add('Shougo/neosnippet.vim')
  call dein#add('Shougo/neosnippet-snippets')

  " You can specify revision/branch/tag.
  call dein#add('Shougo/vimshell', { 'rev': '3787e5' })

  " Required:
  call dein#end()
  call dein#save_state()
endif

" Required:
filetype plugin indent on
syntax enable

" If you want to install not installed plugins on startup.
"if dein#check_install()
"  call dein#install()
"endif

"End dein Scripts-------------------------
```
  
このとき下記のコメントを外すと自動インストールするようになります

```
" If you want to install not installed plugins on startup.
if dein#check_install()	" ここのコメントを外す
  call dein#install()	" ここのコメントを外す
endif			" ここのコメントを外す
```
  
するといい感じにインストール完了です〜

## vim-markdownをインストール
hexoでmarkdownを使っていることもあってdeinを導入したついでに入れてみます

先ほどの`" Add or remove your plugins here:`の下に追加して

```
  " Add or remove your plugins here:
  call dein#add('Shougo/neosnippet.vim')	" でふぉ
  call dein#add('Shougo/neosnippet-snippets')	" でふぉ
  call dein#add('godlygeek/tabular') 		" マークダウン用 (こっちが先じゃないと動かない!!)
  call dein#add('plasticboy/vim-markdown')	" マークダウン用
```
  
これでインストール完了です。

参考にさせてもらったサイトは以下
ありがとうございます。
	[Vim + Markdown](http://qiita.com/iwataka/items/5355bdf03d0afd82e7a7)
	[github: plasticboy/vim-markdown](https://github.com/plasticboy/vim-markdown)

