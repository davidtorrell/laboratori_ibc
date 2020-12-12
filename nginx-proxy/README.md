# NGINX - PROXY + WHOAMI

### Generar SSL
http://www.selfsignedcertificate.com/ auto signats

### Temes importants
- El nom l'arxiu ha de tindre el mateix nom que el host
- L'extensió ha de ser `crt` NO `cert`, s'ha de canviar de nom 
- Posar a la carpeta `certs`

###  Docker-compose | arxiu únic |
```bash
$ docker-compose -f 1-docker-compose_one-file.yml up -d
``` 
### Docker-compose | arxius separats |
```bash
$ docker-compose -f 2-docker-compose-web1.yml up -d
$ docker-compose -f 2-docker-compose-whoami.yml up -d
$ docker-compose -f 2-docker-compose-proxy.yml up -d
``` 

### Test
```bash
$ curl whoami.localhost.com
$ curl web1.localhost.com

$ curl -k https://whoami.localhost.com
$ curl -k https://web1.localhost.com
```

>  \* Amb l'opció -k obviem la signatura del SSL

> ** Recordar posar l'arxiu hosts les entrades cap a 127.0.0.1