# API-CRUD-POSTGRESQL
API utilizando Golang e PostgreSQL com Docker




Para subir uma imagem de postgres:
docker run  -d --name api-todo -p 5432:5432 -e POSTGRES_PASSWORD=1234 postgres:13.5

Para conectar no postgres:
docker exec -it api-todo psql -U postgres

Para criar o BD no postgres:
create database api_todo;

Para criar o usuario no postgres:
create user user_todo;

Para alterar a senha o usuario:
alter user user_todo with encrypted password '1122';

Para dar permissão do usuario usar a tabela:
grant all privileges on database api_todo to user_todo;

Para conectar ao database:
\c api_todo;

Para criar tabela no database:
create table todos (id serial primary key, title varchar, description varchar, done bool);

Permissão geral:
grant all privileges on all tables in schema public to user_todo;
grant all privileges on all sequences in schema public to user_todo;







Exemplo de post no postman:
Usando POST- http://localhost:9000/
Body -
{
    "title": "meu primeiro TODO",
    "description": "aqui vai a descrição...",
    "done": false
}

Retorno:
{
    "Error": false,
    "Message": "Todo inserido com sucesso! ID: 1"
}


