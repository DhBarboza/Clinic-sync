### Descrição

### Ferramentas:

- Drizzle (ORM)
- Next.js
- TypeScript
- Neon (Database - Postgress)
- Shadcn/ui
- Zod - Biblioteca de validação de schema

Pass:
1º Aula: A

### Timeline building

1. Gerar projeto:
   1. npx create-next-app@15.3.2
2. Instalar dependências:
   1. npm i -D prettier-plugin-tailwindcss@0.6.11
   2. npm i -D prettier@3.5.3
   3. npm i eslint-plugin-simple-import-sort@12.1.1
   4. npm i drizzle-orm pg dotenv & npm i -D drizzle-kit tsx @types/pg
   5. npm i pg@8.15.6
3. Configurar setup e bibliotecas:
   1. drizzle.config.ts
   2. eslint.config.mjs
   3. prettierrc.json
4. Configurar o banco de Dados:
   1. .env
   2. db/index.ts
   3. db/schema.ts
5. Executar script de criação do banco de dados (ORM):
   1. npm i drizzle-kit@0.31.1
   2. npx drizzle-kit push
   3. npx drizzle-kit studio
6. Configurar biblioteca de estilização UI:
   1. npx shadcn@2.5.0 init
7. Criar página de autenticação:
   1. authentication/page.tsx
   1. Instalação do component UI: npx shadcn@2.5.0 add tabs & npx shadcn@2.5.0 add card & npx shadcn@2.5.0 add input label form
