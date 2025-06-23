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

```bash
git clone https://github.com/brksam/API-de-Autentica-o-e-Autoriza-o-JWT.git
cd API-de-Autentica-o-e-Autoriza-o-JWT
📌 Executando a aplicação:
bash
Copy
Edit
./mvnw spring-boot:run
A aplicação estará disponível em:
http://localhost:8080

📑 Documentação Swagger
Acesse a documentação interativa após iniciar o projeto:

http://localhost:8080/swagger-ui/index.html

🛢️ Console H2 Database
Acesse em:

http://localhost:8080/h2-console

Configurações:

JDBC URL: jdbc:h2:mem:testdb

Username: sa

Password: (deixe vazio ou ajuste no application.yml)

🧪 Executar os Testes
📌 Testes Unitários e de Integração:
bash
Copy
Edit
./mvnw test
📊 Testes de Carga com JMeter
📌 Como rodar:
Instale o Apache JMeter.

Abra o arquivo tests/load-test.jmx no JMeter.

Configure a URL de destino (se necessário).

Execute o plano de teste.

📌 Observações
O projeto está preparado para uso em ambiente de desenvolvimento, com banco em memória.

Autenticação via JWT é configurada através do pacote com.auth0:java-jwt.

Configuração de endpoints públicos e protegidos via Spring Security.

Documentação automatizada com SpringDoc OpenAPI.

Hot reload habilitado via Spring Boot DevTools.

