# Roteiro de capturas — Manual RIT360 Solidário

Ambiente: **dev-wp** (`http://localhost:3080/`), OSC de exemplo "Instituto
Esperança", dados fictícios semeados. Viewport **1920×1080** em todas.
Destino dos arquivos: `manual/assets/img/`.

> **Recaptura 2026-07-21 (plugin v2.24.0):** todas as telas de **admin** foram
> refeitas contra a UI **React** (migração #18) — cada tela tem o cabeçalho com
> logo + seção + "RIT360 Solidário · vX.Y.Z" e os botões "Manual do usuário"/
> "Enviar feedback" no canto superior direito. **O selo de versão aparece em cada
> print → recapturar TODO o admin a cada bump de versão.** As superfícies públicas
> reusaram o CSS existente (visualmente idênticas). `api-chaves.png` passou a ser
> capturada (estado "Expirada" + entrega de webhook "failed" com tooltip de erro).

> **v2.25.0 (issue #59):** `projetos.png` recapturada com o campo Categoria visível
> (`Doações › Nome do projeto`), no cenário dos três projetos. Capturada também
> `projetos-mobile.png` (375×812) — primeira captura mobile deste manual; estender
> a convenção mobile ao resto é decisão do Bruno.


## Pendências de recaptura (fazer junto da próxima implementação)

Ambas foram migradas para React (F3b) mas **ficaram fora da recaptura de 2026-07-21**
(não estavam na lista pedida e exigem estado específico). Os prints atuais mostram a
UI PHP antiga. Recapturar quando houver a próxima mexida no plugin:

| Arquivo | Rota / estado necessário | Deve mostrar |
|---|---|---|
| `setup-wizard.png` | `…?page=bs-setup` — exige o plugin em **modo setup** (ou reabrir o assistente) | Passo 1 do assistente (Organização) na UI React v2.24.0+ |
| `produto-doacao.png` | editar o produto de doação (ex.: `/wp-admin/post.php?post=67&action=edit`), aba **"Configuração de Doação"** | Metabox do WooCommerce (valores, valor livre, frase de impacto, vídeo) na UI atual |

## Regras
- **Admin** (área `/wp-admin/`): capturar **logado** (a barra do WordPress pode
  aparecer — é a área administrativa).
- **Front-end** (`/doe`, transparência, portal do doador, checkout): capturar
  **deslogado do wp-admin** (um doador real NÃO vê a barra preta do WordPress).
  Usar contexto limpo / cookies zerados.
- Esperar a tela carregar antes de capturar. Preferir viewport (não fullPage),
  exceto onde indicado "página inteira".

## Admin — logado

| Arquivo | Rota | Deve mostrar |
|---|---|---|
| `painel.png` | `/wp-admin/admin.php?page=rit360-solidario` | KPIs + Top 10 doadores |
| `doadores-lista.png` | `…?page=rit360-solidario-donors` | Busca, tabela de doadores, ações em lote, blocos de exportação (página inteira) |
| `doador-detalhe.png` | clicar num doador da lista (ex.: Roberto Nascimento) | Dados + Recibos + Declarações |
| `projetos.png` | `…?page=rit360-solidario-projetos` | Lista de projetos com meta/campanha/padrão/**categoria** (`Doações › Nome do projeto`) + form "Novo projeto" (página inteira) |
| `campanhas.png` | `…?page=rit360-solidario-campanhas` | Lista de campanhas com progresso vs meta |
| `prestacao-contas.png` | `…?page=rit360-solidario-prestacao-contas` | Filtro de período + totais + quebra por campanha/projeto + evolução (página inteira) |
| `config-organizacao.png` | `…?page=rit360-solidario-settings&tab=organizacao` | Formulário de dados da OSC |
| `config-visual.png` | `…&tab=visual` | Cores + preview |
| `config-lembretes.png` | `…&tab=lembretes` | Ativar lembretes + intervalo + envio manual |
| `config-emails.png` | `…&tab=emails` | Templates (assunto+corpo TinyMCE) + botão único "Salvar todos os templates" (página inteira) |
| `config-pdf.png` | `…&tab=pdf` | Cabeçalho/rodapé/recibo/declaração + pré-visualizar (página inteira) |
| `config-avancado.png` | `…&tab=avancado` | Reset de rate limit do magic link |
| `auditoria-lgpd.png` | `…?page=rit360-solidario-lgpd` | Aviso ROPA + tabela de auditoria |
| `shortcodes-tela.png` | `…?page=rit360-solidario-shortcodes` | Referência dos shortcodes em cards (tag + exemplo copiável + parâmetros), página inteira — v2.7.0 |
| `setup-wizard.png` | `…?page=bs-setup` | Passo 1 do Setup Wizard (Organização) |
| `produto-doacao.png` | editar produto 67 (`/wp-admin/post.php?post=67&action=edit`), aba "Configuração de Doação" | Campos: valores, valor livre, frase de impacto, vídeo |
| `feedback-modal.png` | qualquer tela do plugin → clicar "Enviar feedback" | Modal de feedback |

## API e integrações — `api-chaves.png` (capturada em v2.24.0)

Rota: menu **RIT360 Solidário → Shortcodes e API → API** (submenu "API"). Página inteira,
admin logado, 1920×1080. A tela agrupa numa só captura: **endereço base**, **Nova chave**
(rótulo + escopos + validade), **Chaves** (com estados *Ativa*/*Expirada*/*Revogada*),
**Novo destino** de webhook, **Webhooks** e **Últimas entregas** (com entrega *failed* +
tooltip de erro). Referenciada em `modulos/api-integracoes.md` (front-matter `screenshots:
[api-chaves]`).

Prints ainda **opcionais** (não capturados; a página é referência técnica e já ilustra o
essencial com `api-chaves.png`):

| Arquivo (sugerido) | Rota / ação | Deve mostrar |
|---|---|---|
| `api-chave-criada.png` | após criar uma chave | Aviso "copie agora, aparece uma única vez" com a chave |

## Front-end — deslogado (sem barra do WordPress)

| Arquivo | Rota / ação | Deve mostrar |
|---|---|---|
| `doe-pagina.png` | `http://localhost:3080/doe/` | Imagem/título/frase de impacto + valores + "Doar agora" + vídeo + descrição (página inteira) |
| `checkout-doacao.png` | em `/doe`, escolher R$ 50 → "Doar agora" → checkout | Rótulos "Doar agora"/"Valor da doação", campo CPF, consentimento LGPD, "doar anonimamente" |
| `checkout-doacao-pj.png` | no checkout, marcar **"Pessoa jurídica"** no seletor | Seletor "Você está doando como: Pessoa física / Pessoa jurídica" com PJ marcado + campo **CNPJ** + dica de preencher "Empresa" (razão social) |
| `transparencia.png` | `http://localhost:3080/transparencia-teste/` | Cards de campanhas/projetos com arrecadado + barra de meta (sem nomes de doadores) |
| `portal-login.png` | `http://localhost:3080/minhas-doacoes/` | Formulário "Acessar meu painel" (e-mail + "Receber link") |
| `portal-doacoes.png` | portal logado (magic link donor 11) → aba "Minhas doações" | Histórico + "Baixar PDF" |
| `portal-dados.png` | aba "Meus dados" | Formulário editável (e-mail/CPF bloqueados) + zona de perigo |
| `portal-declaracao.png` | aba "Declaração anual" | Exercício + "Baixar declaração" |
| `portal-preferencias.png` | aba "Preferências" | Opt-in de lembretes |
| `portal-consentimentos.png` | aba "Consentimentos" | Consentimento c/ data + revogar + histórico |
| `portal-anonimizacao.png` | aba "Consentimentos" → botão de excluir/anonimizar dados → **tela/modal de confirmação** | ⏳ **pendente (v2.13.1)** — o novo aviso explícito: "os dados serão anonimizados, mas os **recibos fiscais já emitidos são mantidos**" + os dois passos de dupla confirmação. Doador demo (magic link donor 11). NÃO confirmar a exclusão de verdade (é definitiva) — capturar só a tela de aviso. |

### Magic link do portal (uso único — gerar fresco no contexto limpo)
```bash
docker exec dev-wp wp --allow-root eval '
global $wpdb; $b=random_bytes(32);
$plain=rtrim(strtr(base64_encode($b),"+/","-_"),"=");
$wpdb->insert($wpdb->prefix."bs_magic_links",[
 "donor_id"=>11,"token_hash"=>hash("sha256",$plain),
 "created_at"=>current_time("mysql"),
 "expires_at"=>date("Y-m-d H:i:s",time()+86400),
 "ip_address"=>"127.0.0.1","user_agent"=>"capture"]);
echo "http://localhost:3080/minhas-doacoes/?rit360sol_token=".$plain."\n";'
```
Navegar a URL retornada UMA vez; a sessão do doador fica ativa por cookie para as 5 abas.
