# Repositório de Automações com n8n

[![n8n](https://img.shields.io/badge/Feito%20com-n8n-blueviolet?logo=n8n)](https://n8n.io/)
[![Tipo](https://img.shields.io/badge/Tipo-Automação-orange)](https://n8n.io/)
[![Linguagem](https://img.shields.io/badge/Linguagem-JSON-lightgrey)](https://www.json.org/)

Este repositório contém um workflow pronto para uso com a plataforma de automação n8n. O objetivo é compartilhar meus primeiros experimentos.

## 📜 Pré-requisitos

Para utilizar estes workflows, você precisa ter:

1.  **Uma instância do n8n rodando**: Seja via n8n.cloud, self-hosted com Docker, ou qualquer outro método.
2.  **Acesso às contas dos serviços utilizados**: Por exemplo, para um workflow do Google Sheets, você precisará de uma conta Google e acesso ao Google Cloud Console para gerar as credenciais.

## 🔑 Configuração de Credenciais (Exemplo: Google Sheets)

Os workflows neste repositório requerem que você configure suas próprias credenciais dentro da sua instância do n8n. As credenciais **NÃO** são armazenadas aqui.

**Para configurar o acesso ao Google Sheets, siga os passos abaixo:**

1.  **Acesse sua instância do n8n.**
2.  No menu lateral esquerdo, navegue até **Credentials**.
3.  Clique no botão **Add credential**.
4.  Na barra de busca, digite `Google Sheets` e selecione a opção "Google Sheets OAuth2 API".
5.  Uma janela de configuração de credenciais será aberta. É **nesta tela** que você deverá inserir as variáveis obtidas no Google Cloud Console.

    > ### Onde Inserir suas Chaves
    >
    > -   **`Client ID`**: Cole o seu "ID do cliente" OAuth 2.0 neste campo.
    > -   **`Client Secret`**: Cole o seu "Segredo do cliente" OAuth 2.0 neste campo.
    >
    > ![Exemplo da tela de credenciais do N8N](https://i.imgur.com/K1U1u2B.png)

6.  **Importante**: A tela de credenciais do n8n mostrará uma **"OAuth Redirect URL"**. Você deve copiar esta URL e adicioná-la na seção "URIs de redirecionamento autorizados" da sua credencial OAuth 2.0 no Google Cloud Console para que a autenticação funcione.
7.  Clique em **"Sign in with Google"** e siga o processo para conectar sua conta.
8.  Salve a credencial.

## 🚀 Como Usar os Workflows

1.  **Clone este repositório ou faça o download dos arquivos:**
    ```bash
    git clone [https://github.com/seu-usuario/seu-repositorio.git](https://github.com/seu-usuario/seu-repositorio.git)
    ```
    Ou simplesmente baixe o arquivo `.json` desejado da pasta `workflows/`.

2.  **Importe o workflow no n8n:**
    -   Vá para a seção **Workflows** na sua instância do n8n.
    -   Clique em **Import from File**.
    -   Selecione o arquivo `.json` do workflow que você baixou.

3.  **Associe as Credenciais:**
    -   Abra o workflow recém-importado.
    -   Encontre os nós que precisam de autenticação (ex: o nó "Google Sheets").
    -   No campo "Credential", selecione a credencial que você configurou no passo anterior.

4.  **Ative o Workflow:**
    -   Salve as alterações e ative o workflow no botão "Active" no canto superior direito.

Pronto! Sua automação está configurada e pronta para rodar.