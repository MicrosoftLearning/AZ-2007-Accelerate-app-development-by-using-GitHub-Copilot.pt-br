---
demo:
  title: 'Demonstração: Criar testes de unidade para condições específicas usando o GitHub Copilot'
  module: 'Module 4: Develop unit tests using GitHub Copilot tools'
---

# Demonstração: Criar testes de unidade para condições específicas usando o GitHub Copilot

## Instruções

As atividades de demonstração são projetadas para um ambiente que inclui os seguintes recursos:

- Visual Studio Code.
- A extensão do kit de desenvolvimento em C# para o Visual Studio Code.
- As extensões do GitHub Copilot e do GitHub Copilot Chat para Visual Studio Code. É necessária uma conta do GitHub com uma assinatura ativa do GitHub Copilot.
- Projetos de amostras de código criadas usando C#.

**OBSERVAÇÃO**: Recomendamos que os instrutores considerem usar sua própria conta do GitHub e a assinatura do GitHub Copilot para as demonstrações. Isso irá permitir que você controle e personalize seu ambiente de desenvolvimento. Também facilitará o ajuste das demonstrações para atender às necessidades de suas salas de aula.

**IMPORTANTE**: Se você optar por executar as demonstrações no ambiente de laboratório hospedado em vez do seu computador de instrutor, poderá descompactar os aplicativos de exemplo no ambiente hospedado. Você precisará configurar as extensões do GitHub Copilot no ambiente hospedado antes de executar as demonstrações. Você pode perceber que o ambiente hospedado é mais lento do que o seu ambiente local, então talvez precise ajustar o ritmo das demonstrações de acordo.

### Apresentar a demonstração

As extensões do GitHub Copilot podem ajudá-lo a criar testes de unidade para condições específicas em seu código. Por exemplo, você pode usar o GitHub Copilot Chat para testar o comportamento de um método quando ele recebe uma entrada específica.

Nesta demonstração, você usará as extensões do GitHub Copilot para criar testes de unidade para condições específicas.

### Criar testes de unidade usando o GitHub Copilot

Você pode criar testes de unidade usando sugestões de preenchimento automático do GitHub Copilot. O uso de sugestões de preenchimento automático pode ajudá-lo a gerar rapidamente testes de unidade para seu código.

Nesta seção da demonstração, você usa o GitHub Copilot para criar testes de unidade para o método `IsPrime` da classe `PrimeService`.

Use as seguintes etapas para concluir esta seção da demonstração:

1. Abra a pasta de projeto **APL2007M4PrimeService-UnitTests** no Visual Studio Code.

1. Abra o arquivo PrimeServiceTests.cs no editor.

1. Exclua todo o código na classe `PrimeServiceTests`.

    O conteúdo do arquivo PrimeServiceTests.cs deve ser semelhante ao seguinte snippet de código:

    ```csharp

    namespace System.Numbers.UnitTests;
    public class PrimeServiceTests
    {
    }

    ```

1. Salve o arquivo PrimeServiceTests.cs e, a seguir, recompile a solução.

1. Para que o GitHub Copilot gere uma conclusão embutida, crie uma linha em branco dentro da classe `PrimeServiceTests`.

    Se você aguardar um segundo ou dois, o GitHub Copilot sugerirá uma conclusão para a classe `PrimeServiceTests`.

1. Selecione **Aceitar** e reserve um minuto para examinar os testes de unidade gerados pelo GitHub Copilot.

1. Reserve um minuto para examinar a coleção de testes de unidade que o GitHub Copilot gerou para o método `IsPrime`.

    A próxima seção da demonstração mostra como usar o GitHub Copilot Chat para pedir ao GitHub Copilot que sugira casos extremos adicionais que devem ser testados.

    ```csharp

    namespace System.Numbers.UnitTests
    {
        public class PrimeServiceTests
        {
            private readonly PrimeService _primeService;
            public PrimeServiceTests()
            {
                _primeService = new PrimeService();
            }
            [Fact]
            public void IsPrime_ReturnsFalse_ForNegativeNumbers()
            {
                // Arrange
                int candidate = -5;
                // Act
                bool result = _primeService.IsPrime(candidate);
                // Assert
                Assert.False(result);
            }
            [Fact]
            public void IsPrime_ReturnsFalse_ForZero()
            {
                // Arrange
                int candidate = 0;
                // Act
                bool result = _primeService.IsPrime(candidate);
                // Assert
                Assert.False(result);
            }
            [Fact]
            public void IsPrime_ReturnsFalse_ForOne()
            {
                // Arrange
                int candidate = 1;
                // Act
                bool result = _primeService.IsPrime(candidate);
                // Assert
                Assert.False(result);
            }
            [Fact]
            public void IsPrime_ReturnsTrue_ForPrimeNumbers()
            {
                // Arrange
                int candidate = 7;
                // Act
                bool result = _primeService.IsPrime(candidate);
                // Assert
                Assert.True(result);
            }
        }
    }

    ```

### Criar testes de unidade para condições específicas usando o GitHub Copilot e o GitHub Copilot Chat

1. Selecione o conteúdo da classe `PrimeServiceTests`.

1. Abra o modo de exibição de chat.

1. Para adicionar o arquivo PrimeService.cs ao contexto de exibição de Chat, arraste e solte o arquivo PrimeService.cs da Exibição do Gerenciador para o modo de exibição chat.

1. Insira a seguinte solicitação no modo de exibição de chat:

    ```plaintext
    @workspace #selection are there any edge cases that should also be tested 
    ```

1. Reserve um minuto para examinar as sugestões fornecidas pelo GitHub Copilot.

    ```plaintext
    Yes, there are a few edge cases that should also be tested:
    
    1. Large Prime Numbers: Ensure the function can handle large prime numbers.

    2. Large Non-Prime Numbers: Ensure the function can handle large non-prime numbers.

    3. Even Numbers Greater Than 2: Ensure the function returns false for even numbers greater than 2.

    4. Small Prime Numbers: Ensure the function correctly identifies small prime numbers like 2 and 3.

    Here are the additional test cases:
    ```

    ```csharp

    [Fact]
    public void IsPrime_ReturnsTrue_ForTwo()
    {
        // Arrange
        int candidate = 2;
        // Act
        bool result = _primeService.IsPrime(candidate);
        // Assert
        Assert.True(result);
    }
    [Fact]
    public void IsPrime_ReturnsTrue_ForThree()
    {
        // Arrange
        int candidate = 3;
        // Act
        bool result = _primeService.IsPrime(candidate);
        // Assert
        Assert.True(result);
    }
    [Fact]
    public void IsPrime_ReturnsFalse_ForEvenNumbersGreaterThanTwo()
    {
        // Arrange
        int candidate = 4;
        // Act
        bool result = _primeService.IsPrime(candidate);
        // Assert
        Assert.False(result);
    }
    [Fact]
    public void IsPrime_ReturnsTrue_ForLargePrimeNumber()
    {
        // Arrange
        int candidate = 7919;
        // Act
        bool result = _primeService.IsPrime(candidate);
        // Assert
        Assert.True(result);
    }
    [Fact]
    public void IsPrime_ReturnsFalse_ForLargeNonPrimeNumber()
    {
        // Arrange
        int candidate = 8000;
        // Act
        bool result = _primeService.IsPrime(candidate);
        // Assert
        Assert.False(result);
    }

    ```

1. Crie uma linha em branco após o último método de teste na classe `PrimeServiceTests`.

1. No modo de exibição de Chat, passe o mouse sobre o snippet de código e selecione **Inserir no Cursor**.

1. Salve o arquivo PrimeServiceTests.cs e, a seguir, recompile a solução.

1. Reserve um minuto para examinar a coleção de testes de unidade que o GitHub Copilot gerou para o método `IsPrime`.

    Como sempre, é importante examinar o trabalho concluído pelo GitHub Copilot para garantir que os testes sejam válidos e que eles abrangem os casos de borda a serem testados. Quando estiver satisfeito com os testes, você poderá executá-los para verificar se eles são aprovados.

1. Passe o ponteiro do mouse sobre uma das “setas de teste” verdes.

    Observe a mensagem de dica de ferramenta informando que você poderá clicar para executar o teste ou clicar com o botão direito para visualizar mais opções.

1. Clique com o botão direito em uma das “setas de teste” verdes.

1. Selecione **Revelar no Gerenciador de Testes**.

    A exibição do Gerenciador de Testes é aberta. A exibição do Gerenciador de Testes pode ser usada para executar e depurar testes e exibir os resultados das execuções de teste. Para abrir a exibição do Gerenciador de Testes manualmente, selecione **Teste** na Barra de Atividades no lado esquerdo da janela do Visual Studio Code. O ícone do modo de exibição **Teste** é aquele que se parece com um flask de laboratório.

1. Na parte superior do modo de exibição do Gerenciador de Testes, selecione **Executar Testes**.

    Após alguns segundos, o Gerenciador de Testes mostra os resultados da execução do teste. Você visualizará que todos os testes foram aprovados. Marcas de seleção verdes no Gerenciador de Testes e à esquerda dos testes de unidade no Editor indicam que o teste foi aprovado.

### Resumo

Nesta demonstração, você usou o GitHub Copilot e o GitHub Copilot Chat para criar testes de unidade para condições específicas na classe `PrimeService`. Você usou conclusões de linha de código para gerar declarações para garantir que os parâmetros de entrada de função sejam válidos e usou o modo de exibição de Chat, para pedir ao GitHub Copilot que sugerisse casos de borda adicionais que deveriam ser testados. Você analisou as sugestões fornecidas pelo GitHub Copilot e executou os testes para verificar se elas foram aprovadas. Você também aprendeu a usar o Gerenciador de Testes no Visual Studio Code para executar e exibir os resultados das execuções de teste.
