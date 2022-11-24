Aplicação de cadastro de usuários
=================================
Esta aplicação foi criada com base no guia do prof. Eliel Cruz (https://www.youtube.com/watch?v=BSqtIw_hW8M)
Foi testada usando o XAMPP no Windows 10.
Ela usa HTML+CSS+JS(Bootstrap)+PHP  e o banco de dados roda em MySQL.

Depois que estava funcionando no servidor local, transformei em dois containers docker, criando as imagens e os containers separadamente.
Neste repositório, criei o docker-compose.yml, para gerar automaticamente os containers e executar a aplicação.
O IP do container do mysql está inserido no arquivo config.php, que fica no container da aplicação. Por este motivo, depois de rodar o comando:
> docker-compose up
>
É necessário rodar os comandos:
> docker network ls (para ver ID nome da rede default)
>
> docker network inspect iddarede (para ver o IP que foi atribuído ao container do mysql)
>
> docker container exec -ti IDdocontainerapp bash
>
Entrar no arquivo config.php e alterar o IP.

## Melhorias a fazer:
### No arquivo docker-compose.yml:
Criar uma rede e configurar os containers para utilizá-la.

### No container mysql:
Atribuir um nome ao banco de dados, pelo qual a aplicação possa referenciá-lo, ao invés de usar o IP.

### No container da aplicação:
No arquivo config.php, usar o nome do banco de dados, ao invés do IP.

## Para testar a aplicação, acessar este endereço no navegador local:
http://localhost:8081/

## As imagens utilizadas estão no meu repositório do docker hub (szalbuque).
### Veja o repositório: https://github.com/szalbuque/crud-php-sql
