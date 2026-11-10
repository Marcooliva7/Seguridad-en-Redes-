## Descripción
Why search for the flag when I can make a bookmarklet to print it for me? Browse [here](http://chatelaine.cylabacademy.net:37860/), and find the flag!

1.- A bookmarklet is a bookmark that runs JavaScript instead of loading a webpage.

2.- What happens when you click a bookmarklet?

3.- Web browsers have other ways to run JavaScript too.
## Solución
```
```
javascript:(function() {
    var encryptedFlag = "...";
    var key = "picoctf";
    var decryptedFlag = "";
    for (var i = 0; i < encryptedFlag.length; i++) {
        decryptedFlag += String.fromCharCode((encryptedFlag.charCodeAt(i) - key.charCodeAt(i % key.length) + 256) % 256);
    }
    alert(decryptedFlag);
})();
```

academy{p@g3_turn3r_dfbc8ec5}
```

## Notas Adicionales

## Referencias
-
