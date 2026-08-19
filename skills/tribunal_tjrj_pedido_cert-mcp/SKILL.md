---
name: tribunal_tjrj_pedido_cert-mcp
description: Skill da REST API do Tribunal TJRJ: Cadastro de Pedido de Certidão na MCP.AI: 1 endpoint em /api/tribunal_tjrj_pedido_cert. Tribunal TJRJ: Cadastro de Pedido de Certidão, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Tribunal TJRJ: Cadastro de Pedido de Certidão — REST API skill

Você tem acesso à **Tribunal TJRJ: Cadastro de Pedido de Certidão** REST API na MCP.AI.

> Tribunal TJRJ: Cadastro de Pedido de Certidão, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/tribunal_tjrj_pedido_cert
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/tribunal_tjrj_pedido_cert/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"nome":"...","email":"...","tipo_certidao":"...","comarca":"...","finalidade":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/tribunal_tjrj_pedido_cert/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `tribunal_tjrj_pedido_cert_consultar`

Tribunal TJRJ: Cadastro de Pedido de Certidão, consulta em fonte oficial. _(POST /api/tribunal_tjrj_pedido_cert/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `nome` | string | Sim | Parâmetro de consulta "nome". |
| `cpf` | string | Não | Parâmetro de consulta "cpf". |
| `cnpj` | string | Não | Parâmetro de consulta "cnpj". |
| `email` | string | Sim | Parâmetro de consulta "email". |
| `tipo_certidao` | string | Sim | Parâmetro de consulta "tipo_certidao". |
| `comarca` | string | Sim | Parâmetro de consulta "comarca". |
| `finalidade` | string | Sim | Parâmetro de consulta "finalidade". |
| `inscricao_imovel` | string | Não | Parâmetro de consulta "inscricao_imovel". |
| `endereco` | string | Não | Parâmetro de consulta "endereco". |
| `numero_endereco` | string | Não | Parâmetro de consulta "numero_endereco". |
| `complemento_endereco` | string | Não | Parâmetro de consulta "complemento_endereco". |
| `bairro` | string | Não | Parâmetro de consulta "bairro". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_tribunal_tjrj_pedido_cert` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
