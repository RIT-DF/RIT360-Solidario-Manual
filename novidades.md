---
title: "Novidades"
nav_order: 6
permalink: /novidades/
task: novidades
role: admin
source_docs: [CHANGELOG.md]
last_verified: 2026-07-21
status: publicado
---

# Novidades

O que mudou no RIT360 Solidário, em linguagem de quem usa. A versão instalada
aparece em **Plugins**, na lista de plugins do WordPress.

> 💡 **Nota**
>
> Esta é a versão amigável do histórico. O registro técnico completo fica no
> `CHANGELOG.md` do projeto.

---

## Versões 2.14 a 2.24 — Painel com a cara da família RIT360

As telas do plugin no painel administrativo foram **repaginadas**. O que você faz
continua igual — mudou o visual, que ficou mais moderno e alinhado à família RIT360.

- **Novo visual das telas.** Painel, doadores, projetos, campanhas, prestação de
  contas, configurações, auditoria LGPD e shortcodes ganharam **cartões** com a cor
  da marca e uma leitura mais limpa. As páginas públicas (formulário de doação,
  listagens e portal do doador) continuam com a mesma aparência de sempre.
- **Cabeçalho em todas as telas.** No topo de cada tela aparece a **logomarca**, o
  nome da seção e a **versão instalada** (ex.: “RIT360 Solidário · v2.24.0”). No
  canto direito ficam os botões **Manual do usuário** e **Enviar feedback** — antes
  numa barra separada, agora integrados ao cabeçalho.
- **“Enviar feedback” numa janela.** O botão abre uma janela onde você relata um
  problema, manda uma sugestão, deixa um elogio ou registra um depoimento, com a
  opção de anexar imagens ou PDF. É o canal direto com a equipe do produto.

**Melhorias pontuais desta leva (v2.24):**

- **Doadores:** a planilha (XLSX) de doadores passou a incluir a coluna **CNPJ** dos
  doadores pessoa jurídica; e as ações de manutenção (*reprocessar recibos*,
  *atribuir projeto*) agora mostram um **aviso com a contagem** do que foi feito.
- **API e integrações:** uma chave vencida agora aparece corretamente como
  **“Expirada”**; as ações de chave e de webhook mostram **aviso de sucesso**; e as
  entregas de webhook que falharam trazem o **último erro** num ícone de informação
  (ⓘ), para diagnosticar sem sair da tela.
- **Prestação de contas:** o texto perto dos botões de exportar ficou mais claro —
  as exportações (CSV/XLSX) vêm com os **dados pessoais mascarados por padrão
  (LGPD)**.

---

## Versões 2.13 — Mais privacidade para o doador (LGPD)

Melhorias de transparência e de proteção de dados. A maioria funciona **de
bastidor**, sem nada para configurar.

- **Fica claro o que é mantido ao excluir os dados.** Quando o doador pede para
  **excluir os próprios dados** no [portal](/modulos/portal-do-doador/), ele agora vê
  um aviso explícito: os dados pessoais são anonimizados, **mas os recibos fiscais já
  emitidos são mantidos como estão** — por obrigação legal de guarda fiscal (a lei
  exige guardar o recibo, e a LGPD permite reter dado por obrigação legal). A
  [Auditoria LGPD](/modulos/auditoria-lgpd/) registra que os recibos foram retidos.
- **Menos dado pessoal no registro de auditoria.** Quando o doador altera os próprios
  dados, a auditoria passa a guardar **apenas quais campos mudaram**, não mais os
  valores em texto plano.
- **IP e navegador apagados após 6 meses.** O plugin **remove automaticamente** o IP e
  o navegador (user-agent) dos registros de auditoria e de acesso com mais de **6
  meses**, mantendo o restante do histórico. É automático, não precisa configurar.

---

## Versões 2.10 a 2.12 — API e integrações (n8n)

- **Chegou a API do RIT360 Solidário.** Agora dá para **conectar o plugin ao n8n** e a
  outros sistemas: mandar cada nova doação para uma planilha, avisar a equipe no chat
  quando bater a meta, criar campanhas a partir de outra ferramenta, e mais.
- **Chaves de integração com permissões.** Na tela **Shortcodes e API → aba API**, você
  cria chaves escolhendo exatamente o que cada uma pode fazer (só números, doações,
  doadores, dados pessoais, escrever campanhas/projetos) e a validade. A chave aparece
  **uma única vez** — copie na hora — e pode ser **revogada** quando quiser.
- **Webhooks em tempo real.** Cadastre um destino (por exemplo, a URL de um fluxo no
  n8n) e o plugin avisa sozinho a cada doação concluída, novo doador, recibo emitido e
  outros eventos. Cada envio é **assinado** para garantir a origem, tem **reenvio
  automático**, **log de entregas** e botão **Enviar teste**.
- **Privacidade em primeiro lugar.** O acesso a dados pessoais depende de uma permissão
  própria (`donors:read_pii`) e **todo acesso a PII é registrado na Auditoria LGPD**.
- Passo a passo e exemplos em [API e integrações](/modulos/api-integracoes/).
- **Nota de instalação:** o menu do plugin que se chamava "Shortcodes" agora é
  **"Shortcodes e API"**.

---

## Versão 2.9.2 — Portal do doador sem página duplicada

- **Fim das páginas “Minhas doações” repetidas.** Em alguns sites, a página do portal
  aparecia duplicada (`minhas-doacoes-2`, `-3`…), criada de novo a cada atualização ou
  reinstalação. Ao atualizar para esta versão, o plugin **move para a lixeira** as
  duplicatas antigas que sobraram — sempre de forma **reversível**, sem tocar na página
  ativa nem em nenhuma página que você tenha editado. Nada a fazer da sua parte.

---

## Versão 2.9.1 — Correção do acesso ao portal do doador

- **Portal do doador voltou a abrir em sites que vieram da Bússola.** Nesses sites, ao
  pedir o link de acesso em **Minhas doações**, o doador podia cair numa página
  “não encontrada”, porque a página do portal havia sido movida para a lixeira ou
  apontava para um endereço antigo. Agora o plugin **localiza e conserta a página do
  portal automaticamente** ao atualizar, e só usa a página quando ela está publicada.
  Sites migrados se corrigem sozinhos ao atualizar para esta versão.

---

## Versão 2.9 — Doações de empresas (pessoa jurídica)

- **Empresas agora podem doar.** No checkout, o doador escolhe entre **Pessoa física**
  e **Pessoa jurídica**. Quem doa como empresa informa a **razão social** (no campo
  “Empresa”) e o **CNPJ** — e o **recibo** e a **declaração anual** saem com esses
  dados. Pessoa física continua exatamente como antes, com CPF.
- **CNPJ com letras:** o campo aceita o novo formato de CNPJ alfanumérico da Receita.
- **CPF conferido:** quando o doador pessoa física informa o CPF, ele passa a ser
  validado, reduzindo recibos com número errado.
- Para habilitar a doação de empresas, deixe o campo **“Empresa”** visível no checkout
  do WooCommerce (como *opcional*).

---

## Versão 2.8.3 — Logomarca da OSC nos e-mails

- Os e-mails automáticos (agradecimento, acesso ao painel e lembrete) passam a exibir a
  **logomarca da organização** no topo, sobre um fundo branco, quando há logo
  configurada na **Identidade Visual**. Sem logo, o e-mail continua como antes.

---

## Versão 2.8.1 — Correções

- **Doações passam a registrar sempre.** Em alguns meios de pagamento (como o Pix), uma doação paga
  podia concluir sem registrar o doador nem gerar o recibo. Agora o doador é registrado no momento em
  que a doação é **concluída**, independentemente do meio de pagamento.
- **Recuperar doações antigas sem recibo:** em **Doadores → Manutenção**, o botão *Reprocessar recibos
  pendentes* agora também **cria o doador** quando faltar e gera o recibo.
- **Instalação sobre a Bússola Solidária:** o painel deixa de ficar preso no assistente de
  configuração quando a organização já estava configurada — vai direto para o Painel.

---

## Versão 2.8 — Formulário de doação sob medida e edição rápida do produto

- O **formulário de doação** (`[rit360sol_doar]`) agora deixa você **mostrar ou ocultar** cada parte:
  imagem, título, frase de impacto, descrição, valores sugeridos, vídeo e história. Assim você adapta
  o formulário ao layout da sua página. Por padrão continua tudo visível — quem já tem páginas montadas
  não precisa mudar nada. Para ocultar algo, use, por exemplo, `show_imagem="0"`.
- Na tela **Projetos de doação**, cada projeto ganhou o link **“Editar produto”**, que abre o produto
  no editor do WooCommerce — o jeito rápido de trocar a imagem, os valores, o vídeo e os textos da sua
  página de doação (inclusive a `/doe`).

---

## Versão 2.7 — Novos componentes para montar suas páginas

- **Botão de doação** (`[rit360sol_botao_doar]`): um botão pronto, com a cor da sua marca, que leva
  direto para a página da causa. Ótimo para chamar à ação no meio de um texto.
- **Barra de progresso** (`[rit360sol_meta]`): mostre só a barrinha "arrecadado × meta" de uma
  campanha ou projeto, onde você quiser.
- **Contador** (`[rit360sol_contador]`): exiba um número que engaja — "já arrecadamos R$ X",
  "N doações" — do total ou de uma campanha/projeto específico.
- **Listas na ordem que você quer**: em projetos, campanhas e transparência, agora dá para **ordenar**
  (por título, valor arrecadado ou percentual da meta) e mostrar, por exemplo, os **3 mais
  arrecadados**.
- **Nova tela "Shortcodes"** no menu do plugin: uma referência com todos os componentes, seus
  parâmetros e um botão **Copiar** em cada exemplo. (A antiga "Manual do Usuário" saiu do painel — o
  manual completo agora fica aqui, on-line.)

> **Atenção** — se você montou alguma página com os nomes antigos `[bs_doar]` ou
> `[bs_painel_doador]`, troque-os por `[rit360sol_doar]` e `[rit360sol_painel_doador]`: os apelidos
> antigos foram descontinuados.

---

## Versão 2.6 — E-mails com a cara da sua organização e página de doação mais rica

- Os **e-mails automáticos** (agradecimento, magic link, lembrete) agora herdam as
  **cores da sua identidade visual** — a faixa e o botão saem na sua marca, com o
  texto sempre legível.
- Os **templates de e-mail** ganharam um **único botão “Salvar todos”**: edite
  quantos modelos quiser e grave tudo de uma vez.
- A **página de doação** ficou mais rica: além dos valores e do botão, ela mostra a
  **imagem**, a **frase de impacto**, um **vídeo** e a **descrição** da causa — na
  ordem que mais converte.

> **Correções** — a **logomarca** da organização voltou a salvar corretamente nas
> configurações, e o **preenchimento automático de endereço pelo CEP** foi
> restabelecido.

---

## Versão 2.5 — Prestação de contas por campanha e projeto

- Nova visão de **prestação de contas** com quebra por **campanha e projeto**,
  evolução mensal e exportação em **PDF, CSV e XLSX** (com dados pessoais
  mascarados por padrão).
- O **recibo** e a **declaração anual** passaram a **discriminar o projeto** de
  origem da doação — muito mais clareza para o doador e para o conselho.
- Suporte ao novo **CNPJ alfanumérico** da Receita Federal.

---

## Versão 2.4 — Campanhas e metas

- Chegaram as **campanhas**: agrupe projetos, defina **meta** e **prazo** e
  acompanhe o **progresso** automaticamente.
- Página de **transparência pública** com o shortcode `[rit360sol_transparencia]`,
  mostrando o quanto foi arrecadado sem expor nomes de doadores.

---

## Versão 2.3 — Vários projetos de doação

- Agora a OSC pode ter **vários projetos**, cada um com sua página, seus valores e
  sua meta — em vez de um único “caixa” de doações.

---

## Versão 2.2 — Doações atribuídas a projetos

- Cada doação passou a ser **atribuída a um projeto**, base para os relatórios por
  causa que vieram depois.

---

## Versão 2.1 — Privacidade, bases legais e a barra da família

- Nova página de **Privacidade e bases legais** (o registro de tratamento de dados
  — ROPA) e um resumo na tela de LGPD do plugin.
- **Barra da família RIT360** no topo das telas, com acesso ao manual e ao
  **Enviar feedback**.
- Diversas correções de estabilidade nos formulários do painel.

---

## Versão 2.0 — Nova marca: RIT360 Solidário

- O plugin antes conhecido como **Bússola Solidária** passou a se chamar **RIT360
  Solidário**, integrando a família de produtos RIT360. As páginas e configurações
  existentes continuaram funcionando.
