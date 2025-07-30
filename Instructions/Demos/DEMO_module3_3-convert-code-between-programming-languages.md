---
demo:
  title: 'Demonstração: Converter código de uma linguagem de programação para outra'
  module: 'Module 3: Develop code features using GitHub Copilot tools'
---

# Demonstração: Converter código de uma linguagem de programação para outra

## Instruções

As atividades de demonstração são projetadas para um ambiente que inclui os seguintes recursos:

- Visual Studio Code.
- A extensão do kit de desenvolvimento em C# para o Visual Studio Code.
- As extensões do GitHub Copilot e do GitHub Copilot Chat para Visual Studio Code. É necessária uma conta do GitHub com uma assinatura ativa do GitHub Copilot.
- Projetos de amostras de código criadas usando C#.

**OBSERVAÇÃO**: Recomendamos que os instrutores considerem usar sua própria conta do GitHub e a assinatura do GitHub Copilot para as demonstrações. Isso irá permitir que você controle e personalize seu ambiente de desenvolvimento. Também facilitará o ajuste das demonstrações para atender às necessidades de suas salas de aula.

**IMPORTANTE**: Se você optar por executar as demonstrações no ambiente de laboratório hospedado em vez do seu computador de instrutor, poderá descompactar os aplicativos de exemplo no ambiente hospedado. Você precisará configurar as extensões do GitHub Copilot no ambiente hospedado antes de executar as demonstrações. Você pode perceber que o ambiente hospedado é mais lento do que o seu ambiente local, então talvez precise ajustar o ritmo das demonstrações de acordo.

### Apresentar a demonstração

O GitHub Copilot pode ajudá-lo a converter código de uma linguagem de programação para outra. Por exemplo, você pode pedir ao GitHub Copilot para converter uma função ou snippet de código em outra linguagem de programação.

Você pode concluir os seguintes tipos de conversões de código usando o GitHub Copilot:

- Converta um arquivo de código inteiro em outra linguagem de programação.
- Converter uma função em outra linguagem de programação.
- Converta um snippet de código em outra linguagem de programação.

Cada uma das interfaces de chat (exibição de chat, janela chat rápido e chat embutido) pode ser usada para converter código entre linguagens de programação. Sua escolha de interface de chat depende da sua preferência e da complexidade do código que você deseja converter.

Suponha que você esteja apenas começando no projeto `QuarterlyIncomeReport`. Você discute as metas do projeto com um colega. Eles mencionam que eles têm um arquivo Python que pode fornecer alguns dos recursos que você está procurando. Eles apontam o repositório para o código Python. Você decide abrir o projeto de código do Python no Visual Studio Code e usar o modo de exibição chat para converter o código Python em C#.

## Converter código entre linguagens de programação usando o modo de exibição chat

1. Abra a pasta do projeto **APL2007M3Python** no Visual Studio Code.

    Este projeto contém uma versão do Python do projeto `QuarterlyIncomeReport` em que você trabalhou durante este módulo. Você pode fazer com que o GitHub Copilot explique o código usando o modo de exibição chat ou explique esta ação inteligente.

1. Executar o aplicativo Python.

    Observe que a saída do aplicativo Python é essencialmente a mesma que a saída do aplicativo C# que você criou anteriormente.

1. Abra o arquivo Python `main.py`.

    O arquivo Python contém uma função que gera dados de vendas. Você deseja converter esse código Python em C#.

1. Selecione todo o conteúdo do arquivo.

1. Abra o modo de exibição de Chat e, em seguida, insira o seguinte prompt:

    ```plaintext
    Convert #selection to C#
    ```

1. Reserve um momento para examinar a resposta do GitHub Copilot.

    A resposta deve conter a versão em C# do código Python que você selecionou.

1. Abra uma segunda instância do Visual Studio Code.

1. Abra o modo de exibição de Chat, insira o seguinte prompt:

    ```plaintext
    @workspace /new console application in C# NET8 named APL2007M3B. Only .cs and .csproj files. Enable ImplicitUsings and Nullable
    ```

    Se Copilot responder com uma mensagem de erro sobre o "argumento de caminho", tente o mesmo prompt novamente.

1. Selecione **Criar Workspace**

1. Na caixa de diálogo Abrir Pasta, selecione a pasta **Área de Trabalho** e selecione **Selecionar como Pasta Pai**.

    aguarde até que o workspace seja criado.

1. Quando o workspace for criado, selecione **Program.cs**e exclua o conteúdo do arquivo.

1. Alterne para a instância do Visual Studio Code que contém o código Python.

1. Role até a parte superior do modo de exibição de Chat e clique no botão **Copiar** para copiar o código C# gerado para a área de transferência.

1. Alterne para a instância do Visual Studio Code que contém o código C#.

1. Cole o código C# no arquivo Program.cs.

1. Salve o arquivo Program.cs.

1. Execute o aplicativo C#.

    Observe que a saída do aplicativo C# é essencialmente a mesma que a saída do aplicativo Python.

    Se você tiver tempo, leve alguns minutos para examinar as diferenças entre o código C# convertido e o código C# da unidade anterior.

## Converter código entre linguagens de programação usando o chat embutido

1. Volte para a instância do Visual Studio Code que contém o projeto Python que você abriu anteriormente.

1. Selecione o código no arquivo main.py.

1. Abra o chat embutido e insira o seguinte prompt:

    ```plaintext
    Convert #selection to C#
    ```

1. Examine a resposta do GitHub Copilot e selecione **Aceitar**.

    O arquivo Python agora deve conter código C#.

1. Copie o código C# gerado para a área de transferência.

1. Feche o arquivo main.py sem salvar as alterações.

1. Alterne para a instância do Visual Studio Code que contém o projeto C# e abra o arquivo Program.cs.

1. Para substituir o código C# existente, cole o código C# da área de transferência (convertida do Python usando chat embutido) sobre o conteúdo do arquivo Program.cs.

1. Salve o arquivo Program.cs.

1. Execute o aplicativo C#.

    Observe que a saída do aplicativo C# é essencialmente a mesma que a saída do aplicativo Python.

Ao usar o GitHub Copilot para converter código entre linguagens de programação, tente a conversão no modo de exibição chat e no chat embutido. Embora ambas as ferramentas compartilhem o mesmo modelo de IA, seus resultados podem ser diferentes. Experimentar ambas as ferramentas pode ajudá-lo a determinar qual ferramenta é melhor para seu caso de uso específico.

> [!NOTE]
> Linguagens de programação geralmente têm um "estilo de programação" associado, e algumas linguagens podem ter recursos ou bibliotecas de código exclusivos. Quando você estiver convertendo grandes seções de código de uma linguagem de programação para outra, é importante entender completamente a linguagem de programação de destino e a intensão do código. As sugestões do GitHub Copilot sempre devem ser revisadas antes de aceitar.

### Resumo

Nesta demonstração, você usou o GitHub Copilot para converter o código Python em C#. Você usou o modo de exibição de chat e o chat embutido para converter o código Python em C#. Em seguida, você executou o aplicativo C# para verificar se a saída era a mesma que a saída do aplicativo Python. Usando o GitHub Copilot para converter código entre linguagens de programação, você pode adaptar rapidamente o código de uma linguagem para outra. Lembre-se de revisar o código convertido para garantir que ele atenda aos seus requisitos e que ele siga o estilo de programação da linguagem de destino.
