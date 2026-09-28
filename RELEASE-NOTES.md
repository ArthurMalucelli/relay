# Relay 1.0.0 — prévia de 28/09/2026

Build **`09bf98c9fa03`** · macOS Apple Silicon · [Instalação](https://github.com/ArthurMalucelli/relay/blob/main/INSTALL.md)

**[Baixar ZIP](https://github.com/ArthurMalucelli/relay/releases/download/v1.0.0-preview.20260928/Relay-1.0.0-09bf98c9fa03-arm64.zip)** · [Download pelo Terminal](https://github.com/ArthurMalucelli/relay/blob/main/INSTALL.md#baixar-pelo-terminal-opcional) · [DMG alternativo](https://github.com/ArthurMalucelli/relay/releases/download/v1.0.0-preview.20260928/Relay-1.0.0-09bf98c9fa03-arm64.dmg)

## Incluído

- Conversas persistentes, busca, renomeação, arquivamento/restauração e rascunhos separados.
- Codex e Claude Code pelos runtimes oficiais, com catálogo de modelos e níveis de raciocínio compatíveis.
- Aprovações por conversa, modo automático quando suportado, Dangerous mode e Stop.
- Arquivos e imagens anexados; Markdown e fórmulas nas respostas.
- Navegação e criação de conversa durante execução, indicação imediata de envio e preparação sob demanda.
- Continuidade entre agentes com contexto público limitado e referências locais para histórico longo.
- Biblioteca de skills, plugins e MCP, instalação/importação explícita e configuração privada por provedor.
- Importação de registros MCP simples do Claude JSON e do Codex TOML; entradas com segredos/campos incompatíveis não são copiadas silenciosamente.

## Verificado localmente

- 612 testes automatizados, typecheck e build aprovados.
- Interface integrada em Electron: 18 fases / 64 verificações offline; biblioteca/importação: 11 verificações em cenário focado.
- Aceitação nativa dos dois agentes: skills, plugins, MCP local, aprovação/recusa, reinício e remoção de extensões; 15 verificações e 10 prompts curtos.
- 22 verificações de instalação com perfil vazio, usando o DMG identificado abaixo, no Mac de desenvolvimento. Esse ensaio não completou um novo login externo.
- Integridade profunda do bundle e da cópia dentro do DMG aprovada.
- ZIP extraído e comparado ao app dentro do DMG: 6.361 arquivos e 14 links simbólicos iguais, permissões/quarentena preservadas e integridade profunda aprovada. Nenhuma nova autenticação ou inferência foi feita nesse teste de empacotamento.

## Ainda não confirmado

- Instalação, login e uso por outra pessoa em outro Mac.
- OAuth de um serviço MCP externo em navegador; MCP de plugin Claude não oferece login pela rota atual.
- Abertura de um download sem avisos de segurança: candidato com assinatura ad hoc, sem Developer ID/notarização; avaliação Gatekeeper rejeitada.
- Confirmação do alcance das condições Anthropic para distribuir esta integração baseada no Agent SDK e no login por assinatura.

Essa é uma prévia para teste, não uma declaração de produção concluída. O manifesto mantém `distributable: false`, refletindo a ausência de assinatura/notarização e a avaliação macOS.

## Downloads

**Principal:** `Relay-1.0.0-09bf98c9fa03-arm64.zip` · 348.105.110 bytes

SHA-256: `4e21c641573e619828277c6f17d695813171c690ad29b60b4004ecff4de10009`

Descompacte e mova **Relay.app** para **Aplicativos**. Não é necessário clonar o repositório nem compilar.

**Alternativa:** `Relay-1.0.0-09bf98c9fa03-arm64.dmg` · 400.815.369 bytes

SHA-256: `e95d7d7a8262a6ecbcf11e7cd379c1a0f69a55390aaf2bb98995cc9903263a90`

Componentes embutidos: Codex 0.153.4, Claude Code 2.1.281, Claude Agent SDK 0.3.281 e Electron 44.4.5. O instalador não depende do checkout de desenvolvimento nem de uma instalação global desses runtimes.
