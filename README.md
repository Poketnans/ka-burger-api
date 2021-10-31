# ka-burger-api

API criada para realização da entrega "5A12 - Entrega - Hamburgueria 2.0 - com TypeScript e JSON Server" do curso de fullstack na Kenzie Academy

<h1 align="center" >API Personal Controler Sheet</h1>

Esse é o repositório da API Personal Controler Sheet, baseada em JSON-Server + JSON-Server-Auth.

A API Personal Controler Sheet visa auxiliar aplicações voltadas para o gerencimento pessoal de rotinas.

<hr/>

## **Tecnologias envolvidas**

- Node.js
- Heroku
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
    "id": "id do usuário"
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
    "id": "id do usuário"
  }id": number
  }
}
```

## **Listando Grupos**

### Endpoint:

```
GET /groups
```

### formato da resposta:

```json
Status 200 OK
```

```json
[
  {
    "name": "nome do grupo",
    "category": "categoria do grupo",
    "userId": "id do criador",
    "id": "id do grupo"
  },
  {
    "name": "nome do grupo",
    "category": "categoria do grupo",
    "userId": "id do criador",
    "id": "id do grupo"
  }
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
  "groups": [],
  "hobbies": [],
  "routines": []
}
```

## **Criando Hobbies**

### Endpoint:

```
POST /hobbies
```

### Body:

```json
{
  "name": "nome do hobbie",
  "frequency": "frequência de atividade",
  "userId": "id do usuário"
}
```

### formato da resposta:

```json
Status 201 Created
```

```json
{
  "name": "nome do hobbie",
  "frequency": "frequência de atividade",
  "userId": "id do usuário",
  "id": "id do hobbie"
}
```

## **Criando Grupos**

### Endpoint:

```
POST /groups
```

### Body:

```json
{
  "name": "nome do grupo",
  "category": "categoria do grupo",
  "userId": "id do criador"
}
```

### formato da resposta:

```json
Status 201 Created
```

```json
{
  "name": "nome do grupo",
  "category": "categoria do grupo",
  "userId": "id do criador",
  "id": "id do grupo"
}
```

## **Criando Rotinas**

### Endpoint:

```
POST /routines
```

### Body:

```json
{
  "name": "nome do grupo",
  "category": "categoria do grupo",
  "starts": "Horário de início",
  "ends": "Horário de fim",
  "frequency": "frequência da rotina",
  "userId": "id do usuário"
}
```

### Formato da resposta:

```json
Status 201 Created
```

```json
{
  "name": "nome do grupo",
  "category": "categoria do grupo",
  "starts": "Horário de início",
  "ends": "Horário de fim",
  "frequency": "frequência da rotina",
  "userId": "id do usuário",
  "id": "id da rotina"
}
```
