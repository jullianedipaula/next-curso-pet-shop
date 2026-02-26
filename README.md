# Pet Shop Scheduling App

Um aplicativo moderno para gerenciamento de agendamentos de serviços de Pet Shop, desenvolvido com Next.js 15 e React 19.

## 🚀 Tecnologias

- **Framework:** [Next.js 15](https://nextjs.org/) (App Router)
- **Linguagem:** [TypeScript](https://www.typescriptlang.org/)
- **Estilização:** [Tailwind CSS](https://tailwindcss.com/)
- **Banco de Dados:** [PostgreSQL](https://www.postgresql.org/)
- **ORM:** [Prisma](https://www.prisma.io/)
- **Validação:** [Zod](https://zod.dev/) & [React Hook Form](https://react-hook-form.com/)
- **Componentes:** [Radix UI](https://www.radix-ui.com/) / [Shadcn UI](https://ui.shadcn.com/)
- **Ícones:** [Lucide React](https://lucide.dev/)
- **Containerização:** [Docker](https://www.docker.com/)

## 📋 Pré-requisitos

Antes de começar, certifique-se de ter instalado em sua máquina:

- [Node.js](https://nodejs.org/) (versão 20 ou superior)
- [Docker](https://www.docker.com/) & Docker Compose
- [pnpm](https://pnpm.io/) (recomendado) ou npm/yarn

## 🛠️ Como rodar o projeto

1. **Clone o repositório**

2. **Instale as dependências**

   ```bash
   pnpm install
   # ou
   npm install
   ```

3. **Configure as variáveis de ambiente**

   Crie um arquivo `.env` na raiz do projeto com a seguinte configuração (baseada no docker-compose):

   ```env
   DATABASE_URL="postgresql://docker:docker@localhost:5432/petshop?schema=public"
   ```

4. **Inicie o banco de dados**

   Suba o container do PostgreSQL utilizando o Docker:

   ```bash
   docker-compose up -d
   ```

5. **Execute as migrações do banco de dados**

   Aplique o schema do Prisma ao banco de dados:

   ```bash
   npx prisma migrate dev
   ```

6. **Inicie o servidor de desenvolvimento**

   ```bash
   pnpm dev
   # ou
   npm run dev
   ```

   O projeto estará rodando em [http://localhost:3000](http://localhost:3000).

## 🗄️ Estrutura do Banco de Dados

O projeto utiliza o Prisma com o seguinte modelo principal:

- **Appointment**:
  - `id`: Identificador único (CUID)
  - `tutorName`: Nome do tutor
  - `petName`: Nome do pet
  - `phone`: Telefone de contato
  - `description`: Descrição do serviço/observações
  - `scheduleAt`: Data e hora do agendamento

## 📝 Scripts Disponíveis

- `dev`: Inicia o servidor de desenvolvimento.
- `build`: Gera o cliente Prisma, aplica migrações e compila o projeto para produção.
- `start`: Inicia o servidor em modo de produção.
- `lint`: Executa o ESLint para verificação de código.
- `format`: Formata o código com Prettier.
- `validate:typecheck`: Verifica erros de tipagem TypeScript.
