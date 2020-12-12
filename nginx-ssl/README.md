# NGINX + SSL

Última versió estable de nginx de hub.docker.com

### Consola |Mode debug|
```bash
$ docker run --name nginx-ssl -v $(pwd)/default.conf:/etc/nginx/conf.d/default.conf -v $(pwd)/certs/:/etc/nginx/certs/ -p 80:80 -p 443:443 -it nginx /bin/bash
```

## Consola
```bash
$ docker run --name nginx-ssl -v $(pwd)/default.conf:/etc/nginx/conf.d/default.conf -v $(pwd)/certs/:/etc/nginx/certs/ -p 80:80 -p 443:443 nginx
```
### Docker-compose
```bash
$ docker-compose up -d
``` 

## Test
```bash
$curl localhost

$curl -k https://localhost
```

> Amb l'opció -k obviem la signatura del SSL