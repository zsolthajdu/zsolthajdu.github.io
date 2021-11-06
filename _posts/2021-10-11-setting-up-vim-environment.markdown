---
layout: post
title:  "Setting up basic VIM environment"
date:   2021-10-11 00:15:24 -0700
categories: editor vim linux config
---

Steps to set up Vim editor environment

## Get plugin manager
Install Vundle plugin manager
{% highlight bash %}
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
{% endhighlight %}

## Color scheme
The sample config below uses the OneDark color scheme from
https://github.com/joshdick/onedark.vim

## GUI Font set
Adobe Source Code Pro  
Used for GVim

## Edit .vimrc
Save this into ~/.vimrc

{% highlight bash %}
set nocompatible              " be iMproved, required
filetype off                  " required

" set the runtime path to include Vundle and initialize
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
" alternatively, pass a path where Vundle should install plugins
"call vundle#begin('~/some/path/here')

" let Vundle manage Vundle, required
Plugin 'VundleVim/Vundle.vim'

" The following are examples of different formats supported.
" Keep Plugin commands between vundle#begin/end.
" plugin on GitHub repo
Plugin 'tpope/vim-fugitive'
Plugin 'preservim/nerdtree'
Plugin 'ctrlpvim/ctrlp.vim'
Plugin 'sheerun/vim-polyglot'
Plugin 'joshdick/onedark.vim'

" All of your Plugins must be added before the following line
call vundle#end()            " required
filetype plugin indent on    " required
" To ignore plugin indent changes, instead use:
"filetype plugin on
"
" Brief help
" :PluginList       - lists configured plugins
" :PluginInstall    - installs plugins; append `!` to update or just :PluginUpdate
" :PluginSearch foo - searches for foo; append `!` to refresh local cache
" :PluginClean      - confirms removal of unused plugins; append `!` to auto-approve removal
"
" see :h vundle for more details or wiki for FAQ
" Put your non-Plugin stuff after this line


set ts=3

set smarttab
set shiftwidth=3
"set expandtab
set guifont=Source\ Code\ Pro\ 10
set cindent number ruler laststatus=2 title hlsearch
colorscheme onedark
syntax on
{% endhighlight %}

### Plugins
This config includes the Vundle plugin manager and the following plugins:  
* [NERDTree](https://github.com/preservim/nerdtree) File system explorer
* [Vim-fugitive](https://github.com/tpope/vim-fugitive) git plugin for Vim
* [Ctrlp](https://github.com/ctrlpvim/ctrlp.vim) Fuzzy file/buffer finder for Vim
* [Vim-poyglot](https://github.com/sheerun/vim-polyglot) Syntax highlighting for lots of additional languages.
* [OneDark colortheme](https://github.com/sheerun/vim-polyglot) Popular colortheme

## Install plugins
Launch vim and in it issue
    :PluginInstall
command
