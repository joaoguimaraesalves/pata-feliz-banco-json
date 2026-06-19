# Pata Feliz — Banco JSON (API mockada)

API REST mockada com [JSON Server](https://github.com/typicode/json-server) que alimenta o front-end **Pata Feliz** (sistema de agendamento de banho & tosa).

## Rodando localmente

```bash
npm install
npm run dev     # sobe em http://localhost:3000
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

1. Suba esta pasta em um repositório próprio no GitHub (ex.: `pata-feliz-banco-json`).
2. No [Render](https://render.com), crie um **New > Web Service** apontando para o repositório.
3. Configurações:
   - **Build Command:** `npm install`
   - **Start Command:** `npm start`
   - O Render define a variável `PORT` automaticamente — o `start` já a utiliza.
4. Ao publicar, copie a URL gerada (ex.: `https://pata-feliz-api.onrender.com`) e coloque no
   arquivo `.env.production` do front-end (`VUE_APP_API_BASE_URL`).
