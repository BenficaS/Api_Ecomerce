<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>API E-commerce</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            background-color: #f0f0f0;
            margin: 0;
            padding: 20px;
        }
        .container {
            max-width: 800px;
            margin: auto;
            background: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
        h1 {
            text-align: center;
            color: #35495e;
        }
        h2 {
            color: #3eaf7c;
        }
        p {
            margin-bottom: 1.2em;
        }
        pre {
            background-color: #f8f9fa;
            padding: 10px;
            border-radius: 5px;
            overflow-x: auto;
        }
        img {
            display: block;
            max-width: 100%;
            margin: 20px auto;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
            border-radius: 8px;
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>API E-commerce</h1>
            <p>Este projeto implementa uma API para um sistema de e-commerce utilizando Spring Boot e Spring Security. Inclui funcionalidades de autenticação com JWT, controle de acesso baseado em papéis e operações básicas para entidades de usuário.</p>
        </header>

        <section>
            <h2>Funcionalidades Principais</h2>
            <ul>
                <li>Autenticação de usuários utilizando JSON Web Token (JWT).</li>
                <li>Controle de acesso baseado em papéis (roles) para diferentes partes da API.</li>
                <li>Operações CRUD básicas para entidades de usuário.</li>
            </ul>
        </section>

        <section>
            <h2>Tecnologias Utilizadas</h2>
            <ul>
                <li>Java 11</li>
                <li>Spring Boot</li>
                <li>Spring Security</li>
                <li>JWT (JSON Web Token)</li>
                <li>Maven (para gerenciamento de dependências)</li>
                <li>PostgreSQL (como banco de dados)</li>
                <li>Postman (para testar endpoints)</li>
            </ul>
        </section>

        <section>
            <h2>Pré-requisitos</h2>
            <ul>
                <li>Java JDK 11 ou superior instalado</li>
                <li>Maven 3.6.x ou superior instalado</li>
                <li>PostgreSQL 10 ou superior instalado e configurado</li>
            </ul>
        </section>

        <section>
            <h2>Configuração do Banco de Dados</h2>
            <p>Criar um banco de dados PostgreSQL:</p>
            <pre>
CREATE DATABASE api_ecommerce;
            </pre>
            <p>Configurar as credenciais no arquivo <code>application.properties</code>:</p>
            <pre>
spring.datasource.url=jdbc:postgresql://localhost:5432/api_ecommerce
spring.datasource.username=seu_usuario
spring.datasource.password=sua_senha
spring.datasource.driver-class-name=org.postgresql.Driver
spring.jpa.database-platform=org.hibernate.dialect.PostgreSQLDialect
spring.jpa.hibernate.ddl-auto=update
            </pre>
        </section>

        <section>
            <h2>Executando a Aplicação</h2>
            <ol>
                <li>Clonar o repositório:</li>
                <pre>
git clone https://github.com/seu-usuario/api-ecommerce.git
                </pre>
                <li>Compilar e executar o projeto:</li>
                <pre>
cd api-ecommerce
mvn clean package
java -jar target/api-ecommerce-0.0.1-SNAPSHOT.jar
                </pre>
                <li>Acessar a API:</li>
                <p>Acesse a API através do navegador ou utilizando ferramentas como Postman:</p>
                <pre>
http://localhost:8080
                </pre>
            </ol>
        </section>

        <section>
            <h2>Estrutura do Projeto</h2>
            <p>A estrutura do projeto segue os padrões recomendados pelo Spring Boot:</p>
            <pre>
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
            </pre>
        </section>

        <section>
            <h2>Diagrama UML da Arquitetura</h2>
            <p>O diagrama abaixo representa a arquitetura geral da aplicação:</p>
            <img src="uml_diagram.png" alt="Diagrama UML da Arquitetura">
            <p>Detalhes dos Componentes:</p>
            <ul>
                <li><strong>Controller:</strong> Responsável por receber as requisições HTTP, processá-las e devolver as respostas apropriadas.</li>
                <li><strong>Service:</strong> Implementa a lógica de negócio da aplicação, interagindo com os repositórios para acessar os dados.</li>
                <li><strong>Repository:</strong> Camada de acesso aos dados, realiza operações de leitura e escrita no banco de dados.</li>
                <li><strong>Security Config:</strong> Configurações de segurança da aplicação, como autenticação e controle de acesso.</li>
                <li><strong>Model:</strong> Representa as entidades de negócio da aplicação, mapeadas para as tabelas do banco de dados.</li>
            </ul>
        </section>

        <footer>
            <p>Contribuições são bem-vindas! Sinta-se à vontade para abrir uma issue ou enviar um pull request com melhorias.</p>
        </footer>
    </div>
</body>
</html>
