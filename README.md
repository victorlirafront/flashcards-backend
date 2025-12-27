# Flashcards API - Backend

## 🚀 Tecnologias

- **Java 25**
- **Spring Boot 4.0.0**
- **Spring Security** - Autenticação e autorização
- **Spring Data JPA** - Persistência de dados
- **JWT (Auth0)** - Tokens de autenticação
- **Maven** - Gerenciamento de dependências

## 📁 Estrutura do Projeto

O projeto segue uma **organização por módulo/feature**, facilitando a escalabilidade:

```
src/
 └── main/
      ├── java/
      │    └── com/flashcards/
      │          ├── application/          # Camada de Aplicação
      │          │     ├── auth/          # Módulo de Autenticação
      │          │     │     ├── dto/     # Data Transfer Objects
      │          │     │     │     ├── LoginRequest.java
      │          │     │     │     ├── LoginResponse.java
      │          │     │     │     └── RegisterRequest.java
      │          │     │     ├── mapper/  # Mappers
      │          │     │     │     └── UserMapper.java
      │          │     │     └── usecases/ # Casos de Uso
      │          │     │           ├── LoginUseCase.java          # Interface
      │          │     │           ├── LoginUseCaseImpl.java     # Implementação
      │          │     │           ├── RegisterUserUseCase.java  # Interface
      │          │     │           └── RegisterUserUseCaseImpl.java
      │          │     └── flashcards/   # Módulo de Flashcards (futuro)
      │          │
      │          ├── domain/              # Camada de Domínio
      │          │     ├── auth/          # Subdomínio de Autenticação
      │          │     │     ├── entity/  # Entidades
      │          │     │     │     └── User.java
      │          │     │     ├── valueobject/ # Value Objects
      │          │     │     │     ├── Email.java
      │          │     │     │     └── Password.java
      │          │     │     ├── repository/ # Interfaces de Repositório
      │          │     │     │     └── UserRepository.java
      │          │     │     ├── port/    # Portas (Interfaces de Infraestrutura)
      │          │     │     │     ├── PasswordEncoder.java
      │          │     │     │     └── TokenProvider.java
      │          │     │     └── exception/ # Exceções de Domínio
      │          │     │           ├── InvalidEmailException.java
      │          │     │           ├── InvalidCredentialsException.java
      │          │     │           ├── UserAlreadyExistsException.java
      │          │     │           └── UserNotFoundException.java
      │          │     └── flashcards/    # Subdomínio de Flashcards (futuro)
      │          │
      │          ├── infrastructure/       # Camada de Infraestrutura
      │          │     ├── auth/          # Módulo de Autenticação
      │          │     │     ├── controller/ # Controllers REST
      │          │     │     │     └── AuthController.java
      │          │     │     ├── persistence/ # Persistência JPA
      │          │     │     │     └── jpa/
      │          │     │     │           ├── entity/
      │          │     │     │           │     └── UserEntity.java
      │          │     │     │           ├── repository/
      │          │     │     │           │     └── JpaUserRepository.java
      │          │     │     │           ├── mapper/
      │          │     │     │           │     └── UserEntityMapper.java
      │          │     │     │           └── adapter/
      │          │     │     │                 └── UserRepositoryAdapter.java
      │          │     │     ├── security/ # Segurança
      │          │     │     │     ├── JwtTokenProvider.java
      │          │     │     │     ├── JwtTokenProviderAdapter.java
      │          │     │     │     ├── JwtAuthenticationFilter.java
      │          │     │     │     └── SpringPasswordEncoderAdapter.java
      │          │     │     └── config/  # Configurações do módulo
      │          │     │           └── AuthUseCaseConfig.java
      │          │     ├── config/        # Configurações globais
      │          │     │     ├── SecurityConfig.java
      │          │     │     └── CorsConfig.java
      │          │     └── exception/     # Exception Handlers
      │          │           └── GlobalExceptionHandler.java
      │          │
      │          └── FlashcardsApplication.java
      │
      └── resources/
            └── application.properties
```

## 🚀 Como Executar

### Pré-requisitos

- Java 25
- Maven 3.6+ (ou use o Maven Wrapper incluído)

### Executar a aplicação

```bash
# Usando Maven Wrapper
./mvnw spring-boot:run

# Ou usando Maven instalado
mvn spring-boot:run
```
