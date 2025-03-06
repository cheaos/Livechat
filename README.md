# Projeto Spring Boot

Este é um projeto Spring Boot utilizando Java 17, Lombok, Flyway para migrações de banco de dados e Docker para containerização.

## Requisitos

- Java 17
- Docker
- Maven

## Configuração do Banco de Dados

O projeto utiliza PostgreSQL como banco de dados.

A configuração do banco de dados é feita no arquivo docker-compose`src/main/resources/application.properties`. Exemplo:
Docker-compose configurado
```properties
# Banco de Dados
spring.datasource.url=jdbc:postgresql://localhost:5432/fullstack
spring.datasource.username=postgres
spring.datasource.password=admin

# Configuração do Flyway
spring.flyway.enabled=true
spring.flyway.locations=classpath:db/migration

Migrações do Banco de Dados
As tabelas do banco já estão na pasta src/main/resources/db/migration:
V1__Cria_tabela_RbtUser.sql
V2__Cria_tabela_RbtUserMen.sql
O Flyway aplicará essas migrações automaticamente ao iniciar a aplicação.

Executando a Aplicação Backend
Para subir a aplicação backend, execute os seguintes comandos no terminal:
- mvn clean package
- docker build -t rbt-app .
- docker run -d -p 8081:8081 --name meu-app-container rbt-app
Observação: Se alterar a porta do backend, será necessário atualizar as requisições no frontend.
Ao fazer o login, utilize como o primeiro login usuário admin senha admin




**** TESTE ******

 **📌 Desafio Técnico – Desenvolvedor Full Stack**
 **Objetivo**
Criar um **chat em tempo real** com autenticação de usuários, listagem de usuários disponíveis e trocas de mensagens.

 📌 Como Participar
1. **Fork** este repositório para a sua conta do GitHub.
2. Desenvolva a solução no seu fork.
3. Após finalizar, **abra um Pull Request (PR)** para este repositório.
4. Aguarde o feedback da equipe.

 **🎯 Requisitos do Desafio**

 **1️⃣ Backend**
Criar uma **API REST + WebSockets** utilizando **C# (.NET)** ou **Java (Spring Boot)** com as seguintes funcionalidades:
- **Autenticação e Registro de Usuários**  
  - Criar um endpoint para **login** e outro para **cadastro de usuários**.  
  - Utilizar **JWT** para autenticação.  
- **Listagem de Usuários Online**  
  - Criar um endpoint que retorna os usuários conectados.  
- **Mensagens em Tempo Real**  
  - Implementar **WebSockets** para o envio e recebimento de mensagens.  
  - Criar um **histórico de mensagens** (armazenar em MongoDB ou outro banco de sua escolha).  

---

 **2️⃣ Frontend**
Criar uma **aplicação web** utilizando **Vue.js** com três telas:
- **Tela de Login**
  - Input de **usuário e senha**.
  - Botão para **cadastrar-se**.
- **Tela de Usuários Disponíveis**
  - Listagem dos usuários conectados.
  - Clique no usuário para iniciar um chat.
- **Tela de Conversa**
  - Exibir **histórico de mensagens**.
  - Permitir envio de mensagens em tempo real via **WebSockets**.

---

 **3️⃣ Docker**
Criar um **Dockerfile e um docker-compose.yml** para subir a aplicação de forma rápida.

- O **backend** deve rodar no **.NET Core** ou **Spring Boot**.
- O **frontend** deve rodar no Vue.js
- Banco de dados pode ser **MongoDB, PostgreSQL ou outro**.
- Criar um **arquivo README.md** com instruções para rodar o projeto.

---

 **🛠 Tecnologias Sugeridas**
 **Backend**
✅ **C# com .NET Core** (ou) **Java 17+ com Spring Boot**  
✅ **Autenticação com JWT**  
✅ **WebSockets para mensagens em tempo real**  
✅ **Banco de dados** (MongoDB, PostgreSQL, ou outro de sua escolha)  
✅ **Docker para containerização**

 **Frontend**
✅ **Vue.js**  
✅ **Consumo de APIs via Axios ou Fetch**  
✅ **Uso de WebSockets para chat em tempo real**  

---

 📌 O que será avaliado?**
✔ **Código bem estruturado e organizado**  
✔ **Boas práticas de desenvolvimento** (Clean Code, SOLID, etc.)  
✔ **Segurança na autenticação e API**  
✔ **Uso correto de WebSockets**  
✔ **Uso eficiente do banco de dados**  
✔ **Documentação clara para rodar a aplicação**  


---

 ** ⏳ Prazo **
-  **5** dias.
