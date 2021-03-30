## Prerequisites
Things that might ease your future experience:
- a screen multiplexer like [_tmux_](https://github.com/tmux/tmux/wiki);
- a note taking application like [_cherrytree_](https://github.com/giuspen/cherrytree);
- bumped into an unknown command or a word? Feel free to _man_ it;
- getting hands on other people write\-ups only _after_ running out of your own ideas\.

Assuming you\'re familiar with __ssh__, ikimashou\!

## Bandit0 \-\- Bandit1  
> __ssh bandit0@bandit\.labs\.overthewire\.org \-p 2220__  
> bandit0@bandit:\~$ __ls__  
> readme  
> bandit0@bandit:\~$ __cat readme__   
> boJ9jbbUNNfktd78OOpsqOltutMc3MY1  
> bandit0@bandit:\~$ __ssh bandit1@localhost__   
> bandit0@localhost\'s password: __boJ9jbbUNNfktd78OOpsqOltutMc3MY1__  

#### Tip:

Using __Tab__ for autocompletion is a good practice:
> bandit0@bandit:\~$ __cat r__\
> (_Tab_)\
> bandit0@bandit:\~$ __cat readme__\
> bandit3@bandit:\~$ ls

## Bandit1 \-\- Bandit2

> bandit1@bandit:\~$ __ls__\
> \-\
> bandit1@bandit:\~$ __cat \./\-__\
> CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9

## Bandit2 \-\- Bandit3

> bandit2@bandit:\~$ __ls__\
> spaces in this filename

There are several ways to display the content of the file:

> bandit2@bandit:\~$ __cat \*__\
> UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK\
> bandit2@bandit:\~$ __cat \./\*__\
> UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK\
> bandit2@bandit:\~$ __cat spaces\\ in\\ this\\ filename__\
> UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK\
> bandit2@bandit:\~$ __cat space__\
> (_Tab_)\
> bandit2@bandit:\~$ __cat spaces\\ in\\ this\\ filename__\
> UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK

Not familiar with regular expressions (regex) and have no clue how escape characters in the above example work? [gitgud](https://regexone.com/) 

## Bandit3 \-\- Bandit4

> bandit3@bandit:\~$ __ls__\
> inhere\
> bandit3@bandit:\~$ __cd inhere/__\
> bandit3@bandit:\~/inhere$ __ls__\
> bandit3@bandit:\~/inhere$ __ls \-alh__\
> total 12K\
> drwxr\-xr\-x 2 root    root    4\.0K May  7  2020 \.\
> drwxr\-xr\-x 3 root    root    4\.0K May  7  2020 \.\.\
> \-rw\-r\-\-\-\-\- 1 bandit4 bandit3   33 May  7  2020 \.hidden\
> bandit3@bandit:\~/inhere$ __cat \.hidden__\
> pIwrPrtPN36QITSp3EQaw936yaFoFgAB

## Bandit4 \-\- Bandit5

> bandit4@bandit:\~$ __ls__\bandit4@bandit:~$ ls
inhere
bandit4@bandit:~$ cd inhere; ls
-file00  -file02  -file04  -file06  -file08
-file01  -file03  -file05  -file07  -file09
bandit4@bandit:~/inhere$ file ./-*
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
bandit4@bandit:~/inhere$ cat ./-file07 
koReBOKuIDDepwhWk7jZC0RTdopnAYKh

> inhere\
> bandit4@bandit:\~$ __cd inhere; ls__\
> \-file00  \-file02  \-file04  \-file06  \-file08\
> \-file01  \-file03  \-file05  \-file07  \-file09\
> bandit4@bandit:\~/inhere$ __file \./\-\*__\
> ./-file00: data\
> ./-file01: data\
> ./-file02: data\
> ./-file03: data\
> ./-file04: data\
> ./-file05: data\
> ./-file06: data\
> ./-file07: ASCII text\
> ./-file08: data\
> ./-file09: data\
> bandit4@bandit:\~/inhere$ __cat \./\-file07__\
> koReBOKuIDDepwhWk7jZC0RTdopnAYKh

## Bandit5 \-\- Bandit6

> bandit5@bandit:\~$ __ls__\
> inhere\
> bandit5@bandit:\~$ __cd inhere/; ls__\
> maybehere00  maybehere04  maybehere08  maybehere12  maybehere16\
> maybehere01  maybehere05  maybehere09  maybehere13  maybehere17\
> maybehere02  maybehere06  maybehere10  maybehere14  maybehere18\
> maybehere03  maybehere07  maybehere11  maybehere15  maybehere19\
> bandit5@bandit:\~/inhere$ __find \. \! \-executable \-size 1033c__\
> \./maybehere07/\.file2\
> bandit5@bandit:\~/inhere$ __cat \./maybehere07/\.file2__\
> DXjZPULLxYr17uwoI01bNLQbtFemEgo7\

A good aftermath practice is to try to get a flag with a single command:
> bandit5@bandit:\~$ __cat $(find \./inhere \-size 1033c \! \-executable)__\
> DXjZPULLxYr17uwoI01bNLQbtFemEgo7

## Bandit6 \-\- Bandit7

> bandit6@bandit:\~$ __find / \-size 33c \-user bandit7 \-group bandit6 2>/dev/null__\
> /var/lib/dpkg/info/bandit7\.password\
> bandit6@bandit:\~$ __cat /var/lib/dpkg/info/bandit7\.password__\
> HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs

_2>/dev/null_ redirects errors to make life easier

> bandit6@bandit:\~$ __cat $(find / \-size 33c \-user bandit7 \-group bandit6 2>/dev/null)__\
> HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs

## Bandit7 \-\- Bandit8

> bandit7@bandit:\~$ __ls__\
> data.txt\
> bandit7@bandit:\~$ __grep millionth data\.txt__\
> millionth	cvX2JJa4CFALtqS87jk27qwqGhBM9plV

## Bandit8 \-\- Bandit9

The man page for the command _uniq_ states:
> Note:  \'uniq\'  does not detect repeated lines unless they are adjacent\.\
> You may want to sort the input first, or use \'sort \-u\' without \'uniq\'\.

So let\'s do this\!
> bandit8@bandit:\~$ __ls__\
> data.txt\
> bandit8@bandit:\~$ __sort data\.txt | uniq \-u__\
> UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR

## Bandit9 \-\- Bandit10

> bandit9@bandit:\~$ __strings data\.txt | grep \=\=__\
> ========== the\*2i\"4\
> ========== password\
> Z)========== is\
> &========== truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk

## Bandit10 \-\- Bandit11

> bandit10@bandit:~$ __base64 -d data.txt__\
> The password is IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR

## Bandit11 \-\- Bandit12

The command _tr_ is required for this level, feel free to _man_ it!

> bandit11@bandit:\~$ __alias rot13\=\"tr \'a\-zA-Z\' \'n\-za\-mN\-ZA\-M\'\"__\
> bandit11@bandit:\~$ __cat data\.txt | rot13__\
> The password is 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu

