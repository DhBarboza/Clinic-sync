### Descrição

Stop aula 2 59:18

### Ferramentas:

- Drizzle (ORM)
- Next.js
- TypeScript
- Neon (Database - Postgress)
- Shadcn/ui
- Zod - Biblioteca de validação de schema
- Better-Auth - Biblioteca de Autenticação

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
   2. Instalação do component UI: npx shadcn@2.5.0 add tabs & npx shadcn@2.5.0 add card & npx shadcn@2.5.0 add input label form
   3. Criação dos componentes: components/login-form.tsx && components/sign-up-form.tsx
8. Instalação da biblioteca de autenticação:
   1. npm i better-auth
9. Configuração de artefatos para autenticação:
   1. Definição de váriaveis de ambiente: .env
   2. Criação de instância: lib/auth.ts && lib/auth-client.ts
10. Conectar Autenticação (better-auth) com o banco de dados (drizzle):
    1. Instalar Dotenv: npm i dotenv@16.5.0
    2. Executar script de geração de schema: npx @better-auth/cli@latest generate
    3. Gerado automáticamente o schema de autenticação: auth-schema.ts
    4. Copiar o schema gerado do arquivo auth-schema.ts, para nosso arquivo padrão
    5. Abrir Drizzle Studio: npx drizzle-kit studio, limpar colunas já existentes
    6. Executar script de geração/atualização das tabelas: npx drizzle-kit push
    7. Excluir arquivo gerado: auth-schema.ts
11. Criação da página dashboard:
    1. app/dashboard
12. Criação do arquivo responsável pela comunicação e ação (GET, POST):
    1. api/auth/[...all]/route.ts
13. Criação de validações na página de autenticação:
    1. Instalar dependência: npx shadcn@2.5.0 add sonner
    2. Adicionado "Toaster" ao arquivo src/app/layout.tsx: para que todas as páginas consigam exibir o Pop-up de alerta instalado anteriormente
