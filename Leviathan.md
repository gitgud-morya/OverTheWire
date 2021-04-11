## Leviathan0 \-\- Leviathan1

> leviathan0@leviathan:\~$ __ls \-a__\
> \.  \.\.  \.backup  \.bash\_logout  \.bashrc  \.profile\
> leviathan0@leviathan:\~$ __cd \.backup; ls \-a__\
> \.  \.\.  bookmarks\.html

bookmarks.html is a huge file so I've decided to poke around and grep for something aaand.. succeeded on the 1st attempt:

> leviathan0@leviathan:\~/\.backup$ __grep \-i leviathan bookmarks.html__\
> \<DT\>\<A HREF=\"http://leviathan\.labs\.overthewire\.org/passwordus\.html | This will be fixed later, the password for leviathan1 is rioGegei8m\" ADD\_DATE=\"1155384634\" LAST\_CHARSET=\"ISO\-8859\-1\" ID=\"rdf:\#$2wIU71\"\>password to leviathan1\</A\>

## Leviathan1 \-\- Leviathan2

> leviathan1@leviathan:\~$ __ls \-lh check__\
> \-r\-sr\-x\-\-\- 1 leviathan2 leviathan1 7\.3K Aug 26  2019 check\
> leviathan1@leviathan:\~$ __\./check__\
> password: __password__\
> Wrong password, Good Bye ...\
> leviathan1@leviathan:\~$ __ltrace \./check__\
> \_\_libc\_start\_main(0x804853b, 1, 0xffffd794, 0x8048610 \<unfinished \.\.\.\>\
> printf(\"password: \")\
>                        = 10\
> getchar(1, 0, 0x65766f6c, 0x646f6700password: abc\
> )                                                                        = 97\
> getchar(1, 0, 0x65766f6c, 0x646f6700)\
>                        = 98\
> getchar(1, 0, 0x65766f6c, 0x646f6700)\
>                        = 99\
> strcmp(\"abc\", \"sex\")\
>                        = \-1\
> puts(\"Wrong password, Good Bye \.\.\.\"Wrong password, Good Bye \.\.\.\
> )                                                                         = 29\
> +++ exited (status 0) +++\
> leviathan1@leviathan:\~$ __\./check__\
> password: __sex__\
> $ __whoami__\
> leviathan2\
> $ __cat /etc/leviathan\_pass/leviathan2__\
> ougahZi8Ta

## Leviathan1 \-\- Levaithan2

