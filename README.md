---

# 👟 DiCuori – API da Loja de Sapatos

## 📌 Visão Geral

**DiCuori** é uma API desenvolvida com **ASP.NET Core Web API** para servir como o back-end de uma loja virtual de sapatos. A API permite o gerenciamento de produtos, controle de estoque e poderá ser expandida com autenticação, carrinho de compras, pedidos e pagamentos.

---

## ⚙️ Tecnologias Utilizadas

* **Linguagem:** C# (.NET 6/7)
* **Framework:** ASP.NET Core Web API
* **ORM:** Entity Framework Core
* **Banco de Dados:** SQL Server (pode ser adaptado para SQLite ou PostgreSQL)
* **Ferramentas de Teste:** Swagger UI / Postman

---

## 📁 Estrutura do Projeto

```
DiCuori.API/
│
├── Controllers/
│   └── ProdutosController.cs
│
├── Models/
│   └── Produto.cs
│
├── Data/
│   └── LojaContext.cs
│
├── appsettings.json
├── Program.cs
└── DiCuori.API.csproj
```

---

## 🧱 Entidade: Produto

```csharp
public class Produto
{
    public int Id { get; set; }
    public string Nome { get; set; }
    public string Descricao { get; set; }
    public decimal Preco { get; set; }
    public int Estoque { get; set; }
    public string Tamanho { get; set; }
}
```

---

## 🔌 Endpoints da API

### 📦 Produtos

| Método | Endpoint             | Descrição                     |
| ------ | -------------------- | ----------------------------- |
| GET    | `/api/produtos`      | Lista todos os produtos       |
| GET    | `/api/produtos/{id}` | Retorna um produto pelo ID    |
| POST   | `/api/produtos`      | Cadastra um novo produto      |
| PUT    | `/api/produtos/{id}` | Atualiza um produto existente |
| DELETE | `/api/produtos/{id}` | Exclui um produto do catálogo |

---

## 🔐 Autenticação (futuramente)

A API poderá ser protegida com **JWT (JSON Web Token)** para proteger áreas como carrinho, pedidos e gerenciamento de usuários.

---

## 🛠️ Como Rodar o Projeto

### 1. Clonar o Repositório

```bash
git clone https://github.com/usuario/DiCuori.API.git
cd DiCuori.API
```

### 2. Restaurar Dependências

```bash
dotnet restore
```

### 3. Configurar o Banco de Dados

No arquivo `appsettings.json`:

```json
"ConnectionStrings": {
  "DefaultConnection": "Server=(localdb)\\mssqllocaldb;Database=DiCuoriDB;Trusted_Connection=True;"
}
```

### 4. Criar o Banco (via EF Core)

```bash
dotnet ef migrations add InitialCreate
dotnet ef database update
```

### 5. Executar a API

```bash
dotnet run
```

Acesse o Swagger em:

```
https://localhost:5001/swagger
```

---

## ✅ Testando a API

Utilize:

* **Swagger UI:** A interface automática para testar endpoints.
* **Postman:** Para simular chamadas REST, útil em desenvolvimento avançado.

---

## 📈 Funcionalidades Futuras

* 🔐 Autenticação e autorização com JWT
* 🛒 Carrinho de compras
* 💳 Integração com pagamentos (ex: Stripe, Mercado Pago)
* 👤 Cadastro e login de usuários
* 🖼️ Upload de imagens dos produtos
* 📊 Dashboard administrativo

---

## 📬 Contato

* Projeto: **DiCuori – Loja de Sapatos**
* Desenvolvedor: \[Seu Nome]
* E-mail: [seu@email.com](mailto:seu@email.com)
* GitHub: [@CoffeesLia](https://github.com/CoffeesLia)

---
