## Leviathan0

> leviathan0@leviathan:\~$ __ls \-a__\
> \.  \.\.  \.backup  \.bash\_logout  \.bashrc  \.profile\
> leviathan0@leviathan:\~$ __cd \.backup; ls \-a__\
> \.  \.\.  bookmarks\.html

bookmarks.html is a huge file so I've decided to poke around and grep for something aaand.. succeeded on the 1st attempt:

> leviathan0@leviathan:\~/\.backup$ __grep \-i leviathan bookmarks.html__\
> \<DT\>\<A HREF=\"http://leviathan\.labs\.overthewire\.org/passwordus\.html | This will be fixed later, the password for leviathan1 is rioGegei8m\" ADD\_DATE=\"1155384634\" LAST\_CHARSET=\"ISO\-8859\-1\" ID=\"rdf:\#$2wIU71\"\>password to leviathan1\</A\>
