# 💈 FSW Barber

Aplicação web para encontrar barbearias e agendar serviços online.

🔗 **Demo:** https://fsw-barber-pedro.vercel.app

## Funcionalidades

- Listagem de barbearias recomendadas e populares
- Busca de barbearias por nome e por tipo de serviço (cabelo, barba, sobrancelha...)
- Página de detalhes da barbearia com serviços, preços e contatos
- Login com conta Google
- Agendamento de serviços com escolha de data e horário (horários ocupados ficam indisponíveis)
- Página "Meus agendamentos" com agendamentos confirmados e finalizados
- Cancelamento de agendamentos
- Layout responsivo (mobile-first)

## Tecnologias

- [Next.js 14](https://nextjs.org/) (App Router, Server Components e Server Actions)
- [TypeScript](https://www.typescriptlang.org/)
- [Prisma ORM](https://www.prisma.io/) + [PostgreSQL](https://www.postgresql.org/) ([Neon](https://neon.tech/))
- [NextAuth.js](https://next-auth.js.org/) (autenticação com Google OAuth)
- [Tailwind CSS](https://tailwindcss.com/) + [shadcn/ui](https://ui.shadcn.com/)
- React Hook Form + Zod, date-fns
- ESLint, Prettier, Husky e lint-staged
- Deploy na [Vercel](https://vercel.com/)

## Como rodar localmente

Pré-requisitos: Node.js 18+ e um banco PostgreSQL (local via `docker compose up -d` ou na nuvem, ex.: Neon).

```bash
# 1. Instalar dependências
npm install

# 2. Configurar variáveis de ambiente
cp .env.example .env
# preencha DATABASE_URL, DIRECT_URL, NEXT_AUTH_SECRET e as credenciais do Google

# 3. Criar as tabelas e popular o banco com dados de exemplo
npx prisma migrate deploy
npx prisma db seed

# 4. Iniciar o servidor de desenvolvimento
npm run dev
```

Acesse http://localhost:3000.

### Google OAuth

No [Google Cloud Console](https://console.cloud.google.com), crie um ID do cliente OAuth (Aplicativo da Web) e adicione os URIs de redirecionamento:

- `http://localhost:3000/api/auth/callback/google`
- `https://SEU-DOMINIO/api/auth/callback/google`

## Créditos

Projeto desenvolvido a partir da Full Stack Week, do [Full Stack Club](https://www.fullstackclub.com.br/).
