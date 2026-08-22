---
title: "Produto de doação"
nav_order: 10
parent: "Módulos"
permalink: /modulos/produto-de-doacao/
task: modulo-produto
role: admin
routes: ["#/wp-admin/post.php?action=edit"]
screenshots: [produto-doacao]
source_docs: [PRODUCT.md]
last_verified: 2026-08-21
status: publicado
---

# Produto de doação

Por trás de cada projeto existe um **produto de doação** — um tipo especial de
produto do WooCommerce que representa o “pacote de valores” oferecido ao doador.
Você o configura na aba **Configuração de Doação** do produto.

![Configuração do produto de doação](/assets/img/produto-doacao.png)

## Campos

- **Valores predefinidos** — a lista de botões de valor (ex.: `25, 50, 100, 250`).
- **Permitir valor livre** — deixa o doador digitar o próprio valor.
- **Valor mínimo (livre)** — o menor valor aceito no campo livre.
- **Valor máximo** — teto opcional, útil como proteção contra fraude.
- **Frase de impacto** (até 160 caracteres) — a linha que traduz o valor em
  impacto (“R$ 50 alimentam uma família por uma semana”). Aparece em destaque na
  página de doação.
- **URL de vídeo** — um vídeo do YouTube ou Vimeo, incorporado na página.

A **imagem de destaque** e a **descrição** são os campos normais do produto no
WooCommerce — e também aparecem na página de doação.

> ✅ **Boas práticas**
>
> - Uma boa **frase de impacto** é o elemento que mais aumenta a conversão. Seja
>   concreto e específico.
> - Ofereça de 4 a 6 valores sugeridos. Poucos limitam; muitos confundem.
> - Um vídeo curto (até 1–2 minutos) mostrando a causa cria conexão — mas nunca
>   substitua o botão de doar por ele: ação primeiro.

> 💡 **Nota**
>
> Você normalmente não precisa criar produtos “na mão”: ao criar um
> [projeto](/modulos/projetos/), o plugin já gera o produto de doação
> correspondente. Esta tela é onde você o **enriquece**.

## Este produto não aparece na loja

Desde a versão 2.25, o produto de doação **não aparece mais no catálogo nem na
busca** da sua loja WooCommerce. Ele continua funcionando normalmente: a
[página do projeto](/modulos/projetos/) e o link direto do produto seguem no
ar, e quem tem o link continua doando sem nenhuma diferença. O que muda é que
ele não aparece mais para quem navega pela loja.

> ⚠️ **Atenção — se você divulgava pelo catálogo da loja**
>
> Se a sua organização divulgava o produto de doação deixando o visitante
> **navegar até ele pela loja**, esse caminho deixa de existir. Divulgue sempre
> pela [página do projeto](/modulos/projetos/) (a URL `/nome-do-projeto`) ou
> pelo link direto do produto — são os dois caminhos que continuam
> funcionando.
