# osticker run on docker

- rename .env.example to .env
- set variables in .env
- download dictrib and unpack
- run:
```
docker-compose up -d
```
- goto http://host:8888 and install using data from .env (mysql host - "db")
