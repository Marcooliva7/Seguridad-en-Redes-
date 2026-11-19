## Descripción
There is some interesting information hidden around this site. Can you find it?

1.- You should have enough hints to find the files, don't run a brute forcer.
## Solución
```
┌──(kali㉿kali)-[~]
└─$ curl -s http://wily-courier.picoctf.net:65278/
<!-- Here's the first part of the flag: picoCTF{t -->

┌──(kali㉿kali)-[~]
└─$ curl -s http://wily-courier.picoctf.net:65278/mycss.css
/* CSS makes the page look nice, and yes, it also has part of the flag. Here's part 2: h4ts_4_l0 */

┌──(kali㉿kali)-[~]
└─$ curl -s http://wily-courier.picoctf.net:65278/myjs.js
/* How can I keep Google from indexing my website? */

┌──(kali㉿kali)-[~]
└─$ curl -s http://wily-courier.picoctf.net:65278/robots.txt
# Part 3: t_0f_pl4c
# I think this is an apache server... can you Access the next flag?

┌──(kali㉿kali)-[~]
└─$ curl -s http://wily-courier.picoctf.net:65278/.htaccess
# Part 4: 3s_2_lO0k
# I love making websites on my Mac, I can Store a lot of information there.

┌──(kali㉿kali)-[~]
└─$ curl -s http://wily-courier.picoctf.net:65278/.DS_Store
Congrats! You've completed the scavenger hunt! Part 5: _9588550}

academy{th4ts_4_l0t_0f_pl4c3s_2_lO0k_2b9c61f}
```
```

```

## Notas Adicionales
- El JavaScript da la pista para revisar robots.txt.
- robots.txt da la pista de Apache, por lo que se revisa htaccess.
## Referencias
-- [http://wily-courier.picoctf.net:65278/](http://wily-courier.picoctf.net:65278/)
- [http://wily-courier.picoctf.net:65278/mycss.css](http://wily-courier.picoctf.net:65278/mycss.css)
- [http://wily-courier.picoctf.net:65278/myjs.js](http://wily-courier.picoctf.net:65278/myjs.js)
- [http://wily-courier.picoctf.net:65278/robots.txt](http://wily-courier.picoctf.net:65278/robots.txt)
- [http://wily-courier.picoctf.net:65278/.htaccess](http://wily-courier.picoctf.net:65278/.htaccess)
- [http://wily-courier.picoctf.net:65278/.DS_Store](http://wily-courier.picoctf.net:65278/.DS_Store)
