---
demo:
  title: 'Demonstração: Gerar documentação do projeto usando o GitHub Copilot Chat'
  module: 'Module 2: Generate documentation using GitHub Copilot tools'
---

# Demonstração: Gerar documentação do projeto usando o GitHub Copilot Chat

## Instruções

As atividades de demonstração são projetadas para um ambiente que inclui os seguintes recursos:

- Visual Studio Code.
- A extensão do kit de desenvolvimento em C# para o Visual Studio Code.
- As extensões do GitHub Copilot e do GitHub Copilot Chat para Visual Studio Code. É necessária uma conta do GitHub com uma assinatura ativa do GitHub Copilot.
- Projetos de amostras de código criadas usando C#.

**OBSERVAÇÃO**: Recomendamos que os instrutores considerem usar sua própria conta do GitHub e a assinatura do GitHub Copilot para as demonstrações. Isso irá permitir que você controle e personalize seu ambiente de desenvolvimento. Também facilitará o ajuste das demonstrações para atender às necessidades de suas salas de aula.

**IMPORTANTE**: Se você optar por executar as demonstrações no ambiente de laboratório hospedado em vez do seu computador de instrutor, poderá descompactar os aplicativos de exemplo no ambiente hospedado. Você precisará configurar as extensões do GitHub Copilot no ambiente hospedado antes de executar as demonstrações. Você pode perceber que o ambiente hospedado é mais lento do que o seu ambiente local, então talvez precise ajustar o ritmo das demonstrações de acordo.

### Apresentar a demonstração

A criação de documentação é uma parte importante do desenvolvimento de software. A documentação embutida ajuda os desenvolvedores a entender a base de código, sua finalidade e como usá-la. A documentação do projeto fornece às partes interessadas informações essenciais para entender o escopo e a finalidade do projeto.

A documentação do projeto geralmente inclui as seguintes seções:

- **Visão geral do projeto**: Um resumo de alto nível do projeto, sua finalidade e suas metas.
- **Requisitos do projeto**: Uma lista dos requisitos do projeto, incluindo requisitos funcionais e não funcionais.
- **Restrições de projeto**: Quaisquer restrições que afetem o projeto, como tempo, orçamento ou restrições técnicas.
- **Dependências do projeto**: Uma lista das dependências do projeto, incluindo bibliotecas, estruturas e outros componentes dos quais o projeto depende.
- **Resumo do Projeto**: Um breve resumo do projeto, sua finalidade e suas metas.

Nesta demonstração, você irá usar o GitHub Copilot Chat para gerar a documentação do projeto `APL2007M2Sample1`.

> [!IMPORTANT]
> Os instrutores devem enfatizar a importância de revisar a documentação sugerida pelo GitHub Copilot. Os desenvolvedores devem verificar a precisão e a integridade. A documentação gerada pelo GitHub Copilot é um ponto de partida. Talvez seja necessário adicionar, remover ou modificar o conteúdo para atender às necessidades específicas do seu projeto.

### Gerar documentação do projeto para o projeto APL2007M2Sample1

A documentação do projeto pode ser gerada no Visual Studio Code usando o modo de exibição chat e participante `@workspace`. Você pode incluir descrições de linguagem natural para gerar seções específicas da documentação do projeto, como a visão geral do projeto, requisitos, restrições, dependências e resumo. Você também pode usar o GitHub Copilot Chat para gerar tipos específicos de arquivos de documentação, como um arquivo `readme.md`.

1. Verifique se o projeto `APL2007M2Sample1` está aberto no Visual Studio Code.

1. Para abrir o modo de exibição de chat, selecione **Abrir Chat**.

1. No modo de exibição chat, para gerar a documentação do workspace, insira o seguinte prompt:

    ```output
    @workspace document this project
    ```

1. Reserve um minuto para examinar a documentação do projeto gerada para o projeto `APL2007M2Sample1`.

    Observe que a documentação do projeto sugerida é semelhante à explicação do projeto gerada na unidade anterior.

    Ao acrescentar prompts como "documentar as restrições do projeto" ou "documentar as dependências do projeto", você pode obter informações detalhadas sobre o projeto.

1. No modo de exibição chat, para gerar a documentação que descreve as dependências do projeto, insira o seguinte prompt:

    ```output
    @workspace document the project dependencies
    ```

1. Reserve um minuto para examinar a documentação de dependências do projeto.

    A resposta gerada pelo Copilot Chat deve ser semelhante às seguintes informações:

    GitHub Copilot Chat pode ajudá-lo a documentar qualquer aspecto de seus projetos. Você pode usar o modo de exibição chat para gerar documentação para arquivos, classes ou funções específicos dentro do projeto. O tamanho e a complexidade do projeto ajudam a determinar o nível de detalhes necessários.

    Se o tempo permitir, use o modo de exibição de Chat para gerar documentação para as seguintes seções de projeto:

    - Requisitos do projeto
    - Restrições de projeto
    - Arquitetura do projeto
    - Design do projeto
    - Teste de projeto
    - Implantação do projeto
    - Resumo do projeto

    Você pode adaptar a documentação do projeto gerada pelo Copilot Chat às necessidades específicas do seu projeto e de seus stakeholders.

1. No modo de exibição chat, para gerar um README para o projeto `APL2007M2Sample1`, insira o seguinte prompt:

    ```output
    @workspace generate a readme document that can be used as a repo description
    ```

1. Reserve um minuto para examinar o README gerado para o projeto `APL2007M2Sample1`.

    O conteúdo do arquivo README gerado pelo Copilot Chat fornece uma visão geral de alto nível do projeto com várias seções que geralmente são incluídas nesse tipo de arquivo.

    Você pode ajustar o prompt para especificar seções específicas do LEIAME. Você também pode escrever prompts individuais para gerar seções específicas de um documento README.

    > [!NOTE]
    > Se desejar que o documento README seja formatado como um arquivo markdown, você poderá inserir um prompt semelhante ao seguinte: `generate readme project documentation formatted using a raw markdown format`. Se o GitHub Copilot estiver configurado para funcionar com arquivos Markdown, você pode usar o recurso de chat embutido para formatar o documento LEIAME como um arquivo Markdown.

### Resumo

Nesta demonstração, você usou o GitHub Copilot Chat para gerar a documentação do projeto `APL2007M2Sample1`. Usando o modo de exibição chat e o participante `@workspace`, você conseguiu gerar documentação para a visão geral do projeto, requisitos, restrições, dependências e resumo. Você também gerou um arquivo README para o projeto `APL2007M2Sample1`. Usando o Copilot Chat para gerar a documentação do projeto, você pode criar uma visão geral de alto nível que ajuda outros desenvolvedores a entender o projeto e suas metas. Lembre-se de revisar a documentação gerada pelo Copilot Chat para garantir a precisão e a integridade.
