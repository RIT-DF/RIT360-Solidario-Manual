---
title: "Projetos de doação"
nav_order: 3
parent: "Módulos"
permalink: /modulos/projetos/
task: modulo-projetos
role: admin
routes: ["admin.php?page=rit360-solidario#/projects"]
screenshots: [projetos]
source_docs: [PRODUCT.md]
last_verified: 2026-09-14
status: publicado
---

# Projetos de doação

Um **projeto** é uma causa com a sua própria página de doação, valores sugeridos
e, se você quiser, uma meta. Cada projeto vira uma página `/…` no site, pronta
para divulgar.

![Projetos de doação](/assets/img/projetos.png)

## Por que cada projeto tem uma categoria

Cada projeto tem, desde a versão 2.25, uma **categoria** — mesmo que você nunca
mexa nela. É o que faz a receita das doações chegar **separada por projeto** na
prestação de contas e no RIT360 Financeiro: sem isso, todas as doações caem
misturadas, e responder "quanto entrou para a creche e quanto para as cestas
básicas" vira trabalho manual de planilha. Com a categoria, essa separação é
automática.

Você não precisa entender WooCommerce para usar isso — só saber que **cada
projeto tem a sua "gaveta"**, e o dinheiro cai na gaveta certa sozinho.

## A lista

Para cada projeto você vê o nome, o produto associado, a **categoria**, a página
pública (permalink) e se ele é o **projeto padrão**. O projeto padrão é o que
alimenta o link “Doar” dos e-mails automáticos.

A categoria aparece como `Doações › Nome do projeto` — uma categoria-pai
**"Doações"** e, dentro dela, uma subcategoria só daquele projeto. Se a sua loja
já tinha uma categoria "Doações" antes de atualizar o plugin, ele **reaproveita**
a que já existe em vez de criar uma segunda; as subcategorias dos projetos
aparecem dentro dela.

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
- **Categoria** — escolha uma subcategoria já existente ou digite um nome para
  criar uma nova. **Deixe em branco e o plugin cria uma categoria com o nome do
  projeto** — o campo nunca fica "sem categoria".
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

> ⚠️ **Atenção — renomear o projeto não renomeia a categoria**
>
> É de propósito: o nome da categoria já apareceu na prestação de contas de
> doações antigas, e mudá-lo reescreveria esse histórico. Se você renomear um
> projeto ("Creche Semear" → "Creche Nova Semear"), a categoria continua com o
> nome anterior. Quer usar outro nome de categoria dali para frente? Crie ou
> escolha outra categoria no campo **Categoria**, em vez de esperar que o plugin
> acompanhe o novo nome sozinho.

> 💡 **Nota — quem já usava o plugin**
>
> Ao atualizar para a 2.25, o plugin organiza os projetos que já existiam
> sozinho: cria a categoria que falta para cada um. Se você **já tinha colocado
> uma categoria à mão** no produto de um projeto (por exemplo, "Doações da
> Igreja"), ela **não é apagada** — a categoria do projeto é somada a ela. Nada a
> fazer da sua parte.

> ✅ **Boas práticas**
>
> - Enriqueça a página de cada projeto (imagem, frase de impacto, vídeo,
>   descrição) na [configuração do produto de doação](/modulos/produto-de-doacao/).
>   Páginas ricas convertem mais.
> - Use nomes concretos (“Refeitório comunitário”), não genéricos (“Doações”) —
>   vale tanto para o nome do projeto quanto para o nome da categoria, já que os
>   dois aparecem juntos na prestação de contas.
