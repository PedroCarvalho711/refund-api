# Refund API

API REST desenvolvida em **Node.js + TypeScript** para gerenciamento de solicitações de reembolso (refunds), com autenticação via **JWT**, validação de dados e paginação de resultados.

Este projeto foi criado com foco em **boas práticas**, **organização de código** e **padrões utilizados no mercado**.

---

# Funcionalidades

- ✅ Autenticação de usuários com JWT
- ✅ Criação de solicitações de reembolso
- ✅ Listagem de reembolsos com paginação e filtro
- ✅ Busca de reembolso por ID
- ✅ Proteção de rotas com middleware de autenticação
- ✅ Validação de dados com Zod
- ✅ Integração com banco de dados via Prisma

---

# Arquitetura do Projeto

O projeto segue uma arquitetura organizada por responsabilidades:

src/
├── configs/ # Configurações (JWT, variáveis globais)
├── controllers/ # Regras de negócio
├── database/ # Conexão com o banco (Prisma Client)
├── middlewares/ # Middlewares (autenticação, etc.)
├── providers/ # Serviços externos
├── routes/ # Definição das rotas da API
├── types/ # Tipagens globais
├── utils/ # Utilitários e erros personalizados


---

# Tecnologias Utilizadas

- **Node.js**
- **TypeScript**
- **Express**
- **Prisma ORM**
- **Zod**
- **JWT (jsonwebtoken)**
- **SQLite / PostgreSQL** (via Prisma)
- **Multer** (upload de arquivos)

---

# Autenticação

A API utiliza **JWT (JSON Web Token)** para autenticação.

Para acessar rotas protegidas, é necessário enviar o token no header:

Authorization: Bearer SEU_TOKEN_AQUI


O middleware `ensureAuthenticated` valida o token e injeta as informações do usuário no objeto `request`.

---

# Rotas Principais

# Autenticação
| Método | Rota | Descrição |
|------|------|----------|
| POST | `/sessions` | Autentica o usuário |

###  Reembolsos
| Método | Rota | Descrição |
|------|------|----------|
| POST | `/refunds` | Cria um novo reembolso |
| GET | `/refunds` | Lista reembolsos com paginação |
| GET | `/refunds/:id` | Busca reembolso por ID |

---

##  Paginação

A listagem de reembolsos suporta paginação através de query params:

# Como Rodar o Projeto /  Pré-requisitos
 
Node.js (v18+)
npm ou yarn

# Instalação

# Clone o repositório
git clone https://github.com/seu-usuario/refund-api.git

# Entre no projeto
cd refund-api

# Instale as dependências
npm install

Variáveis de Ambiente
Crie um arquivo .env:

DATABASE_URL="file:./dev.db"
JWT_SECRET="sua_chave_secreta"

Banco de Dados
npx prisma migrate dev

Executar a API
npm run dev

Servidor disponível em:
http://localhost:3333

# Testes

As rotas podem ser testadas utilizando:

Postman
Insomnia

## Aprendizados

Este projeto reforça conceitos como:

Arquitetura em camadas
Autenticação com JWT
Middlewares no Express
Validação de dados
Paginação de resultados
Organização de projetos Node.js

Desenvolvido por Pedro Carvalho
📌 GitHub: https://github.com/seu-usuario






