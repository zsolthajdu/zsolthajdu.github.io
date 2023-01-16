---
layout: post
title:  "Typescript code-completion for Vim"
date:   2023-01-15 15:15:24 -0700
categories: typescript vim code-completion
---

How to set up Typescript code completion plugins in Vim.

## Client plugin
To add the CoC code completion plugin, add this to your .vimrc
```
Plug 'neoclide/coc.nvim', {'branch': 'release'}
```
This is a generic code completion plugin that supports many programming languages.
## Server plugin
For Typescript code completion to start working, the CoC extension for Typescript has to be installed also.  
Add this to .vimrc
```
let g:coc_global_extensions = ['coc-tsserver']
```
or run this command in Vim
```
:CocInstall coc-tsserver
```

