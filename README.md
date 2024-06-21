%%{init: {'theme': 'base', 'themeVariables': { 'primaryColor': '#3eaf7c', 'secondaryColor': '#35495e', 'tertiaryColor': '#ffc107', 'primaryBorderColor': '#2b3a4e', 'noteBkColor': '#f0f0f0' }}}%%
flowchart TD

subgraph "ApiEcomerceApplication"["com.example.Api_Ecomerce.application.ApiEcomerceApplication"]
    classDef default fill:#35495e,stroke:#2b3a4e,stroke-width:2px;
    class default ApiEcomerceApplication;
    "main(String[] args)" --> "SpringApplication.run(ApiEcomerceApplication.class, args)";
end

subgraph "SecurityConfig"["com.example.Api_Ecomerce.config.SecurityConfig"]
    classDef default fill:#35495e,stroke:#2b3a4e,stroke-width:2px;
    class default SecurityConfig;
    "securityFilterChain(HttpSecurity http)" --> "httpBasic";
    "userDetailsService()" --> "InMemoryUserDetailsManager";
    "passwordEncoder()" --> "BCryptPasswordEncoder";
end

subgraph "UserController"["com.example.Api_Ecomerce.controller.UserController"]
    classDef default fill:#35495e,stroke:#2b3a4e,stroke-width:2px;
    class default UserController;
    "/login" --> "generateToken";
    "/nomeusuario/{token}" --> "extractUsername";
    "/gerente/{token}" --> "Secured(GERENTE)";
    "/admin/{token}" --> "Secured(ADMIN)";
end

subgraph "UserEntity"["com.example.Api_Ecomerce.model.UserEntity"]
    classDef default fill:#35495e,stroke:#2b3a4e,stroke-width:2px;
    class default UserEntity;
end

subgraph "UserService"["com.example.Api_Ecomerce.service.UserService"]
    classDef default fill:#35495e,stroke:#2b3a4e,stroke-width:2px;
    class default UserService;
end

subgraph "JwtUtil"["com.example.Api_Ecomerce.security.JwtUtil"]
    classDef default fill:#35495e,stroke:#2b3a4e,stroke-width:2px;
    class default JwtUtil;
    "generateToken" --> "Jwts.builder";
    "extractUsername" --> "Jwts.parser";
end

subgraph "UserRepository"["com.example.Api_Ecomerce.repository.UserRepository"]
    classDef default fill:#35495e,stroke:#2b3a4e,stroke-width:2px;
    class default UserRepository;
end
