---
title: "Campanhas que dão resultado"
nav_order: 1
parent: "Guias e boas práticas"
permalink: /guias/campanhas-que-dao-resultado/
task: guia-campanhas
role: admin
routes: ["admin.php?page=rit360-solidario#/campaigns", "admin.php?page=rit360-solidario#/projects"]
screenshots: [campanhas, projetos, transparencia]
source_docs: [PRODUCT.md, PRD]
last_verified: 2026-09-14
status: publicado
---

# Campanhas que dão resultado

Uma campanha de doação não é um botão “Doar” esquecido no rodapé do site. É uma
história com começo, meio e fim: uma necessidade concreta, uma meta clara, um
prazo, e um convite que as pessoas entendem e no qual confiam. Este guia mostra
como construir isso — e como o RIT360 Solidário sustenta cada etapa.

## O que é uma campanha aqui

No RIT360 Solidário, três conceitos trabalham juntos:

- **Projeto** — uma causa com sua própria página de doação, seus valores
  sugeridos e, opcionalmente, sua meta. Ex.: *“Refeitório comunitário”*,
  *“Bolsas de estudo”*.
- **Campanha** — um esforço com meta e prazo que **agrupa um ou mais projetos**.
  Ex.: *“Campanha do Agasalho 2026”*. O progresso da campanha é a soma das
  doações aos projetos que ela reúne.
- **Meta** — o valor-alvo (de um projeto ou de uma campanha), que vira uma barra
  de progresso pública e um número para você acompanhar internamente.

> 💡 **Projeto x Campanha, na prática**
>
> Pense no **projeto** como a causa permanente (existe o ano todo) e na
> **campanha** como a temporada de arrecadação (tem início, fim e meta). Uma
> mesma causa pode entrar em várias campanhas ao longo do tempo.

## Passo 1 — Escolha uma causa concreta

Doadores respondem a necessidades específicas, não a instituições abstratas.
*“Ajude o Instituto”* arrecada menos que *“R$ 50 garantem uma cesta básica para
uma família por um mês”*.

> ✅ **Boas práticas**
>
> - Traduza a meta em unidades de impacto: quantas cestas, quantas bolsas,
>   quantos metros de reforma. Use a **frase de impacto** do produto de doação
>   para isso (veja [Produto de doação](/modulos/produto-de-doacao/)).
> - Uma campanha, uma mensagem central. Se você tem cinco causas, faça cinco
>   projetos — não amontoe tudo num texto só.

## Passo 2 — Defina uma meta realista e um prazo

A meta precisa ser ambiciosa o suficiente para mobilizar e realista o suficiente
para ser batida. Uma meta batida gera prova social (“deu certo!”) que puxa a
próxima campanha. Uma meta irreal frustra e desgasta.

> 💡 **Exemplo**
>
> Se no ano passado a OSC arrecadou R$ 15.000 no inverno, uma meta de R$ 20.000
> para a Campanha do Agasalho deste ano é desafiadora e crível. R$ 200.000 não é.

O prazo cria urgência. Campanhas sem data de fim tendem a “morrer de velhice” —
ninguém doa hoje o que pode doar “qualquer dia”.

## Passo 3 — Monte no plugin

1. Em **RIT360 Solidário**, grupo **Doações** na barra, aba **Projetos de
   doação**, crie (ou ajuste) os projetos da campanha: nome, valores sugeridos,
   valor livre e, se quiser, a meta do projeto. Enriqueça a página com imagem,
   **frase de impacto**, vídeo e descrição — isso aumenta a conversão.

   ![Projetos de doação](/assets/img/projetos.png)

2. Na mesma barra, aba **Campanhas**, crie a campanha: nome, descrição, meta,
   início e prazo. Depois, **atribua os projetos** a ela.

   ![Campanhas](/assets/img/campanhas.png)

Pronto: a campanha passa a somar automaticamente todas as doações feitas aos seus
projetos, e a barra de progresso se atualiza sozinha.

## Passo 4 — Dê visibilidade e transparência

Confiança é o que separa uma campanha que arrecada de uma que não sai do lugar.

- Publique uma **página de transparência** com o shortcode
  `[rit360sol_transparencia]`: ela mostra o quanto foi arrecadado e o progresso da
  meta, **sem expor nomes de doadores**. Ótima para colocar no ar durante a
  campanha.

  ![Página de transparência](/assets/img/transparencia.png)

- Use os blocos e shortcodes de **projetos** e **campanhas** para montar o hotsite
  da campanha no seu construtor de páginas (veja [Shortcodes](/modulos/shortcodes/)).

> ✅ **Boas práticas de divulgação**
>
> - Um link direto e curto para doar (`/doe`) em todo lugar: bio das redes,
>   assinatura de e-mail, WhatsApp, materiais impressos com QR Code.
> - Atualize os apoiadores com marcos (“chegamos a 50% da meta!”). Progresso
>   visível gera mais progresso.
> - Peça para pessoas próximas doarem primeiro. Uma barra que já saiu do zero
>   converte muito mais do que uma barra vazia.

## Passo 5 — Agradeça e preste contas

O fim de uma campanha é o começo da próxima. Quem se sente reconhecido e vê que o
dinheiro chegou onde deveria, doa de novo.

- Todo doador já recebe **agradecimento e recibo automáticos**. Personalize o
  tom desses e-mails na aba **Templates de e-mail**, dentro de
  [Configurações](/modulos/configuracoes/).
- Ative o **lembrete mensal** para convidar quem optou por recebê-lo a repetir a
  doação (recorrência “soft”, sem assinatura e com cancelamento em um clique).
- Feche a campanha com uma **prestação de contas**: gere o relatório em PDF/CSV/XLSX
  em [Prestação de contas](/modulos/prestacao-contas/) e compartilhe o resultado
  com doadores e conselho.

> 💡 **Você sabia?**
>
> Manter um doador custa muito menos do que conquistar um novo. A recorrência
> mensal e a prestação de contas honesta são as duas ferramentas mais baratas —
> e mais eficazes — de sustentabilidade que a sua OSC tem.

## Checklist da campanha

- [ ] Causa concreta e mensurável (frase de impacto pronta)
- [ ] Meta realista + prazo definido
- [ ] Projeto(s) com página rica (imagem, frase, vídeo, descrição)
- [ ] Campanha criada e projetos atribuídos
- [ ] Página de transparência no ar
- [ ] Link `/doe` divulgado em todos os canais
- [ ] Plano de agradecimento e prestação de contas ao fim
