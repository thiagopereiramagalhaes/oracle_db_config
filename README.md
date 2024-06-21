# Docker Compose para Oracle DB Express Edition (XE)

Para configurar o Oracle Database Express Edition (XE) usando Docker Compose, 
você precisa criar um arquivo docker-compose.yml que defina os parâmetros necessários para o container.

---

Explicação do arquivo docker-compose.yml:
* version: '3.7': Indica a versão do formato do Docker Compose que estamos utilizando.
* services: Define os serviços que compõem nossa aplicação.
* oracle-db: Nome do serviço que representa o Oracle Database.
* image: Especifica a imagem Docker a ser usada, neste caso, container-registry.oracle.com/database/express:latest.
* container_name: Define o nome do container como oracle-test.
* ports: Mapeia a porta 1521 do host para a porta 1521 do container, permitindo acesso ao banco de dados.
* environment: Define a variável de ambiente ORACLE_PWD com o valor welcome123, que é a senha para o usuário padrão do Oracle.
* stdin_open: true e tty: true: Estas configurações são usadas para manter o terminal aberto e interativo, características que podem ser úteis para interagir com o banco de dados durante o desenvolvimento ou testes.

---

```
docker login
docker pull container-registry.oracle.com/database/express:latest
docker-compose up -d
