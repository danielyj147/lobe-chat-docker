# Lobe Chat Docker Compose

> A simple and easily configurable lobe-chat docker-compose file

**[What is Lobe Chat?](https://github.com/lobehub/lobe-chat)**

## How to start without HTTPS

*Make sure docker is running*

- Comment out the entire `reverse-proxy` service block in `docker-compose.yml`
- Uncomment `ports: ...` in `docker-compose.yml`
- Rename `.env.example` to `.env`
- enter your `OpenAI API key` and `password` to the `.env` file
- cd to the repository & run the command below
```bash
docker compose up -b
```


## How to start with HTTPS

To use https, you need a TLS certificate(either self-signed or CA issued)
We will focus on self-signed certificate. 

- cd to the repository
- Run the command below to generate a certificate. Adjust `-days` tag to change the expiration date. 
```bash
openssl req -x509 -nodes -days 3650 -newkey rsa:2048 -keyout ./certs/mysite.key -out ./certs/mysite.crt
```
- Rename or Duplicate `.env.example` to `.env`
- enter your `OpenAI API key` and `password` to the `.env` file
- run the command below
```bash
docker compose up -b
```
