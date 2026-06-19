# Pata Feliz — Banco JSON (API mockada)

API REST mockada com [JSON Server](https://github.com/typicode/json-server) que alimenta o
front-end **Pata Feliz** (sistema de agendamento de banho & tosa).

Segue o padrão do guia da disciplina: o servidor é iniciado por um arquivo **`index.js`**
que lê a porta de `process.env.PORT` (exigência do Render).

## Estrutura

```
pata-feliz-banco-json/
├── index.js          # sobe o JSON Server na porta do ambiente
├── db.json           # base de dados (na raiz)
├── package.json
└── node_modules/     # ignorado no Git
```

## Rodando localmente

```bash
npm install
npm start          # node index.js -> http://localhost:3000
# ou, com auto-reload ao editar o db.json:
npm run dev
```

## Endpoints

| Recurso            | Rota                | Descrição                                  |
| ------------------ | ------------------- | ------------------------------------------ |
| Portes             | `GET /portes`       | Lista de portes do pet (campo obrigatório) |
| Pelagens           | `GET /pelagens`     | Tipos de pelagem                           |
| Status do pedido   | `GET /status_pedido`| Status do agendamento                      |
| Adicionais         | `GET /adicionais`   | `servicos_extras` e `mimos`                |
| Catálogo           | `GET /catalogo`     | `servicos` oferecidos                      |
| Agendamentos       | `GET/POST/PATCH/DELETE /pedidos` | CRUD de agendamentos          |

## Deploy no Render (gratuito)

1. Suba esta pasta em um repositório próprio no GitHub (`pata-feliz-banco-json`).
2. No [Render](https://render.com): **New > Web Service** apontando para o repositório.
3. Configurações:
   - **Runtime:** Node
   - **Build Command:** `npm install`
   - **Start Command:** `npm start` (executa `node index.js`)
   - **Plan:** Free
   - O Render injeta a variável `PORT` automaticamente — o `index.js` já a utiliza.
4. Copie a URL gerada (ex.: `https://pata-feliz-api.onrender.com`) e coloque no
   `.env.production` do front-end (`VUE_APP_API_BASE_URL`).

> ⚠️ No plano gratuito o serviço "dorme" após ~15 min de inatividade; o primeiro acesso
> depois disso pode levar até ~50 segundos para responder.
