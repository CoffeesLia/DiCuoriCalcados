---

# 📄 Documentação Técnica – Backend C\#

## Projeto: **DiCuori – Loja de Sapatos**

---

## 🧾 Sumário

1. [Introdução](https://github.com/CoffeesLia/DiCuoriCalcados/blob/main/README.md#1-introdu%C3%A7%C3%A3o)
2. [Tecnologias Utilizadas](w)
3. [Arquitetura do Projeto](https://github.com/CoffeesLia/DiCuoriCalcados/tree/main?tab=readme-ov-file#3-arquitetura-do-projeto)
4. [Entidades e Relacionamentos](w)
5. [Endpoints da API](w)
6. [Validações e Regras de Negócio](w)
7. [Autenticação e Autorização](w)
8. [Padrões Adotados](w)
9. [Como Executar o Projeto](w)
10. [Testes](w)
11. [Futuras Melhorias](w)

---

## 1. Introdução

O sistema **DiCuori** é uma API REST desenvolvida em **C# (.NET 7)** com o objetivo de oferecer suporte a uma loja de sapatos, permitindo o gerenciamento de produtos, categorias, estoque, vendas e clientes.

---

## 2. Tecnologias Utilizadas

* [ASP.NET Core Web API](w)
* [Entity Framework Core](w)
* [SQL Server](w)
* [AutoMapper](w)
* [FluentValidation](w)
* [Swagger (Swashbuckle)](w)
* [JWT (JSON Web Token)](w)
* [xUnit](w) / [NUnit](w) para testes
* [Docker](w) (opcional)

---

## 3. Arquitetura do Projeto

A aplicação segue a arquitetura em **camadas**:

```
DiCuori/
│
├── DiCuori.API               # Camada de apresentação (controllers, configs)
├── DiCuori.Application       # Regras de negócio (services, DTOs, validações)
├── DiCuori.Domain            # Entidades e interfaces de domínio
├── DiCuori.Infra.Data        # Repositórios e DbContext
└── DiCuori.Tests             # Testes unitários e de integração
```

---

## 4. Entidades e Relacionamentos

### 4.1. Produto

* Id
* Nome
* Descrição
* Preço
* Tamanho
* CategoriaId *(FK)*
* Estoque

### 4.2. Categoria

* Id
* Nome

### 4.3. Cliente

* Id
* Nome
* Email
* CPF
* Endereço

### 4.4. Pedido

* Id
* ClienteId *(FK)*
* Data
* Total
* Lista de Produtos *(Relacionamento N\:N com Produto)*

---

## 5. Endpoints da API

Exemplo de rotas:

### Produto

| Método | Rota                 | Descrição                |
| ------ | -------------------- | ------------------------ |
| GET    | `/api/produtos`      | Listar todos os produtos |
| GET    | `/api/produtos/{id}` | Buscar por ID            |
| POST   | `/api/produtos`      | Criar novo produto       |
| PUT    | `/api/produtos/{id}` | Atualizar produto        |
| DELETE | `/api/produtos/{id}` | Deletar produto          |

### Cliente

| Método | Rota            | Descrição                |
| ------ | --------------- | ------------------------ |
| GET    | `/api/clientes` | Listar todos os clientes |
| POST   | `/api/clientes` | Criar cliente            |

### Autenticação

* `POST /api/auth/login`
* `POST /api/auth/register`

---

## 6. Validações e Regras de Negócio

* Nenhum produto pode ser criado com preço ≤ 0
* CPF de cliente deve ser único e válido
* Pedido deve conter pelo menos 1 produto
* Estoque é decrementado a cada venda

---

## 7. Autenticação e Autorização

* Login com **JWT**
* Roles: `Admin`, `Cliente`
* Proteção via `[Authorize]` nas rotas sensíveis (ex: criação de produto)

---

## 8. Padrões Adotados

* [RESTful](w) design
* [SOLID](w) principles
* Repository Pattern
* DTOs para entrada e saída de dados
* Logs com [Serilog](w)

---

## 9. Como Executar o Projeto

### Pré-requisitos

* .NET SDK 7+
* SQL Server LocalDB ou Docker
* Visual Studio / VS Code

### Comandos

```bash
# Restaurar pacotes
dotnet restore

# Aplicar migrations
dotnet ef database update

# Rodar a API
dotnet run --project DiCuori.API
```

Swagger disponível em: `https://localhost:5001/swagger`

---

## 10. Testes

* Camada de testes automatizados com **xUnit**
* Mock de dependências com **Moq**
* Testes de integração com banco de dados em memória

---

## 11. Futuras Melhorias

* Integração com métodos de pagamento (Pix, Cartão)
* Dashboard administrativo
* Recuperação de senha por e-mail
* Sistema de recomendação baseado em preferências
* Internacionalização

---
