---
title: "Shortcodes"
nav_order: 11
parent: "Módulos"
permalink: /modulos/shortcodes/
task: modulo-shortcodes
role: admin
routes: ["#/wp-admin/admin.php?page=rit360-solidario-shortcodes"]
screenshots: [shortcodes-tela]
source_docs: [PRODUCT.md]
last_verified: 2026-07-21
status: publicado
---

# Shortcodes

Shortcodes são pequenos códigos que você cola em qualquer página, post ou construtor
(editor do WordPress, Elementor via widget de shortcode, etc.) para inserir componentes
do RIT360 Solidário. É assim que você monta o hotsite de uma campanha com as peças do
plugin.

No painel, o menu **RIT360 Solidário → Shortcodes e API** traz esta mesma referência, com
um botão **Copiar** ao lado de cada exemplo. A aba **API** dessa mesma tela cuida das
integrações com o n8n e outros sistemas — veja [API e integrações](/modulos/api-integracoes/).

![Tela Shortcodes no painel](/assets/img/shortcodes-tela.png)

> 💡 **Onde houver `id="ID"`**, troque `ID` pelo número da campanha, projeto ou produto.
> Você encontra os IDs nas telas **Campanhas** e **Projetos de doação**. Se o conteúdo
> não puder ser exibido (por exemplo, um ID inexistente), a mensagem de erro aparece
> **só para administradores** — o visitante não vê nada.

## Doação

### `[rit360sol_doar]`
Formulário completo de doação de um produto (valores sugeridos, "outro valor" se
habilitado, imagem, frase de impacto, vídeo, descrição e o botão **Doar agora**).

- `id` — ID do produto de doação (obrigatório).
- **Mostrar/ocultar seções** (todas ligadas por padrão; passe `"0"` para ocultar):
  `show_imagem`, `show_titulo`, `show_impacto`, `show_descricao`, `show_valores`,
  `show_video`, `show_historia`. O botão **Doar** e o campo de valor livre continuam sempre.
- Exemplo: `[rit360sol_doar id="67"]`
- Exemplo enxuto (só valores e botão): `[rit360sol_doar id="67" show_imagem="0" show_video="0" show_historia="0" show_descricao="0"]`

### `[rit360sol_botao_doar]`
Um botão/CTA leve que leva à página do produto de doação. Use em páginas de conteúdo,
quando não quiser o formulário inteiro. Usa a **cor de destaque** da sua Identidade
Visual.

- `id` — ID do produto de doação (obrigatório).
- `text` — texto do botão (padrão: "Doar agora").
- `class` — classe CSS extra (opcional).
- Exemplo: `[rit360sol_botao_doar id="67" text="Doe agora"]`

## Listas e progresso

### `[rit360sol_projetos]`
Lista os seus **projetos** em cartões, lista ou grade.

- `ids` — IDs de produto separados por vírgula (vazio = todos).
- `show_goal` — mostra a barra de meta (`"1"` liga; padrão desligado).
- Aceita os [parâmetros comuns de listagem](#parâmetros-comuns-de-listagem).
- Exemplo: `[rit360sol_projetos view="grid" columns="3" show_goal="1" orderby="raised" order="desc" limit="6"]`

### `[rit360sol_campanhas]`
Lista as suas **campanhas**, com progresso de meta.

- `ids` — IDs de campanha separados por vírgula (vazio = todas).
- `show_goal` — mostra a barra de meta (`"1"` liga; padrão desligado).
- Aceita os [parâmetros comuns de listagem](#parâmetros-comuns-de-listagem).
- Exemplo: `[rit360sol_campanhas view="card" show_goal="1"]`

### `[rit360sol_meta]`
Exibe **apenas a barra de progresso** (arrecadado, meta, percentual e prazo) de uma
campanha ou projeto. Usa a **cor primária** da sua Identidade Visual.

- `scope` — `campanha` (padrão) ou `projeto`.
- `id` — ID da campanha ou do projeto/produto (obrigatório).
- `show_deadline` — exibe o prazo quando houver (`"1"` padrão).
- Exemplo: `[rit360sol_meta scope="campanha" id="7"]`

### `[rit360sol_contador]`
Mostra um **número agregado**: total arrecadado, número de doações ou doadores únicos.
Global ou de uma campanha/projeto. Sem dados pessoais, e com o resultado em cache.

- `metric` — `raised` (arrecadado, padrão), `count` (nº de doações) ou `donors`
  (doadores únicos).
- `scope` — `global` (padrão), `campanha` ou `projeto`.
- `id` — obrigatório quando o `scope` não é global.
- `text_before` / `text_after` — texto antes/depois do número.
- Exemplo: `[rit360sol_contador metric="raised" scope="global" text_before="Já arrecadamos "]`

> ⚠️ **Doadores únicos** (`metric="donors"`) só funcionam por campanha ou projeto — não
> há total global de únicos, para não contar duas vezes quem doou para mais de um projeto.

## Transparência e portal

### `[rit360sol_transparencia]`
Página de **transparência pública**: mostra o arrecadado e o progresso das metas, **sem
expor nomes de doadores**. O resultado é armazenado em cache para não pesar no site.

- `scope` — `campanhas` (padrão) ou `projetos`.
- Aceita os [parâmetros comuns de listagem](#parâmetros-comuns-de-listagem).
- Exemplo: `[rit360sol_transparencia scope="campanhas" view="list"]`

### `[rit360sol_painel_doador]`
Exibe o **portal do doador** (a tela de acesso por link mágico e, depois de logado, as
cinco abas). É o que fica na página `/minhas-doacoes`. Não tem atributos.

## Parâmetros comuns de listagem

Valem para `[rit360sol_projetos]`, `[rit360sol_campanhas]` e `[rit360sol_transparencia]`.

- `view` — `card` (padrão), `list` ou `grid`.
- `columns` — número de colunas (só afeta a view `grid`).
- `limit` — número máximo de itens.
- `orderby` — `title` (título), `raised` (arrecadado) ou `pct` (percentual da meta).
- `order` — `asc` (crescente) ou `desc` (decrescente).

> A ordenação é aplicada **antes** do limite. Assim, `orderby="raised" order="desc"
> limit="3"` mostra os **3 projetos/campanhas mais arrecadados**.

> ✅ **Boas práticas**
>
> - Para o hotsite de uma campanha: combine `[rit360sol_meta]` (para mostrar o
>   progresso) com `[rit360sol_botao_doar]` ou `[rit360sol_doar]` (para converter) na
>   mesma página.
> - Os shortcodes funcionam em qualquer construtor, porque são independentes do endereço
>   da página.

> ⚠️ **Atenção — nomes antigos**
>
> Os apelidos `[bs_doar]` e `[bs_painel_doador]` (da época "Bússola Solidária") **foram
> descontinuados**. Se você ainda os usa em alguma página, troque por
> `[rit360sol_doar]` e `[rit360sol_painel_doador]`, respectivamente.
