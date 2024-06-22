<h1>Documentação da API E-commerce</H1>
<H2>Introdução
Este documento descreve a API de um sistema de e-commerce desenvolvido utilizando Spring Boot e Spring Security, que permite gerenciar usuários com diferentes papéis (ADMIN, GERENTE, VENDEDOR, CLIENTE) e implementa autenticação via tokens JWT (JSON Web Token).</H2>

<H1>Visão Geral da Estrutura
O projeto é estruturado em três principais pacotes:</H1>

<h4>h6com.example.Api_Ecomerce.application: Contém a classe principal ApiEcomerceApplication, responsável por inicializar a aplicação Spring Boot.
com.example.Api_Ecomerce.config: Configurações de segurança (SecurityConfig) e beans necessários para autenticação e autorização.
com.example.Api_Ecomerce.controller: Controladores REST que definem os endpoints da API e realizam a integração com o serviço (UserService).
com.example.Api_Ecomerce.model: Modelos de dados utilizados na aplicação, como UserEntity, que representa um usuário do sistema.
com.example.Api_Ecomerce.repository e com.example.Api_Ecomerce.security: Pacotes para futura expansão e melhor organização.
Funcionalidades Principais
Autenticação e Autorização

A autenticação é feita utilizando tokens JWT. O método generateToken da classe JwtUtil gera tokens com base no nome de usuário.
O método extractUsername da mesma classe decodifica e verifica o token JWT para extrair o nome de usuário.
Endpoints Principais

POST /login: Endpoint para autenticar usuários. Retorna um token JWT que deve ser utilizado para acessar outros endpoints.
GET /nomeusuario/{token}: Endpoint para extrair o nome de usuário a partir de um token JWT.
GET /gerente/{token} e /admin/{token}: Endpoints protegidos que requerem os papéis de GERENTE e ADMIN, respectivamente.
Segurança

Configurações de segurança (SecurityConfig) usando Spring Security para definir regras de autorização baseadas em papéis de usuário.
Senhas são codificadas utilizando BCryptPasswordEncoder antes de serem armazenadas nos detalhes do usuário.
Configuração e Uso
Execução: A aplicação é iniciada executando a classe ApiEcomerceApplication.
Autenticação: Para autenticar um usuário, deve-se enviar uma requisição POST para /login com um corpo contendo o nome de usuário e senha.
Autorização: Os endpoints estão protegidos com base nos papéis definidos (ADMIN, GERENTE, VENDEDOR, CLIENTE) utilizando a anotação @Secured.
Exemplo de Uso
Autenticação

POST /login
{
    "nome": "gabriel",
    "senha": "1"
}
Retorna um token JWT que deve ser utilizado para acessar outros endpoints.
Acesso a Recursos Protegidos
sql

GET /gerente/{token}
Authorization: Bearer <token_jwt>
Retorna informações específicas do usuário com o papel GERENTE.
</h4>
