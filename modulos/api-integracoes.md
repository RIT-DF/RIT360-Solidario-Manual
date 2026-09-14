---
title: "API e integrações"
nav_order: 12
parent: "Módulos"
permalink: /modulos/api-integracoes/
task: modulo-api-integracoes
role: admin
routes: ["admin.php?page=rit360-solidario#/api"]
screenshots: [api-chaves]
source_docs: [PRODUCT.md, CHANGELOG.md]
last_verified: 2026-09-14
status: publicado
---

# API e integrações

A API do RIT360 Solidário permite **conectar o plugin a outros sistemas** — como o
**n8n** (automação de fluxos), planilhas, CRMs, ferramentas de e-mail marketing ou
qualquer aplicativo que fale HTTP. Com ela você pode, por exemplo, mandar cada nova
doação para uma planilha, avisar a equipe no chat quando bater a meta de uma campanha,
ou criar campanhas a partir de outro sistema.

Tudo é gerenciado em **RIT360 Solidário**, grupo **Configurações** na barra de
navegação, aba **API**.

> 💡 **Nota — para quem é esta página**
>
> Esta é uma referência técnica, voltada a quem vai montar uma integração (você ou a
> pessoa de tecnologia da sua OSC). Você **não precisa saber programar** para usar o
> n8n, mas vai lidar com endereços (URLs), chaves e alguns termos técnicos. Se for a
> primeira vez, comece pela seção [Como montar no n8n](#como-montar-no-n8n).

## Endereço base da API

Todas as chamadas partem do mesmo endereço, trocando `SEU-SITE` pelo domínio do seu
WordPress:

```
https://SEU-SITE/wp-json/rit360sol/v1
```

Por exemplo, para consultar os números agregados, o endereço completo é
`https://SEU-SITE/wp-json/rit360sol/v1/stats`.

---

## Chaves de integração

Nenhuma chamada à API funciona sem uma **chave de integração**. A chave identifica quem
está acessando e **o que essa integração pode fazer** (os escopos).

![Chaves de integração e webhooks na aba API](/assets/img/api-chaves.png)

### Criar uma chave

1. Entre em **RIT360 Solidário**, abra o grupo **Configurações** na barra e vá à aba **API**.
2. Em **Chaves de integração**, clique em **Nova chave**.
3. Dê um **nome** que ajude a lembrar para que serve (ex.: "n8n — planilha de doações").
4. Marque as **permissões (escopos)** que essa chave precisa — e **apenas** essas (veja
   a tabela de [escopos](#escopos) abaixo).
5. Defina a **validade** (data de expiração) ou deixe sem expiração, conforme sua
   política.
6. Clique em **Criar**.

> ⚠️ **Atenção — a chave aparece uma única vez**
>
> Logo após criar, o sistema mostra a chave completa **uma só vez**. Copie e guarde em
> local seguro **na hora** (no cofre de senhas da sua OSC, por exemplo). Depois que você
> sair da tela, não é possível ver a chave de novo — se perder, revogue e crie outra.

### Usar a chave (autenticação)

Em cada chamada, envie a chave no cabeçalho `Authorization`, no formato **Bearer**:

```
Authorization: Bearer SUA_CHAVE
```

### Revogar uma chave

Na mesma aba **API**, cada chave tem o botão **Revogar**. Ao revogar, ela para de
funcionar **na hora** — qualquer integração que a usava deixa de ter acesso. Revogue as
chaves que você não usa mais, ou qualquer chave que possa ter vazado.

Cada ação de chave (criar, revogar) mostra um **aviso de confirmação** assim que é
concluída.

### Estado da chave

Na lista, cada chave exibe um estado:

- **Ativa** — funcionando normalmente.
- **Expirada** — passou da data de validade e **não autentica mais**. A chave aparece
  marcada como *Expirada* (não some da lista) para você identificar e substituir: crie
  uma nova e atualize a integração que a usava.
- **Revogada** — desativada manualmente por você.

---

## Escopos

O escopo é a **permissão** de uma chave: define exatamente o que ela pode ler ou
escrever. Marque só o necessário — é o princípio do menor privilégio.

| Escopo | O que libera |
|---|---|
| `stats:read` | Ler **números agregados** (total arrecadado, nº de doações, doadores). Sem dados pessoais. |
| `donations:read` | Ler a lista de **doações** (valores, datas, projeto, status). |
| `donors:read` | Ler a lista de **doadores sem dados pessoais** (identificadores e números, sem nome/e-mail/documento). |
| `donors:read_pii` | Ler os **dados pessoais completos** dos doadores (nome, e-mail, documento). **Sensível.** |
| `campaigns:write` | **Criar e editar campanhas**. |
| `projects:write` | **Atualizar projetos** (meta, prazo, campanha). |
| `donations:write` | **Reservado** para registrar doações via API. Aparece na tela, mas ainda **não há endpoint público** para ele — deixe desmarcado até que uma integração de escrita de doações seja disponibilizada. |

> ⚠️ **Atenção — `donors:read_pii` é sensível e auditado**
>
> Esse escopo dá acesso a **dados pessoais** dos doadores. Todo acesso feito com ele é
> **registrado na trilha de Auditoria LGPD**. Só marque `donors:read_pii` quando a
> integração realmente precisar do nome/e-mail/documento; para a maioria dos fluxos, os
> escopos sem PII já bastam.

---

## Endpoints de leitura

Todas as leituras usam o método HTTP `GET` e exigem o cabeçalho `Authorization`.

### Números agregados — `GET /stats`

Requer `stats:read`. Retorna os totais consolidados (arrecadado, nº de doações,
doadores únicos).

```bash
curl -H "Authorization: Bearer SUA_CHAVE" \
  "https://SEU-SITE/wp-json/rit360sol/v1/stats"
```

### Campanhas — `GET /campaigns` e `GET /campaigns/{id}`

Requer `stats:read`. Lista as campanhas ou detalha uma campanha específica (troque
`{id}` pelo número da campanha).

```bash
curl -H "Authorization: Bearer SUA_CHAVE" \
  "https://SEU-SITE/wp-json/rit360sol/v1/campaigns"

curl -H "Authorization: Bearer SUA_CHAVE" \
  "https://SEU-SITE/wp-json/rit360sol/v1/campaigns/7"
```

### Projetos — `GET /projects` e `GET /projects/{id}`

Requer `stats:read`. Lista os projetos de doação ou detalha um projeto.

```bash
curl -H "Authorization: Bearer SUA_CHAVE" \
  "https://SEU-SITE/wp-json/rit360sol/v1/projects/67"
```

### Doações — `GET /donations`

Requer `donations:read`. Lista as doações. Aceita filtros:

- `from` / `to` — período (datas no formato `AAAA-MM-DD`).
- `page` / `per_page` — paginação (página e itens por página).

```bash
curl -H "Authorization: Bearer SUA_CHAVE" \
  "https://SEU-SITE/wp-json/rit360sol/v1/donations?from=2026-07-01&to=2026-07-31&page=1&per_page=50"
```

### Doadores — `GET /donors` e `GET /donors/{id}`

Requer `donors:read`. Lista os doadores ou detalha um doador. **Os dados pessoais só
aparecem se a chave tiver o escopo `donors:read_pii`**; sem ele, a resposta traz apenas
identificadores e números, sem nome, e-mail ou documento.

```bash
curl -H "Authorization: Bearer SUA_CHAVE" \
  "https://SEU-SITE/wp-json/rit360sol/v1/donors/11"
```

---

## Endpoints de escrita

As escritas alteram dados no plugin. Envie o corpo em **JSON** e informe o cabeçalho
`Content-Type: application/json`.

### Criar campanha — `POST /campaigns`

Requer `campaigns:write`. Cria uma nova campanha.

```bash
curl -X POST \
  -H "Authorization: Bearer SUA_CHAVE" \
  -H "Content-Type: application/json" \
  -d '{"title":"Campanha de Inverno","goal":50000,"deadline":"2026-09-30"}' \
  "https://SEU-SITE/wp-json/rit360sol/v1/campaigns"
```

### Editar campanha — `PATCH /campaigns/{id}`

Requer `campaigns:write`. Atualiza os campos enviados de uma campanha existente (o que
você não mandar continua como está).

```bash
curl -X PATCH \
  -H "Authorization: Bearer SUA_CHAVE" \
  -H "Content-Type: application/json" \
  -d '{"goal":75000}' \
  "https://SEU-SITE/wp-json/rit360sol/v1/campaigns/7"
```

### Atualizar projeto — `PATCH /projects/{id}`

Requer `projects:write`. Atualiza a **meta**, o **prazo** e a **campanha** de um projeto.

```bash
curl -X PATCH \
  -H "Authorization: Bearer SUA_CHAVE" \
  -H "Content-Type: application/json" \
  -d '{"goal":20000,"deadline":"2026-12-31","campaign_id":7}' \
  "https://SEU-SITE/wp-json/rit360sol/v1/projects/67"
```

---

## Webhooks

Enquanto os endpoints acima são para você **puxar** dados quando quiser, os **webhooks**
fazem o contrário: o plugin **avisa você** assim que algo acontece — mandando uma
mensagem automática para um endereço que você cadastra (por exemplo, a URL de um fluxo
no n8n). É o jeito mais eficiente de reagir a doações em tempo real, sem ficar
consultando a API o tempo todo.

### Cadastrar um destino

Ainda na aba **API**, na seção **Webhooks**:

1. Clique em **Novo destino**.
2. Informe a **URL de destino** (o endereço que vai receber os avisos — por exemplo, a
   URL do nó Webhook do seu fluxo no n8n).
3. Escolha os **eventos** que esse destino deve receber (veja a tabela abaixo).
4. Marque se o envio **inclui dados pessoais** — deixe **desmarcado** sempre que o fluxo
   não precisar de nome/e-mail/documento.
5. Salve. O plugin gera um **segredo** para esse destino, usado para assinar cada envio
   (guarde-o para configurar a validação no n8n).

### Eventos disponíveis

| Evento | Quando dispara |
|---|---|
| `donation.completed` | Uma doação foi **concluída** (paga). |
| `donor.created` | Um **novo doador** foi registrado. |
| `receipt.issued` | Um **recibo** foi emitido. |
| `donation.anonymous.registered` | Uma **doação anônima** foi registrada. |
| `donor.anonymized` | Um doador **anonimizou** os próprios dados (LGPD). |
| `donor.consent.revoked` | Um doador **revogou o consentimento** de comunicações. |

### Assinatura (HMAC-SHA256)

Cada envio é **assinado**, para o destino ter certeza de que a mensagem veio mesmo do
seu site e não foi adulterada. O plugin acrescenta dois cabeçalhos a cada requisição:

- `X-RIT360SOL-Signature` — a assinatura, no formato `sha256=...`.
- `X-RIT360SOL-Timestamp` — o momento do envio.

A assinatura é um **HMAC-SHA256** calculado sobre o texto `timestamp.corpo` (o
timestamp, um ponto e o corpo da requisição, concatenados), usando o **segredo do
destino** como chave. Para validar, o receptor recalcula o HMAC com o mesmo segredo e
compara com o valor recebido — se baterem, a mensagem é legítima.

> 💡 **Como o n8n valida a assinatura**
>
> No fluxo que recebe o webhook (nó **Webhook**), acrescente um nó de código (Function/
> Code) logo depois que:
> 1. lê os cabeçalhos `X-RIT360SOL-Timestamp` e `X-RIT360SOL-Signature` e o corpo bruto;
> 2. monta o texto `timestamp + "." + corpo`;
> 3. calcula `HMAC-SHA256` desse texto com o **segredo do destino** (guardado como
>    credencial/variável no n8n), no formato `sha256=<hash em hexadecimal>`;
> 4. compara com o cabeçalho `X-RIT360SOL-Signature`. Se for diferente, encerre o fluxo
>    (ignore o evento).
>
> Confira também se o `X-RIT360SOL-Timestamp` é recente (ex.: últimos 5 minutos) para
> descartar reenvios antigos.

### Reenvio, log e teste

- **Reenvio automático:** se o destino não responder com sucesso, o plugin **tenta de
  novo** automaticamente por algumas vezes.
- **Log de entregas:** cada destino tem um histórico de envios (data, evento, resposta),
  para você ver o que chegou e o que falhou. Nas entregas que **falharam**, um ícone de
  informação (ⓘ) mostra o **último erro** ao passar o mouse — ajuda a diagnosticar (URL
  errada, destino fora do ar, assinatura recusada) sem sair da tela.
- **Enviar teste:** o botão **Enviar teste** dispara um evento de exemplo para a URL,
  útil para conferir se o n8n está recebendo e validando a assinatura corretamente.
- As ações de webhook (cadastrar destino, enviar teste) também mostram um **aviso de
  confirmação** ao concluir.

---

## Como montar no n8n

O n8n conversa com o RIT360 Solidário de duas formas. Você escolhe conforme o que
precisa fazer.

### Puxar ou escrever dados — nó HTTP Request

Use o nó **HTTP Request** quando o **n8n** for quem inicia a ação (consultar doações,
criar uma campanha etc.):

1. Adicione um nó **HTTP Request**.
2. Escolha o **método** (`GET` para ler, `POST`/`PATCH` para escrever) e informe a URL
   do endpoint (ex.: `https://SEU-SITE/wp-json/rit360sol/v1/donations`).
3. Em **Authentication → Header Auth** (ou em Headers), adicione o cabeçalho
   `Authorization` com o valor `Bearer SUA_CHAVE`.
4. Para escrever, defina o corpo como **JSON** com os campos desejados.
5. Guarde a chave como **credencial/variável** do n8n — nunca colada no fluxo à vista.

### Receber eventos — nó Webhook (gatilho)

Use o nó **Webhook** quando o **plugin** for quem avisa (uma nova doação, um recibo):

1. Adicione um nó **Webhook** como gatilho do fluxo e copie a **URL** que ele gera.
2. No plugin, cadastre essa URL como **destino de webhook** e escolha os eventos.
3. Copie o **segredo** do destino para o n8n e monte a
   [validação de assinatura](#assinatura-hmac-sha256) logo após o Webhook.
4. Depois da validação, siga o fluxo (gravar em planilha, avisar no chat, etc.).
5. Use **Enviar teste** no plugin para conferir a ponta a ponta.

---

## Boas práticas de segurança

> ✅ **Boas práticas**
>
> - **Guarde a chave como segredo** — no cofre de senhas da OSC e como credencial do
>   n8n. Nunca em e-mail, planilha aberta ou dentro do fluxo à vista.
> - **Use `donors:read_pii` só quando for indispensável.** Prefira os escopos sem dados
>   pessoais; lembre que todo acesso com PII é auditado.
> - **Uma chave por integração**, com o **mínimo de escopos**. Assim, se uma vazar, você
>   revoga só ela sem derrubar as outras.
> - **Revogue chaves não usadas** e as que possam ter vazado.
> - **Prefira destinos de webhook sem PII** sempre que o fluxo não precisar de dados
>   pessoais — marque "incluir dados pessoais" apenas quando for realmente necessário.
> - **Valide sempre a assinatura** dos webhooks no n8n antes de usar o conteúdo, e
>   descarte eventos com timestamp antigo.

---

Precisa da referência dos componentes visuais para montar páginas? Veja
[Shortcodes](/modulos/shortcodes/). Para entender a trilha de auditoria dos acessos a
dados pessoais, veja [Auditoria LGPD](/modulos/auditoria-lgpd/).
