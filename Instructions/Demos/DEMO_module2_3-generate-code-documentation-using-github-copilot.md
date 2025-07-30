---
demo:
  title: 'Demonstração: Gerar documentação de código embutido usando o GitHub Copilot Chat'
  module: 'Module 2: Generate documentation using GitHub Copilot tools'
---

# Demonstração: Gerar documentação de código embutido usando o GitHub Copilot Chat

## Instruções

As atividades de demonstração são projetadas para um ambiente que inclui os seguintes recursos:

- Visual Studio Code.
- A extensão do kit de desenvolvimento em C# para o Visual Studio Code.
- As extensões do GitHub Copilot e do GitHub Copilot Chat para Visual Studio Code. É necessária uma conta do GitHub com uma assinatura ativa do GitHub Copilot.
- Projetos de amostras de código criadas usando C#.

**OBSERVAÇÃO**: Recomendamos que os instrutores considerem usar sua própria conta do GitHub e a assinatura do GitHub Copilot para as demonstrações. Isso irá permitir que você controle e personalize seu ambiente de desenvolvimento. Também facilitará o ajuste das demonstrações para atender às necessidades de suas salas de aula.

**IMPORTANTE**: Se você optar por executar as demonstrações no ambiente de laboratório hospedado em vez do seu computador de instrutor, poderá descompactar os aplicativos de exemplo no ambiente hospedado. Você precisará configurar as extensões do GitHub Copilot no ambiente hospedado antes de executar as demonstrações. Você pode perceber que o ambiente hospedado é mais lento do que o seu ambiente local, então talvez precise ajustar o ritmo das demonstrações de acordo.

### Apresentar a demonstração

A documentação do seu código é um aspecto importante do processo de desenvolvimento de software. A documentação embutida (comentários no código) ajuda os desenvolvedores a entender a base de código, sua finalidade e como usá-la.

O GitHub Copilot Chat pode ajudá-lo a documentar seu código de maneira rápida e precisa. Você tem algumas opções para gerar documentação embutida usando o GitHub Copilot Chat:

- Construa sua própria solicitação em linguagem natural que pode ser usada para gerar a documentação específica para o seu código.
- Use o comando `/doc` durante uma sessão de chat embutida para gerar comentários para o código selecionado.
- Use a ação inteligente **Gerar Documentos** para gerar comentários para o código selecionado.

Documentar corretamente seu código cria uma base de código mais legível e de fácil manutenção, que é mais fácil de ser compreendida e trabalhada por outros desenvolvedores

### Gerar documentação de código embutido usando o modo de exibição chat

Nesta demonstração, você irá usar o GitHub Copilot Chat para gerar a documentação de código embutido para o projeto `APL2007M2Sample1`.

Use as seguintes etapas para concluir esta seção da demonstração:

1. Verifique se o projeto `APL2007M2Sample1` está aberto no Visual Studio Code.

1. Abra o arquivo `MainWindow.xaml.cs` .

1. Selecione todo o código começando da declaração de namespace até o final do arquivo.

1. Abra o modo de exibição de chat.

1. Para ver como o GitHub Copilot Chat documentaria o código selecionado, insira o seguinte prompt:

    ```output
    @workspace #selection generate inline code documentation for the selected code
    ```

1. Reserve um minuto para examinar a documentação de código sugerida.

    A resposta gerada deve ser semelhante ao seguinte exemplo de código:

    ```csharp

    namespace ParallelAsyncExample
    {
        public partial class MainWindow : Window
        {
            // HttpClient instance with a maximum response content buffer size of 1,000,000 bytes
            private readonly HttpClient _client = new HttpClient { MaxResponseContentBufferSize = 1_000_000 };
            // List of URLs to download content from
            private readonly IEnumerable<string> _urlList = new string[]
            {
                "https://docs.microsoft.com",
                "https://docs.microsoft.com/azure",
                "https://docs.microsoft.com/powershell",
                "https://docs.microsoft.com/dotnet",
                "https://docs.microsoft.com/aspnet/core",
                "https://docs.microsoft.com/windows",
                "https://docs.microsoft.com/office",
                "https://docs.microsoft.com/enterprise-mobility-security",
                "https://docs.microsoft.com/visualstudio",
                "https://docs.microsoft.com/microsoft-365",
                "https://docs.microsoft.com/sql",
                "https://docs.microsoft.com/dynamics365",
                "https://docs.microsoft.com/surface",
                "https://docs.microsoft.com/xamarin",
                "https://docs.microsoft.com/azure/devops",
                "https://docs.microsoft.com/system-center",
                "https://docs.microsoft.com/graph",
                "https://docs.microsoft.com/education",
                "https://docs.microsoft.com/gaming"
            };
            // Event handler for the start button click event
            private void OnStartButtonClick(object sender, RoutedEventArgs e)
            {
                // Disable the start button and clear the results text box
                _startButton.IsEnabled = false;
                _resultsTextBox.Clear();
                // Start the asynchronous operation to sum page sizes
                Task.Run(() => StartSumPageSizesAsync());
            }
            // Starts the asynchronous operation to sum page sizes
            private async Task StartSumPageSizesAsync()
            {
                // Perform the main download operation
                await SumPageSizesAsync();
                // Update the UI to re-enable the start button and indicate that control has returned
                await Dispatcher.BeginInvoke(() =>
                {
                    _resultsTextBox.Text += $"\nControl returned to {nameof(OnStartButtonClick)}.";
                    _startButton.IsEnabled = true;
                });
            }
            // Asynchronously sums the sizes of the pages from the URLs
            private async Task SumPageSizesAsync()
            {
                // Start a stopwatch to measure elapsed time
                var stopwatch = Stopwatch.StartNew();
                // Create tasks to download content from each URL
                IEnumerable<Task<int>> downloadTasksQuery =
                    from url in _urlList
                    select ProcessUrlAsync(url, _client);
                // Convert the sequence of tasks into an array
                Task<int>[] downloadTasks = downloadTasksQuery.ToArray();
                // Wait for all tasks to complete and sum the lengths of the downloaded content
                int[] lengths = await Task.WhenAll(downloadTasks);
                int total = lengths.Sum();
                // Update the UI with the total bytes and elapsed time
                await Dispatcher.BeginInvoke(() =>
                {
                    stopwatch.Stop();
                    _resultsTextBox.Text += $"\nTotal bytes returned:  {total:#,#}";
                    _resultsTextBox.Text += $"\nElapsed time:          {stopwatch.Elapsed}\n";
                });
            }
            // Asynchronously processes a URL by downloading its content and returning the length of the content
            private async Task<int> ProcessUrlAsync(string url, HttpClient client)
            {
                try
                {
                    // Download the content of the URL
                    byte[] byteArray = await client.GetByteArrayAsync(url);
                    // Update the UI with the URL and content length
                    await DisplayResultsAsync(url, byteArray);
                    // Return the length of the downloaded content
                    return byteArray.Length;
                }
                catch (HttpRequestException e)
                {
                    // Handle HTTP request exceptions by updating the UI with an error message
                    await Dispatcher.BeginInvoke(() =>
                    {
                        _resultsTextBox.Text += $"{url,-60} {"Error",-10}\n";
                        _resultsTextBox.Text += $"Exception: {e.Message}\n";
                    });
                    // Return 0 to indicate failure
                    return 0;
                }
            }
            // Updates the UI with the URL and the length of the downloaded content
            private Task DisplayResultsAsync(string url, byte[] content) =>
                Dispatcher.BeginInvoke(() =>
                    _resultsTextBox.Text += $"{url,-60} {content.Length,10:#,#}\n")
                          .Task;
            // Disposes of the HttpClient instance when the window is closed to free up resources
            protected override void OnClosed(EventArgs e) => _client.Dispose();
        }
    }

    ```

    A resposta inclui comentários de código sugeridos e *uma parte* do código associado. Algumas partes do seu código podem ser omitidas deixá-lo mais sucinto. Você pode mover manualmente os comentários de código para o arquivo de código real.

    O chat embutido oferece uma abordagem mais direta para adicionar comentários ao seu código.

### Gerar documentação de código embutido usando chat embutido

1. Role até a parte superior do arquivo `MainWindow.xaml.cs`.

1. Selecione o método `OnStartButtonClick`.

1. Para abrir um chat embutido, pressione **Ctrl+I**.

1. Para gerar a documentação embutida para o método `OnStartButtonClick`, insira o seguinte prompt:

    ```output
    /doc
    ```

1. Leve um minuto para examinar a documentação de código gerada.

    Observe que a documentação sugerida para o método `OnStartButtonClick` inclui um resumo e descrições dos dois parâmetros. Quando um método inclui um valor de retorno, uma descrição do valor de retorno também é incluída.

    > [!IMPORTANT]
    > Sempre revise as atualizações sugeridas do GitHub Copilot antes de aceitá-las. Se você descobrir um problema em uma atualização de código sugerida, poderá descartar a atualização ou tentar corrigir o problema antes de aceitar a atualização de código sugerida.

1. Para descartar a atualização sugerida, selecione **Descartar**.

    Na próxima seção, você gerará a documentação para todos os métodos de uma só vez.

### Gerar documentação de código embutido usando a ação inteligente **Gerar Documentos**

A ação inteligente **Gerar Documentos** é outra maneira de gerar documentação de código embutido. Você pode usar esta ação inteligente para gerar comentários que descrevem o código selecionado.

Use as seguintes etapas para concluir esta seção da demonstração:

1. No editor do Visual Studio Code, selecione todos os métodos *dentro* da classe `MainWindow`.

1. Clique com o botão direito do mouse no código selecionado, selecione **Copilot** e selecione **Gerar Documentos**.

    Aguarde até que a documentação seja gerada.

1. Examine as alterações sugeridas.

    > [!IMPORTANT]
    > Se você encontrar problemas na documentação gerada, modifique as alterações sugeridas antes de continuar.

1. Selecione **Aceitar**.

    Cada um dos métodos na classe `MainWindow` agora inclui comentários gerados.

### Resumo

Nesta demonstração, você usou o GitHub Copilot Chat para gerar a documentação de código embutido para o aplicativo `APL2007M2Sample1`. Você aprendeu a gerar documentação de código em linha usando a exibição Chat, o chat em linha e a ação inteligente **Gerar documentos**. Ao gerar comentários de código, você pode criar uma base de código mais legível e de fácil manutenção, que é mais fácil de ser entendida e trabalhada por outros desenvolvedores. A documentação de código embutido é uma parte essencial do desenvolvimento de software que ajuda os desenvolvedores a entender a base de código, sua finalidade e como usá-la.
