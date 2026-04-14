# staffpro

## API

### URL base

A API foi padronizada com URL base por ambiente via variáveis de ambiente:

- `API_BASE_URL_DEV=https://dev.api.staffpro.local/v1`
- `API_BASE_URL_STAGING=https://staging.api.staffpro.local/v1`
- `API_BASE_URL_PROD=https://api.staffpro.com/v1`

Use `API_ENV` para selecionar o ambiente ativo (`dev`, `staging`, `prod`).

### Autenticação

O padrão de autenticação é **Bearer Token** no header `Authorization`:

```http
Authorization: Bearer <token>
```

Variáveis utilizadas:

- `API_AUTH_TYPE=bearer`
- `API_BEARER_TOKEN=<seu_token>`

### Exemplo de chamada

```bash
curl "$API_BASE_URL_PROD/users/me" \
  -H "Authorization: Bearer $API_BEARER_TOKEN" \
  -H "Content-Type: application/json"
```

## Configuração rápida

1. Copie `.env.example` para `.env`.
2. Preencha `API_BEARER_TOKEN` com o token válido.
3. Ajuste `API_ENV` e as URLs conforme sua infraestrutura.
