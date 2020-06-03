#backend

->rota: endereço completo da requisição
->recurso: qual entidade estamos acessando do sistema

localhost:3030 -> rota
/users -> acessando o recurso users (entidade users)

-> requisições:

GET: buscar infos - uma ou mais
POST: criar nova info
PUT: atualiza info existente no backend
DELETE: deleta info

request params -> parametros que vem na propria rota que identificam o recurso. obrigatorio.
query params => parametros geralmente opcionais, para filtros, paginação...
request body => parametros para criacao e atualizacao.

knex.js -> biblioteca de linguagem unificada para muitos banco de dados.
-> permite escrever as queries em formato de javascript

*npm install Knex*
*npm install sqlite3*

_knex('users').where('name', 'diego').select('*')_ => escrito em JS
ao invez de:
_SELECT * FROM users WHERE name = 'diego'_

consigo adaptar para qualquer banco de dados.


exemplos da aula
```
app.get('/users', (request, response) => {
	console.log('listagem de usuarios');

	return response.json(users);
});

app.get('/users/search', (request, response) => {
	const search = String(request.query.search);

	const filteredUsers = search ? users.filter(user => user.includes(search)) : users;

	return response.json(filteredUsers);
})

app.get('/users/:id', (request, response) => {
	const id = Number(request.params.id);

	const user = users[id];

	return response.json(user);
})

app.post('/users', (request, response) => {
	const data = request.body;

	console.log(data)

	const user = {
		name: data.name,
		email: data.email
	};
	return response.json(user);
})

////
__dirname -> retorna o caminho pro diretorio do arquivo que estamos executando
```
identidades: _tabelas que vamos utlizar e campos de cada uma delas_
* points - pontos de coleta
	* image
	* nome
	* email
	* whasapp
	* latitude
	* longitude
	* city
	* uf
* items - items para coleta
	* titulo
	* image
* point-items (relacionamento dos items que um ponto coleta)
	* point_id
	* item_id
* muitos para muitos - n:n - tabela pivot


**criação das tabelas - com migrations do knex**
migrations - historico do banco de dados

para fazer as migracoes:
npx knex migrate:latest --knexfile knexfile.ts migrate:latest
 

no packege.json:
 "knex:migrate": "knex migrate:latest --knexfile knexfile.ts migrate:latest"

**aqui tabelas criadas e rodando**


funcionalidade:
* cadastro de ponto de coleta
* lista os itens de coleta
* listar pontos (filtro por estado, cidade e itens)
* lista ponto de coleta específico

CRIAÇAO: 
seed




