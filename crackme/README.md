tag: reversing, warmup

crackme
88 pts

authored by ptr-yudai

Can you crack the password?

```
 crackme
 linux環境でcrackmeバイナリを実行する。 mac では実行できなかったので、WSLで調べながら実行した
 パスワードの入力が求められる。対象バイナリを $ strings crackme で出力された
 N1pp0n-Ich!_s3cuR3_p45$w0rD
 を入力すると、flagが出力された
 
 RicSec{U_R_h1y0k0_cr4ck3r!}

 https://hex-rays.com/ida-free/#download
 IDA Freeを利用する。
```

writeupを書かれている方の参考情報
https://tan.hatenadiary.jp/entry/2023/04/23/030022

```
 void (*v6)(void); // rdx
  char _0[96]; // [rsp+0h] [rbp+0h] BYREF
  int anonymous0; // [rsp+60h] [rbp+60h]
  unsigned __int64 vars68; // [rsp+68h] [rbp+68h]

  dwReturnCode = 1;
  vars68 = __readfsqword(0x28u);
  __printf_chk(1LL, "Password: ", a3);
  memset(_0, 0, sizeof(_0));
  v4 = _0;
  anonymous0 = 0;
  v5 = "%99s";
  if ( (unsigned int)__isoc99_scanf("%99s", _0) == 1 )
  {
    v4 = "N1pp0n-Ich!_s3cuR3_p45$w0rD";
    dwReturnCode = 1;
    if ( !strcmp(_0, "N1pp0n-Ich!_s3cuR3_p45$w0rD") )
    {
      dwReturnCode = 0;
      puts("[+] Authenticated");
      v5 = _0;
      sub_1290(_0);
    }
    else
    {
      v5 = "[-] Permission denied";
      puts("[-] Permission denied");
    }
  }
  if ( __readfsqword(0x28u) != vars68 )
    start((__int64)v5, (__int64)v4, v6);
  return dwReturnCode;
}
```