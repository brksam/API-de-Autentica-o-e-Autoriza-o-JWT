# 🔐 API de Autenticação e Autorização com JWT

Este projeto é uma API REST desenvolvida em **Java 21 com Spring Boot 3.5.3**, que implementa autenticação e autorização de usuários via **JWT (JSON Web Token)**.  
A API permite o cadastro de usuários, login e controle de acesso a endpoints protegidos, validando tokens JWT.

---

## 📂 Estrutura do Projeto

- `src/main/java`
  - **Entidades:** classes de modelo
  - **Repositórios:** interfaces JPA para acesso ao banco
  - **Serviços:** regras de negócio
  - **Controladores:** endpoints REST
  - **Configurações:** segurança, CORS, JWT, etc.

- `src/main/resources`
  - `application.yml` → configurações da aplicação (porta, banco, JWT secret)
  
- `src/test/java`
  - Testes unitários e de integração com **JUnit** e **Spring Security Test**

- `tests/load-test.jmx`
  - Plano de carga configurado para o **JMeter**

- `pom.xml`
  - Dependências e configurações do projeto Maven

---

## 🛠️ Tecnologias Utilizadas

- Java 21
- Spring Boot 3.5.3
- Spring Security
- JWT (com Auth0)
- H2 Database
- Spring Data JPA
- SpringDoc OpenAPI (Swagger)
- JUnit 5
- Apache JMeter
- Lombok
- Maven

---

## 📥 Como Clonar e Executar o Projeto

### 📌 Clonando o repositório:

```
git clone https://github.com/brksam/API-de-Autentica-o-e-Autoriza-o-JWT.git
cd API-de-Autentica-o-e-Autoriza-o-JWT
```
### 📌 Executando a aplicação:
```
./mvnw spring-boot:run
```
A aplicação estará disponível em:
http://localhost:8080

### 📑 Documentação Swagger

Acesse a documentação interativa após iniciar o projeto:
http://localhost:8080/swagger-ui/index.html

### 🛢️ Console H2 Database:
Acesse em:

http://localhost:8080/h2-console

Configurações:
 - JDBC URL: jdbc:h2:mem:testdb
 - Username: sa
 - Password: (deixe vazio ou ajuste no application.yml)

### 📖 Endpoints Principais
| Método | Endpoint             | Descrição                           | Autenticação |
| :----- | :------------------- | :---------------------------------- | :----------- |
| `POST` | `/api/auth/register` | Cadastro de novo usuário            | ❌            |
| `POST` | `/api/auth/login`    | Login e geração do JWT              | ❌            |
| `GET`  | `/api/users`         | Listar usuários (exemplo protegido) | ✅            |

### 📌 JMX
O arquivo está em projeto-api
### 📦 Exemplos de Payload
```
{
  "username": "admin",
  "password": "123456"
}
```
### 📌 Login
```
{
  "username": "admin",
  "password": "123456"
}
```
Resposta:
```
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6..."
}
```
### 🔐 Utilização do Token JWT
Para acessar endpoints protegidos, envie o token no header Authorization da requisição:
```
Authorization: Bearer <seu_token_jwt>
```
Exemplo:
```
curl -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6..." http://localhost:8080/api/users
```
### 🧪 Executar os Testes
📌 Testes Unitários e de Integração:
```
./mvnw test
```
### 📊 Testes de Carga com JMeter
📌 Como rodar:
 - Instale o Apache JMeter.
 - No repositório do projeto, navegue até a pasta:
   ```
   projeto-api/jmeter-tests/
   ```
 - Abra o arquivo login_stress_test.jmx no JMeter.
 - Configure a URL de destino (se necessário).
 - Execute o plano de teste.
### 📸 Evidência de Teste de Carga (JMeter)
Abaixo, uma evidência visual da execução bem-sucedida do teste de carga usando o Apache JMeter.
Todos os requests foram processados com sucesso (código 200) durante o teste com múltiplos usuários simultâneos.

![TESTES](teste_print.jpg)

### 📌 Observações:
 - O projeto está preparado para ambiente de desenvolvimento, com banco H2 em memória.
 - Autenticação via JWT implementada com a biblioteca java-jwt.
 - Configuração de segurança via Spring Security e filtros JWT customizados.
 - Documentação automatizada com SpringDoc OpenAPI.
 - Hot reload habilitado via Spring Boot DevTools.
