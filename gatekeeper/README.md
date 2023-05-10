tag: misc

gatekeeper
200 pts

authored by Arata

Bypass the base64 filter

nc gatekeeper.2023.ricercactf.com 10005

====
https://medium-company.com/base64/
https://github.com/coreutils/gnulib/blob/master/lib/base64.c

```
➜ nc 0.0.0.0 10005
password: bw==cGVuIHNlc2FtZSE=
RicSec{*** REDUCTED ***}
```
