---
layout: post
title:  "VIM environment using vim-plug plugin manager"
date:   2022-05-18 00:15:24 -0700
categories: editor vim linux config
---

Steps to set up Vim editor environment

## Get plugin manager
Install vim-plug plugin manager
{% highlight bash %}
curl -fLo ~/.vim/autoload/plug.vim --create-dirs https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
{% endhighlight %}

## Color scheme
The sample config below uses the OneDark color scheme from
https://github.com/joshdick/onedark.vim

## GUI Font set
Adobe Source Code Pro  
Used for GVim

## Typescript language support plugin
The COC Typescript server, which is also installed by the vim sample config below, requires Node version 12 or later to be installed on the system.

## Edit .vimrc
Add this into ~/.vimrc

{% highlight bash %}
call plug#begin()

" Shorthand notation; fetches https://github.com/junegunn/vim-easy-align
Plug 'junegunn/vim-easy-align'

" The following are examples of different formats supported.
" Keep Plugin commands between vundle#begin/end.
" plugin on GitHub repo
Plug 'tpope/vim-fugitive'
Plug 'preservim/nerdtree'
Plug 'junegunn/fzf', { 'do': { -> fzf#install() } }
Plug 'sheerun/vim-polyglot'
Plug 'joshdick/onedark.vim'
Plug 'neoclide/coc.nvim', {'branch': 'release' }

" All of your Plugins must be added before the following line
call plug#end()            " required
filetype plugin indent on    " required
" To ignore plugin indent changes, instead use:
"filetype plugin on
"
" Brief help
" :PluginList       - lists configured plugins
" :PlugInstall      - installs plugins; append `!` to update or just :PluginUpdate
" :PluginSearch foo - searches for foo; append `!` to refresh local cache
" :PluginClean      - confirms removal of unused plugins; append `!` to auto-approve removal
"
" see :h vundle for more details or wiki for FAQ
" Put your non-Plugin stuff after this line


" FZF key bindings
nnoremap <C-f> :FZF<CR>
let g:fzf_action = {
  \ 'ctrl-t': 'tab split',
  \ 'ctrl-i': 'split',
  \ 'ctrl-v': 'vsplit' }

let $FZF_DEFAULT_COMMAND='find . \( -name node_modules -o -name .git \) -prune -o -print'


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
* [FZF fuzzy file search](https://github.com/junegunn/fzf) Fuzzy file/buffer finder for Vim
* [Vim-poyglot](https://github.com/sheerun/vim-polyglot) Syntax highlighting for lots of additional languages.
* [OneDark colortheme](https://github.com/sheerun/vim-polyglot) Popular colortheme

## Install plugins
Launch vim and in it issue
    :PlugInstall
command
