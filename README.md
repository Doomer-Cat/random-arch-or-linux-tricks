(WIP) = Work In da Progress

(?) = not sure if grammar or what i'm saying makes sense (or works?)

# 1. Change colors vc & login shell
## 1.1 /etc/issue

see 1.2 for explanation on colors

#### /etc/issue:

    \e]P01d2021\e]P1fb4934\e]P2b8bb26\e]P3fabd2f\e]P483a598\e]P5d3869b\e]P68ec07c\e]P7ebdbb2\e]P83c3836\e]P9fb4934\e]PAb8bb26\e]PBfabd2f\e]PC83a598\e]PDd3869b\e]PE8ec07c\e]PFebdbb2\ec
    Arch Linux \r (\l)

Note: The line has to be appended since the shell needs to be cleared (?) for no artifacting

## 1.2 in [Bash Configuration Files](https://wiki.archlinux.org/title/Bash#Configuration_files) (?)

#### $HOME/.bashrc

```sh
# gruvbox dark hard (?)
    if [ "$TERM" = "linux" ]; then
    echo -en "\e]P01d2021" #black
    echo -en "\e]P83C3836" #darkgrey
    echo -en "\e]P1FB4934" #darkred
    echo -en "\e]P9FB4934" #red
    echo -en "\e]P2b8bb26" #darkgreen
    echo -en "\e]PAb8bb26" #green
    echo -en "\e]P3FABD2F" #brown
    echo -en "\e]PBFABD2F" #yellow
    echo -en "\e]P483A598" #darkblue
    echo -en "\e]PC83A598" #blue
    echo -en "\e]P5d3869b" #darkmagenta
    echo -en "\e]PDd3869b" #magenta
    echo -en "\e]P68EC07C" #darkcyan
    echo -en "\e]PE8EC07C" #cyan
    echo -en "\e]P7EBDBB2" #lightgrey
    echo -en "\e]PFEBDBB2" #white
    clear #for background artifacting
fi
```
NOTE: This only changes the console & not the login shell

## 1.3 lydm 

#### /lib/systemd/system/ly.service

```sh
...
[Service]
Type=idle
ExecStartPre=/usr/bin/printf '%%b' '\e]P01D2021\e]P7EBDBB2\ec'
...
```
