# Luan-veicules

url base:

# Rotas que não precisam de autenticação

## cadastro de usuários

Este endpoint ``/register``, irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password. Você pode adicionar qualquer outra propriedade no corpo do cadastro dos usuários.

`POST /register - FORMATO DA REQUISIÇÃO`
```json
{
    "email": "luan@gmail.com",
	"password": "123456",
	"name": "luan",
	"age":23
}
```

se for um sucesso,a resposta será:

```json
{
    "accessToken": "xxxxxxxx.xxxxxxxx.xxxxxxxx",
	"user": {
		"email": "luan@gmail.com",
		"name": "luan",
		"age": 23,
		"id": 1
}
```

## Login

este endpoint ``/login`` será usado para que seja realizado login em uma conta cadastrada.

`POST /login - FORMATO DA REQUISIÇÃO`
```json
{
    "email": "luan@gmail.com",
	"password": "123456"
}
```

se for um sucesso,a resposta será:

```json
{
    "accessToken": "xxxxxxxx.xxxxxxxx.xxxxxxxx",
	"user": {
		"email": "luan@gmail.com",
		"name": "luan",
		"age": 23,
		"id": 1
}
```

# Rotas que precisam de autenticação

## Requisições de carros  ``/cars``

### Adicionar carro

Este endpoint irá cadastrar um novo carro,deve utilizar a propriedade `userId` para referenciar o usuário.

`POST /cars - FORMATO DA REQUISIÇÃO`
```json
{
    "car": "civic",
	"userId": 1
}
```

se for um sucesso,a resposta será:

```json
{
    "car": "civic",
	"userId": 1,
	"id": 4
}
```

### Visualizar carros

aqui irá visualizar a lista de carros do usuario,deverá utilizar o userId=id do usuario como queryparams.

`GET /cars?userId=1 - FORMATO DA REQUISIÇÃO`
se for um sucesso,a resposta será:

```json
[
	{
		"car": "horus",
		"userId": 1,
		"id": 1
	},
	{
		"car": "golf",
		"userId": 1,
		"id": 2
	},
	{
		"car": "crossfox",
		"userId": 1,
		"id": 3
	},
	{
		"car": "civic",
		"userId": 1,
		"id": 4
	}
]
```

## Requisições de motos  ``/motorcycles``

### Adicionar moto

Este endpoint irá cadastrar um novo moto,deve utilizar a propriedade `userId` para referenciar o usuário.

`POST /motorcycles - FORMATO DA REQUISIÇÃO`
```json
{
    "motorcycle": "yamaha 125",
	"userId": 1
}
```

se for um sucesso,a resposta será:

```json
{
    "motorcycle": "yamaha 125",
	"userId": 1,
	"id": 3
}
```

### Visualizar motos

aqui irá visualizar a lista de carros do usuario,deverá utilizar o userId=id do usuario como queryparams.

`GET /motorcycles?userId=1 - FORMATO DA REQUISIÇÃO`

se for um sucesso,a resposta será:

```json
[
	{
		"motorcycle": "xre",
		"userId": 1,
		"id": 1
	},
	{
		"car": "yamaha 125",
		"userId": 1,
		"id": 2
	},
	{
		"motorcycle": "yamaha 125",
		"userId": 1,
		"id": 3
	}
]
```