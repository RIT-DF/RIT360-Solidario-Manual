---
title: "Configurações"
nav_order: 6
parent: "Módulos"
permalink: /modulos/configuracoes/
task: modulo-configuracoes
role: admin
routes: ["admin.php?page=rit360-solidario#/settings"]
screenshots: [config-organizacao, config-visual, config-lembretes, config-emails, config-pdf, config-avancado]
source_docs: [PRODUCT.md]
last_verified: 2026-09-14
status: publicado
---

# Configurações

A tela **Configurações** reúne tudo que personaliza o RIT360 Solidário para a sua
organização, em seis abas. Cada aba tem o seu próprio botão de salvar.

## Organização

Os dados da sua OSC — os mesmos do primeiro passo do assistente: razão social,
nome fantasia, CNPJ (aceita o novo formato **alfanumérico**), e-mail, telefone,
endereço (com preenchimento automático pelo CEP), website, **logomarca** e o
**tipo de operação** (apenas digital ou também produtos físicos).

![Configurações — Organização](/assets/img/config-organizacao.png)

Esses dados aparecem no recibo, na declaração e nos e-mails. Mantê-los corretos é
o que dá validade e profissionalismo aos documentos.

## Identidade visual

As três cores da marca — **primária, secundária e de destaque (o botão de doar)** —
com pré-visualização ao vivo.

![Configurações — Identidade visual](/assets/img/config-visual.png)

> 💡 **Você sabia?**
>
> As cores definidas aqui também são usadas nos **e-mails** que a OSC envia (a
> faixa do cabeçalho e o botão de ação). A cor do texto é ajustada
> automaticamente para continuar legível sobre a cor que você escolher.

## Lembretes

Ativa o **lembrete mensal** de doação e define o **intervalo em dias** (padrão 30).
Há também um bloco de **envio manual** (“Enviar lembretes agora”) para disparar na
hora.

![Configurações — Lembretes](/assets/img/config-lembretes.png)

O lembrete é a recorrência “soft” do RIT360 Solidário: convida quem optou por
recebê-lo a repetir a doação, sem criar assinatura no gateway e com cancelamento
em um clique.

## Templates de e-mail

Personalize o **assunto** e o **corpo** dos e-mails automáticos (magic link,
lembrete mensal e agradecimento/doação recebida). Cada template tem um editor
visual, as **tags de mesclagem** disponíveis (como `{% raw %}{{donor_name}}{% endraw %}`), botões de
**pré-visualizar** e **enviar teste**, e **restaurar o padrão**.

![Configurações — Templates de e-mail](/assets/img/config-emails.png)

> 💡 **Nota — um único botão salva tudo**
>
> No fim da aba há **um só botão “Salvar todos os templates”**, que grava as
> alterações de todos os modelos de uma vez. As cores dos e-mails vêm da aba
> **Identidade visual**.

> ✅ **Boas práticas**
>
> Antes de valer para os doadores, use **Enviar teste** para receber o e-mail no
> seu próprio endereço e conferir como ele chega de verdade.

## Documentos PDF

Personaliza o **recibo** e a **declaração anual**:

- **Cabeçalho** — o que aparece no topo (logo, CNPJ, endereço, telefone, website).
- **Rodapé** — nome da OSC, website, endereço, telefone, data.
- **Recibo** — o texto jurídico (editável, com opção de restaurar o padrão) e uma
  mensagem extra sua, antes ou depois.
- **Declaração anual** — texto jurídico e mensagem extra, com as tags de ano e
  total.
- **Pré-visualizar** — gera um PDF de amostra com dados fictícios, para você ver o
  resultado antes de valer.

![Configurações — Documentos PDF](/assets/img/config-pdf.png)

> ⚠️ **Atenção**
>
> O texto do recibo e da declaração tem valor fiscal. Se for alterá-lo, valide o
> conteúdo com a contabilidade da OSC. Na dúvida, use **Restaurar padrão**.

## Avançado

Ferramenta de manutenção: **resetar o limite de envio do magic link** para um
e-mail (por padrão são 3 pedidos a cada 15 minutos). Útil quando um doador tentou
várias vezes e ficou temporariamente bloqueado.

![Configurações — Avançado](/assets/img/config-avancado.png)
