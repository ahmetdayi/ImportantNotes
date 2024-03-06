```
version: '2'
services:

  vault:

      image: hashicorp/vault

      container_name: vault

      volumes:

        - ./volumes/logs:/vault/logs

        - ./volumes/file:/vault/file

        - ./volumes/config:/vault/config

      ports:

        - "8200:8200"

      restart: always  

      environment:

        VAULT_ADDR: http://127.0.0.1:8200

      cap_add:

        - IPC_LOCK

      entrypoint: vault server -config=/vault/config/vault.json

```
yukardakı docker composeyı calıstırmadan once docker composenın bulundugu konuma volume adlı bır klosor olustur. Icersıne confıg adlı bır klasor daha olusturup vault.json adında bır dosya olustur ıcıne
```json
{

    "backend": {

        "file": {

            "path": "/vault/file"

        }

    },

    "listener": {

        "tcp": {

            "address": "0.0.0.0:8200",

            "tls_disable": 1

        }

    },

    "ui": true,

    "disable_mlock": true

}
```
json objesını yapıstır.

![image](https://github.com/ahmetdayi/ImportantNotes/assets/74869229/8e1abd43-aa5d-48b7-b85e-55bb9115c0fd)

![image](https://github.com/ahmetdayi/ImportantNotes/assets/74869229/af4955e9-463a-4395-9de9-769f23a1418a)

