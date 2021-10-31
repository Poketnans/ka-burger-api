<h1 align="center" >API KA Burger</h1>

API criada para realização da entrega "5A12 - Entrega - Hamburgueria 2.0 - com TypeScript e JSON Server" do curso de fullstack na Kenzie Academy

Este é o repositório da API KA Burger, baseada em JSON-Server + JSON-Server-Auth.

<hr/>

## **Tecnologias envolvidas**

- Node.js
- Heroku Deployer
- Json Server
- Json Server Auth

<hr/>

<h2 align="center" >Rotas Não Autenticadas</h2>

## **Registrando um novo usuário**

### Endpoint:

```
POST /register
```

### Body:

```json
{
  "name": "nome",
  "email": "email",
  "password": "senha"
}
```

### formato da resposta:

```json
Status 201 Created
```

```json
{
  "accessToken": "token de acesso",
  "user": {
    "email": "email cadastrado",
    "password": "senha encriptada",
    "id": "id do usuário",
    "name": "nome cadastrado"
  }
}
```

## **Login**

### Endpoint:

```
POST /login
```

### Body:

```json
{
  "email": "email cadastrado",
  "password": "senha cadastrada"
}
```

### formato da resposta:

```json
Status 200 OK
```

```json
{
  "accessToken": "token de acesso",
  "user": {
    "email": "email cadastrado",
    "password": "senha encriptada",
    "id": "id do usuário",
    "name": "nome cadastrado"
  }
}
```

## **Listando Produtos**

### Endpoint:

```
GET /products
```

### formato da resposta:

```json
Status 200 OK
```

```json
[
  {
    "id": "id do grupo",
    "name": "nome do produto",
    "description": "descrição do produto",
    "price": "preço (number)",
    "storage": "quantidade em estoque (number)",
    "userId": "id do criador"
  },
  {...}
]
```

<br/>
<hr/>
<h2 align="center" >Rotas Autenticadas</h2>

Todas as rotas autenticadas precisam conter o seguinte Header:

### Header

```json
{
  "Content-Type": "application/json",
  "headers": {
    "Authorization": "Bearer <token>"
  }
}
```

## **Acessando dados do usuário**

### Endpoint:

```
POST /users/:id
```

### formato da resposta:

```json
Status 200 OK
```

```json
{
  "name": "nome do hobbie",
  "frequency": "frequência de atividade",
  "userId": "id do usuário",
  "id": "id do hobbie",
  "history": [],
  "products": []
}
```

## **Criando Produtos**

### Endpoint:

```
POST /products
```

### Body:

```json
{
  "name": "nome do produto",
  "price": "preço do produto (number)",
  "description": "Descrição do produto",
  "storage": "Quantidade em estoque (number)",
  "image": "url da imagem",
  "userId": "id do usuário"
}
```

### formato da resposta:

```json
Status 201 Created
```

```json
{
  "name": "nome do produto",
  "price": "preço do produto (number)",
  "description": "Descrição do produto",
  "storage": "Quantidade em estoque (number)",
  "image": "url da imagem",
  "userId": "id do usuário"
}
```

## **Alimentando o histórico de compras**

### Endpoint:

```
POST /history
```

### Body:

```json
{
  "userId": "id do usuário",
  "date": "data da compra",
  "products": [
    {
      "productId": "id do produto 1",
      "quantity": "quantidade"
    },
    {
      "productId": "id do produto 2",
      "quantity": "quantidade"
    },
    {...}
  ]
}
```

### formato da resposta:

```json
Status 201 Created
```

```json
{
  "userId": "id do usuário",
  "date": "data da compra",
  "products": [
    {
      "productId": "id do produto 1",
      "quantity": "quantidade"
    },
    {
      "productId": "id do produto 2",
      "quantity": "quantidade"
    },
    {...}
  ]
}
```
