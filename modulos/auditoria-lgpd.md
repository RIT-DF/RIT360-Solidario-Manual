---
title: "Auditoria LGPD"
nav_order: 7
parent: "Módulos"
permalink: /modulos/auditoria-lgpd/
task: modulo-lgpd
role: admin
routes: ["admin.php?page=rit360-solidario#/lgpd"]
screenshots: [auditoria-lgpd]
source_docs: [solidario-privacy-ropa.md, solidario-privacy-ropa.md#26, solidario-privacy-ropa.md#27, solidario-privacy-ropa.md#29]
last_verified: 2026-09-14
status: publicado
---

# Auditoria LGPD

O RIT360 Solidário foi desenhado com a LGPD em mente. A tela **Auditoria LGPD**
reúne a trilha de ações sobre dados pessoais e um resumo das bases legais do
tratamento.

![Auditoria LGPD](/assets/img/auditoria-lgpd.png)

## O que a tela mostra

- Um **aviso com o resumo do tratamento** de dados e um link para a página de
  **Privacidade e bases legais** (o ROPA — registro de operações de tratamento).
- Uma **tabela somente leitura** com os últimos eventos: data, doador, ação, IP e
  o conteúdo (payload) de cada registro.

> 💡 **Nota — a OSC é a controladora**
>
> Quem responde pelos dados dos doadores é a **sua organização** (a controladora).
> A RIT/V3RTECH fornece o software. Esta tela ajuda você a demonstrar
> conformidade, mas as decisões e a responsabilidade sobre os dados são da OSC.

## Como o doador exerce os direitos dele

Um ponto importante: **a anonimização é feita pelo próprio doador**, no
[Portal do doador](/modulos/portal-do-doador/) — não pelo administrador. Lá o
doador pode revogar comunicações e **excluir/anonimizar os próprios dados**, com
dupla confirmação.

Ao anonimizar, os dados pessoais são substituídos por valores anônimos, mas os
**registros de doação são preservados** de forma anônima — porque a legislação
fiscal exige a guarda por alguns anos. O doador deixa de receber comunicações, e a
ação fica registrada nesta trilha de auditoria.

> 💡 **O que é mantido — e por quê**
>
> Os **recibos fiscais já emitidos são mantidos como estão** na anonimização: não
> são apagados nem alterados. A lei fiscal obriga a organização a guardar o recibo
> (o documento) por alguns anos, e a LGPD permite reter um dado quando há
> **obrigação legal**. Por isso, ao confirmar a exclusão, o doador vê um aviso
> explícito de que os recibos serão retidos — e esta trilha de auditoria **registra
> a retenção dos recibos**.

> ⚠️ **Atenção**
>
> Se um doador pedir a exclusão dos dados por e-mail, oriente-o a fazer isso pelo
> **portal do doador** (ele acessa por magic link, sem senha). É lá que a
> anonimização acontece, com a devida confirmação.

## Menos dado pessoal guardado (melhorias de bastidor)

Duas melhorias de privacidade funcionam **sozinhas**, sem nada para configurar. Elas
reduzem a quantidade de dado pessoal que fica guardado nos registros de auditoria e
de acesso.

- **A auditoria registra só o que mudou, não os valores.** Quando um doador altera os
  próprios dados (nome, telefone, endereço), o registro passa a guardar **apenas
  quais campos foram alterados** — não mais o conteúdo antigo e novo em texto plano.
  A trilha continua completa, sem duplicar o dado pessoal fora do cadastro do doador.
- **IP e navegador são apagados após 6 meses.** O plugin **remove automaticamente** o
  **IP** e o **navegador (user-agent)** dos registros de auditoria e de acesso com
  mais de **6 meses**, mantendo o restante do histórico. É automático — não precisa
  ativar nada. (Quem faz a manutenção técnica do site pode ajustar esse prazo.)

## Boas práticas de privacidade

> ✅ **Boas práticas**
>
> - Publique a **Política de Privacidade da sua OSC** e aponte para ela no
>   checkout (o consentimento do doador referencia essa política).
> - Exporte dados pessoais só quando necessário e prefira as versões
>   **mascaradas**.
> - Não compartilhe listas de doadores fora da organização.
