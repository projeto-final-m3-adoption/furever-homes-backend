# json-server-base

Esse é o repositório com a base de JSON-Server + JSON-Server-Auth já configurada, feita para ser usada no desenvolvimento das API's nos Projetos Front-end.

## Endpoints

Assim como a documentação do JSON-Server-Auth traz (https://www.npmjs.com/package/json-server-auth), existem 3 endpoints que podem ser utilizados para cadastro e 2 endpoints que podem ser usados para login.

### Cadastro

POST /register <br/>
POST /signup <br/>
POST /users

Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password.
Você pode ficar a vontade para adicionar qualquer outra propriedade no corpo do cadastro dos usuários.

* Resultado da Requisição:

<code>{
	"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Im1hdGV1czJAbWFpbC5jb20iLCJpYXQiOjE2ODI5NTAwMDMsImV4cCI6MTY4Mjk1MzYwMywic3ViIjoiMyJ9.QIyrbjKJMkWjEPnutU-0u8j468GH8eJFUGEN7tK2W2Y",
	"user": {
		"email": "mateus2@mail.com",
		"name": "Mateus",
		"age": 31,
		"id": 3
	}
} </code>

### Login

POST /login <br/>
POST /signin

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users"

* Resultado da Requisição:

<code> {
	"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Im1hdGV1czJAbWFpbC5jb20iLCJpYXQiOjE2ODI5NTAwODgsImV4cCI6MTY4Mjk1MzY4OCwic3ViIjoiMyJ9.BW_F-Q2mJ9ZFGLUX0ATuXeaC_FfweLaJdk_HrzBUBEI",
	"user": {
		"email": "mateus2@mail.com",
		"name": "Mateus",
		"age": 31,
		"id": 3
	}
} </code>

### Pet

GET /pet <br/>
GET /pet/id <br/>

Essas rotas pegam todos os animais cadastrados, ou um animal com base em seu id.

* Resultado da Requisição:

<code> [
	{
		"name": "Caramelo",
		"type": "Cachorro",
		"age": "Filhote",
		"gender": "Macho",
		"size": "Pequeno",
		"img": "https://www.rbsdirect.com.br/imagesrc/25743537.jpg?w=700",
		"description": "Caramelo é perfeito para a segurança da sua casa",
		"address": "Florianopolis",
		"isAdopted": false,
		"userId": 1,
		"id": 1
	}]</code>

POST /pet <br/>

Faz o cadastro de um novo pet. Rota necessita de token

* Body Necessário para cadastrar o pet:

<code> {
	"name": "Gato",
  "type": "Gato",
  "age": "Idoso",
  "gender": "Femea",
  "size": "Grande",
	"img": "",
	"description": "",
	"adress": "",
	"isAdopted": false,
	"userId": 2
}
</code>

PATCH /pet/id

Faz a adoção do pet. Rota necessita de token

* Body necessário para a rota:

<code>{
	"isAdopted": true	
} </code>


### Imsonia

[![Run in Insomnia}](https://insomnia.rest/images/run.svg)](https://insomnia.rest/run/?label=&uri=)
