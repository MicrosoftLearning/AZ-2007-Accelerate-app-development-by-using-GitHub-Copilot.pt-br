---
demo:
  title: 'Demonstração: Gerar explicações de código usando o GitHub Copilot Chat'
  module: 'Module 2: Generate documentation using GitHub Copilot tools'
---

# Demonstração: Gerar explicações de código usando o GitHub Copilot Chat

## Instruções

As atividades de demonstração são projetadas para um ambiente que inclui os seguintes recursos:

- Visual Studio Code.
- A extensão do kit de desenvolvimento em C# para o Visual Studio Code.
- As extensões do GitHub Copilot e do GitHub Copilot Chat para Visual Studio Code. É necessária uma conta do GitHub com uma assinatura ativa do GitHub Copilot.
- Projetos de amostras de código criadas usando C#.

**OBSERVAÇÃO**: Recomendamos que os instrutores considerem usar sua própria conta do GitHub e a assinatura do GitHub Copilot para as demonstrações. Isso irá permitir que você controle e personalize seu ambiente de desenvolvimento. Também facilitará o ajuste das demonstrações para atender às necessidades de suas salas de aula.

**IMPORTANTE**: Se você optar por executar as demonstrações no ambiente de laboratório hospedado em vez do seu computador de instrutor, poderá descompactar os aplicativos de exemplo no ambiente hospedado. Você precisará configurar as extensões do GitHub Copilot no ambiente hospedado antes de executar as demonstrações. Você pode perceber que o ambiente hospedado é mais lento do que o seu ambiente local, então talvez precise ajustar o ritmo das demonstrações de acordo.

### Apresentar a demonstração

O GitHub Copilot Chat usa a assistência de IA de conversa e comandos inteligentes para ajudar você com tarefas relacionadas à codificação. Um exemplo é a capacidade de explicar código desconhecido e complexo.

Você pode usar o Chat do GitHub Copilot para gerar explicações por vários motivos. Por exemplo:

- O Chat do GitHub Copilot pode explicar um espaço de trabalho inteiro ou arquivos de projeto específicos quando você ingressar em um projeto existente.
- O Chat do GitHub Copilot pode explicar seções ou linhas de código específicas quando o código é complexo ou difícil de entender.
- O Chat do GitHub Copilot pode explicar erros no seu código e sugerir maneiras de corrigi-los.
- O Chat do GitHub Copilot pode explicar como adicionar recursos ao seu projeto e fornecer snippets de código que demonstram como implementar o novo código.

### Explicações de arquivo de projeto e workspace

O GitHub Copilot Chat pode ajudá-lo a entender novos projetos ou arquivos de projeto específicos. Você pode usar uma combinação de `@workspace` `/explain`, e `#file` na Modo de exibição de chat ou na janela de Chat Rápido para gerar uma explicação do projeto ou arquivos de projeto específicos.

Use as seguintes etapas para concluir esta seção da demonstração:

1. Abra a pasta **APL2007M2Sample1** no Visual Studio Code.

    1. Abra o Visual Studio Code no computador.
    1. No Visual Studio Code, no menu **Arquivo**, selecione **Abrir Pasta**.
    1. Navegue até a pasta Área de Trabalho do Windows, abra a pasta **SampleApps** e localize a pasta **APL2007M2Sample1**.
    1. Selecione **APL2007M2Sample1** e selecione **Selecionar Pasta**.

    A exibição do exploração do Visual Studio Code deve mostrar um projeto de código APL2007M2Sample1 contendo os seguintes arquivos:

    - APL2007M2Sample1.csproj
    - APL2007M2Sample1.sln
    - App.xaml
    - App.xaml.cs
    - MainWindow.xaml
    - MainWindow.xaml.cs

1. Na barra de menu superior do Visual Studio Code, selecione **Abrir Chat**.

    O botão Abrir Chat está localizado na barra de menus no topo da janela do Visual Studio Code, à direita da Caixa de Pesquisa. Ele exibe um pequeno logotipo do GitHub Copilot.

1. Use o seguinte comando para pedir ao Copilot Chat para explicar o projeto `APL2007M2Sample1`:

    ```plaintext
    @workspace Explain this project
    ```

1. Reserve um minuto para examinar a resposta na Modo de exibição de chat.

    O Chat do GitHub Copilot gera uma explicação do projeto APL2007M2Sample1 semelhante à seguinte resposta:

    > [!IMPORTANT]
    > O Chat do GitHub Copilot usa um modelo de IA para gerar respostas. As respostas que você recebe são semelhantes às respostas mostradas neste treinamento, mas não são idênticas.

1. Na parte inferior da Modo de exibição de chat, observe que o GitHub Copilot Chat sugeriu uma pergunta de acompanhamento.

    Sua resposta pode incluir uma pergunta complementar diferente.

    O GitHub Copilot Chat mantém um histórico da conversa de chat. O histórico ajuda o GitHub Copilot Chat a entender seus interesses. À medida que você cria um histórico de chat, o modelo de IA aprende com suas interações e fornece perguntas de acompanhamento mais relevantes. Não é recomendável explorar perguntas complementares "aleatórias".

1. Abra o arquivo `MainWindow.xaml.cs` no editor.

1. Use o seguinte comando para pedir ao Copilot para explicar o arquivo `MainWindow.xaml.cs`:

    ```plaintext
    @workspace /explain #file:MainWindow.xaml.cs
    ```

1. Reserve um minuto para examinar a resposta na Modo de exibição de chat.

    Observe que o GitHub Copilot Chat gera uma explicação detalhada do arquivo `MainWindow.xaml.cs`. A explicação inclui informações sobre a finalidade, a estrutura e os principais componentes do arquivo. Você também pode ver uma seção que descreve possíveis problemas e aprimoramentos.

    Mais uma vez, o GitHub Copilot Chat sugere uma pergunta de acompanhamento.

    > [!IMPORTANT]
    > O GitHub Copilot Chat mantém um histórico da conversa de chat. À medida que você continua a fazer perguntas, ele refina suas respostas adequadamente. O contexto de suas perguntas, especialmente em relação ao seu projeto de código, influencia as respostas subsequentes do GitHub Copilot Chat. Isso ajuda a fornecer respostas mais precisas e relevantes. Isso também significa que a resposta que você recebe para uma pergunta específica provavelmente variará com base no histórico da conversa.

### Explicações de código selecionadas

Até mesmo desenvolvedores experientes encontram códigos difíceis de entender. Em vez de gastar tempo tentando decifrar um código complexo, você pode pedir ao GitHub Copilot Chat para fornecer uma explicação. O Modo de exibição de chat, o chat embutido e as ações inteligentes podem ser usados para gerar explicações para linhas de código ou seções selecionadas.

Nesta seção da demonstração, você usará a ação inteligente **Explicar** para gerar uma explicação das linhas de código selecionadas.

1. Verifique se você abriu o arquivo `MainWindow.xaml.cs` no editor.

1. Role para baixo para localizar o método `SumPageSizesAsync()`.

    ```csharp

    private async Task SumPageSizesAsync()
    {
        var stopwatch = Stopwatch.StartNew();
        IEnumerable<Task<int>> downloadTasksQuery =
            from url in _urlList
            select ProcessUrlAsync(url, _client);
        Task<int>[] downloadTasks = downloadTasksQuery.ToArray();
        int[] lengths = Task.WhenAll(downloadTasks);
        int total = lengths.Sum();
        await Dispatcher.BeginInvoke(() =>
        {
            stopwatch.Stop();
    
            _resultsTextBox.Text += $"\nTotal bytes returned:  {total:#,#}";
            _resultsTextBox.Text += $"\nElapsed time:          {stopwatch.Elapsed}\n";
        });
    }

    ```

1. Selecione as seguintes linhas de código e, em seguida, use a ação inteligente **Explicar** para gerar uma explicação.

    Para selecionar a ação inteligente **Explicar**, clique com o botão direito nas linhas de código selecionadas, selecione **Copilot** e, em seguida, selecione **Explicar** no menu de contexto.

    ```csharp

    IEnumerable<Task<int>> downloadTasksQuery =
        from url in _urlList
        select ProcessUrlAsync(url, _client);
    Task<int>[] downloadTasks = downloadTasksQuery.ToArray();

    ```

1. Reserve um minuto para examinar a resposta na Modo de exibição de chat.

1. Observe o nível das informações detalhadas na explicação.

    O Chat do GitHub Copilot gera explicações detalhadas que incluem informações sobre as linhas de código selecionadas, sua finalidade e como elas funcionam. As respostas incluem snippets de código e descrições de linguagem natural que ajudam você a entender o código.

### Explicações de erro

O gerenciamento de erros é um aspecto essencial do desenvolvimento de software. Alguns erros são fáceis de detectar e corrigir, enquanto outros podem ser mais desafiadores. Quando você encontra um erro difícil de entender em seu código, você pode pedir ao GitHub Copilot Chat para fornecer uma explicação. Por exemplo, você pode pedir ao GitHub Copilot Chat para explicar por que uma linha de código específica está causando um erro.

Use as seguintes etapas para concluir esta seção da demonstração:

1. Verifique se você abriu `MainWindow.xaml.cs` no editor.

1. No método `SumPageSizesAsync()`, localize a seguinte linha de código:

    ```csharp
    int[] lengths = Task.WhenAll(downloadTasks);
    ```

1. Passe o cursor do mouse sobre `downloadTasks` para exibir a mensagem de erro.

    Mensagens de erro nem sempre explicam como corrigir problemas de codificação. Quando a solução não for óbvia, você poderá pedir ao GitHub Copilot Chat para explicar um erro e sugerir maneiras de corrigi-lo.

1. Selecione a linha de código que contém o erro e pressione **Ctrl+I** para abrir um chat embutido.

1. Para gerar uma explicação para o erro, insira o seguinte prompt:

    ```plaintext
    /explain why is the selection causing an error
    ```

1. Reserve um minuto para examinar a resposta na Modo de exibição de chat.

    Observe que a resposta inclui informações sobre o erro e sugestões para corrigi-lo. Nesse caso, o GitHub Copilot Chat explica que a linha `Task.WhenAll(downloadTasks)` está causando um erro porque está faltando a palavra-chave `await`. A resposta também fornece um snippet de código que mostra como corrigir o erro adicionando `await` a palavra-chave antes da linha `Task.WhenAll(downloadTasks)`.

1. Use as explicações fornecidas pelo GitHub Copilot Chat para corrigir os erros em seu código.

    Adicione a palavra-chave `await` antes da linha `Task.WhenAll(downloadTasks)`, conforme mostrado no seguinte snippet de código:

    ```csharp
    int[] lengths = await Task.WhenAll(downloadTasks);
    ```

    Depois de fazer essa alteração, o erro deve ser resolvido.

### Novas explicações de funcionalidade ou recurso

O Chat do GitHub Copilot pode explicar como adicionar novos recursos ou funcionalidade ao projeto.

Considere o projeto APL2007M2Sample1. Seu código baixa páginas da Web e calcula o tamanho total das páginas baixadas. Suponha que você precise adicionar tratamento de exceção ao aplicativo. Nesta seção da demonstração, você usa o GitHub Copilot Chat para explicar como gerenciar exceções durante o processo de download.

Use as seguintes etapas para concluir esta seção da demonstração:

1. Selecione as linhas de código que incluem os métodos `SumPageSizesAsync` e `ProcessUrlAsync`.

1. No Modo de exibição de chat, para que o GitHub Copilot Chat explique como lidar com exceções geradas durante o processo de download, insira a seguinte pergunta:

    ```plaintext
    @workspace /explain #MainWindow.xaml.cs How can I handle exceptions thrown during the download process?
    ```

1. Reserve um minuto para examinar a resposta na Modo de exibição de chat.

    O Copilot Chat gera uma resposta semelhante à seguinte explicação:

    A resposta fornece uma explicação detalhada de como lidar com exceções geradas durante o processo de download. Você também obtém um snippet de código que implementa o código de tratamento de exceção sugerido. Você pode copiar o snippet de código ou inseri-lo em seu projeto de código no local do cursor.

    Em vez de copiar ou inserir o snippet de código do modo de exibição de Chat, a próxima etapa investiga o uso do chat embutido para implementar o código de tratamento de exceção sugerido.

1. Para perguntar ao chat embutido como implementar um tratamento de exceção, selecione o método `ProcessUrlAsync`, pressione **Ctrl+I** e insira a seguinte solicitação:

    ```plaintext
    How can I handle exceptions thrown during the download process?
    ```

1. Reserve um minuto para examinar a resposta embutida.

1. Para aceitar o código de tratamento de erro proposto, selecione **Aceitar**.

    Observe que o bloco `try-catch` proposto é implementado.

### Resumo

Nesta demonstração, você usou o GitHub Copilot Chat para gerar explicações sobre linhas de código, erros e novos recursos. O GitHub Copilot Chat fornece um conjunto poderoso de recursos que podem ajudá-lo a aumentar rapidamente o novo projeto. Usando o chat embutido e a Modo de exibição de chat, você pode obter ajuda do GitHub Copilot Chat sem sair do ambiente do Visual Studio Code. O modelo de IA do GitHub Copilot Chat gera respostas precisas e úteis que podem ajudá-lo a se tornar um desenvolvedor mais eficiente e eficaz.
