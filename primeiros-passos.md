---
title: "Primeiros passos"
nav_order: 2
permalink: /primeiros-passos/
task: primeiros-passos
role: admin
routes: ["admin.php?page=rit360-solidario#/wizard", "admin.php?page=rit360-solidario"]
screenshots: [setup-wizard, menu-entrada-unica, painel, doacoes-grupo-aberto-mobile, feedback-modal, doe-pagina]
source_docs: [PRD#5.4, PRODUCT.md]
last_verified: 2026-09-14
status: publicado
---

# Primeiros passos

Em cerca de 15 minutos a sua organização sai do zero e já consegue receber a
primeira doação. Esta página mostra o caminho completo: instalar, configurar pelo
assistente e conferir que tudo funciona.

## Quem usa o RIT360 Solidário

Antes de começar, vale entender os dois papéis:

- **Administrador(a) da OSC** — é você, que instala, configura e opera o plugin
  dentro do WordPress. Tem acesso ao menu **RIT360 Solidário** no painel
  administrativo. Recebe doações, emite recibos, gerencia doadores, organiza
  campanhas e presta contas.
- **Doador** — quem contribui. **Não precisa criar conta.** Doa pela página
  pública e, quando quer ver recibos ou histórico, acessa um painel próprio por um
  link enviado ao e-mail (o *magic link*). Nunca vê o painel administrativo.

> 💡 **Por que “sem conta”?**
>
> Cada campo a mais no cadastro derruba a taxa de conclusão da doação. Ao
> dispensar senha e cadastro, o RIT360 Solidário remove a maior fonte de
> desistência — e ainda evita guardar mais dados pessoais do que o necessário
> (um princípio da LGPD).

## Como navegar no painel

Tudo do RIT360 Solidário mora numa **única entrada** no menu lateral do WordPress
— não existe mais o menu com um item para cada tela. Ao clicar em **RIT360
Solidário**, você entra no painel e navega por dentro dele, com três peças:

![Menu lateral com a entrada única](/assets/img/menu-entrada-unica.png)

- **Cabeçalho.** No topo de toda tela, com a logomarca à esquerda e, ao lado do
  título da tela atual, a **versão instalada** (por exemplo, “v2.29.0”) — o jeito
  rápido de conferir qual versão você está usando. No canto direito ficam dois
  botões presentes em **qualquer tela**: **Manual do usuário** (abre este manual
  on-line) e **Enviar feedback** (abre uma janela para você relatar um problema,
  mandar uma sugestão, deixar um elogio ou registrar um depoimento — escolha o
  tipo, escreva a mensagem, com seu e-mail já preenchido para retorno, e anexe
  imagens ou um PDF se quiser).

  ![A janela “Enviar feedback”](/assets/img/feedback-modal.png)

- **Barra de navegação.** Logo abaixo do cabeçalho, é por ela que você troca de
  tela: **Painel** (solto) · **Doações** (Doadores, Projetos de doação, Campanhas,
  Prestação de contas) · **Configurações** (Configurações, Auditoria LGPD,
  Shortcodes e API, API, Licença — confira na sua tela quais desses grupos e
  abas aparecem, porque isso pode variar). A tela em que você está fica marcada em
  verde-azulado, e clicar num grupo abre as abas de dentro dele.

  ![O grupo Doações aberto na barra](/assets/img/doacoes-grupo-aberto-mobile.png)

- **Área de avisos.** Abaixo da barra, os avisos do próprio WordPress (por
  exemplo, sobre atualização disponível) ganharam um lugar próprio — eles não se
  misturam mais com o conteúdo da tela.

> 💡 **Favorito antigo continua funcionando**
>
> Se você salvou um atalho ou favorito para um endereço antigo (de antes desta
> versão), ele continua levando à tela certa — inclusive **Configurações** lembra
> em qual aba você estava. Não precisa refazer os favoritos.

> ⚠️ **Configuração inicial incompleta**
>
> Enquanto o assistente de configuração não for concluído, a entrada **RIT360
> Solidário** abre direto o assistente, e a barra de navegação não aparece —
> ela só existe depois que a configuração inicial está pronta. Veja o passo a
> passo em [3. O Assistente de configuração](#3-o-assistente-de-configuração-3-passos).

## 1. Requisitos

- WordPress atualizado e **WooCommerce ativo** (é ele que processa o pagamento).
- Pelo menos um **meio de pagamento** configurado no WooCommerce (PIX via
  Mercado Pago, Pagar.me, PagBank, Stripe, boleto, cartão…). Se você ainda não
  tiver nenhum, o assistente avisa e sugere opções.

## 2. Instalar e ativar

1. No painel do WordPress, vá em **Plugins → Adicionar novo → Enviar plugin**.
2. Escolha o arquivo `rit360-solidario.zip` e clique em **Instalar agora**.
3. Clique em **Ativar**.

Ao ativar pela primeira vez, o plugin abre automaticamente o **Assistente de
configuração** (Setup Wizard).

## 3. O Assistente de configuração (3 passos)

![O assistente de configuração e seus três passos](/assets/img/setup-wizard.png)

O assistente guia você por três passos — **Organização**, **Identidade visual** e
**Produto de doação** —, mostrados na barra de progresso no topo. Pode voltar a
qualquer momento, e o progresso fica salvo caso precise sair e retomar depois.

**Passo 1 — Organização.** Os dados da sua OSC: razão social, nome fantasia,
CNPJ, e-mail de contato, telefone, endereço (o CEP preenche o restante
automaticamente) e a **logomarca**. Escolha também o **tipo de operação**:

- *Apenas doações digitais* — o endereço do doador vira opcional no checkout
  (recomendado para a maioria das OSCs).
- *Também vende produtos físicos* — mantém o endereço, necessário para entrega.

> ⚠️ **Atenção — a logomarca do recibo**
>
> Use **PNG ou JPG**. Formatos como WEBP e SVG são ignorados no recibo e na
> declaração (documentos fiscais em PDF/A). Uma imagem com fundo transparente
> aparece com fundo branco no PDF.

**Passo 2 — Identidade visual.** As cores da sua marca: primária, secundária e
de destaque (o botão de doar). Há uma pré-visualização ao vivo. Essas cores
passam a valer também nos e-mails que a OSC envia.

**Passo 3 — Produto de doação.** O “pacote de valores” que o doador vê: nome,
valores predefinidos (ex.: 25, 50, 100, 250) e se aceita **valor livre** (com um
mínimo). Ao concluir, o plugin cria o produto, publica a **página de doação**
(`/doe`) e, se você ainda não tiver gateway, habilita um meio provisório para
você testar.

Na tela final, **Setup concluído**, você tem atalhos para ver a página de
doação, gerenciar produtos e reabrir o assistente.

## 4. Conferir que está tudo pronto

Entre em **RIT360 Solidário** — a primeira tela já é o **Painel**. Ele mostra os
indicadores da sua operação — no começo, tudo zerado, com um convite para
receber a primeira doação.

![Painel do RIT360 Solidário](/assets/img/painel.png)

## 5. Fazer uma doação de teste

Abra a página **`/doe`** do seu site (o endereço aparece na tela final do
assistente). Escolha um valor, clique em **Doar agora** e conclua pelo checkout.

![Página de doação](/assets/img/doe-pagina.png)

Assim que o pagamento é confirmado, o doador recebe o **e-mail de agradecimento
com o recibo em PDF**, e a doação passa a contar no **Painel**.

> ✅ **Boas práticas**
>
> - Faça uma doação de teste real (um valor pequeno, no seu próprio gateway)
>   antes de divulgar. É a forma mais segura de confirmar que o pagamento, o
>   e-mail e o recibo estão funcionando de ponta a ponta.
> - Adicione o link **/doe** ao menu principal do site e ao botão “Doar” — quanto
>   mais visível, mais doações.

## Próximos passos

- Aprenda a captar de verdade em [Campanhas que dão resultado](/guias/campanhas-que-dao-resultado/).
- Conheça cada tela em [Módulos](/modulos/).
