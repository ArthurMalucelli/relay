# Instalar o Relay no Mac

[← Página principal](README.md)

## 1. Confira seu Mac

Abra **menu Apple → Sobre Este Mac**. Em **Chip**, deve aparecer um chip Apple, como M1, M2, M3 ou posterior. Este download não é para Macs Intel. O aplicativo declara macOS 13 como mínimo.

Use sua própria conta com acesso ao Codex/Claude Code pelo respectivo provedor. Você pode conectar apenas um agente. O suporte à assinatura Claude está em teste e tem a condição de distribuição descrita na [página principal](README.md#limites-desta-versão).

## 2. Baixe o aplicativo

**[Baixar Relay.zip para Apple Silicon](https://github.com/ArthurMalucelli/relay/releases/download/v1.0.0-preview.20260928/Relay-1.0.0-09bf98c9fa03-arm64.zip)**

Se abrir a página da versão, expanda **Assets** e escolha **`Relay-1.0.0-09bf98c9fa03-arm64.zip`**. “Source code (zip)” e “Source code (tar.gz)” contêm apenas esta documentação; não são o aplicativo.

## 3. Instale

1. Dê dois cliques no `.zip` na pasta **Downloads** para descompactar.
2. Mova o **Relay.app** extraído para **Aplicativos** no Finder.
3. Abra o Finder, vá a **Aplicativos** e abra **Relay**.

### Baixar pelo Terminal (opcional)

Este comando baixa o mesmo ZIP e abre o descompactador do macOS quando o download terminar. Não clona código, não compila e não instala dependências.

```sh
curl --fail --location 'https://github.com/ArthurMalucelli/relay/releases/download/v1.0.0-preview.20260928/Relay-1.0.0-09bf98c9fa03-arm64.zip' \
  --output "$HOME/Downloads/Relay-1.0.0-09bf98c9fa03-arm64.zip" &&
open "$HOME/Downloads/Relay-1.0.0-09bf98c9fa03-arm64.zip"
```

Depois, mova **Downloads → Relay.app** para **Aplicativos** e abra. Se o navegador já tiver descompactado o ZIP, use o app extraído diretamente.

**Sobre `git clone`:** clonar este repositório baixa a documentação, não o aplicativo. Não há etapa de `npm install` ou compilação para usar o Relay.

### Alternativa: DMG

O **[DMG](https://github.com/ArthurMalucelli/relay/releases/download/v1.0.0-preview.20260928/Relay-1.0.0-09bf98c9fa03-arm64.dmg)** continua disponível com o mesmo aplicativo: abra, arraste **Relay.app** para **Applications / Aplicativos** e ejete a imagem depois de instalar.

### Aviso de segurança do macOS

Esta prévia não tem assinatura Developer ID nem notarização Apple. O Mac pode mostrar “A Apple não pôde verificar…” ou recusar a abertura. Não trate isso como instalação concluída: registre o texto do alerta e [reporte o problema](https://github.com/ArthurMalucelli/relay/issues/new), com sua versão do macOS.

Não remova a quarentena por Terminal nem desative o Gatekeeper para seguir este roteiro. As explicações da Apple sobre cada alerta e as decisões disponíveis ao dono do Mac estão em **[Abrir apps com segurança no Mac](https://support.apple.com/pt-br/102445)**. Se o aviso disser que o app está danificado ou contém software malicioso, interrompa a instalação e reporte; não tente ignorá-lo.

Uma abertura sem esse obstáculo depende de um futuro pacote assinado e notarizado. Esta prévia ainda não oferece essa garantia.

## 4. Entre na sua conta

1. Abra **Contas**, no canto inferior da barra lateral.
2. Clique em **Entrar com ChatGPT** para Codex ou **Entrar com Claude** para Claude Code.
3. Conclua o login na página oficial que abre no navegador, incluindo MFA ou consentimento quando solicitado pelo provedor.
4. Volte ao Relay e confira o estado da conta antes de enviar uma mensagem.

Não envie seu código de login a ninguém. O Relay não exige que você cole chave de API, copie credenciais de outro app ou edite arquivos. Se a página não abrir, use a ação para reabrir a página de login quando estiver disponível em **Contas**.

## 5. Faça um teste curto

1. Crie **Nova conversa** e mantenha **Sem projeto**.
2. Escolha um agente conectado e um modelo disponível. Use **Solicitar aprovação**.
3. Envie **“Responda apenas: Relay funcionando.”** e aguarde a resposta.
4. Crie uma segunda conversa e escreva um rascunho, sem enviar. Volte à primeira: as mensagens devem continuar nela.
5. Se você conectou os dois agentes, troque o agente da primeira conversa e pergunte **“Qual foi minha primeira mensagem nesta conversa?”**.
6. Quando não houver execução em andamento, feche e reabra o Relay. Confira as duas conversas e o rascunho.

Cada mensagem usa sua conta e está sujeita aos limites do provedor. O teste não compra créditos nem altera seu plano.

## Problemas comuns

| O que aconteceu | O que fazer |
|---|---|
| O macOS impediu a abertura | Leia o [aviso de segurança](#aviso-de-segurança-do-macos) acima e reporte o alerta exato. |
| Apareceu uma versão antiga | Feche a versão ociosa e abra **Finder → Aplicativos → Relay**. Confira o build em **Contas**; nesta prévia ele é `09bf98c9fa03`. |
| Conta não conectou | Confira a página oficial de login e volte a **Contas**. Não compartilhe tokens ou códigos. |
| Limite de uso atingido | Confira seu plano no provedor. O Relay não aumenta esse limite nem troca para faturamento por API. |
| Um modelo não está disponível | Escolha explicitamente outro modelo oferecido pelo agente, ou confira seu acesso no provedor. |
| Uma extensão pediu novo login | As extensões usam um perfil próprio do Relay; conclua seu login oficial nesse perfil. |
| Uma extensão/MCP falhou | Abra **Extensões**, confira compatibilidade e status. Desative a extensão para testar a conversa sem ela; reporte o erro sem credenciais. |

## Atualizar depois

Aguarde as execuções terminarem, feche o Relay, baixe o novo ZIP de [Releases](https://github.com/ArthurMalucelli/relay/releases), descompacte e substitua o app em **Aplicativos**. Os dados são guardados separadamente em `~/Library/Application Support/Relay`; não apague essa pasta ao atualizar. Não há atualizador automático nesta prévia.

## Reportar o teste

Na [issue](https://github.com/ArthurMalucelli/relay/issues/new), informe:

- Chip e versão do macOS.
- Build mostrado em **Contas**.
- Se instalou e abriu normalmente ou qual aviso apareceu.
- Quais agentes conectou e se recebeu a primeira resposta.
- Se a segunda conversa, a troca de agente e o reinício funcionaram.

Não é necessário informar seu e-mail de login. Não anexe arquivos de credenciais ou o diretório completo do perfil.
