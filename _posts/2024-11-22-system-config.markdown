---
layout: post
title:  "System config steps"
date:   2024-11-21 17:15:24 -0700
categories: ubuntu setup haproxy linux
---

## Desktop system
Components for Ubuntu linux.

### Terminal fuzzy finder
Install from [GitHub](https://github.com/junegunn/fzf#using-git)

Then for bash config:
```
export FZF_DEFAULT_COMMAND='find . \( -name node_modules -o -name .git \) -prune -o -print'
export FZF_CTRL_T_COMMAND=$FZF_DEFAULT_COMMAND
[ -f ~/.fzf.bash ] && source ~/.fzf.bash
```

### Editor
To enable spell chelking in VIM
```
:set spell spelllang=hu
```
This should download the language dictionary if necessary.

### Windows dual-boot

#### Fix local time difference problem
```
sudo timedatectl set-local-rtc 1
```

## Raspberry Pi
Stuff for the board running Raspbian (Debian) Linux

### HAProxy
To test haproxy config file:
```
haproxy  -db -f /etc/haproxy/haproxy.cfg
```
To check current status
```
journalctl -xeu haproxy  
systemctl status haproxy.service
```
Place security certificates into /etc/haproxy/certs

