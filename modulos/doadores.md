---
title: "Doadores"
nav_order: 2
parent: "Módulos"
permalink: /modulos/doadores/
task: modulo-doadores
role: admin
routes: ["#/wp-admin/admin.php?page=rit360-solidario-donors"]
screenshots: [doadores-lista, doador-detalhe]
source_docs: [PRODUCT.md]
last_verified: 2026-07-21
status: publicado
---

# Doadores

A tela **Doadores** é a sua base de relacionamento. Aqui você encontra quem doou,
consulta recibos, envia lembretes e exporta dados para o conselho e a
contabilidade.

> 💡 **Nota**
>
> Os doadores **não são usuários do WordPress**. Eles vivem numa base própria do
> plugin, identificados pelo e-mail — por isso não aparecem em “Usuários” e não
> têm senha.

![Lista de doadores](/assets/img/doadores-lista.png)

## A lista

- **Busca** por nome ou e-mail.
- Colunas: nome (link para a ficha), e-mail (mascarado), número de doações, total
  doado, situação, data do último lembrete e **ações rápidas**.
- **Ações rápidas** (ícones): baixar o último recibo, emitir a declaração anual do
  ano e enviar lembrete. Quando o doador optou por não receber comunicações, o
  ícone de lembrete indica isso.

## Ações em lote

Selecione vários doadores (ou todos do filtro atual) e aplique:

- **Enviar lembrete** para os selecionados;
- **Exportar selecionados (XLSX)**;
- **Declaração anual (zip)** de um ano informado.

Operações grandes rodam em segundo plano; ao terminar, aparece um aviso com o link
para baixar o arquivo (protegido e temporário).

## Exportações e manutenção

Na parte inferior da tela:

- **Exportar relatório CSV** por intervalo de datas.
- **Exportar doadores (XLSX)** — respeita a busca ativa, inclui anonimizados e traz
  CPF, **CNPJ** (para doadores pessoa jurídica), CEP e telefone como texto (para não
  “quebrar” na planilha).
- **Manutenção**: *reprocessar recibos pendentes* e *atribuir projeto às doações
  antigas* (útil para doações anteriores à organização por projetos). O *reprocessar
  recibos pendentes* também **recupera doações pagas que ficaram sem doador** (por
  exemplo, se o meio de pagamento não registrou o doador na hora): ele cria o doador
  e gera o recibo faltante. Ao terminar, cada ação de manutenção mostra um **aviso com
  a contagem** do que foi processado — você sabe na hora quantos recibos foram
  reprocessados ou quantas doações foram atribuídas.

> ⚠️ **Atenção — dados pessoais**
>
> As exportações contêm dados pessoais de doadores. Trate os arquivos com cuidado,
> compartilhe apenas com quem precisa e apague quando não forem mais necessários.
> É a sua OSC que responde por esses dados (veja [Auditoria LGPD](/modulos/auditoria-lgpd/)).

## Ficha do doador

Ao clicar num nome, você abre a ficha: dados de contato, totais, situação, a
tabela de **recibos** (com download em PDF) e as **declarações anuais** por ano.

![Ficha do doador](/assets/img/doador-detalhe.png)

> 💡 **Dica**
>
> Quando um doador pede a segunda via de um recibo, você resolve na ficha dele em
> segundos — sem precisar procurar em e-mails antigos.
