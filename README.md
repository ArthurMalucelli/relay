# Relay

**Codex e Claude Code em um app para Mac.** Converse, trabalhe com arquivos e troque de agente mantendo o histórico público da conversa.

**[Baixar Relay.zip para Mac](https://github.com/ArthurMalucelli/relay/releases/download/v1.0.0-preview.20260928/Relay-1.0.0-09bf98c9fa03-arm64.zip)** · [Guia de instalação](INSTALL.md) · [Baixar pelo Terminal](INSTALL.md#baixar-pelo-terminal-opcional) · [Versões](https://github.com/ArthurMalucelli/relay/releases) · [Reportar problema](https://github.com/ArthurMalucelli/relay/issues/new)

## Antes de instalar

| Você precisa de | Detalhe |
|---|---|
| Mac com Apple Silicon | Chip Apple M1 ou posterior. Intel, Windows e Linux não têm instalador nesta versão. |
| macOS 13 ou posterior | Mínimo declarado pelo aplicativo; não há teste em todas essas versões. |
| Internet e sua própria conta | Conta com acesso ao Codex pelo ChatGPT e/ou ao Claude Code pela assinatura Claude. |
| Aplicativo pronto em ZIP · aproximadamente 348 MB | Os componentes necessários à conversa já estão incluídos. DMG também disponível em Releases. |

Não é necessário instalar Node, Homebrew ou CLIs, abrir Terminal, clonar código ou configurar JSON para conversar. A disponibilidade de modelos e o consumo seguem as regras e limites da sua conta em cada provedor. O Relay não inclui uma assinatura, não oferece uso ilimitado e não tem alternativa de inferência por chave de API.

## Instalar e começar

1. **[Baixe o arquivo `.zip`](https://github.com/ArthurMalucelli/relay/releases/download/v1.0.0-preview.20260928/Relay-1.0.0-09bf98c9fa03-arm64.zip)** e dê dois cliques para descompactar. Não escolha “Source code”: esse ZIP contém apenas a documentação do repositório.
2. Mova **Relay.app** para **Aplicativos** no Finder.
3. Abra **Aplicativos → Relay**. Se o macOS impedir, consulte [Aviso de segurança do macOS](INSTALL.md#aviso-de-segurança-do-macos).
4. No Relay, abra **Contas** e escolha **Entrar com ChatGPT** ou **Entrar com Claude**. Complete você mesmo o login na página oficial aberta no navegador e volte ao app. É possível começar com um agente só; veja a ressalva Claude abaixo.
5. Escolha o agente e o modelo no compositor. Para testar, envie: **“Responda apenas: Relay funcionando.”**

Cada pessoa entra com as próprias contas. O instalador não leva o perfil, as credenciais ou as conversas do desenvolvedor.

Prefere Terminal? Use o [comando de download](INSTALL.md#baixar-pelo-terminal-opcional). **`git clone` não instala o Relay:** este repositório hospeda a documentação; o aplicativo pronto está nos arquivos da versão.

## O que você pode testar

| Recurso | Como usar |
|---|---|
| Conversas persistentes | Crie, busque, renomeie, arquive e restaure pela barra lateral. |
| Agentes e modelos | Escolha Codex ou Claude Code no compositor. O catálogo depende do runtime e da conta. |
| Raciocínio | Ajuste o nível quando o modelo oferecer essa opção. |
| Arquivos e imagens | Use o botão **+** para anexar conteúdo. |
| Pasta do projeto | Escolha uma pasta ou mantenha **Sem projeto**, que usa uma pasta própria. |
| Aprovações | Escolha **Solicitar aprovação**, **Aprovar por mim** ou **Dangerous mode**, conforme o agente permitir. |
| Extensões | Abra **Extensões** para instalar/importar skills, plugins e servidores MCP compatíveis. |
| Continuidade | Troque de agente na mesma conversa; o Relay transfere contexto público e referências locais do histórico. |

Para o primeiro teste, mantenha **Solicitar aprovação**. **Dangerous mode** permite executar ações sem a revisão normal, incluindo comandos fora da pasta do projeto. Use apenas quando você entender e aceitar esse acesso. O modo automático e as permissões disponíveis variam entre os agentes; MCP no Claude ainda pede aprovação no modo automático.

As extensões são revisadas antes de instalar e começam desativadas. O Relay mantém sua própria configuração, preserva a origem importada e pode pedir outro login oficial ao ativar o perfil de extensões. Programas exigidos por um MCP de terceiros não vêm necessariamente no instalador.

## Seus dados

Conversas, rascunhos e configuração do Relay ficam no seu Mac, em `~/Library/Application Support/Relay`. A inferência é executada pelos componentes oficiais dos provedores: mensagens, anexos e conteúdo usado por ferramentas podem ser enviados ao provedor escolhido ou aos serviços MCP que você ativar. Armazenamento local não significa processamento offline.

Trocar de agente compartilha com o destino o contexto público necessário à conversa. O Relay não transfere raciocínio privado. Não há sincronização de conversas entre computadores nesta versão.

## Limites desta versão

- **Instalação macOS:** a avaliação Gatekeeper rejeitou o candidato no Mac de desenvolvimento. A integridade do pacote passou, mas isso não equivale à notarização nem garante abertura em outro Mac. O [guia](INSTALL.md#aviso-de-segurança-do-macos) explica como reportar o aviso.
- **Integração Claude:** login e respostas pela assinatura funcionaram nos testes locais. Isso não comprova autorização de distribuição: a documentação distingue o uso do binário Claude Code original das condições para produtos que usam o Agent SDK. A confirmação aplicável ao Relay continua pendente. Não há alegação de aprovação, parceria ou endosso da Anthropic. [Fontes e componentes](THIRD-PARTY-NOTICES.md).
- **Validação externa:** instalação, login e uso por outra pessoa em outro Mac ainda não foram confirmados.
- **Extensões:** compatibilidade varia por provedor. OAuth de um serviço MCP externo em navegador ainda não foi validado; login de MCP fornecido por plugin Claude não é suportado pela rota atual. Importação de configurações com credenciais ou campos incompatíveis exige cadastro próprio.
- **Histórico longo:** a troca utiliza contexto limitado e referências locais ao excedente. Não é transferência integral da sessão interna do outro provedor e não usa JEV.
- **Atualizações:** por enquanto são manuais, baixando a versão desejada em Releases.

## Identificação do download

| Campo | Valor |
|---|---|
| Versão | 1.0.0 — prévia de 28/09/2026 |
| Build do aplicativo | `09bf98c9fa03` |
| Arquivo principal | `Relay-1.0.0-09bf98c9fa03-arm64.zip` |
| Tamanho exato do ZIP | 348.105.110 bytes |
| SHA-256 do ZIP | `4e21c641573e619828277c6f17d695813171c690ad29b60b4004ecff4de10009` |

ZIP e DMG contêm o mesmo aplicativo. A extração do ZIP preservou os **6.361 arquivos, 14 links simbólicos, permissões e integridade de assinatura** do app no DMG. A rodada final do aplicativo registrou **612 testes automatizados** e **22 verificações de instalação pelo DMG em perfil vazio no mesmo Mac**. Houve também aceitação real com os dois agentes, skills, plugins e MCP local, incluindo aprovações e reinício. Isso não substitui o teste em outro Mac. [Notas da versão](RELEASE-NOTES.md) · [Manifesto dos downloads](release-manifest.json) · [Checksums do ZIP e DMG](SHA256SUMS.txt).

## Encontrou um problema?

Abra uma [issue](https://github.com/ArthurMalucelli/relay/issues/new) com o modelo/chip do Mac, versão do macOS, build mostrado em **Contas**, o que você fez e a mensagem de erro. Se usar uma captura, oculte informações pessoais. Não publique senhas, códigos de login, tokens, conversas privadas nem arquivos do perfil.

Este repositório contém a documentação de instalação e os downloads do Relay. O código-fonte do aplicativo e o histórico privado de desenvolvimento não fazem parte deste repositório. Relay é um projeto independente, sem afiliação com OpenAI, Anthropic ou Apple.
