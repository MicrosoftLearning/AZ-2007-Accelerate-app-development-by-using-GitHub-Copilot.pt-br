---
demo:
  title: 'Demonstração: Criar código usando o chat embutido do GitHub Copilot'
  module: 'Module 3: Develop code features using GitHub Copilot tools'
---

# Demonstração: Criar código usando o chat embutido do GitHub Copilot

## Instruções

As atividades de demonstração são projetadas para um ambiente que inclui os seguintes recursos:

- Visual Studio Code.
- A extensão do kit de desenvolvimento em C# para o Visual Studio Code.
- As extensões do GitHub Copilot e do GitHub Copilot Chat para Visual Studio Code. É necessária uma conta do GitHub com uma assinatura ativa do GitHub Copilot.
- Projetos de amostras de código criadas usando C#.

**OBSERVAÇÃO**: Recomendamos que os instrutores considerem usar sua própria conta do GitHub e a assinatura do GitHub Copilot para as demonstrações. Isso irá permitir que você controle e personalize seu ambiente de desenvolvimento. Também facilitará o ajuste das demonstrações para atender às necessidades de suas salas de aula.

**IMPORTANTE**: Se você optar por executar as demonstrações no ambiente de laboratório hospedado em vez do seu computador de instrutor, poderá descompactar os aplicativos de exemplo no ambiente hospedado. Você precisará configurar as extensões do GitHub Copilot no ambiente hospedado antes de executar as demonstrações. Você pode perceber que o ambiente hospedado é mais lento do que o seu ambiente local, então talvez precise ajustar o ritmo das demonstrações de acordo.

### Apresentar a demonstração

A extensão de Chat do GitHub Copilot para Visual Studio Code inclui três interfaces de chat:

- A **visualização do Chat** oferece um assistente de IA que está disponível para ajudá-lo a qualquer momento.
- Uma janela **Quick Chat** pode ser usada para fazer uma pergunta rápida e, em seguida, voltar ao que você está fazendo.
- A **interface de chat** embutida é aberta diretamente no editor para interações contextuais enquanto você está codificando.

A exibição de Chat e a janela de Chat Rápido permitem conversas interativas de vários turnos com a IA. Ambas as interfaces fornecem uma maneira de fazer perguntas, obter ajuda com um problema de codificação e gerar código. Durante uma conversa, as respostas do GitHub Copilot incluem texto em linguagem natural, blocos de código e outros elementos. Quando os blocos de código são fornecidos em uma resposta, você pode copiá-los ou injetá-los diretamente no editor de código.

A interface de chat embutida foi projetada para fornecer ajuda contextual e sugestões de código enquanto você está codificando.

Nesta demonstração, você irá usar o recurso de chat embutido do GitHub Copilot para gerar novos recursos de código. A demonstração é uma continuação do cenário do projeto apresentado na demonstração anterior. Use o aplicativo de exemplo preparado, `APL2007M3SalesReport-InlineChat`, para iniciar a demonstração. Durante a demonstração, você irá atualizar a estrutura de dados `SalesData` e o método `GenerateSalesData`. Você também atualizará o método `QuarterlySalesReport` para incluir cálculos adicionais e opções de exibição.

#### Examinar as tarefas de codificação e as metas do projeto

Esta demonstração se concentra no uso do GitHub Copilot para acelerar as seguintes tarefas:

1. Você irá atualizar a estrutura de dados `SalesData` e o método `GenerateSalesData` para produzir uma amostra de dados que se assemelhe aos dados “reais”.

    - dateSold: nenhuma alteração é necessária.
    - departmentName: Os valores de cadeia de caracteres devem ser selecionados aleatoriamente em uma lista de 8 departamentos. Para cada nome de departamento, crie uma abreviação de 4 caracteres que pode ser incluída no productID.
    - productID: alterar do tipo de dados `int` para `string`. Os valores productID devem ser formatados usando o padrão "`DDDD-###-SS-CC-MMM`" em que os componentes da ID são definidos da seguinte maneira:

        - um código de 4 caracteres que representa o departamento.
        - um número de 3 dígitos que representa o produto.
        - um código de 2 caracteres que representa o tamanho do produto.
        - um código de 2 caracteres que representa a cor do produto.
        - um código de 3 caracteres que representa o site de fabricação (selecionado aleatoriamente em uma lista de 10 sites de fabricação). Os códigos devem ser um código de país ISO de 2 letras seguido por um dígito (por exemplo, US1, CA2, MX3 etc.).

    - quantitySold: nenhuma alteração é necessária.
    - unitPrice: Aumente o limite inferior da faixa de preços para 25 e o limite superior para 300.
    - baseCost: Adicione um campo para o custo de fabricação do item. Os valores baseCost devem ser gerados usando o desconto gerado aleatoriamente do unitPrice (5 a 20%).
    - volumeDiscount: Adicione um campo para uma porcentagem de desconto de volume. O valor atribuído a volumeDiscount deve ser o componente inteiro de 10% da quantitySold (10% de 19 unidades = 1% volumeDiscount).
    - Aumente o número de registros gerados para 10.000.

1. Você irá atualizar o método `QuarterlySalesReport` da seguinte maneira:

    1. Ao exibir os resultados das vendas, liste os resultados em uma ordem lógica. Por exemplo, ao listar a venda total por trimestre, os trimestres devem ser listados em ordem do 1º ao 4º trimestre.
    1. Exibir valores de moeda usando configurações regionais.
    1. Incluir cálculos para o lucro trimestral e o percentual de lucro
    1. Inclui cálculos para vendas trimestrais, lucro e percentual de lucro por departamento.

#### Explique sua abordagem para desenvolver prompts para o GitHub Copilot Chat

O recurso de chat embutido do GitHub Copilot usa a solicitação que você envia para entender a tarefa ou o problema que você está tentando resolver. As solicitações devem ser específicas e concisas. Solicitações bem feitas produzem respostas melhores.

Ao desenvolver solicitações para o GitHub Copilot, considere as seguintes práticas recomendadas:

- Especifique e simplifique: Forneça solicitações claras e concisas que descrevem a tarefa ou o problema que você está tentando resolver. Evite usar linguagem complexa ou jargão que possa confundir a IA.
- Use linguagem natural: Escreva solicitações em um tom de conversa. Use a linguagem natural que você usaria ao falar com um colega ou membro da equipe.
- Divida tarefas complexas: Se a tarefa for complexa, divida-a em etapas menores. Forneça solicitações para cada etapa para ajudar o GitHub Copilot a gerar o código correto.
- Forneça contexto: Inclua informações relevantes que ajudam o GitHub Copilot a entender a tarefa ou o problema que você está tentando resolver. Inclua detalhes sobre os dados, variáveis ou blocos de código relevantes para a solicitação.
- Use participantes de chat, comandos de barra e variáveis de chat: O recurso de chat embutido do GitHub Copilot dá suporte a participantes de chat, comandos de barra e variáveis de chat. Use esses recursos para interagir com o GitHub Copilot e fornecer contexto adicional para suas solicitações.

### Gerar estruturas de dados usando chat embutido

Os projetos geralmente começam com recursos ou parâmetros que são fixos ou conhecidos. Selecionar uma fonte de dados ou criar dados de exemplo geralmente é um bom lugar para começar.

Nesta seção da demonstração, você irá usar estruturas de dados para ajudar a criar dados de vendas simulados. Os dados fornecem contexto útil para o GitHub Copilot quando você atualiza o método `QuarterlySalesReport`.

> [!NOTE]
> Em um projeto de negócios real, você provavelmente usaria dados históricos em vez de gerar dados simulados. Neste treinamento, a geração de dados simulados oferece uma oportunidade de praticar usando as ferramentas do GitHub Copilot. A simulação de dados não é sugerida como uma prática recomendada para projetos de negócios.

Suas metas de projeto indicam que você precisa trabalhar nas seguintes estruturas de dados:

- Você precisa de uma lista de 8 nomes de departamento. Cada nome de departamento deve ser abreviado usando uma cadeia de caracteres de 4 caracteres. Escolha uma indústria para sua empresa fictícia, como Roupas ou Equipamentos Esportivos, e faça com que o GitHub Copilot gere um dicionário de nomes de departamento e códigos de 4 caracteres.
- Você precisa de uma lista de 10 locais de fabricação. Cada site deve ser representado por um código de 3 caracteres. Os códigos podem ser um código de país ISO de 2 letras seguido por um dígito (por exemplo, US1, CA2, MX3 etc.). Fazer com que o GitHub Copilot gere um dicionário de 10 sites de fabricação usando códigos de país 3 a 4.
- Você precisa atualizar a estrutura de dados `SalesData`. Você precisa incluir os novos campos para: código do departamento, código do site de fabricação. Você também precisa alterar o tipo de dados para productID de `int` para `string`.

Para criar e atualizar a estrutura de dados, conclua as seguintes etapas:

1. Abra a pasta de projeto **APL2007M3SalesReport-InlineChat** no Visual Studio Code.

1. Verifique se o aplicativo é executado e produz um relatório semelhante à seguinte saída:

    ```plaintext
    Quarterly Sales Report
    ----------------------
    Q3: $690095.7142725277
    Q4: $600536.3320750712
    Q2: $678194.7943550209
    Q1: $595963.0477790226
    ```

    Como os dados são gerados aleatoriamente, os valores numéricos variam de acordo com cada execução.

1. Abra o arquivo Program.cs.

1. Posicione o cursor em uma linha em branco abaixo da estrutura de dados `SalesData`.

1. Para abrir a interface de chat embutido, pressione **Ctrl+I** no teclado.

1. Digite a seguinte solicitação:

    ```output
    I need a public struct ProdDepartments that contains a static string array for 8 clothing industry departments. Create separate string array containing 4-character abbreviations for each department name. The abbreviation must be unique. The department names should represent real department names for the clothing industry.
    ```

    Se você tivesse uma lista específica de nomes de campo, poderia fornecê-los no prompt. Por exemplo, os dados reais da empresa podem ser usados para especificar os nomes de departamento.

1. Examine as sugestões fornecidas pelo GitHub Copilot.

    Desde que o prompt seja claro e específico, o GitHub Copilot deve fornecer uma sugestão útil. Se a sugestão não for o que você esperava, você poderá rejeitá-la e tentar novamente. Nesse caso, os nomes dos departamentos não são importantes, portanto, você provavelmente pode aceitar a sugestão.

    Sua estrutura de dados deve ser semelhante ao seguinte código:

    ```csharp

    public struct ProdDepartments
    {
        public static string[] DepartmentNames =  ["Men's Clothing", "Women's Clothing", "Children's Clothing", "Accessories", "Footwear", "Outerwear", "Sportswear", "Undergarments"];
        public static string[] DepartmentAbbreviations =  ["MENS", "WOMN", "CHLD", "ACCS", "FOOT", "OUTR", "SPRT", "UNDR" ];
    }

    ```

1. Para aceitar a sugestão, pressione a tecla tab ou selecione **Aceitar**.

    Você também pode usar o recurso de chat embutido para documentar o novo código. Selecione o código, pressione **Ctrl+I** para abrir o chat embutido, insira `/doc`, examine a documentação embutida sugerida e aceite a atualização.

1. Posicione o cursor em uma linha em branco abaixo da estrutura de dados `ProdDepartments`.

1. Para abrir a interface de chat embutido, pressione **Ctrl+I** no teclado.

1. Digite a seguinte solicitação:

    ```output
    I need a public struct ManufacturingSites that contains a static string array for 10 manSites. Manufacturing sites should be represented by a 3-character code that includes a 2-letter ISO country code followed by a digit. Use 3 ISO country codes.
    ```

    Se você tivesse uma lista específica de nomes de campo, poderia fornecê-los no prompt. Por exemplo, os dados reais da empresa podem ser usados para especificar os nomes de campo.

1. Examine as sugestões fornecidas pelo GitHub Copilot.

    Suas estruturas de dados deve ser semelhante ao seguinte código:

    ```csharp

    public struct ManufacturingSites
    {
        public static string[] manSites = [ "US1", "US2", "US3", "UK1", "UK2", "UK3", "JP1", "JP2", "JP3", "MX1" ];
    }

    ```

1. Para aceitar a sugestão, pressione a tecla tab ou selecione **Aceitar**.

1. Selecione a estrutura de dados `SalesData` e pressione **Ctrl+I** para abrir a interface de chat embutida.

    Você precisa adicionar campos para `baseCost` e `volumeDiscount` à estrutura de dados `SalesData` (um `double` e `int`). Você também precisa alterar o tipo de dados para `productID` de `int` para `string`.

1. Digite a seguinte solicitação:

    ```output
    add double field baseCost and int field volumeDiscount to SalesData. Change productID from int to string.
    ```

    Na prática, pode ser mais fácil fazer essas alterações manualmente. No entanto, usar o GitHub Copilot pode ajudá-lo a aprender a estruturar seus prompts para obter melhores resultados.

1. Examine as sugestões fornecidas pelo GitHub Copilot e selecione **Aceitar**.

    Suas estruturas de dados SalesData atualizadas devem ser semelhantes ao seguinte código:

    ```csharp

    public struct SalesData
    {
        public DateOnly dateSold;
        public string departmentName;
        public string productID;
        public int quantitySold;
        public double unitPrice;
        public double baseCost;
        public int volumeDiscount;
    }

    ```

Com as estruturas de dados novas e atualizadas em vigor, agora você pode trabalhar na atualização do método `GenerateSalesData`.

### Atualizar o método GenerateSalesData usando chat embutido

Suas metas de projeto indicam que você precisa atualizar o método `GenerateSalesData` para produzir um exemplo de dados semelhante a dados "reais". Você já atualizou a estrutura de dados `SalesData` para incluir novos campos para código de departamento e código do site de fabricação. Você também alterou o tipo de dados para `productID` de `int` para `string`. Agora você precisa atualizar o método `GenerateSalesData` para gerar dados para os campos atualizados.

Você precisa implementar as seguintes atualizações:

- departmentName: Atualize o valor atribuído. Atribua um nome de departamento selecionado aleatoriamente na estrutura de dados `ProdDepartments`.
- productID: Atualize o valor atribuído. Formate a productID usando o padrão "`DDDD-###-SS-CC-MMM`" em que os componentes da ID são definidos da seguinte maneira:

    - um código de 4 caracteres que representa o departamento. Use a abreviação da estrutura de dados `ProdDepartments` correspondente ao nome do departamento atribuído.
    - um número de 3 dígitos que representa o produto. O primeiro dígito deve ser o número de índice do departamento selecionado aleatoriamente. Os próximos dois dígitos devem ser um número aleatório de 1 a 99, mas incluem 0s à esquerda. Por exemplo, 1 deve ser formatado como 01.
    - um código de 2 caracteres que representa o tamanho do produto. Selecione aleatoriamente um tamanho de produto em uma lista de 5 tamanhos: XS, S, M, L, XL.
    - um código de 2 caracteres que representa a cor do produto. Selecione aleatoriamente uma cor do produto em uma lista de abreviações de cores de 8 2 caracteres: BK, BL, GR, RD, YL, OU, WT, GY.
    - um código de 3 caracteres que representa o local de fabricação. Selecione aleatoriamente um site de fabricação na estrutura de dados `ManufacturingSites`.

- unitPrice: Aumente o limite inferior da faixa de preços para 25 e o limite superior para 300. Suponha que o tamanho e a cor não afetem o preço unitário.
- baseCost: Atribua um valor a baseCost que representa os custos de fabricação. Os valores podem ser gerados usando o desconto gerado aleatoriamente na unitPrice (5 a 20%). Não realista, mas aceitável para esta demonstração.
- volumeDiscount: Atribua um valor a volumeDiscount que representa um desconto percentual concedido ao comprador de varejo. O valor atribuído a volumeDiscount deve ser o componente inteiro de 10% da quantitySold (10% de 19 unidades = 1% volumeDiscount).

Para atualizar o método `GenerateSalesData`, conclua as seguintes etapas:

1. Localize o método `GenerateSalesData` no arquivo Program.cs.

1. Selecione a linha de código usada para atribuir o valor `departmentName`.

1. Para abrir a interface de chat embutido, pressione **Ctrl+I** no teclado.

1. Digite a seguinte solicitação:

    ```output
    Update the departmentName assignment to randomly select a department name. Use the ProdDepartments data structure. 
    ```

1. Examine as sugestões fornecidas pelo GitHub Copilot, e selecione **Aceitar**.

1. Crie três linhas de código em branco após a atribuição de `departmentName`.

1. Leve um minuto para considerar como você deseja construir o valor atribuído a `productID`.

    Os valores productID devem ser formatados como "`DDDD-###-SS-CC-MMM`" em que os componentes da ID são definidos da seguinte maneira:

    - `DDDD` é um código de 4 caracteres que representa o departamento. Use a abreviação da estrutura de dados `ProdDepartments` correspondente ao nome do departamento atribuído.
    - `###` são 3 caracteres numéricos que representam um produto. O primeiro dígito é o número de índice do departamento. Em seguida, é um número aleatório 1-99 com um 0 à esquerda (por exemplo: "07").
    - `SS` é um código de 2 caracteres que representa o tamanho do produto. Selecione aleatoriamente um tamanho de produto em uma lista de 5 tamanhos: XS, S, M, L, XL.
    - `CC` é um código de 2 caracteres que representa a cor do produto. Selecione aleatoriamente uma cor do produto em uma lista de abreviações de cores de 8 2 caracteres: BK, BL, GR, RD, YL, OU, WT, GY.
    - `MMM` é um código de 3 caracteres que representa o site de fabricação. Selecione aleatoriamente um site de fabricação na estrutura de dados `ManufacturingSites`.

    Essa especificação de formatação é muito complexa para descrever como um único prompt. Ele deve ser dividido em etapas menores.

    Vale a pena observar que o número de índice de departmentName selecionado pode ser usado para selecionar o departmentAbbreviation e calcular o primeiro dígito do número do produto.

1. Copie as declarações de variável a seguir e cole-as no local da segunda linha de código em branco que você criou.

    ```csharp

    int indexOfDept = 0;
    string deptAbb = "";
    string firstDigit = "";
    string nextTwoDigits = "";
    string sizeCode = "";
    string colorCode = "";
    string manufacturingSite = "";

    ```

    Você deve ter uma linha de código em branco antes e depois das declarações de variável.

    As declarações de variável não são necessárias para o chat embutido gerar sugestão de atualização de código de uma solicitação, mas elas ajudam a indicar o GitHub Copilot em uma linha de código específica à qual a atualização pertence.

1. Selecione a linha de código `int indexOfDept = 0;`, abra o chat embutido e insira o seguinte prompt:

    ```output
    Assign the array index for departmentName to indexOfDept.
    ```

1. Examine as sugestões fornecidas pelo GitHub Copilot.

    Você deve ver uma sugestão que atribui o número de índice da matriz correspondente ao departmentName selecionado para indexOfDept.

    Se você não receber a sugestão esperada, poderá selecionar **Descartar** para rejeitar a sugestão e tentar novamente. O prompt a seguir fornece contexto adicional para a atribuição:

    ```output
    Create an int named indexOfDept. Assign the array index number corresponding to the selected departmentName to indexOfDept.
    ```

    Esse prompt especifica a criação de uma variável de inteiro chamada `indexOfDept`, bem como atribuir um valor. Você pode executar esse prompt sem criar/selecionar a declaração de variável, mas o GitHub Copilot ocasionalmente pode perder seu ponto de ancoragem quando você abre o chat embutido sem nenhum código selecionado.

    > [!NOTE]
    > O botão **Alternar Alterações** (acessível do menu suspenso **Mais Ações** à direita dos botões **Aceitar** e **Descartar**) pode ser usado para mostrar/ocultar o código excluído pela atualização sugerida. Isso pode ser útil quando você quer ver o código original com a atualizar do código sugerido.

1. Para aceitar a sugestão fornecida pelo GitHub Copilot, selecione **Aceitar**.

1. Selecione a linha de código `string deptAbb = "";`, abra o chat embutido e insira o seguinte prompt:

    ```output
    Use indexOfDept to assign a department abbreviation to deptAbb.
    ```

1. Examine as sugestões fornecidas pelo GitHub Copilot.

    Você deve ver uma sugestão que atribui o número de índice da matriz correspondente ao departmentName selecionado para indexOfDept.

1. Para aceitar a sugestão fornecida pelo GitHub Copilot, selecione **Aceitar**.

1. Selecione a linha de código `string firstDigit = "";`, abra o chat embutido e insira o seguinte prompt:

    ```output
    Assign indexOfDept + 1 to firstDigit.
    ```

1. Examine as sugestões fornecidas pelo GitHub Copilot, e selecione **Aceitar**.

1. Selecione a linha de código `string string nextTwoDigits = ""; = "";`, abra o chat embutido e insira o seguinte prompt:

    ```output
    Assign a random number 1-99 to nextTwoDigits. Include a leading 0 for numbers less than 10.
    ```

1. Examine as sugestões fornecidas pelo GitHub Copilot, e selecione **Aceitar**.

1. Selecione a linha de código `string sizeCode = "";`, abra o chat embutido e insira o seguinte prompt:

    ```output
    From the list {XS, S, M, L, XL}, randomly select a product size and assign it to sizeCode.
    ```

1. Examine as sugestões fornecidas pelo GitHub Copilot, e selecione **Aceitar**.

    Nesse caso, você deverá ver uma sugestão que atribui um tamanho de produto selecionado aleatoriamente à variável `sizeCode`. O GitHub Copilot pode sugerir o uso de uma ou várias linhas de código para atender a esse prompt. De qualquer forma, ele provavelmente sugerirá a criação de uma matriz de cadeia de caracteres de tamanhos de produto e, em seguida, usará `random` para atribuir um dos tamanhos a `sizeCode`.

1. Selecione a linha de código `string colorCode = "";`, abra o chat embutido e insira o seguinte prompt:

    ```output
    From the list {BK, BL, GR, RD, YL, OR, WT, GY}, randomly select a product color and assign it to colorCode.
    ```

1. Examine as sugestões fornecidas pelo GitHub Copilot, e selecione **Aceitar**.

1. Selecione a linha de código `string manufacturingSite = "";`, abra o chat embutido e insira o seguinte prompt:

    ```output
    Assign a randomly selected manufacturing site to manufacturingSite.
    ```

1. Examine as sugestões fornecidas pelo GitHub Copilot, e selecione **Aceitar**.

1. Reserve um minuto para revisar seu código.

    Você deve ter uma série de linhas de código que atribuam valores às variáveis usadas para construir a productID. A próxima etapa é construir o valor productID.

    ```csharp

    int indexOfDept = Array.IndexOf(ProdDepartments.departmentNames, salesData[i].departmentName);
    string deptAbb = ProdDepartments.departmentAbbreviations[indexOfDept];
    string firstDigit = (indexOfDept + 1).ToString();
    string nextTwoDigits = random.Next(1, 100).ToString("D2");
    string sizeCode = new string[] { "XS", "S", "M", "L", "XL" }[random.Next(0, 5)];
    string colorCode = new string[] { "BK", "BL", "GR", "RD", "YL", "OR", "WT", "GY" }[random.Next(0, 8)];
    string manufacturingSite = ManufacturingSites.manufacturingSites[random.Next(0, ManufacturingSites.manufacturingSites.Length)];

    ```

1. Selecione a linha de código `salesData[i].productID = random.Next(1, 101);`, abra o chat embutido e insira o seguinte prompt:

    ```output
    Add a "-" to deptAbb, nextTwoDigits, sizeCode, and colorCode. Combine deptAbb, firstDigit, nextTwoDigits, sizeCode, colorCode, and manufacturingSite to create the productID.
    ```

1. Examine as sugestões fornecidas pelo GitHub Copilot, e selecione **Aceitar**.

    Você deve ver uma sugestão que constrói o valor productID usando as variáveis atribuídas anteriormente. A sugestão deve incluir o código necessário para formatar a productID como "`DDDD-###-SS-CC-MMM`".

1. Atualize manualmente a atribuição `unitPrice` para usar um intervalo de 25 a 300 da seguinte maneira:

    ```csharp
    salesData[i].unitPrice = random.Next(25, 300) + random.NextDouble();
    ```

1. Crie uma linha em branco após a atribuição de `unitPrice`.

1. Aceite a conclusão da linha de código exibida:

    O GitHub Copilot deve fornecer uma sugestão que atribua um valor a `baseCost` que aparece semelhante à seguinte linha de código:

    ```csharp
    salesData[i].baseCost = random.Next(10, 100) + random.NextDouble();
    ```

1. Selecione a linha de código usada para atribuir um valor a `salesData[i].baseCost`, abra o chat embutido e insira a seguinte solicitação:

    ```output
    Discount the unitPrice by a random percentage between 5 and 20. Assign the result to baseCost.
    ```

1. Examine as sugestões fornecidas pelo GitHub Copilot, e selecione **Aceitar**.

1. Crie uma linha em branco após a atribuição de `baseCost` e aceite a conclusão da linha de código exibida.

    O GitHub Copilot deve fornecer uma sugestão que atribua um valor a `volumeDiscount`.

1. Selecione a linha de código usada para atribuir um valor a `salesData[i].volumeDiscount`, abra o chat embutido e insira a seguinte solicitação:

    ```output
    Assign 10 percent of quantitySold to volumeDiscount. Truncate any fractional values.
    ```

1. Examine as sugestões fornecidas pelo GitHub Copilot, e selecione **Aceitar**.

1. O método GenerateSalesData atualizado agora deve ser semelhante ao seguinte snippet:

    ```csharp

    public SalesData[] GenerateSalesData()
    {
        SalesData[] salesData = new SalesData[1000];
        Random random = new Random();
        for (int i = 0; i < 1000; i++)
        {
            salesData[i].dateSold = new DateOnly(2023, random.Next(1, 13), random.Next(1, 29));
            salesData[i].departmentName = ProdDepartments.departmentNames[random.Next(0, ProdDepartments.departmentNames.Length)];
            int indexOfDept = Array.IndexOf(ProdDepartments.departmentNames, salesData[i].departmentName);
            string deptAbb = ProdDepartments.departmentAbbreviations[indexOfDept];
            string firstDigit = (indexOfDept + 1).ToString();
            string nextTwoDigits = random.Next(1, 100).ToString("D2");
            string sizeCode = new string[] { "XS", "S", "M", "L", "XL" }[random.Next(0, 5)];
            string colorCode = new string[] { "BK", "BL", "GR", "RD", "YL", "OR", "WT", "GY" }[random.Next(0, 8)];
            string manufacturingSite = ManufacturingSites.manufacturingSites[random.Next(0, ManufacturingSites.manufacturingSites.Length)];
            salesData[i].productID = $"{deptAbb}-{firstDigit}{nextTwoDigits}-{sizeCode}-{colorCode}-{manufacturingSite}";
            salesData[i].quantitySold = random.Next(1, 101);
            salesData[i].unitPrice = random.Next(25, 300) + random.NextDouble();
            salesData[i].baseCost = salesData[i].unitPrice * (1 - (random.Next(5, 21) / 100.0));
            salesData[i].volumeDiscount = (int)(salesData[i].quantitySold * 0.1);
        }
        return salesData;
    }

    ```

1. Salve suas alterações.

### Atualizar o método QuarterlySalesReport usando chat embutido

Você precisa atualizar o método `QuarterlySalesReport`. Com base nas metas do projeto, você precisa implementar as seguintes atualizações:

- Ao exibir os resultados das vendas, liste os resultados em uma ordem lógica. Por exemplo, ao listar a venda total por trimestre, os trimestres devem ser listados em ordem do 1º ao 4º trimestre.
- Exibir valores de moeda usando configurações regionais.
- Adicionar cálculos para o lucro trimestral e o percentual de lucro
- Adicione cálculos específicos a departamentos individuais: vendas trimestrais, lucro e percentual de lucro.
- Adicione cálculos para locais de fabricação específicos: vendas trimestrais, lucro e percentual de lucro.

Neste ponto, seu método `QuarterlySalesReport` deve ser semelhante ao seguinte snippet de código:

```csharp

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
        Console.WriteLine("{0}: ${1}", quarter.Key, quarter.Value);
    }
}

```

Para atualizar o método `QuarterlySalesReport`, conclua as seguintes etapas:

1. Para verificar a saída do relatório de vendas trimestral atual, execute o aplicativo.

    Você deve ver uma lista de resultados de vendas trimestrais exibidos na janela do console. Valores aleatórios são usados, portanto, os dados numéricos variam a cada execução.

    A saída do relatório de vendas trimestrais deve ser semelhante à seguinte:

    ```output
    Quarterly Sales Report
    ----------------------
    Q3: $2060165.1045630067
    Q2: $2000706.5521363618
    Q4: $2168920.603583816
    Q1: $2174302.3663762277
    ```

    Observe que os trimestres não estão listados em ordem e os valores de moeda não estão formatados corretamente.

    Sua primeira tarefa é corrigir esses problemas.

1. Localize o método `QuarterlySalesReport` no arquivo Program.cs.

1. Selecione todo o método.

1. Abra a interface do chat embutido e insira a seguinte solicitação:

    ```output
    Update the QuarterlySalesReport method to display quarterly results in order. Format currency using regional settings. 
    ```

1. Reserve um minuto para examinar as sugestões fornecidas pelo GitHub Copilot.

    Você deve ver uma sugestão que inclui o código necessário para calcular o lucro trimestral e a porcentagem de lucro. A sugestão deve incluir o código necessário para calcular o lucro e o percentual de lucro para cada trimestre.

1. Para aceitar a sugestão fornecida pelo GitHub Copilot, selecione **Aceitar**.

1. Salve suas alterações.

1. Execute o aplicativo e verifique se os resultados de vendas trimestrais agora são exibidos em ordem e se os valores de moeda estão formatados corretamente.

    Embora os valores numéricos sejam diferentes, a saída do relatório de vendas trimestrais agora deve ser formatada de forma semelhante à seguinte saída:

    ```output
    Quarterly Sales Report
    ----------------------
    Q1: $2,174,302.37
    Q2: $2,000,706.55
    Q3: $2,060,165.10
    Q4: $2,168,920.60

    ```

    Sua próxima etapa é adicionar cálculos para o lucro trimestral e o percentual de lucro.

1. Localize o método `QuarterlySalesReport` no arquivo Program.cs.

1. Selecione todo o método.

1. Abra a interface do chat embutido e insira a seguinte solicitação:

    ```output
    Update the QuarterlySalesReport method to include calculations for quarterly profit and profit percentage. Include the new calculations in the report output.
    ```

1. Reserve um minuto para examinar as sugestões fornecidas pelo GitHub Copilot.

    Você deve ver uma sugestão que inclui o código necessário para calcular o lucro trimestral e a porcentagem de lucro. A sugestão deve incluir o código necessário para calcular o lucro e o percentual de lucro para cada trimestre.

1. Para aceitar a sugestão fornecida pelo GitHub Copilot, selecione **Aceitar**.

1. Continue selecionando **Aceitar** para as sugestões restantes.

1. Salve suas alterações.

1. Execute o aplicativo e verifique se os resultados de vendas trimestrais agora incluem cálculos para o lucro e o percentual de lucro.

    Embora os valores numéricos sejam diferentes, a saída do relatório de vendas trimestrais agora deve ser formatada de forma semelhante à seguinte saída:

    ```output
    Quarterly Sales Report
    ----------------------
    Q1: Sales: $1,881,091.17, Profit: $231,351.24, Profit Percentage: 12.00%
    Q2: Sales: $1,949,240.91, Profit: $244,649.35, Profit Percentage: 11.00%
    Q3: Sales: $2,298,017.35, Profit: $273,622.53, Profit Percentage: 5.00%
    Q4: Sales: $2,279,185.96, Profit: $272,548.80, Profit Percentage: 16.00%    

    ```

    Sua próxima etapa é adicionar cálculos para vendas trimestrais, lucro e percentual de lucro por departamento.

1. Selecione todo o método.

1. Para abrir a interface do chat embutido e depois inserir a seguinte solicitação:

    ```output
    Update the QuarterlySalesReport method to include calculations for quarterly sales, profit, and profit percentage by department. Include the new calculations in the report output. 
    ```

1. Reserve um minuto para examinar as sugestões fornecidas pelo GitHub Copilot.

    Você deve ver uma sugestão que inclui o código necessário para calcular o lucro trimestral e a porcentagem de lucro. A sugestão deve incluir o código necessário para calcular o lucro e o percentual de lucro para cada trimestre.

1. Para aceitar a sugestão fornecida pelo GitHub Copilot, selecione **Aceitar**.

1. Continue selecionando **Aceitar** para as sugestões restantes.

1. Salve suas alterações.

1. Execute o aplicativo e verifique se os resultados de vendas trimestrais agora incluem cálculos para o lucro e o percentual de lucro.

    Embora os valores numéricos sejam diferentes, a saída do relatório de vendas trimestrais agora deve ser formatada de forma semelhante à seguinte saída:

    ```output
    Quarterly Sales Report
    ----------------------
    Q1: Sales: $2,043,493.57, Profit: $262,571.72, Profit Percentage: 14.00%
    By Department:
    Department: Accessories, Sales: $188,977.90, Profit: $25,229.53, Profit Percentage: 14.00%
    Department: Children's Clothing, Sales: $186,552.49, Profit: $25,511.74, Profit Percentage: 13.00%
    Department: Footwear, Sales: $293,706.49, Profit: $39,224.99, Profit Percentage: 19.00%
    Department: Men's Clothing, Sales: $301,385.47, Profit: $36,756.06, Profit Percentage: 19.00%
    Department: Outerwear, Sales: $238,099.65, Profit: $24,371.92, Profit Percentage: 15.00%
    Department: Sportswear, Sales: $251,349.38, Profit: $34,142.40, Profit Percentage: 8.00%
    Department: Undergarments, Sales: $297,690.60, Profit: $35,305.13, Profit Percentage: 9.00%
    Department: Women's Clothing, Sales: $285,731.58, Profit: $42,029.95, Profit Percentage: 19.00%
    
    Q2: Sales: $1,925,948.90, Profit: $232,929.95, Profit Percentage: 17.00%
    By Department:
    Department: Accessories, Sales: $251,572.42, Profit: $33,250.17, Profit Percentage: 11.00%
    Department: Children's Clothing, Sales: $311,862.99, Profit: $36,537.33, Profit Percentage: 8.00%
    Department: Footwear, Sales: $203,148.87, Profit: $23,041.46, Profit Percentage: 11.00%
    Department: Men's Clothing, Sales: $229,781.14, Profit: $26,226.68, Profit Percentage: 9.00%
    Department: Outerwear, Sales: $211,610.47, Profit: $23,684.65, Profit Percentage: 9.00%
    Department: Sportswear, Sales: $204,083.63, Profit: $20,750.56, Profit Percentage: 8.00%
    Department: Undergarments, Sales: $264,733.26, Profit: $35,155.66, Profit Percentage: 15.00%
    Department: Women's Clothing, Sales: $249,156.13, Profit: $34,283.45, Profit Percentage: 17.00%
    
    Q3: Sales: $2,113,223.50, Profit: $256,591.16, Profit Percentage: 7.00%
    By Department:
    Department: Accessories, Sales: $288,161.91, Profit: $32,279.54, Profit Percentage: 10.00%
    Department: Children's Clothing, Sales: $198,313.55, Profit: $24,146.72, Profit Percentage: 7.00%
    Department: Footwear, Sales: $205,840.60, Profit: $27,630.49, Profit Percentage: 5.00%
    Department: Men's Clothing, Sales: $229,279.26, Profit: $26,618.62, Profit Percentage: 13.00%
    Department: Outerwear, Sales: $353,696.46, Profit: $44,634.82, Profit Percentage: 14.00%
    Department: Sportswear, Sales: $229,490.12, Profit: $27,697.91, Profit Percentage: 5.00%
    Department: Undergarments, Sales: $316,942.44, Profit: $40,518.71, Profit Percentage: 5.00%
    Department: Women's Clothing, Sales: $291,499.15, Profit: $33,064.35, Profit Percentage: 10.00%
    
    Q4: Sales: $1,896,279.88, Profit: $248,226.28, Profit Percentage: 15.00%
    By Department:
    Department: Accessories, Sales: $336,698.68, Profit: $44,714.55, Profit Percentage: 11.00%
    Department: Children's Clothing, Sales: $193,345.18, Profit: $23,261.33, Profit Percentage: 13.00%
    Department: Footwear, Sales: $215,183.23, Profit: $29,616.00, Profit Percentage: 15.00%
    Department: Men's Clothing, Sales: $171,663.38, Profit: $24,299.37, Profit Percentage: 5.00%
    Department: Outerwear, Sales: $229,791.52, Profit: $28,211.17, Profit Percentage: 15.00%
    Department: Sportswear, Sales: $230,031.90, Profit: $32,732.40, Profit Percentage: 8.00%
    Department: Undergarments, Sales: $300,824.19, Profit: $34,649.79, Profit Percentage: 6.00%
    Department: Women's Clothing, Sales: $218,741.80, Profit: $30,741.67, Profit Percentage: 20.00%

    ```

### Resumo

Nesta demonstração, você usou o recurso de chat embutido para atualizar os métodos `GenerateSalesData` e `QuarterlySalesReport`. Você adicionou novos campos à estrutura de dados `SalesData` e atualizou o método `GenerateSalesData` para gerar dados para os novos campos. Você também atualizou o método `QuarterlySalesReport` para incluir cálculos para o lucro trimestral e o percentual de lucro. Você também adicionou cálculos para vendas trimestrais, lucro e percentual de lucro por departamento.
