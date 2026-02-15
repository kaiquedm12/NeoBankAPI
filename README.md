# 🏦 NeoBank Core API

Backend de um banco digital simplificado desenvolvido com Java + Spring Boot, focado em boas práticas, arquitetura em camadas, transações financeiras seguras e testes automatizados.

## 📌 Sobre o Projeto

O NeoBank Core API simula o núcleo de um banco digital, permitindo:

- Cadastro de usuários
- Gestão de contas bancárias
- Depósitos e saques
- Transferências entre contas
- Registro de histórico de transações
- Validações financeiras
- Controle transacional

O projeto foi desenvolvido com foco em:

- Arquitetura limpa
- Boas práticas REST
- Consistência transacional
- Testes automatizados
- Escalabilidade futura

## 🏗️ Arquitetura

Arquitetura baseada em camadas:

```
Controller → Service → Repository → Database
```

**🔹 Controller**
- Responsável por expor os endpoints REST.

**🔹 Service**
- Contém regras de negócio e controle transacional.

**🔹 Repository**
- Comunicação com o banco via Spring Data JPA.

**🔹 Model**
- Entidades mapeadas com JPA.

## 🚀 Tecnologias Utilizadas

| Tecnologia | Finalidade |
|---|---|
| Java 21+ | Linguagem principal |
| Spring Boot | Framework backend |
| Spring Web | APIs REST |
| Spring Data JPA | Persistência |
| PostgreSQL | Banco de dados |
| Hibernate | ORM |
| JUnit 5 | Testes |
| Mockito | Mock de dependências |
| Flyway | Versionamento de banco |
| Docker | Containerização |

## 📂 Estrutura do Projeto

```
bank-api/
 ├── controller/
 │     ├── UserController.java
 │     ├── AccountController.java
 │     └── TransferController.java
 │
 ├── service/
 │     ├── UserService.java
 │     ├── AccountService.java
 │     └── TransferService.java
 │
 ├── repository/
 │     ├── UserRepository.java
 │     ├── AccountRepository.java
 │     └── TransactionRepository.java
 │
 ├── model/
 │     ├── User.java
 │     ├── Account.java
 │     └── Transaction.java
 │
 ├── dto/
 ├── exception/
 └── config/
```

## 👤 Funcionalidades

### 🔹 Usuários

- `POST /users` → Criar usuário
- `GET /users/{id}` → Buscar usuário
- `GET /users` → Listar usuários
- `PUT /users/{id}` → Atualizar usuário
- `DELETE /users/{id}` → Remover usuário

### 💰 Conta

- `POST /accounts` → Criar conta
- `GET /accounts/{id}` → Consultar saldo
- `POST /accounts/deposit` → Depositar
- `POST /accounts/withdraw` → Sacar

### 🔁 Transferências

- `POST /transfers`

**Exemplo Request**
```json
{
  "fromAccountId": "uuid",
  "toAccountId": "uuid",
  "amount": 200.00
}
```

## 🧠 Regras de Negócio

- ✔ Não permite saldo insuficiente
- ✔ Não permite valores <= 0
- ✔ Não permite transferência para mesma conta
- ✔ Operações financeiras são transacionais
- ✔ Histórico de todas as movimentações
- ✔ Validação de existência de conta

## 🔐 Segurança (Roadmap)

- Autenticação JWT
- Autorização por usuário
- Proteção contra acesso indevido a contas
- Logs de auditoria financeira

## 🧪 Testes Automatizados

O projeto possui:

- Testes unitários de Service
- Testes de validação de regras de negócio
- Testes de exceções
- Testes de transferência com sucesso
- Testes de saldo insuficiente

**Exemplo de Caso Testado**

- Transferência válida reduz saldo da conta origem
- Transferência inválida lança exceção
- Transação é revertida em caso de erro

## 🐳 Executando com Docker

```bash
docker-compose up -d
```

Inclui:

- API
- PostgreSQL

## 🗄️ Banco de Dados

Entidades principais:

**User**
- id
- name
- email

**Account**
- id
- user_id
- balance

**Transaction**
- id
- from_account
- to_account
- amount
- date

## 📈 Melhorias Futuras

- Integração com gateway de pagamento
- Cache com Redis
- Event-driven (Kafka)
- Rate limiting
- Observabilidade (Prometheus + Grafana)
- Deploy em Kubernetes

## 🎯 Objetivo do Projeto

Projeto criado para:

- Portfólio backend Java
- Demonstrar domínio de transações financeiras
- Praticar arquitetura escalável
- Simular ambiente real de banco digital

## 👨‍💻 Autor

**Kaique Demetrio**  
Desenvolvedor Backend | Java | Microsserviços | Arquitetura
