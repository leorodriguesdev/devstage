# Projeto devstage

Este repositório contém tanto o frontend quanto o backend da aplicação. Abaixo, estão as instruções para configurar e rodar ambos os ambientes.

---

## Tecnologias Utilizadas

### Frontend
- [Next.js](https://nextjs.org/) (com Turbopack)
- [React](https://react.dev/)
- [Tailwind CSS](https://tailwindcss.com/)
- [React Hook Form](https://react-hook-form.com/)
- [Zod](https://zod.dev/)

### Backend
- [Fastify](https://www.fastify.io/)
- [Drizzle ORM](https://orm.drizzle.team/)
- [PostgreSQL](https://www.postgresql.org/)
- [ioredis](https://github.com/luin/ioredis)
- [Zod](https://zod.dev/)

---

## Configuração do Ambiente

### Requisitos
Antes de iniciar, certifique-se de ter instalado:
- [Node.js](https://nodejs.org/) (Recomendado: Versão 18+)
- [Docker](https://www.docker.com/)

### Clonando o Repositório
```bash
git clone https://github.com/leorodriguesdev/devstage.git
cd devstage
```

---

## Configuração do Frontend

1. Acesse a pasta do frontend:
```bash
cd frontend
```

2. Instale as dependências:
```bash
npm install
# ou
yarn install
```

3. Inicie o servidor de desenvolvimento:
```bash
npm run dev
# ou
yarn dev
```

O frontend estará rodando em `http://localhost:3000`.

---

## Configuração do Backend

1. Acesse a pasta do backend:
```bash
cd backend
```

2. Instale as dependências:
```bash
npm install
# ou
yarn install
```

3. Configure as variáveis de ambiente:
Crie um arquivo `.env` na raiz do backend e configure suas credenciais, por exemplo:
```env
# Server
PORT=3333

# Database
DATABASE_URL="postgresql://docker:docker@localhost:5432/connect"

# Redis
REDIS_URL="redis://localhost:6379"

# URLs
API_URL="http://localhost:3333"
WEB_URL="http://localhost:3000"
```

4. Inicie os containers do banco de dados (PostgreSQL e Redis) com Docker:
```bash
docker compose up -d
```

5. Execute as migrações do banco de dados:
```bash
npm run db:migrate
```

6. Inicie o servidor backend:
```bash
npm run dev
# ou
yarn dev
```

O backend estará rodando em `http://localhost:4000`.

---

## Scripts Disponíveis

### Frontend
| Comando          | Descrição |
|------------------|------------|
| `npm run dev`   | Inicia o servidor de desenvolvimento |
| `npm run build` | Compila a aplicação para produção |
| `npm run start` | Inicia o servidor em modo de produção |
| `npm run lint`  | Executa a verificação de lint |

### Backend
| Comando            | Descrição |
|--------------------|------------|
| `npm run dev`     | Inicia o servidor backend em modo de desenvolvimento |
| `npm run build`   | Compila o código para produção |
| `npm run start`   | Inicia o servidor em modo de produção |
| `npm run db:generate` | Gera a estrutura do banco de dados (Drizzle ORM) |
| `npm run db:migrate`  | Aplica as migrações no banco de dados |

---

## Estrutura do Projeto
```
/devstage
├── frontend/       # Código-fonte do frontend
│   ├── src/
│   ├── public/
│   ├── package.json
│   ├── next.config.js
│   └── ...
│
├── backend/        # Código-fonte do backend
│   ├── src/
│   ├── prisma/
│   ├── package.json
│   ├── .env.example
│   └── ...
│
├── docker-compose.yml # Configuração dos containers
└── README.md        # Documentação do projeto
```

---

## Contribuição
Se quiser contribuir com o projeto, siga estes passos:

1. Faça um fork do repositório
2. Crie um branch para sua feature (`git checkout -b minha-feature`)
3. Commit suas mudanças (`git commit -m 'Minha nova feature'`)
4. Faça o push para o branch (`git push origin minha-feature`)
5. Abra um Pull Request

---

## Licença
Este projeto está licenciado sob a licença MIT. Consulte o arquivo `LICENSE` para mais detalhes.

---

Se tiver dúvidas, sinta-se à vontade para abrir uma issue! 🚀

