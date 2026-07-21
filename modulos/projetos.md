---
title: "Projetos de doação"
nav_order: 3
parent: "Módulos"
permalink: /modulos/projetos/
task: modulo-projetos
role: admin
routes: ["#/wp-admin/admin.php?page=rit360-solidario-projetos"]
screenshots: [projetos]
source_docs: [PRODUCT.md]
last_verified: 2026-07-21
status: publicado
---

# Projetos de doação

Um **projeto** é uma causa com a sua própria página de doação, valores sugeridos
e, se você quiser, uma meta. Cada projeto vira uma página `/…` no site, pronta
para divulgar.

![Projetos de doação](/assets/img/projetos.png)

## A lista

Para cada projeto você vê o nome, o produto associado, a página pública
(permalink) e se ele é o **projeto padrão**. O projeto padrão é o que alimenta o
link “Doar” dos e-mails automáticos.

Na coluna **Ações**, o link **“Editar produto”** abre o produto de doação no editor do
WooCommerce (em nova aba) — é onde você muda imagem, valores sugeridos, frase de impacto,
vídeo e descrição. Vale para o projeto padrão (página `/doe`) e para todos os outros.

Ao lado de cada projeto, você define:

- **Meta** (valor-alvo em R$);
- **Prazo** (data);
- **Campanha** — a qual campanha aquele projeto pertence (veja [Campanhas](/modulos/campanhas/)).

## Criar um projeto

No formulário **Novo projeto**, informe:

- **Nome** do projeto;
- **Valores predefinidos** (lista separada por vírgula, ex.: `25, 50, 100, 250`);
- **Permitir valor livre** (o doador digita quanto quer);
- **Valor mínimo** para o valor livre.

Ao salvar, o plugin cria o produto de doação correspondente e a página pública do
projeto.

> 💡 **Nota — uma doação, um projeto**
>
> Cada doação pertence a **um** projeto. O carrinho não mistura projetos
> diferentes numa mesma doação — isso mantém a atribuição (e a prestação de contas)
> sempre clara.

> ✅ **Boas práticas**
>
> - Enriqueça a página de cada projeto (imagem, frase de impacto, vídeo,
>   descrição) na [configuração do produto de doação](/modulos/produto-de-doacao/).
>   Páginas ricas convertem mais.
> - Use nomes concretos (“Refeitório comunitário”), não genéricos (“Doações”).
