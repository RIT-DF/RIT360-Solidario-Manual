---
title: "Painel"
nav_order: 1
parent: "Módulos"
permalink: /modulos/painel/
task: modulo-painel
role: admin
routes: ["admin.php?page=rit360-solidario"]
screenshots: [painel]
source_docs: [PRODUCT.md]
last_verified: 2026-09-14
status: publicado
---

# Painel

O Painel é a primeira tela ao entrar em **RIT360 Solidário** — o item **Painel**
solto na barra de navegação, antes dos grupos Doações e Configurações. Ele resume
a sua operação de doações no período escolhido.

![Painel](/assets/img/painel.png)

## Seletor de período

No canto superior direito você escolhe o período de análise: **mês atual, mês
anterior, trimestre atual, ano atual, últimos 12 meses** ou **histórico (total)**.
Todos os números da tela se ajustam ao período.

## Indicadores (KPIs)

Quatro cartões, cada um com a variação em relação ao período anterior:

- **Arrecadado** — total recebido no período.
- **Doações** — quantidade de doações.
- **Doadores únicos** — quantas pessoas diferentes doaram.
- **Ticket médio** — valor médio por doação.

Logo abaixo, uma linha destaca as **doações anônimas** do período (quantidade e
valor).

## Top 10 doadores

Uma tabela com os dez maiores doadores do período: posição, nome, e-mail
(mascarado, por privacidade), número de doações e total. É o ponto de partida
para reconhecer e cultivar quem mais apoia a causa.

> 💡 **Você sabia?**
>
> O e-mail aparece **mascarado** (ex.: `m****@exemplo.com`) em todas as listas do
> painel. É uma medida de minimização de dados: mostra o suficiente para você
> reconhecer o registro, sem expor o endereço completo em tela.

> 💡 **Nota**
>
> Quando ainda não houve nenhuma doação, o Painel mostra um convite para receber a
> primeira, com atalhos para a página de doação e para reabrir o assistente de
> configuração.
