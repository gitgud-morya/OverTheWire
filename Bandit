## Preset
Things that might ease your future experience: 
- a screen multiplexer like [_tmux_](https://github.com/tmux/tmux/wiki);
- a note taking application like [_cherrytree_](https://github.com/giuspen/cherrytree);
- bumped into an unknown command or a word? Feel free to _man_ it;
- getting hands on other people write-ups only _after_ running out of your own ideas.

Assuming you're familiar with __ssh__, ikimashou! 

## Bandit0 -- Bandit1
> __ssh bandit0@bandit.labs.overthewire.org -p 2220__
> bandit0@bandit:~$ __ls__
> readme
> bandit0@bandit:~$ __cat readme__ 
> boJ9jbbUNNfktd78OOpsqOltutMc3MY1
> bandit0@bandit:~$ __ssh bandit1@localhost__ 
> bandit0@localhost's password: __boJ9jbbUNNfktd78OOpsqOltutMc3MY1__

#### Tip:

Using __Tab__ for autocompletion is a good practice:
> bandit0@bandit:~$ __cat r__
> (_Tab_)
> bandit0@bandit:~$ __cat readme__bandit3@bandit:~$ ls

## Bandit1 -- Bandit2

> bandit1@bandit:~$ __ls__
> \-
> bandit1@bandit:~$ __cat \.\/\-__
> CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9

## Bandit2 -- Bandit3

> bandit2@bandit:~$ __ls__
> spaces in this filename

There are several ways to display the content of the file:

> bandit2@bandit:~$ __cat *__
> UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
> bandit2@bandit:~$ __cat ./*__
> UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
> bandit2@bandit:~$ __cat spaces\ in\ this\ filename__
> UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
> bandit2@bandit:~$ __cat space__
> (_Tab_)
> bandit2@bandit:~$ __cat spaces\ in\ this\ filename__
> UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK

Not familiar with regular expressions (regex) and have no clue how escape characters in the above example work? [gitgud](https://regexone.com/) 

## Bandit2 -- Bandit3

> bandit3@bandit:~$ __ls__
> inhere
> bandit3@bandit:~$ __cd inhere/__
> bandit3@bandit:~/inhere$ __ls__
> bandit3@bandit:~/inhere$ __ls -alh__
> total 12K
> drwxr-xr-x 2 root    root    4.0K May  7  2020 .
> drwxr-xr-x 3 root    root    4.0K May  7  2020 . .
> -rw-r----- 1 bandit4 bandit3   33 May  7  2020 .hidden
> bandit3@bandit:~/inhere$ __cat .hidden__ 
> pIwrPrtPN36QITSp3EQaw936yaFoFgAB
