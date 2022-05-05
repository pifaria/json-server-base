## Endpoints

URL base: (https://json-server-luiz-felipe.herokuapp.com/)

### Cadastro

POST /register <br>
POST /signup  <br>
POST /users

Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e senha.
Você pode ficar a vontade para adicionar qualquer outra propriedade no corpo do cadastro dos usuários (nome, idade, ...).

RESPONSE: 201 Created 
{
    "acessToken": "xxxx.xxxx.xxx"
}

### Login

POST /login <br>
POST /signin

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users"

RESPONSE: 200 OK
{
    "acessToken": "xxxx.xxxx.xxx"
}

### Cadastrar animais
POST /animals

cadastrar um novo animal de estimação sendo necessário passar o id do usuário e o token de autorização.

exemplo:
{
    type: gato,
    name: paçoca,
    userId: 1
}

RESPONSE: 200 OK 

### Listar animais
GET /animals

Lista pública que qualquer usuário pode ver, sem necessidade do login

RESPONSE: 200 OK

exemplo:
[
    {
        type: gato,
        name: paçoca,
        id: 1,
        userId: 1
    }
]

### Cadastrar vacina

POST /animalVaccine

cadastrar um novo animal de estimação sendo necessário passar o id do usuário, o nome e id do animal e o token de autorização.

RESPONSE: 200 OK

[
    {
        name: paçoca,
        id: 1,
        userId: 1,
        vaccines: ["cinomose"]
    }
]

## Listar vacina

GET /animalVaccine

Listar as vacinas que foram aplicadas no animal de estimação 

RESPONSE: 200 OK

[
    {
        name: paçoca,
        vaccines: ["cinomose", "parvovirose"]
    },
    {
        name: lilo,
        vaccines: ["cinomose" ,"parvovirose"]
    }
]