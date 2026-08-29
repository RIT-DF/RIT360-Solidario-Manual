---
title: "Licença"
nav_order: 13
parent: "Módulos"
permalink: /modulos/licenca/
task: modulo-licenca
role: admin
routes: ["#/wp-admin/admin.php?page=rit360-solidario-license"]
screenshots: [licenca]
source_docs: [PRODUCT.md]
last_verified: 2026-08-28
status: publicado
---

# Licença

> 💡 **Por que isso importa**
>
> O RIT360 Solidário **funciona sem licença** — não existe funcionalidade paga que trave. A
> licença serve para uma coisa só: **liberar as atualizações automáticas**, inclusive as de
> correção de bugs e segurança. Enquanto a licença não estiver ativada, o site continua
> recebendo o plugin na versão instalada, mas **não recebe nada de novo** — nem quando sai
> um ajuste que corrige um problema sério. Ative logo depois de instalar.

## Onde fica

Menu **RIT360 Solidário → Licença**.

![Licença — nenhuma ativada](/assets/img/licenca.png)

## Como ativar

1. Abra **RIT360 Solidário → Licença**.
2. No bloco **Ativar licença**, cole a **chave de licença** (formato `V3RL-XXXX-XXXX-XXXX-XXXX`) no
   campo **Chave de licença**.
3. Clique em **Ativar**.

> ⚠️ **A chave completa só aparece nesta tela, no momento da ativação.** Depois disso, o
> sistema sempre mostra a versão mascarada (por exemplo `V3RL-XXXX-...-B428`) — guarde a
> chave original em lugar seguro (ex.: no e-mail de compra ou em um gerenciador de senhas)
> caso precise reativar em outro site.

## O que cada campo mostra

| Campo | O que significa |
|---|---|
| **Status** | *Nenhuma licença ativada*, *Ativa* ou o motivo de recusa (chave inválida, expirada, limite atingido). |
| **Chave** | A chave mascarada, depois de ativada. |
| **Expira em** | A data-limite da assinatura. Depois dela, a licença para de renovar sozinha e as atualizações voltam a parar. |
| **Ativações** | Quantos domínios já usam essa chave, sobre o limite contratado (ex.: `0/1`). |
| **Última verificação** | Quando o plugin conferiu pela última vez, junto ao servidor da V3RTECH, se a licença continua válida. |

## Ativações por domínio

Uma mesma licença pode valer para **vários sites**, até o limite contratado — cada domínio
ativado ocupa uma vaga. Para trocar de servidor ou liberar uma vaga para outro site, use
**Desativar licença** no site antigo antes de ativar no novo: **desativar libera a vaga**
na hora.

> 💡 **Ambiente de teste não consome cota.** Um site de homologação/desenvolvimento
> reconhecido como tal pelo servidor de licenças não ocupa vaga de ativação — pode manter a
> licença ativada ali sem gastar uma das ativações contratadas.

## Quando dá errado

| Mensagem / situação | O que fazer |
|---|---|
| **Chave inválida** ou recusada | Confira se copiou a chave inteira, sem espaços extras. Chaves não usam a letra `O` nem o número `0` de forma ambígua — confira caractere a caractere se digitou à mão. |
| **Limite de ativações atingido** | Desative a licença em um site que não usa mais essa chave (**Desativar licença** naquele site), ou contrate um plano com mais ativações. |
| **Licença expirada** | Renove a assinatura; depois de renovada, clique em **Verificar agora** nesta tela para atualizar o status sem esperar a próxima checagem automática. |
| **Servidor de licenças indisponível** | O plugin continua funcionando normalmente com a última verificação válida; tente **Verificar agora** de novo em alguns minutos. Se persistir por mais de um dia, fale com o suporte. |

## Armadilhas

- **Achar que licença vencida "desliga" o plugin.** Não desliga. O que para é só o fluxo de
  atualização — o site continua arrecadando, emitindo recibos e funcionando normalmente.
- **Deixar a licença nunca ativada.** É o erro mais caro: parece inofensivo porque nada
  quebra, mas o site fica anos sem receber correção de segurança sem ninguém perceber.
