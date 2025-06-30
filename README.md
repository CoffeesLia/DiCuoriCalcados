# DiCuoriCalcados

Claro! Aqui está um **modelo de documentação técnica** para o back-end do site de **loja de sapatos** desenvolvido em **C# com ASP.NET Core**. Essa documentação pode ser incluída em um arquivo `README.md` (caso esteja no GitHub) ou em um documento interno da equipe.

---

# 📄 Documentação da API – Loja de Sapatos 👟

## 📌 Visão Geral

Esta API foi desenvolvida em **ASP.NET Core Web API** com o objetivo de gerenciar os dados de uma loja virtual de sapatos. A aplicação permite o controle de produtos, usuários, pedidos, e integrações com pagamentos.

---

## ⚙️ Tecnologias Utilizadas

* **Linguagem:** C# (.NET 6/7)
* **Framework:** ASP.NET Core Web API
* **ORM:** Entity Framework Core
* **Banco de Dados:** SQL Server (ou SQLite)
* **API Test:** Swagger / Postman
* **Autenticação:** JWT (opcional)

---

## 📁 Estrutura do Projeto

```
LojaDeSapatos.API/
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
└── Startup.cs (caso use .NET 5 ou anterior)
```

---

## 🧱 Entidades (Models)

### 📦 Produto

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

### 🔍 Produtos

| Método | Endpoint             | Descrição                       |
| ------ | -------------------- | ------------------------------- |
| GET    | `/api/produtos`      | Lista todos os produtos         |
| GET    | `/api/produtos/{id}` | Retorna um produto específico   |
| POST   | `/api/produtos`      | Cria um novo produto            |
| PUT    | `/api/produtos/{id}` | Atualiza os dados de um produto |
| DELETE | `/api/produtos/{id}` | Remove um produto               |

---

## 🔐 Autenticação (se aplicável)

**JWT (JSON Web Token)** pode ser utilizado para proteger endpoints sensíveis (como `/pedidos`, `/usuarios`, etc).

---

## 🛠️ Configuração e Execução

### 1. Clonar o Projeto

```bash
git clone https://github.com/usuario/LojaDeSapatos.API.git
cd LojaDeSapatos.API
```

### 2. Instalar Dependências

```bash
dotnet restore
```

### 3. Configurar o Banco de Dados

No `appsettings.json`:

```json
"ConnectionStrings": {
  "DefaultConnection": "Server=(localdb)\\mssqllocaldb;Database=LojaDeSapatosDB;Trusted_Connection=True;"
}
```

### 4. Aplicar Migrações

```bash
dotnet ef migrations add InitialCreate
dotnet ef database update
```

### 5. Rodar o Projeto

```bash
dotnet run
```

Acesse o Swagger em:

```
https://localhost:5001/swagger
```

---

## ✅ Testes

Recomenda-se testar os endpoints com:

* **Swagger UI** (já embutido)
* **Postman** (coleções podem ser criadas para facilitar)

---

## 📈 Funcionalidades Futuras

* Autenticação e autorização com JWT
* CRUD de usuários
* Integração com gateways de pagamento (ex: Stripe, PagSeguro)
* Carrinho de compras
* Upload de imagens
* Painel administrativo

---

## 📬 Contato

* Desenvolvedor: Seu Nome
* E-mail: [seu@email.com](mailto:seu@email.com)
* GitHub: [@seuusuario](https://github.com/seuusuario)

---
