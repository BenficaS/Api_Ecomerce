API E-commerce
Este projeto implementa uma API para um sistema de e-commerce utilizando Spring Boot e Spring Security. Ele inclui funcionalidades de autenticação com JWT, controle de acesso baseado em papéis e operações básicas para entidades de usuário.

Funcionalidades Principais
Autenticação de usuários utilizando JSON Web Token (JWT).
Controle de acesso baseado em papéis (roles) para diferentes partes da API.
Operações CRUD básicas para entidades de usuário.
Tecnologias Utilizadas
Java 11
Spring Boot
Spring Security
JWT (JSON Web Token)
Maven (para gerenciamento de dependências)
PostgreSQL (como banco de dados)
Postman (para testar endpoints)
Pré-requisitos
Java JDK 11 ou superior instalado
Maven 3.6.x ou superior instalado
PostgreSQL 10 ou superior instalado e configurado
Configuração do Banco de Dados
Criar um banco de dados PostgreSQL:

bash
Copiar código
CREATE DATABASE api_ecommerce;
Configurar as credenciais no arquivo application.properties:

properties
Copiar código
spring.datasource.url=jdbc:postgresql://localhost:5432/api_ecommerce
spring.datasource.username=seu_usuario
spring.datasource.password=sua_senha
spring.datasource.driver-class-name=org.postgresql.Driver
spring.jpa.database-platform=org.hibernate.dialect.PostgreSQLDialect
spring.jpa.hibernate.ddl-auto=update
Executando a Aplicação
Clonar o repositório:

bash
Copiar código
git clone https://github.com/seu-usuario/api-ecommerce.git
Compilar e executar o projeto:

bash
Copiar código
cd api-ecommerce
mvn clean package
java -jar target/api-ecommerce-0.0.1-SNAPSHOT.jar
Acessar a API:

Acesse a API através do navegador ou utilizando ferramentas como Postman:

arduino
Copiar código
http://localhost:8080
Estrutura do Projeto
A estrutura do projeto segue os padrões recomendados pelo Spring Boot:

css
Copiar código
api-ecommerce/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/
│   │   │       └── example/
│   │   │           └── Api_Ecomerce/
│   │   │               ├── application/
│   │   │               │   └── ApiEcomerceApplication.java
│   │   │               ├── config/
│   │   │               │   └── SecurityConfig.java
│   │   │               ├── controller/
│   │   │               │   └── UserController.java
│   │   │               ├── model/
│   │   │               │   └── UserEntity.java
│   │   │               ├── repository/
│   │   │               │   └── UserRepository.java
│   │   │               └── security/
│   │   │                   └── JwtUtil.java
│   │   └── resources/
│   │       └── application.properties
│   └── test/
├── target/
├── pom.xml
└── README.md
Diagrama UML da Arquitetura
O diagrama abaixo representa a arquitetura geral da aplicação:

lua
Copiar código
                        +---------------------+
                        |      Controller     |
                        +----------+----------+
                                   |
                                   |
                  +----------------+----------------+
                  |                                 |
                  |                                 |
     +------------+-------------+      +------------+------------+
     |       Service          |      |        Repository        |
     |                         |      |                           |
     +------------+------------+      +------------+--------------+
                  |                                 |
                  |                                 |
          +-------+-------+                 +-------+--------+
          |    Security   |                 |      Model      |
          |   Config      |                 |                   |
          +---------------+                 +-------------------+
Detalhes dos Componentes
Controller: Responsável por receber as requisições HTTP, processá-las e devolver as respostas apropriadas.
Service: Implementa a lógica de negócio da aplicação, interagindo com os repositórios para acessar os dados.
Repository: Camada de acesso aos dados, realiza operações de leitura e escrita no banco de dados.
Security Config: Configurações de segurança da aplicação, como autenticação e controle de acesso.
Model: Representa as entidades de negócio da aplicação, mapeadas para as tabelas do banco de dados.
