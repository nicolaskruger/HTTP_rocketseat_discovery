# Guia estelar HTTP

## HyperText Transfer Protocol

protocolo de transferência de HyperTexto

### Visão Geral

- Permite troca de informação e dados na internet
- Uma troca de mensagens
- HTML, CSS, Script, Imagem, Video
- Uma chamada para cada um desses recursos

![alt](./img/001.png)

## Mensagem

### Pedido(Request)

![pedido](./img/pedido.png)

### REQUEST MESSAGE

~~~~code
GET /index.html HTTP/1.1
User-Agent: Mozilla/4.0
Accept:text/html
~~~~

### Resposta(Response)

![resposta](./img/resposta.png)

### RESPONSE MESSAGE

~~~~code
HTTP/1.1 200 OK
Server:Express
Content-Type: text/html
~~~~

### header

![header](./img/header.png)

### body

![body](./img/body.png)

## Recurso

![recurso](./img/recurso.png)

## curl

~~~~bash
curl -i https://google.com # retorna requisição com informação do HEADER

curl -v https://google.com # retorna requisição com todas as informações
~~~~

## conceitos

![conceito](./img/conceito.png)

## cliente

![cliente](./img/cliente.png)

## servidor

![servidor](./img/servidor.png)

## json-server

~~~~bash
npm install -g json-server
~~~~

## Methods

### options

![options](./img/options.png)

~~~~bash
curl -X OPTIONS http://localhost:3000/posts -i # faz uma chamada do tipo options
~~~~

### get

![get](./img/get.png)

~~~~bash
curl http://localhost:3000/posts # recebe a resposta do tipo GET
~~~~

### head

![head](./img/head.png)

Vem somente o cabeçalho.

~~~~bash
curl -I  http://localhost:33000/posts
~~~~

### post

![post](./img/post.png)

~~~~bash
d '{"id": 2, "title": "json-server", "author": "typicode"}' -H "Contet-type: application/json" -X POST  http://localhost:3000/posts # resposta do tipo POST
~~~~

### put

muda o recurso par Inteiro

![put](./img/put.png)

~~~~bash
curl  -d '{"name":"nicolas"}' -H 'Content-type: application/json' -X PUT  http://localhost:3000/profile
~~~~

### patch

muda parte do recurso

![patch](./img/patch.png)

~~~~bash
curl -d '{"title":"my-title"}' -H "Content-type: application/json" -X PATCH  http://localhost:3000/posts/1
~~~~

### delete

![delete](./img/delete.png)

~~~~bash
curl -X DELETE  http://localhost:3000/posts/2
~~~~

## headers

![headers](./img/headers.png)

### header-contexto

![header-contexto](./img/header-contexto.png)

## status code

### 100

- 100: Continue

### 200

- 200: OK (GET,POST)
- 201: Created (PUT)
- 204: No Content (DELETE,PUT)

### 300

- 301: Moved Permanently
- 308: Permanent Redirect
- 302: found
- 307: Temporary Redirect

### 400

- 400: Bad Request
- 401: Unauthorized
- 403: Forbiden
- 404: Not Found
- 405: Method Not Allowed
- 429: Too Many Request

### 500

- 500: internal Server Erros
- 503: Service Unavalible
