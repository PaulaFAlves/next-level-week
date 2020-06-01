back end -> node-js - API RESTful
-> regras de negócio
-> conexão com banco de dados
-> envio de emails e conexão com serviços externos
-> autenticação e autorização de usuários
-> criptografia e segurança

padrão - MVC - model-view-controllers
view -> template engine - retornar html do backend 

estrutura REST 
-> /users - retorna apenas os dados do usuário, em json
[
{
 “nome”:”paula”,
 “email”:”paula@paula.com”node
}
]

front end -> reactJS
html  e CSS da listagem dos usuários


front end mobile -> react native

typeScript - javascript com a possibilidade de acrescentar tipagem


#backend:
server.ts
pacotes: express, typescript -D, @types/express -D (contem tipagem para express), ts-node -D(para rodar o servidor), ts-node-dev -D (tipo o nodemon)
tsc --init (para criar o tsconfig.ts - obrigatório)

#frontend:
npx create-react-app nome-do-app --template=typescript