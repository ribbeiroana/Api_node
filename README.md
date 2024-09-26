# API Node JS

Api de CRUD de Usuário.

## Tecnologias Utilizadas

- **Node.js**: Ambiente de execução JavaScript no lado do servidor.
- **Express**: Framework para construir APIs em Node.js.
- **MongoDB**: Banco de dados NoSQL para armazenar informações dos usuários.
- **Prisma**: ORM (Object-Relational Mapping) para facilitar a interação com o banco de dados.

## Instalação

### Pré-requisitos

- Node.js
- MongoDB
- Prisma CLI

### Passos para Configuração

1. **Clone o repositório**:
   ```bash
   git clone <url-do-repositorio>
   cd <nome-do-repositorio>

2. **Instale as dependências**:
     ```bash 
     npm install

3. **Crie o arquivo de configuração do Prisma: Crie um arquivo schema.prisma na pasta prisma com o seguinte conteúdo**: 
    ```bash
      generator client {
        provider = "prisma-client-js"
      }
      datasource db {
        provider = "mongodb"
        url      = env("DATABASE_URL")
      }
      model User {
        id    String @id @default(auto()) @map("_id") @db.ObjectId
        email String @unique
        name  String
        age   String
      }
### **Configure o Prisma**:

5. **Crie um arquivo .env na raiz do projeto com a seguinte variável:**
    ```bash 
    DATABASE_URL="mongodb://<usuario>:<senha>@localhost:27017/<nome-do-banco>"

6. **Execute as migrações (caso tenha definido esquemas no Prisma):**
    ```bash 
    npx prisma migrate dev --name init
7. **Inicie o servidor:**
    ```bash 
    npm start
O servidor estará disponível em http://localhost:3000.

 ## Endpoints da API
1. **Criar um Usuário
Método: POST
URL: /usuarios
Body (JSON):**
   ```bash 
   {
    "name": "Nome do Usuário",
    "email": "email@exemplo.com",
    "age": "30"
   }
2. **Listar Usuários
Método: GET
URL:**
   ```bash 
   /usuarios
3. **Atualizar um Usuário
Método: PUT
URL: / Body (JSON):**
   ```bash 
   /usuarios/:id
   {
    "name": "Nome Atualizado",
    "email": "emailatualizado@exemplo.com",
    "age": "31"
   }
4. **Deletar um Usuário
Método: DELETE
URL:**
   ```bash 
   /usuarios/:id
## Considerações Finais
A API é acessível em http://localhost:3000.
Para testes, você pode usar ferramentas como Postman ou Insomnia.
Certifique-se de ter o MongoDB em execução antes de iniciar a API.



 