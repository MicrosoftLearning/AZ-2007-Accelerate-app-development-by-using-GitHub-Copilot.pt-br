---
demo:
  title: 'Demonstração: Criar código usando preenchimento de linha de código'
  module: 'Module 3: Develop code features using GitHub Copilot tools'
---

# Demonstração: Criar código usando preenchimento de linha de código

## Instruções

As atividades de demonstração são projetadas para um ambiente que inclui os seguintes recursos:

- Visual Studio Code.
- A extensão do kit de desenvolvimento em C# para o Visual Studio Code.
- As extensões do GitHub Copilot e do GitHub Copilot Chat para Visual Studio Code. É necessária uma conta do GitHub com uma assinatura ativa do GitHub Copilot.
- Projetos de amostras de código criadas usando C#.

**OBSERVAÇÃO**: Recomendamos que os instrutores considerem usar sua própria conta do GitHub e a assinatura do GitHub Copilot para as demonstrações. Isso irá permitir que você controle e personalize seu ambiente de desenvolvimento. Também facilitará o ajuste das demonstrações para atender às necessidades de suas salas de aula.

**IMPORTANTE**: Se você optar por executar as demonstrações no ambiente de laboratório hospedado em vez do seu computador de instrutor, poderá descompactar os aplicativos de exemplo no ambiente hospedado. Você precisará configurar as extensões do GitHub Copilot no ambiente hospedado antes de executar as demonstrações. Você pode perceber que o ambiente hospedado é mais lento do que o seu ambiente local, então talvez precise ajustar o ritmo das demonstrações de acordo.

### Apresentar a demonstração

O GitHub Copilot pode fornecer sugestões de preenchimento de código para várias linguagens de programação e uma ampla gama de estruturas, mas funciona muito bem para Python, JavaScript, TypeScript, Ruby, Go, C# e C++. Os preenchimentos de linha de código são gerados com base no contexto do código que você está escrevendo. Você pode aceitar, rejeitar ou aceitar parcialmente as sugestões fornecidas pelo GitHub Copilot.

O GitHub Copilot oferece duas formas de gerar preenchimentos de linha de código:

- **A partir de um comentário**: você pode gerar preenchimentos de linha de código escrevendo um comentário que descreva o código que desejar gerar. O GitHub Copilot oferece sugestões de preenchimento de código com base no comentário que você escreve.

- **A partir do código**: você pode gerar preenchimentos de linha de código iniciando uma linha de código ou pressionando Enter depois de terminar uma linha. O GitHub Copilot oferece sugestões de preenchimento de código com base no código que você escreve.

Nesta demonstração, você usará o GitHub Copilot para gerar preenchimentos de linha de código em seu ambiente do Visual Studio Code.

### Criar um aplicativo de console em seu ambiente do Visual Studio Code

Nesta demonstração, você irá criar um aplicativo de console usando as ferramentas do GitHub Copilot.

Use as seguintes etapas para concluir esta seção da demonstração:

1. Abra uma nova instância do Visual Studio Code e abra o modo de exibição de Chat.

    Você pode abrir o modo de exibição de Chat selecionando **Abrir Chat** no Centro de Comando do Visual Studio Code ou usando o atalho de teclado **Ctrl+Alt+I**.

1. No modo de exibição de Chat, insira a seguinte solicitação:

    ```plaintext
    @workspace /new console application named APL2007M3. Use C# LangVersion 12 and NET8.0. Only .cs and .csproj files. Enable ImplicitUsings and Nullable
    ```

1. No modo de exibição de Chat, selecione **Criar Espaço de trabalho**.

    O GitHub Copilot usa essa solicitação para criar o espaço de trabalho para um novo aplicativo de console. O aplicativo usa `C#` e `.NET8.0`. O projeto de código é nomeado `APL2007M3` e inclui os arquivos `.cs` e `.csproj`. O arquivo `APL2007M3.csproj` especifica C# `LangVersion 12` e habilita `ImplicitUsings` e `Nullable`.

1. Na caixa de diálogo Selecionar Pasta, navegue até a sua pasta Área de Trabalho, selecione **Área de Trabalho** e, em seguida, escolha **Selecionar como Pasta Pai**.

    Você receberá uma solicitação para escolher uma pasta principal para o espaço de trabalho. Selecionar a pasta Área de Trabalho é uma boa opção para esta demonstração. A pasta Área de Trabalho é fácil de localizar. Lembre-se de limpar quando concluir este treinamento.

1. Quando solicitado a abrir o novo projeto, selecione **Abrir**.

1. No modo de exibição Explorador, selecione **Program.cs**.

1. Substitua o conteúdo do arquivo Program.cs pelo seguinte código:

    ```csharp

    namespace ReportGenerator
    {
        class QuarterlyIncomeReport
        {
            static void Main(string[] args)
            {
                // create a new instance of the class
                QuarterlyIncomeReport report = new QuarterlyIncomeReport();
                // call the GenerateSalesData method
                // call the QuarterlySalesReport method
            }
            public void QuarterlySalesReport()
            {
                Console.WriteLine("Quarterly Sales Report");
            }
        }    
    }

    ```

Seus requisitos de configuração estão completos e você está pronto para continuar a demonstração.

### Use o GitHub Copilot para gerar preenchimentos de linha de código a partir de um comentário

O GitHub Copilot gera sugestões de preenchimento de código baseadas no comentário e no contexto do seu aplicativo. Você pode usar comentários para descrever trechos de código, métodos, estruturas de dados e outros elementos do código.

Use as seguintes etapas para concluir esta seção da demonstração:

1. No arquivo **Program.cs**, crie duas linhas de código em branco abaixo do método `Main`.

1. Para criar uma estrutura de dados que possa ser usada para gerar dados de teste, crie o seguinte comentário de código e, em seguida, pressione Enter:

    ```C#
    // public struct SalesData. Include the following fields: date sold, department name, product ID, quantity sold, unit price
    ```

    O GitHub Copilot gera uma ou mais sugestões de preenchimento de código com base nos comentários do seu código e em qualquer código que ele encontrar em seu aplicativo.

1. Reserve um minuto para analisar as sugestões de preenchimento de código fornecidas pelo GitHub Copilot.

    > [!NOTE]
    > Se o GitHub Copilot gerar sugestões para um método em vez de uma estrutura de dados, digite **public str** e aguarde a sugestão de preenchimento do código ser atualizada. O GitHub Copilot usa as informações adicionais para melhorar suas sugestões.

    Observe os tipos de dados usados para declarar os campos da estrutura de dados. O GitHub Copilot seleciona tipos de dados e nomes de variáveis com base no seu código e nos comentários do código. O GitHub Copilot tenta determinar como o aplicativo usa variáveis e define os tipos de dados de acordo.

    Quando o GitHub Copilot gera mais de uma sugestão, você pode verificá-las selecionando as setas para a esquerda ou para a direita (`>` ou `<`) localizadas à esquerda do botão **Aceitar**. Isso permite que você examine e selecione a sugestão que melhor atenda às suas necessidades.

    Não há problema em aceitar uma sugestão de preenchimento de código que não seja uma correspondência exata do que você deseja. No entanto, as alterações necessárias para "corrigir" a sugestão devem ser claras. Nesse caso, alguns dos tipos de dados não são o que você quer, mas você pode ajustá-los depois de aceitar a preenchimento automático sugerido.

    Se nenhuma das opções sugeridas for parecido com o que você precisa, você pode tentar duas coisas. Para abrir uma nova guia do editor que contém uma lista de outras sugestões, pressione as teclas **Ctrl** + **Enter**. Essa combinação de teclas de acesso abre uma nova guia que contém mais 10 sugestões. Cada sugestão é seguida por um botão que você pode usar para aceitar a sugestão. A guia é fechada automaticamente depois que você aceita uma sugestão. A outra opção é pressionar a tecla **Esc** para ignorar as sugestões e tentar novamente. Você pode ajustar o comentário de código para fornecer mais contexto para o GitHub Copilot usar.

    > [!NOTE]
    > Ocasionalmente, o GitHub Copilot poderá propor uma sugestão em etapas. Se isso acontecer, pressione Enter para ver as etapas adicionais da sugestão após pressionar a tecla Tab.

1. Para aceitar uma sugestão de estrutura de dados, pressione a tecla Tab ou selecione **Aceitar**.

1. Para modificar os tipos de dados dos campos, atualize o código da seguinte forma:

    ```csharp

    public struct SalesData
    {
        public DateOnly dateSold;
        public string departmentName;
        public int productID;
        public int quantitySold;
        public double unitPrice;
    }

    ```

    Fazer ajustes rápidos nas sugestões de preenchimento de código ajuda a garantir que você esteja criando o código desejado. É especialmente importante fazer correções no início do processo de desenvolvimento quando grandes partes da base de código ainda precisam ser desenvolvidas. As conclusões de código subsequentes serão baseadas no código que você já escreveu, portanto, é importante garantir que seu código seja o mais preciso possível.

1. Crie duas linhas de código vazias abaixo da estrutura de dados `SalesData`.

1. Para criar um método que gera dados de teste usando a estrutura de dados `SalesData`, escreva o seguinte comentário de código e, em seguida, pressione Enter:

    ```C#
    /* the GenerateSalesData method returns 1000 SalesData records. It assigns random values to each field of the data structure */
    ```

1. Reserve um minuto para analisar as sugestões de preenchimento de código fornecidas pelo GitHub Copilot.

    Observe que o método `GenerateSalesData` foi desenvolvido para retornar uma matriz de objetos `SalesData`. O método gera 1.000 registros de dados de teste, com valores aleatórios atribuídos a cada campo da estrutura de dados `SalesData`.

    Você sempre deve examinar as sugestões propostas pelo GitHub Copilot e Chat do GitHub Copilot, mesmo quando elas parecem estar corretas.

    > [!NOTE]
    > Se o GitHub Copilot sugerir uma única linha de código em vez de um método `GenerateSalesData` concluído, pressione **Ctrl+Enter** para abrir a guia Sugestões do GitHub Copilot. Examine as sugestões na nova guia. Na próxima etapa, use o botão "Aceitar sugestão #" para aceitar a sugestão. O GitHub Copilot apresenta sugestões incrementalmente em algumas ocasiões. Embora você possa aceitar os preenchimentos de código incrementalmente, é melhor usar a guia Sugestões do GitHub Copilot para examinar a sugestão completa antes de tomar uma decisão de aceitar ou descartar.

1. Role as sugestões de conclusão de código e selecione a melhor correspondência para os requisitos.

1. Para aceitar o preenchimento de código, pressione a tecla Tab.

    Observe que a sugestão de preenchimento de código inclui um erro de sintaxe no código usado para gerar o campo `DateSold`. O `DateOnly` aceita três valores inteiros que devem ser listados na ordem correta: **Ano**, **Mês**, **Dia**.

1. Para especificar um único ano no código usado para gerar o campo `DateSold`, atualize a linha de código da seguinte forma:

    ```C#
    salesData[i].DateSold = new DateOnly(2023, random.Next(1, 13), random.Next(1, 29));
    ```

1. Se necessário, ajuste as outras linhas de código para corresponder ao seguinte snippet de código:

    ```csharp

    public SalesData[] GenerateSalesData()
    {
        SalesData[] salesData = new SalesData[1000];
        Random random = new Random();
        for (int i = 0; i < salesData.Length; i++)
        {
            salesData[i].dateSold = new DateOnly(2023, random.Next(1, 13), random.Next(1, 29));
            salesData[i].departmentName = "Department " + random.Next(1, 11);
            salesData[i].productID = random.Next(1, 101);
            salesData[i].quantitySold = random.Next(1, 101);
            salesData[i].unitPrice = random.NextDouble() * 100;
        }
        return salesData;
    }

    ```

A capacidade de gerar código a partir dos comentários é um recurso poderoso do GitHub Copilot. Com apenas dois comentários, você conseguiu gerar uma estrutura de dados e um método que gera dados de teste.

### Use o GitHub Copilot para gerar preenchimentos de linha de código

O GitHub Copilot pode gerar preenchimentos de linha de código com base no código que você insere. Você pode gerar esses preenchimentos de duas maneiras:

- Comece a digitar uma linha de código e aguarde que o GitHub Copilot sugira uma preenchimento automático para sua linha de código incompleta.
- Insira uma linha de código completa, pressione a tecla **Enter** e aguarde o GitHub Copilot sugerir um preenchimento automático para a próxima linha de código.

> [!NOTE]
> O GitHub Copilot gera sugestões de preenchimentos com base no código inserido por você e no contexto definido pelo código em seu aplicativo. Quanto mais código de boa qualidade você tiver no seu aplicativo, mais contexto o GitHub Copilot terá disponível. À medida que o volume e a qualidade do código existente aumentam, a qualidade e a confiabilidade dos preenchimentos de linha de código sugeridos pelo GitHub Copilot também melhoram. O GitHub Copilot é muito eficiente na geração de preenchimentos de linhas de código para tarefas e padrões de programação comuns, principalmente quando é necessário gerar uma sequência de componentes relacionados.

Nessa parte da demonstração, você trabalha no método `QuarterlySalesReport`.

Estas são as tarefas que você deve concluir:

- Atualize o construtor do método com um parâmetro que aceite sua coleção de objetos `SalesData`.
- Use o GitHub Copilot para gerar preenchimentos de linhas de código que processem dados de vendas para o relatório trimestral.
- Execute o aplicativo e analise o relatório de vendas do trimestre.

Use as seguintes etapas para concluir esta seção da demonstração:

1. Atualize o construtor de métodos do `QuarterlySalesReport` da seguinte maneira:

    ```C#
    public void QuarterlySalesReport(SalesData[] salesData)
    ```

1. Pense por um momento no código que você precisa desenvolver.

    O conceito é bem simples. Você quer que seu código calcule as vendas trimestrais com base nos dados de vendas e depois crie um relatório. Para fazer isso, seu código precisa:

    - Iterar através da coleção `salesData`.
    - Calcular o valor de cada venda com base na quantidade vendida e no preço unitário.
    - Usar a data da venda para determinar a qual trimestre uma venda pertence.
    - Somar as vendas de cada trimestre.
    - Escrever um relatório das vendas por trimestre.

    Uma opção é começar programar um loop `foreach` e ver o que o GitHub Copilot sugere.

1. No método `QuarterlySalesReport`, crie uma linha de código na parte superior do bloco de código.

    Deve haver pelo menos uma linha de código em branco entre a nova linha de código e a linha de código que contém `Console.WriteLine()`.

1. Para criar um preenchimento de linha de código, basta digitar `foreach (` e aguardar as sugestões do GitHub Copilot.

1. Analise o preenchimento de código sugerido pelo GitHub Copilot.

    O preenchimento de código sugerido não é o que você queria.

    Embora o GitHub Copilot sugira um loop `foreach` que itera os `salesData`, não há nenhuma análise ou cálculo dentro do loop. Cada opção sugerida incluem instruções `Console.WriteLine` que você não deseja ou precisa.

1. Pense por um momento sobre o motivo pelo qual o GitHub Copilot está sugerindo instruções `Console.WriteLine`.

    Lembre-se de que o GitHub Copilot cria sugestões de preenchimento de código com base no contexto do seu código. Neste caso, você realmente não tem muito código para que o GitHub Copilot analise. E a situação piora.

    O código que o GitHub Copilot vê dentro de seu método é uma instrução `Console.WriteLine`. Sem outro contexto disponível dentro do método e sem métodos semelhantes em seu código para se basear, o GitHub Copilot conclui que você pode *querer* `Console.WriteLine` instruções dentro do loop `foreach`.

    O GitHub Copilot funciona melhor quando seu código está limpo e direcionado. Se você vir comentários de código desnecessários ou instruções no seu código, considere removê-los antes de tentar usar os preenchimentos de código do GitHub Copilot.

1. Para limpar seu código antes de dar outra chance para o GitHub Copilot, conclua as seguintes etapas:

    - Cancele o preenchimento de código `foreach (` sugerido.
    - Exclua a instrução `foreach (` parcial que você inseriu.
    - Exclua a instrução `Console.WriteLine` do seu método `QuarterlySalesReport`.

    Agora é o momento de dar outra chance ao GitHub Copilot.

1. Verifique se o seu método `QuarterlySalesReport` é semelhante ao código a seguir:

    ```C#
    public void QuarterlySalesReport(SalesData[] salesData)
    {


    }
    ```

1. Posicione o cursor em uma linha de código em branco dentro do método `QuarterlySalesReport` e pressione Enter.

    Pode demorar um pouco para o GitHub Copilot gerar a sugestão de preenchimento de código.

1. Analise os preenchimentos de código sugeridos.

    > [!NOTE]
    > Mesmo que o GitHub Copilot tenha apenas um nome de método e um parâmetro para trabalhar, isso pode ser suficiente para gerar sugestões úteis. Você verá sugestões que calculam as vendas por trimestre. Rejeitar as sugestões e tentar novamente pode trazer resultados diferentes.

    Você pode alternar entre as sugestões usando `>` ou `<`.

    Observe que a sugestão de preenchimento de código itera por meio dos dados de vendas e faz os cálculos das vendas trimestrais.

1. Para aceitar a sugestão de preenchimento, pressione a tecla Tab.

    A sugestão de preenchimento de código calcula e mostra a renda trimestral com base nos dados de vendas.

    ```csharp

    // create a dictionary to store the quarterly sales data
    Dictionary<string, double> quarterlySales = new Dictionary<string, double>();
    // iterate through the sales data
    foreach (SalesData data in salesData)
    {
        // calculate the total sales for each quarter
        string quarter = GetQuarter(data.dateSold.Month);
        double totalSales = data.quantitySold * data.unitPrice;
        if (quarterlySales.ContainsKey(quarter))
        {
            quarterlySales[quarter] += totalSales;
        }
        else
        {
            quarterlySales.Add(quarter, totalSales);
        }
    }
    // display the quarterly sales report
    Console.WriteLine("Quarterly Sales Report");
    Console.WriteLine("----------------------");
    foreach (KeyValuePair<string, double> quarter in quarterlySales)
    {
        Console.WriteLine(entry.Key + ": $" + entry.Value);
    }

    ```

1. Note que o método `GetQuarter` é usado para determinar o trimestre com base no mês da venda.

    Esse método não é implementado em seu código, mas é necessário para que o código seja compilado e executado.

1. Crie duas linhas de código em branco abaixo do método `QuarterlySalesReport`.

1. Observe que o GitHub Copilot sugere um preenchimento de código para o método `GetQuarter`.

    Com o contexto fornecido pelo método `QuarterlySalesReport`, o GitHub Copilot pode facilmente gerar um preenchimento para o método `GetQuarter` que determina o trimestre com base no mês da venda.

1. Dedique um momento para analisar a sugestão de preenchimento de linha de código para o método `GetQuarter`.

1. Para aceitar a sugestão de preenchimento, pressione a tecla Tab.

    ```csharp

    public string GetQuarter(int month)
    {
        if (month >= 1 && month <= 3)
        {
            return "Q1";
        }
        else if (month >= 4 && month <= 6)
        {
            return "Q2";
        }
        else if (month >= 7 && month <= 9)
        {
            return "Q3";
        }
        else
        {
            return "Q4";
        }
    }

    ```

1. Observe que o método `Main` precisa ser concluído antes que você possa executar o código.

    Você pode usar os comentários no método `Main` para atualizar seu código.

1. Posicione o cursor no final do comentário `// call the GenerateSalesData method` do código e pressione Enter.

    O GitHub Copilot usa o comentário para propor uma instrução de chamada para o método.

1. Analise e depois aceite o preenchimento de código sugerido pelo GitHub Copilot.

1. Repita o processo para o comentário `// call the QuarterlySalesReport method` do código.

1. Seu método `Main` deve conter o seguinte código:

    ```csharp

    static void Main(string[] args)
    {
        // create a new instance of the class
        QuarterlyIncomeReport report = new QuarterlyIncomeReport();
        // call the GenerateSalesData method
        SalesData[] salesData = report.GenerateSalesData();
        // call the QuarterlySalesReport method
        report.QuarterlySalesReport(salesData);
    }

    ```

1. Reserve um minuto para analisar o código na sua classe `QuarterlyIncomeReport`.

    ```csharp

    namespace ReportGenerator
    {
        class QuarterlyIncomeReport
        {
            static void Main(string[] args)
            {
                // create a new instance of the class
                QuarterlyIncomeReport report = new QuarterlyIncomeReport();
                // call the GenerateSalesData method
                SalesData[] salesData = report.GenerateSalesData();
                // call the QuarterlySalesReport method
                report.QuarterlySalesReport(salesData);
            }
            /* public struct SalesData includes the following fields: date sold, department name, product ID, quantity sold, unit price */
            public struct SalesData
            {
                public DateOnly dateSold;
                public string departmentName;
                public int productID;
                public int quantitySold;
                public double unitPrice;
            }
            /* the GenerateSalesData method returns 1000 SalesData records. It assigns random values to each field of the data structure */
            public SalesData[] GenerateSalesData()
            {
                SalesData[] salesData = new SalesData[1000];
                Random random = new Random();
                for (int i = 0; i < 1000; i++)
                {
                    salesData[i].dateSold = new DateOnly(2023, random.Next(1, 13), random.Next(1, 29));
                    salesData[i].departmentName = "Department " + random.Next(1, 11);
                    salesData[i].productID = random.Next(1, 101);
                    salesData[i].quantitySold = random.Next(1, 101);
                    salesData[i].unitPrice = random.NextDouble() * 100;
                }
                return salesData;
            }
            public void QuarterlySalesReport(SalesData[] salesData)
            {
                // create a dictionary to store the quarterly sales data
                Dictionary<string, double> quarterlySales = new Dictionary<string, double>();
                // iterate through the sales data
                foreach (SalesData data in salesData)
                {
                    // calculate the total sales for each quarter
                    string quarter = GetQuarter(data.dateSold.Month);
                    double totalSales = data.quantitySold * data.unitPrice;
                    if (quarterlySales.ContainsKey(quarter))
                    {
                        quarterlySales[quarter] += totalSales;
                    }
                    else
                    {
                        quarterlySales.Add(quarter, totalSales);
                    }
                }
                // display the quarterly sales report
                Console.WriteLine("Quarterly Sales Report");
                Console.WriteLine("----------------------");
                foreach (KeyValuePair<string, double> quarter in quarterlySales)
                {
                    Console.WriteLine(entry.Key + ": $" + entry.Value);
                }
            }
            public string GetQuarter(int month)
            {
                if (month >= 1 && month <= 3)
                {
                    return "Q1";
                }
                else if (month >= 4 && month <= 6)
                {
                    return "Q2";
                }
                else if (month >= 7 && month <= 9)
                {
                    return "Q3";
                }
                else
                {
                    return "Q4";
                }
            }
        }
    }
    
    ```

    Lembre-se de que este código foi criado, quase inteiramente, usando preenchimento de linhas de código geradas pelo GitHub Copilot. No entanto, sua revisão das sugestões de código é importante e as correções eram necessárias. Você sempre deve examinar as conclusões de código sugeridas pelo GitHub Copilot para garantir que o código atenda aos seus requisitos.

1. Para revisar a saída do relatório, execute o aplicativo.

    Abra um Terminal no Visual Studio Code e insira o comando a seguir:

    ```bash
    dotnet run
    ```

    A saída deve mostrar o relatório de rendimentos trimestrais, mostrando o nome do departamento, o trimestre e a renda para cada departamento e trimestre representados nos dados de teste.

1. Revise a saída na janela Terminal.

    Embora os resultados trimestrais sejam baseados em valores numéricos aleatórios, você deverá ver um relatório formatado semelhante à seguinte saída:

    ```output

    Quarterly Sales Report
    ----------------------
    Q3: $635637.5019563352
    Q4: $672247.315297204
    Q2: $667269.194630603
    Q1: $642769.2700531208

    ```

    Ainda há trabalho a ser feito para concluir a classe `QuarterlyIncomeReport`. Na próxima unidade, você usará o GitHub Copilot Chat para expandir e atualizar seu aplicativo.

### Resumo

Nesta demonstração, você usou o GitHub Copilot para gerar preenchimentos de linhas de código no seu ambiente do Visual Studio Code. Você usou comentários de código criar uma estrutura de dados e um método que gera dados de teste. Também usou preenchimentos de linha de código para criar o código que processa dados de vendas para elaborar um relatório de rendimentos trimestrais.
