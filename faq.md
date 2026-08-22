---
title: "Dúvidas frequentes"
nav_order: 5
permalink: /faq/
task: faq
role: admin
routes: []
source_docs: [PRODUCT.md]
last_verified: 2026-07-15
status: publicado
---

# Dúvidas frequentes

## Sobre o funcionamento

**Preciso do WooCommerce?**
Sim. O RIT360 Solidário usa o WooCommerce como motor de pagamento e checkout. É
ele que integra PIX, boleto, cartão e os gateways nacionais.

**O doador precisa criar conta?**
Não. Ele doa informando só nome e e-mail (o documento é opcional). Para ver
recibos e histórico, acessa um painel próprio por um link enviado ao e-mail — sem
senha.

**Como o doador recupera um recibo antigo?**
Pelo **portal do doador** (`/minhas-doacoes`): informa o e-mail, recebe o magic
link e baixa o recibo ou a declaração anual. Você também consegue reenviar pela
ficha do doador.

**Dá para usar o mesmo site para vender outros produtos?**
Sim. A troca de linguagem (“doação” em vez de “pedido”) só acontece quando o
carrinho tem **apenas** produtos de doação. Produtos comuns seguem no checkout
normal do WooCommerce.

## Recibos e documentos

**O recibo tem numeração fiscal?**
Sim, com numeração sequencial no formato `AAAA/NNNNNN`, em PDF, com os dados da
OSC. A **declaração anual** consolida as doações do ano.

**Posso personalizar o texto do recibo?**
Sim, em **Configurações → Documentos PDF**. Há um botão de pré-visualização e a
opção de restaurar o texto padrão. Valide alterações com a sua contabilidade.

**O doador informou o CPF errado / não informou. E agora?**
O documento é opcional no checkout, mas necessário para o recibo fiscal. Sem ele,
não há como emitir o recibo em nome da pessoa. Oriente o doador a doar informando o
documento quando quiser o comprovante para dedução.

## Campanhas, projetos e metas

**Qual a diferença entre projeto e campanha?**
O **projeto** é a causa com sua página e valores. A **campanha** é a temporada de
arrecadação, com meta e prazo, que agrupa projetos. Veja
[Campanhas que dão resultado](/guias/campanhas-que-dao-resultado/).

**Como mostro o progresso da arrecadação no site sem expor os doadores?**
Use o shortcode `[rit360sol_transparencia]`. Ele mostra o arrecadado e a meta, sem
nomes de doadores.

**Para que serve a categoria do projeto? Preciso mexer nela?**
Não precisa. É o que faz o dinheiro de cada projeto chegar **separado** na
prestação de contas — sem ela, todas as doações apareceriam misturadas. O
plugin cria a categoria sozinho quando você não escolhe uma. Veja
[Projetos de doação](/modulos/projetos/#por-que-cada-projeto-tem-uma-categoria).

**Por que o produto de doação sumiu da loja?**
Ele não some — só deixou de aparecer no catálogo e na busca da loja, desde a
versão 2.25. A página do projeto e o link direto continuam funcionando
normalmente. Veja [Produto de doação](/modulos/produto-de-doacao/).

## Recorrência e lembretes

**O RIT360 Solidário faz assinatura mensal?**
Não no sentido de cobrança automática. Ele usa recorrência “soft”: envia um
**lembrete mensal** com um botão para repetir a doação. O doador decide a cada mês
e pode cancelar o lembrete em um clique.

## LGPD e privacidade

**Como um doador pede a exclusão dos dados?**
Pelo próprio **portal do doador**, na aba **Consentimentos** — com dupla
confirmação. Não é o administrador que anonimiza; é o doador. Os registros de
doação são preservados de forma anônima (exigência fiscal).

**Quem é o responsável pelos dados dos doadores?**
A sua organização (a controladora). O RIT360 Solidário fornece as ferramentas de
conformidade; as decisões e a responsabilidade são da OSC.

## Versão e suporte

**Como sei qual versão está instalada?**
Em **Plugins**, na lista de plugins do WordPress, ao lado de “RIT360 Solidário”.

**Como falo com a equipe?**
Pelo botão **Enviar feedback**, na barra do topo de qualquer tela do plugin. Você
pode relatar um problema, sugerir uma melhoria ou deixar um elogio.
