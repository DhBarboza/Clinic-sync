### Descrição

Stop aula 2 15:09

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
2º Aula: 7

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
    3. Aprimorado pop-up de notificação: app/layout.tsx
    4. Aprimorando as páginas de autenticação: login-forms.tsx & sign-up-forms.tsx (components)
    5. Elaboração dá página do dashboard e adição de validação de sessão: app/dashboard/page.tsx
14. Implementação de Query´s do banco de dados:
    1. Modificação no arquivo "db/index.ts"
15. Criação da página de clinicas
    1. Instalação da dependêcia: npx shadcn@2.5.0 add dialog
    2. Criação do formulário de cadastro de clínica: app/clinic-form
16. Criação do "Server actions" (Rotas de API´s)
    1. criação da rota de "Criação de clinica"
17. Implementação da autenticação com o Google:
    1. Acessar: Google cloud platform - developer Console
    2. Criar projeto
    3. Acessar: API & Sevices > Credencials
    4. Configure consent screen > Get started
    5. Configurar o projeto
    6. Retornar: API & Sevices > Credencials => Create credentials > OAuth Client ID
    7. Application type: Web Application
    8. Authorized Redirec URI: https://localhost:3000/api/auth/callback/google
    9. Authorized JavaScript origins: https://localhost:3000
    10. Copiar "Client ID" E "Client Secret" gerado
    11. Configurar variavel de ambiente: .env
    12. Configurar arquivo de autenticação: lib/auth.ts
    13. Adicionar nas páginas de Login o component: authentication/components/login-form.tsx
18. Criação da Sidebar
    1. Instalação de dependêcia: npx shadcn@2.5.0 add sidebar
    2. Criação de pasta: src/app/(protected): Rotas aonde o usuário precisa estar logado para que possa acessar
    3. Mover as pastas de dashboard e clinic-form para (protected)
    4. Criar component App Sidebar: (protected)/\_components/app-sidebar.tsx
    5. configurar app-sidebar.tsx
    6. Adicionar dependencia: npx shadcn@2.5.0 add dropdown-menu
    7. Adicionar configuração de retorno de informações do usuário logado, como por exemplos as clinicas em que ele possui: lib/auth.ts & lib/auth-client.ts
    8. Criar componente personalizado que será utilziado em todas as páginas: components/ui/page-container.tsx
    9. Criar a página de médicos: (protected)/doctors/page.tsx
    10. Adicionar validação para averiguar se o usuário possuí clinica cadastrada: lib/auth.ts
    11. Criação do recurso de cadastro de médico:
        1. Adicionar dependencia: npx shadcn@2.5.0 add select
        2. Criação do componente: (protected)/doctors/\_components/add-doctor-button.tsx
        3. Criação do componente: (protected)/doctors/\_components/upsert-doctor-form.tsx
    12. Criado a pasta e arquivo de "(protected)/doctors/\_constants/index.ts", para adicionar as opções que serão consumidas no dropdown
    13. Adicionado dependencia que será responsável por formatar os valores monetários: npm i react-number-format@5.4.4
