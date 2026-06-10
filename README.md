## ms-produtos

Microsserviço `ms-produtos` para Marketplace — API REST de produtos.

Como rodar localmente (com Docker):

1. Iniciar serviços:

```powershell
docker compose -f compose.yaml up --build -d
```

2. Verificar logs:

```powershell
docker compose -f compose.yaml logs -f ms-produtos
```

Endpoints principais:

- `POST /produtos` — criar produto
- `GET /produtos` — listar produtos
- `GET /produtos/{id}` — buscar por id
- `PUT /produtos/{id}` — atualizar produto
- `DELETE /produtos/{id}` — remover produto

Testes com a coleção Bruno:

Use a coleção dentro da pasta `bruno/` (suporta REST Client / Thunder Client / Insomnia).

Publicar no GitHub:

```bash
git init
git add .
git commit -m "Entrega: ms-produtos"
gh repo create <user>/ms-produtos --public --source=. --push
```

Build e publicar imagem Docker no Docker Hub:

```bash
# build local
docker build -t <dockerhub-username>/ms-produtos:latest .

# login
docker login

# push
docker push <dockerhub-username>/ms-produtos:latest
```

Observações:
- Configure `DB_URL`, `DB_USER`, `DB_PASSWORD` via variáveis de ambiente quando necessário.
- Se preferir `docker-compose` use `docker compose -f compose.yaml up --build`.
