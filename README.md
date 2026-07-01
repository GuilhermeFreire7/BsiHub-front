# bsi.hub

Aplicação web para organização acadêmica de estudantes: gerenciamento de disciplinas/grade, quadro de tarefas estilo Kanban e autenticação de usuário.

## Tecnologias

- [React 18](https://react.dev/) + [TypeScript](https://www.typescriptlang.org/)
- [Vite](https://vitejs.dev/) — build e dev server
- [React Router](https://reactrouter.com/) — roteamento
- [TanStack Query](https://tanstack.com/query) — cache e sincronização de dados assíncronos
- [Axios](https://axios-http.com/) — cliente HTTP
- [Tailwind CSS](https://tailwindcss.com/) + [Radix UI](https://www.radix-ui.com/) — estilização e componentes acessíveis
- [React Hook Form](https://react-hook-form.com/) + [Zod](https://zod.dev/) — formulários e validação
- [dnd-kit](https://dndkit.com/) / [react-beautiful-dnd](https://github.com/atlassian/react-beautiful-dnd) — drag and drop do quadro Kanban
- [Sonner](https://sonner.emilkowal.ski/) — notificações (toasts)

## Pré-requisitos

- [Node.js](https://nodejs.org/) 18+
- [pnpm](https://pnpm.io/)

## Configuração

1. Instale as dependências:

   ```bash
   pnpm install
   ```

2. Crie um arquivo `.env` na raiz do projeto com a URL da API:

   ```env
   VITE_API_URL=http://localhost:3000
   ```

## Scripts disponíveis

```bash
pnpm dev       # inicia o servidor de desenvolvimento
pnpm build     # gera o build de produção (roda type-check antes)
pnpm lint      # executa o ESLint
pnpm preview   # serve o build de produção localmente
```

## Estrutura do projeto

```
src/
├── api/              # chamadas HTTP para a API (autenticação, disciplinas, tarefas...)
├── components/       # componentes reutilizáveis (UI, header, kanban, sessão etc.)
├── lib/               # configuração de axios e react-query
├── pages/
│   ├── _layouts/      # layouts de app e autenticação
│   ├── app/           # páginas autenticadas (home, disciplinas, grade, quadro de tarefas)
│   └── auth/          # páginas de login e cadastro
├── types/             # tipos compartilhados
├── routes.tsx         # definição das rotas
└── env.ts             # validação das variáveis de ambiente (Zod)
```

## Funcionalidades

- **Autenticação**: login e cadastro de estudantes, com rotas protegidas via `ProtectedRoute`.
- **Grade de disciplinas**: listagem, filtro e inclusão de disciplinas do aluno.
- **Quadro de tarefas (Kanban)**: organização de atividades por colunas com drag and drop.
- **Tema claro/escuro**: alternância de tema persistida em `localStorage`.
