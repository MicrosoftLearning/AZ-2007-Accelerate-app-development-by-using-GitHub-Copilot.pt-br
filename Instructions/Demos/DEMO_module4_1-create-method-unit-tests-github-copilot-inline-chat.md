---
demo:
  title: 'Demonstração: Criar testes de unidade usando o GitHub Copilot Chat'
  module: 'Module 4: Develop unit tests using GitHub Copilot tools'
---

# Demonstração: Criar testes de unidade usando o GitHub Copilot Chat

## Instruções

As atividades de demonstração são projetadas para um ambiente que inclui os seguintes recursos:

- Visual Studio Code.
- A extensão do kit de desenvolvimento em C# para o Visual Studio Code.
- As extensões do GitHub Copilot e do GitHub Copilot Chat para Visual Studio Code. É necessária uma conta do GitHub com uma assinatura ativa do GitHub Copilot.
- Projetos de amostras de código criadas usando C#.

**OBSERVAÇÃO**: Recomendamos que os instrutores considerem usar sua própria conta do GitHub e a assinatura do GitHub Copilot para as demonstrações. Isso irá permitir que você controle e personalize seu ambiente de desenvolvimento. Também facilitará o ajuste das demonstrações para atender às necessidades de suas salas de aula.

**IMPORTANTE**: Se você optar por executar as demonstrações no ambiente de laboratório hospedado em vez do seu computador de instrutor, poderá descompactar os aplicativos de exemplo no ambiente hospedado. Você precisará configurar as extensões do GitHub Copilot no ambiente hospedado antes de executar as demonstrações. Você pode perceber que o ambiente hospedado é mais lento do que o seu ambiente local, então talvez precise ajustar o ritmo das demonstrações de acordo.

### Apresentar a demonstração

O Visual Studio Code e o Kit de Desenvolvimento em C# fornecem um conjunto avançado de recursos para ajudar você a criar e gerenciar testes de unidade para seus projetos em C#. Você pode habilitar os testes para seu projeto, adicionar pacotes de estrutura de testes, executar e gerenciar testes de unidade e gerar casos de testes de unidade usando o Kit de Desenvolvimento em C#.

O GitHub Copilot pode ajudar você a gerar testes de unidade para seu código fornecendo sugestões de chat embutidas.

Nesta demonstração, você criará testes de unidade para um projeto de código usando o GitHub Copilot Chat no Visual Studio Code.

### Criar um projeto de teste do xUnit para seus testes de unidade

Os projetos de testes de unidade costumam ser criados em uma pasta separada do projeto que você está testando. Essa separação ajuda a manter o código de teste separado do código de produção. Nesta demonstração, você irá criar um projeto de teste do xUnit para o projeto APL2007M4PrimeService.

Para criar um novo projeto de teste do xUnit, execute as seguintes etapas:

1. Abra a pasta **APL2007M4PrimeService** no Visual Studio Code.

1. Abra o modo de exibição do Gerenciador de Soluções no Visual Studio Code.

    A exibição do Gerenciador de Soluções é acessível no painel da barra lateral do Visual Studio Code. O Gerenciador de Soluções é semelhante ao modo de exibição do Gerenciador, mas foi especificamente projetado para trabalhar com projetos do Visual Studio Code, em vez de sistemas de arquivos de caráter geral.

1. No modo de exibição do Gerenciador de Soluções, clique com o botão direito do mouse na pasta **APL2007M4PrimeService** e, em seguida, selecione **Novo Projeto**.

    Se você não vir a opção **Novo Projeto**, verifique se você está trabalhando no modo de exibição do *Gerenciador de Soluções*, não no modo de exibição do *Gerenciador*.

1. Quando a lista de tipos de projeto aparecer, selecione **Projeto de Testes do xUnit**.

1. Para o nome do projeto, digite **PrimeService.UnitTests** e pressione Enter.

    O nome do projeto deve refletir o nome da classe que você está testando e deve ser exclusivo dentro da solução. Nesse caso, a classe é chamada `PrimeService` e, portanto, o projeto de teste será chamado de `PrimeService.UnitTests`.

1. Selecione o local do diretório padrão.

    Você também pode criar o projeto de testes do xUnit usando o terminal do Visual Studio Code. Abra um terminal, navegue até a pasta Números e, em seguida, execute o seguinte comando:

    ```plaintext
    dotnet new xunit -n PrimeService.UnitTests
    ```

1. Selecione **Criar Projeto** e, em seguida, expanda a pasta PrimeService.UnitTests.

1. Exclua o arquivo UnitTest1.cs criado com o projeto PrimeService.UnitTests.

    Antes de criar um novo teste de unidade, você precisa adicionar uma referência ao projeto de teste de unidade que aponta para o projeto da classe que você quer testar.

1. Para adicionar uma referência ao projeto de código, clique com o botão direito do mouse em **PrimeService.UnitTests**, selecione **Adicionar Referência do Projeto** e selecione **Números**.

1. Para criar uma classe para seus testes de unidade, clique com o botão direito do mouse em **PrimeService.UnitTests**, selecione **Novo arquivo**, selecione **Classe**, digite **PrimeServiceTests** e pressione Enter.

    O Visual Studio Code deve abrir o arquivo PrimeServiceTests.cs para você.

1. Reserve um minuto para examinar o arquivo PrimeServiceTests.cs.

    Seu arquivo deve ser semelhante ao seguinte snippet de código:

    ```csharp

    namespace PrimeService.UnitTests;
    public class PrimeServiceTests
    {
    }

    ```

1. Para ajudar a evitar problemas de namespace quando você compilar o projeto, atualize o arquivo PrimeServiceTests.cs da seguinte maneira:

    ```csharp

    namespace System.Numbers.UnitTests;
    public class PrimeServiceTests
    {
    }

    ```

    Um namespace em C# é usado para organizar classes e tipos relacionados. É uma maneira de evitar colisões de nome e facilitar a compreensão da organização do código. O sufixo `.UnitTests` no namespace do projeto de teste é uma convenção comum para indicar que o código nesse namespace está testando o código no namespace System.Numbers. Isso deixa claro ao examinar a estrutura do projeto qual código é o código de produção e qual código é o código de teste.

1. Reserve um minuto para examinar o arquivo PrimeService.UnitTests.csproj.

    O arquivo PrimeService.UnitTests.csproj deve incluir um `<ItemGroup>` que contém os seguintes elementos `<PackageReference />`:

    ```xml

    <PackageReference Include="coverlet.collector" Version="6.0.0" />
    <PackageReference Include="Microsoft.NET.Test.Sdk" Version="17.8.0" />
    <PackageReference Include="xunit" Version="2.5.3" />
    <PackageReference Include="xunit.runner.visualstudio" Version="2.5.3" />

    ```

    Essas referências de pacote são necessárias para usar o xUnit como biblioteca de testes e configurar o executor de testes. Você também deve ver os seguintes elementos `<ItemGroup>` no arquivo PrimeService.UnitTests.csproj:

    ```xml

    <ItemGroup>
        <Using Include="Xunit" />
    </ItemGroup>
    <ItemGroup>
        <ProjectReference Include="..\Numbers\Numbers.csproj" />
    </ItemGroup>

    ```

    Esses elementos são necessários para fazer referência ao projeto Números e usar a estrutura de testes do xUnit.

1. Para criar a solução, pressione **Ctrl+Shift+B** e selecione **dotnet: build**.

    Você também pode construir a solução usando um comando .NET CLI (dotnet build) ou clicando com o botão direito do mouse no nó da solução na exibição do Gerenciador de Soluções e selecionando **Build**.

    > [!NOTE]
    > Se você vir **erros** de build, corrija os erros antes de continuar a demonstração. Você precisa obter um build bem-sucedido antes de continuar.

Agora você está pronto para criar um teste de unidade usando o Chat do GitHub Copilot.

### Criar testes de unidade usando o modo de exibição de Chat

O GitHub Copilot e o Chat do GitHub Copilot podem ajudar você a gerar testes de unidade para seu código fornecendo sugestões com base no contexto da sua base de código. Você pode usar o Chat do GitHub Copilot para gerar testes de unidade para classes ou métodos específicos no seu código.

Use as seguintes etapas para concluir esta seção da demonstração:

1. Na exibição do Gerenciador de Soluções em Numbers, abra o arquivo PrimeService.cs.

1. Selecione o método **IsPrime**.

1. Abra o modo de exibição de chat.

1. Selecione o botão **Anexar contexto**.

    O botão **Anexar contexto** (ícone de clipe de papel) é usado para informar o GitHub Copilot sobre o contexto relevante dentro da sua base de código. O contexto adicional ajuda o GitHub Copilot Chat a fornecer sugestões mais precisas. Nesse caso, você quer que o GitHub Copilot use seu arquivo PrimeServiceTests.cs ao propor testes de unidade.

1. Na lista suspensa **Pesquisar anexos**, na seção **aberta recentemente**, selecione **PrimeServiceTests.cs**.

    O menu suspenso **Pesquisar anexos** fornece algumas opções padrão que você pode escolher. Ele também inclui uma lista de arquivos abertos recentemente. O arquivo PrimeServiceTests.cs deve ser listado na seção aberta recentemente.

    As opções de anexos de pesquisa incluem

1. Selecione o botão **Anexar contexto** novamente.

1. Na caixa de texto Pesquisar anexos, digite **PrimeService.Unit** e selecione **PrimeService.UnitTests.csproj**.

    > [!NOTE]
    > Demonstre como arrastar um arquivo da visualização do Explorer e soltá-lo na visualização de chat. Em muitos casos, essa é uma maneira mais rápida de anexar contexto.

1. Observe que a visualização do chat é atualizada com o contexto adicional.

1. Na visualização de chat, selecione **/tests adicionar testes de unidade para meu código**.

    A opção **/tests adiciona testes de unidade para meu código** é usada para gerar testes de unidade para o código que você selecionou no editor. Nesse caso, você selecionou o método **IsPrime** no arquivo PrimeService.cs.

1. Reserve um minuto para revisar as sugestões do GitHub Copilot.

    A sugestão do GitHub Copilot inclui duas seções, um "Plano" e um exemplo de código contendo testes de unidade.

    O plano sugere a criação de um novo arquivo PrimeServiceTest.cs para os testes unitários. Ele também sugere criar o arquivo na pasta do projeto Numbers.

1. Na visualização de chat, selecione **Aplicar edições**.

1. Observe que o botão Aplicar edições coloca o código do teste de unidade em uma nova guia no editor.

    Você pode usar este código para atualizar o arquivo PrimeServiceTests.cs no seu projeto PrimeService.UnitTests.

1. No menu **Arquivo**, selecione **Salvar como** e navegue até a pasta PrimeService.UnitTests.

1. Selecione **PrimeServiceTests.cs** e, em seguida, selecione **Salvar**.

1. Quando solicitado a substituir o arquivo existente, selecione **Sim**.

1. Reserve um minuto para revisar o arquivo PrimeServiceTests.cs atualizado.

    O código sugerido pelo GitHub Copilot Chat deve incluir testes para números primos e não primos específicos. O código sugerido pode incluir testes parametrizados (usando atributos `[Theory]` e `[InlineData]`) para testar múltiplos conjuntos de dados de forma mais concisa.

    O snippet de código fornecido deve ser semelhante ao seguinte snippet de código:

    ```csharp

    using Xunit;
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
            public void IsPrime_InputIs1_ReturnsFalse()
            {
                var result = _primeService.IsPrime(1);
                Assert.False(result, "1 should not be prime");
            }
            [Fact]
            public void IsPrime_InputIs2_ReturnsTrue()
            {
                var result = _primeService.IsPrime(2);
                Assert.True(result, "2 should be prime");
            }
            [Fact]
            public void IsPrime_InputIs3_ReturnsTrue()
            {
                var result = _primeService.IsPrime(3);
                Assert.True(result, "3 should be prime");
            }
            [Fact]
            public void IsPrime_InputIs4_ReturnsFalse()
            {
                var result = _primeService.IsPrime(4);
                Assert.False(result, "4 should not be prime");
            }
            [Theory]
            [InlineData(5, true)]
            [InlineData(6, false)]
            [InlineData(7, true)]
            [InlineData(8, false)]
            [InlineData(9, false)]
            [InlineData(10, false)]
            public void IsPrime_Values_ReturnExpectedResult(int value, bool expected)
            {
                var result = _primeService.IsPrime(value);
                Assert.Equal(expected, result);
            }
        }
    }

    ```

    Observe que os testes de unidade exigem uma instância da classe PrimeService.

    ```csharp

    private readonly PrimeService _primeService;
    public PrimeServiceTests()
    {
        _primeService = new PrimeService();
    }

    ```

1. Recrie a solução.

    Você deverá ver "setas de teste" verdes ao lado de cada teste de unidade se a compilação for bem-sucedida.

    Você criará mais testes de unidade na próxima seção, portanto, não é necessário executar os testes no momento.

    No entanto, existem várias formas de executar seus testes. Por exemplo:

    - Você pode executar os testes no terminal do Visual Studio Code usando o comando `dotnet test`.
    - Você pode executar os testes no modo de exibição do Gerenciador de Testes do Visual Studio Code.
    - Você pode executar os testes na Paleta de Comandos do Visual Studio Code usando o comando **Test: Run All Tests**.
    - Você pode executar os testes no editor do Visual Studio Code selecionando a opção **Executar Testes no Arquivo Atual** no menu de contexto.

    Os testes criados durante esta seção da demonstração devem ser executados com sucesso. As "setas de teste" verdes ao lado do teste de unidade se tornam círculos verdes com uma marca de seleção.

### Criar testes de unidade usando o chat embutido

Use as seguintes etapas para concluir esta seção da demonstração:

1. No modo de exibição do Gerenciador de Soluções, abra o arquivo PrimeService.cs.

    O PrimeService.cs está localizado na pasta Números.

1. Selecione o método IsPrime.

1. Abra uma sessão de chat embutida e insira o seguinte prompt:

    ```plaintext
    Create unit tests for the IsPrime method using the xUnit framework.
    ```

1. Reserve um minuto para ler as sugestões fornecidas pelo chat embutido.

    ```csharp

    using Xunit;
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
            public void IsPrime_InputIs1_ReturnsFalse()
            {
                var result = _primeService.IsPrime(1);
                Assert.False(result, "1 should not be prime");
            }
            [Fact]
            public void IsPrime_InputIs2_ReturnsTrue()
            {
                var result = _primeService.IsPrime(2);
                Assert.True(result, "2 should be prime");
            }
            [Fact]
            public void IsPrime_InputIs3_ReturnsTrue()
            {
                var result = _primeService.IsPrime(3);
                Assert.True(result, "3 should be prime");
            }
            [Fact]
            public void IsPrime_InputIs4_ReturnsFalse()
            {
                var result = _primeService.IsPrime(4);
                Assert.False(result, "4 should not be prime");
            }
            [Theory]
            [InlineData(5, true)]
            [InlineData(6, false)]
            [InlineData(7, true)]
            [InlineData(8, false)]
            [InlineData(9, false)]
            [InlineData(10, false)]
            public void IsPrime_Values_ReturnExpectedResult(int value, bool expected)
            {
                var result = _primeService.IsPrime(value);
                Assert.Equal(expected, result);
            }
        }
    }

    ```

1. Observe que a visualização de chat e o bate-papo em linha produzem cobertura de teste semelhante.

1. Para descartar a sugestão de chat em linha, selecione **Descartar** e feche a guia de arquivo criada pelo chat em linha.

    Tenha em mente que os testes de unidade sugeridos pelo GitHub Copilot durante esta demonstração podem estar incompletos. A próxima demonstração examina casos extremos adicionais que você pode considerar testar.

### Resumo

Nesta demonstração, você criou testes de unidade para um projeto de código usando o GitHub Copilot Chat no Visual Studio Code. Você criou um projeto de testes do xUnit, adicionou uma referência ao projeto que você queria testar e gerou testes de unidade para o método `IsPrime` na classe `PrimeService`. Você usou o Chat do GitHub Copilot para gerar testes de unidade no modo de exibição de Chat e no chat embutido.
