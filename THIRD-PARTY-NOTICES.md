# Componentes, marcas e condições

Relay é um aplicativo independente. Não é produto oficial nem parceiro da OpenAI, Anthropic ou Apple. Os nomes dos provedores identificam os componentes usados e pertencem aos respectivos titulares.

| Componente | Versão no pacote | Referência |
|---|---|---|
| Codex | 0.153.4 | [Projeto oficial, Apache-2.0](https://github.com/openai/codex) |
| Claude Code | 2.1.281 | [Condições oficiais da Anthropic](https://code.claude.com/docs/en/legal-and-compliance) |
| Claude Agent SDK | 0.3.281 | [Documentação e condições do SDK](https://code.claude.com/docs/en/agent-sdk/overview) |
| Electron | 44.4.5 | [Projeto oficial](https://github.com/electron/electron) |

O pacote conserva os arquivos de licença dos componentes. No Finder, clique com o botão direito em **Relay.app → Mostrar Conteúdo do Pacote**. Os avisos principais estão em `Contents/Resources/THIRD-PARTY-LICENSES`; dependências adicionais preservam suas licenças nas respectivas pastas do pacote.

## Claude: funcionamento e autorização são verificações distintas

O binário original do Claude Code é embutido sem modificação e executado pelo Agent SDK. A autenticação completa o fluxo oficial no próprio computador, usando a conta do usuário. Login e inferência por assinatura funcionaram nos testes locais do Relay.

A [documentação do Claude Code](https://code.claude.com/docs/en/legal-and-compliance) descreve condições para produtos que pré-instalam/executam o binário original e permite o login do usuário final nesse binário, sob esse enquadramento. A [documentação do Agent SDK](https://code.claude.com/docs/en/agent-sdk/overview) também estabelece uma condição de aprovação para terceiros oferecerem login Claude.ai/limites de assinatura em seus produtos.

O enquadramento específico do Relay permanece pendente de confirmação; o funcionamento técnico não equivale a autorização. Esta publicação não afirma aprovação da Anthropic, não aceita contratos por terceiros e não oferece API como substituição do login por assinatura. Cada usuário continua sujeito às condições do seu provedor.

## Código e licenças deste repositório

Este repositório publica documentação e artefatos de teste. Não contém o código-fonte completo do aplicativo e não concede uma licença de código aberto para o Relay. As licenças de terceiros continuam sendo as de seus respectivos componentes.
