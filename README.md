# 🏗️ BlocoZero - Backend Server

Este repositório contém o servidor (API RESTful) do **BlocoZero**, uma plataforma SaaS para gestão civil. O sistema gerencia empresas, obras, funcionários, estoques, cronogramas e relatórios de progresso, servindo como a inteligência por trás do frontend.

![Status](https://img.shields.io/badge/Status-Concluído-brightgreen?style=flat-square)
![NodeJS](https://img.shields.io/badge/Node.js-18.0+-339933?logo=node.js&style=flat-square)
![Express](https://img.shields.io/badge/Express.js-4.0+-000000?logo=express&style=flat-square)
![Prisma](https://img.shields.io/badge/Prisma-ORM-2D3748?logo=prisma&style=flat-square)
![Database](https://img.shields.io/badge/Database-SQL-4479A1?logo=postgresql&style=flat-square)

## 🚀 Funcionalidades da API

A API está organizada em módulos para atender aos diferentes aspectos da gestão de obras:

* **Autenticação & Usuários:** Login, cadastro e gestão de permissões (RBAC: Manager, Engineer, Tender, etc.).
* **Gestão de Obras:** Cadastro completo de obras, prazos e orçamentos.
* **Cronograma Físico:** Gerenciamento de Etapas (Stages) e Subetapas (Substages).
* **Relatórios de Progresso:**
    * Envio de relatórios com fotos (Upload via Multer).
    * Fluxo de revisão (Aprovação/Recusa) por gerentes.
* **Estoque:** Controle de entrada e saída de materiais (`types`, `categories`, `items`).
* **Financeiro:** Controle de orçamentos e custos de mão de obra.

## 🛠️ Tecnologias Utilizadas

* **Runtime:** [Node.js](https://nodejs.org/)
* **Framework Web:** [Express](https://expressjs.com/)
* **ORM:** [Prisma](https://www.prisma.io/)
* **Uploads:** [Multer](https://github.com/expressjs/multer) (Gerenciamento de arquivos/fotos)
* **Segurança:** JWT (JSON Web Tokens) e BCrypt (Hash de senhas).
* **Arquitetura:** MVC / Layered (Routes -> Controllers -> Services -> Models).

1.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/seu-usuario/BlocoZero-Frontend.git](https://github.com/Jorgeigor/BlocoZero-Server.git)
    cd BlocoZero-Server
    ```

2.  **Instale as dependências:**
    ```bash
    npm install
    # ou
    yarn install
    ```

3.  **Execute o projeto:**
    ```bash
    npm run dev
    ```
    O acesso geralmente será em `http://localhost:8080`.



## 📂 Estrutura de Pastas

```text
src/
├── controllers/     # Lógica de entrada/saída das requisições (req, res)
├── entitys/         # Classes/Entidades de negócio
├── generated/       # Arquivos gerados automaticamente (ex: Prisma Client)
├── middlewares/     # Validações (Auth, Uploads, Erros)
├── models/          # Interação direta com o banco de dados
├── routes/          # Definição dos endpoints da API
├── services/        # Regras de negócio complexas
└── server.js        # Ponto de entrada da aplicação
prisma/
└── schema.prisma    # Modelagem do banco de dados
uploads/             # Armazenamento local de imagens enviadas