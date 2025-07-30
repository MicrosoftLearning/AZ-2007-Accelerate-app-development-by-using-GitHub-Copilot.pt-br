---
demo:
  title: 'Demonstração: Configurar as extensões do GitHub Copilot para Visual Studio Code'
  module: 'Module 1: Get started with GitHub Copilot'
---

# Demonstração: Configurar as extensões do GitHub Copilot para Visual Studio Code

## Instruções

As atividades de demonstração são projetadas para um ambiente que inclui os seguintes recursos:

- Visual Studio Code.
- A extensão do kit de desenvolvimento em C# para o Visual Studio Code.
- As extensões do GitHub Copilot e do GitHub Copilot Chat para Visual Studio Code. É necessária uma conta do GitHub com uma assinatura ativa do GitHub Copilot.
- Projetos de amostras de código criadas usando C#.

**OBSERVAÇÃO**: Recomendamos que os instrutores considerem usar sua própria conta do GitHub e a assinatura do GitHub Copilot para as demonstrações. Isso irá permitir que você controle e personalize seu ambiente de desenvolvimento. Também facilitará o ajuste das demonstrações para atender às necessidades de suas salas de aula.

**IMPORTANTE**: Se você optar por executar as demonstrações no ambiente de laboratório hospedado em vez do seu computador de instrutor, poderá descompactar os aplicativos de exemplo no ambiente hospedado. Você precisará configurar as extensões do GitHub Copilot no ambiente hospedado antes de executar as demonstrações. Você pode perceber que o ambiente hospedado é mais lento do que o seu ambiente local, então talvez precise ajustar o ritmo das demonstrações de acordo.

### Apresentar a demonstração

As configurações do GitHub Copilot são definidas em sua conta GitHub.com e no ambiente do Visual Studio Code. No Visual Studio Code, você acessa as configurações do GitHub Copilot e do GitHub Copilot Chat usando o menu de status do GitHub Copilot.

As configurações no Visual Studio Code permitem habilitar ou desabilitar o GitHub Copilot para linguagens específicas, configurar o comportamento do GitHub Copilot Chat e personalizar a experiência do GitHub Copilot para atender às suas preferências. Você também pode definir as configurações do GitHub Copilot no GitHub.com para gerenciar sua assinatura do GitHub Copilot, configurar a retenção de prompts e sugestões e permitir ou bloquear sugestões correspondentes ao código público.

## Habilitar ou desabilitar o GitHub Copilot

O GitHub Copilot é habilitado por padrão quando você instala a extensão no Visual Studio Code. Você pode desabilitar o GitHub Copilot por um período de tempo, se necessário.

Para mostrar as opções habilitar e desabilitar a extensão do GitHub Copilot, siga estas etapas:

1. No Visual Studio Code, abra o modo de exibição de **Extensões**.

1. Na lista de extensões instaladas, role para baixo até encontrar **GitHub Copilot**.

1. Para exibir um menu suspenso para a extensão do GitHub Copilot que lista as opções Habilitar e Desabilitar, selecione no ícone de engrenagem ao lado do GitHub Copilot.

Se você quiser demonstrar as opções de habilitar/desabilitar, poderá selecionar a opção de desabilitar. No entanto, certifique-se de reabilitar o GitHub Copilot antes de continuar com esta demonstração.

## Configurar o GitHub Copilot e o Chat do Copilot no Visual Studio Code

As extensões do GitHub Copilot são definidas com configurações padrão quando você instala as extensões no Visual Studio Code. Você pode personalizar essas configurações para atender às suas preferências.

O Visual Studio Code fornece duas maneiras de acessar as configurações das extensões do GitHub Copilot:

- Você pode usar o ícone `Manage` para abrir a guia Configurações do Visual Studio Code. Na guia Configurações, você pode selecionar **Extensões** e, em seguida, selecionar **Copilot**.
- Você pode usar o ícone de status do GitHub Copilot para acessar o menu de status do GitHub Copilot e selecionar **Editar configurações**.

Demonstre o uso do menu de status do GitHub Copilot para acessar as configurações. Isso abre a guia de Configurações do Visual Studio Code com as configurações filtradas para o GitHub Copilot. Usar o menu de status é a maneira mais rápida de acessar as configurações das extensões do GitHub Copilot.

### Definir as configurações do GitHub Copilot

Para mostrar as configurações do GitHub Copilot, siga estas etapas:

1. No painel inferior da janela do Visual Studio Code, para abrir o menu de status do GitHub Copilot, selecione o ícone de status do GitHub Copilot.

    O ícone de status do GitHub Copilot indica se o GitHub Copilot está habilitado ou desabilitado. Quando habilitada, a cor da tela de fundo do ícone corresponde à cor da barra de status. Quando desabilitada, a cor da tela de fundo do ícone contrasta com a cor da barra de status.

1. No menu de status do GitHub Copilot, selecione **Editar configurações**.

1. Reserve um minuto para examinar a lista de configurações disponíveis.

    Observe que as configurações do GitHub Copilot e do Chat do GitHub Copilot estão listadas. Além disso, no rótulo Extensões à esquerda, ambas as extensões são rotuladas como Copilot. A primeira extensão do Copilot é para o GitHub Copilot e a segunda é para o Chat do GitHub Copilot.

1. No rótulo Extensões, selecione a primeira extensão do Copilot.

    Observe que a lista de configurações agora está filtrada apenas para o GitHub Copilot.

    As configurações do GitHub Copilot incluem as seguintes opções:

    - Habilitar Conclusões automáticas
    - Habilitar ou desabilitar conclusões do Copilot para idiomas especificados

1. Reserve um minuto para examinar as configurações de **Habilitar ou desabilitar conclusões do Copilot para idiomas especificados**.

    Observe que as configurações dessa opção são configuradas usando uma lista de idiomas e um valor de **verdadeiro** ou **falso** para habilitar ou desabilitar o GitHub Copilot para cada idioma. Por padrão, o GitHub Copilot está habilitado para todos os idiomas. Essa configuração é especificada com o caractere curinga `*` na primeira linha e o valor **verdadeiro**. As linhas subsequentes especificam idiomas para os quais o GitHub Copilot está habilitado ou desabilitado. Por exemplo, o GitHub Copilot está habilitado para **C#**, **JavaScript** e **Python** e desabilitado para **Texto não criptografado** e **Markdown**.

1. Em **Habilitar ou desabilitar conclusões do Copilot para idiomas especificados**, selecione **Markdown**.

    Observe que o valor de Markdown está definido como **falso**. Isso significa que o GitHub Copilot está desabilitado para arquivos Markdown.

1. Para habilitar o Copilot para arquivos Markdown, selecione **Editar Item** (ícone de lápis), selecione **false**, altere o valor para **true**e selecione **OK**.

    Agora você pode usar projetos de documentos do GitHub Copilot usando arquivos Markdown.

1. No rótulo Extensões, selecione a segunda extensão do Copilot.

    Observe que a lista de configurações agora está filtrada apenas para o Chat do GitHub Copilot.

    As configurações do Chat do GitHub Copilot incluem opções **Versão prévia** e **Experimental**. Entre as opções de configuração estão:

    - **Corrigir Falha de Teste**: Essa opção é habilitada por padrão para que o GitHub Copilot possa fornecer sugestões para corrigir falhas de teste.
    - **Acompanhamentos**: Por padrão, essa configuração é definida como **firstOnly**, o que significa que o GitHub Copilot fornece sugestões de acompanhamento somente após a primeira sugestão. As outras opções são **sempre** e **nunca**.
    - **Substituição Local**: Por padrão, essa opção é definida como **automática**, o que significa que o GitHub Copilot usa a localidade da linguagem de exibição do Visual Studio Code.
    - **Seleção de Escopo**: Essa opção é desabilitada por padrão. Quando habilitado, o usuário é solicitado a criar um símbolo de escopo quando o usuário usa `/explain` no Chat sem nada selecionado no Editor.
    - **Localização do Chat do Terminal**: A configuração padrão é chatView, que especifica a Exibição de Chat. As outras opções são para a área de Chat Rápido e o Terminal.
    - **Usar Modelos de Projeto**: Essa opção é habilitada por padrão para que o GitHub Copilot use modelos de projeto relevantes do GitHub quando o usuário usa `/new` no Chat.
    - **Habilitar Ações de Código**: Essa opção é habilitada por padrão para que o GitHub Copilot possa fornecer ações de código no Editor.
    - **Disparar Automaticamente**: Essa opção é habilitada por padrão para que as sugestões do GitHub Copilot sejam mostradas automaticamente conforme você digita.

    É recomendável manter as configurações padrão durante este treinamento. Isso ajuda a garantir que você tenha a experiência esperada ao trabalhar nos módulos neste roteiro de aprendizagem. Ao concluir o treinamento, você pode experimentar essas configurações para personalizar sua experiência com o Chat do GitHub Copilot e do Copilot.

## Definir as configurações do GitHub Copilot no GitHub.com

As configurações da conta do GitHub no GitHub.com incluem opções para configurar o GitHub Copilot. Você também pode definir as configurações do GitHub Copilot no GitHub.com para gerenciar sua assinatura do GitHub Copilot, configurar a retenção de prompts e sugestões e permitir ou bloquear sugestões correspondentes ao código público.

O GitHub Copilot pode ser gerenciado por meio de contas pessoais com o GitHub Copilot Individual ou por meio de contas da organização com o GitHub Copilot Business/Enterprise.

## Atalhos de teclado para o GitHub Copilot

Você pode usar os atalhos de teclado padrão no Visual Studio Code ao usar o GitHub Copilot. Como alternativa, você pode reassociar os atalhos no editor de Atalhos de Teclado usando os atalhos de teclado preferidos de cada comando específico.
