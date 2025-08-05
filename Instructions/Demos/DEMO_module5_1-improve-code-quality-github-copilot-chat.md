---
demo:
  title: 'Demonstração: Melhorar a qualidade do código usando o GitHub Copilot Chat'
  module: 'Module 5: Implement code improvements using GitHub Copilot tools'
---

# Demonstração: Melhorar a qualidade do código usando o GitHub Copilot Chat

## Instruções

As atividades de demonstração são projetadas para um ambiente que inclui os seguintes recursos:

- Visual Studio Code.
- A extensão do kit de desenvolvimento em C# para o Visual Studio Code.
- As extensões do GitHub Copilot e do GitHub Copilot Chat para Visual Studio Code. É necessária uma conta do GitHub com uma assinatura ativa do GitHub Copilot.
- Projetos de amostras de código criadas usando C#.

**OBSERVAÇÃO**: Recomendamos que os instrutores considerem usar sua própria conta do GitHub e a assinatura do GitHub Copilot para as demonstrações. Isso irá permitir que você controle e personalize seu ambiente de desenvolvimento. Também facilitará o ajuste das demonstrações para atender às necessidades de suas salas de aula.

**IMPORTANTE**: Se você optar por executar as demonstrações no ambiente de laboratório hospedado em vez do seu computador de instrutor, poderá descompactar os aplicativos de exemplo no ambiente hospedado. Você precisará configurar as extensões do GitHub Copilot no ambiente hospedado antes de executar as demonstrações. Você pode perceber que o ambiente hospedado é mais lento do que o seu ambiente local, então talvez precise ajustar o ritmo das demonstrações de acordo.

### Apresentar a demonstração

O termo "qualidade do código" refere-se à qualidade geral da base de código, incluindo legibilidade, manutenção e modularidade. A qualidade do código é uma medida de quão "bem estruturado" seu código é e quão facilmente ele pode ser compreendido, mantido e estendido.

> [!IMPORTANT]
> Explique aos alunos que esta demonstração não trata das melhores práticas para desenvolver código de alta qualidade. Em vez disso, ele se concentra em como usar o GitHub Copilot Chat para gerar sugestões para melhorar a qualidade do código em um aplicativo de exemplo. As sugestões não representam práticas recomendadas ou soluções abrangentes para o desenvolvimento de código de alta qualidade. Os desenvolvedores devem usar seu julgamento e experiência para avaliar e implementar as sugestões fornecidas pelo GitHub Copilot Chat. A implementação de sugestões propostas pelo GitHub Copilot não substitui a necessidade de testes e revisões detalhadas de código.

As seções a seguir fornecem uma visão geral sobre refatoração de código e qualidade de código que seus alunos devem conhecer.

#### Refatoração de código e código de alta qualidade

A refatoração de código é o processo de reestruturação do código existente sem alterar seu comportamento externo. O objetivo da refatoração de código é melhorar a estrutura interna da base de código, facilitando a compreensão, a manutenção e a extensão. A refatoração de código pode ajudá-lo a produzir código de alta qualidade, melhorando a legibilidade, reduzindo a complexidade, melhorando a modularidade e aumentando a reutilização. Cada um desses fatores ajuda a criar uma base de código mais gerenciável e mantenedível.

Os desenvolvedores devem considerar os seguintes fatores ao trabalhar em melhorias de qualidade de código:

- Legibilidade: Melhorar ou aprimorar a legibilidade do código pode facilitar a compreensão dos desenvolvedores.
- Complexidade: Reduzir a complexidade do código torna o código mais fácil de entender, gerenciar e manter.
- Modularidade e reutilização: Dividir o código em módulos ou componentes menores e reutilizáveis pode facilitar o gerenciamento e a manutenção do código.

Os fatores listados acima representam três áreas comuns que os desenvolvedores identificam ao discutir a qualidade do código. Outros fatores que podem ser associados à qualidade do código incluem:

- Teste: A facilidade com que o código pode ser testado para garantir que ele funcione corretamente. Muitas vezes um subproduto de bom design e modularidade.
- Extensibilidade: A facilidade com que o código pode ser estendido ou aprimorado para adicionar novos recursos ou funcionalidades. Muitas vezes um subproduto de bom design e modularidade.

A qualidade do código não é o único fator que os desenvolvedores consideram durante as revisões de código. Aqui estão mais alguns fatores que os desenvolvedores geralmente avaliam além da qualidade do código:

- Confiabilidade: A capacidade do código de executar suas funções pretendidas em condições especificadas.
- Desempenho: Com que eficiência o código é executado.
- Segurança: A capacidade do código de proteger dados e recursos contra acesso ou modificação não autorizados.
- Escalabilidade: A capacidade do código de lidar com o aumento de cargas de trabalho ou o crescimento no futuro.
- Usabilidade: A facilidade com que o código pode ser usado por desenvolvedores ou usuários finais.
- Portabilidade: A capacidade do código de ser executado em diferentes plataformas ou ambientes.

> [!NOTE]
> As duas próximas unidades neste módulo abrangem a melhoria da confiabilidade, do desempenho e da segurança do código usando o GitHub Copilot Chat.

Melhorar a qualidade do código geralmente é considerado um precursor para adicionar novos recursos ou aprimoramentos. Você deve considerar melhorias na qualidade do código antes de trabalhar na confiabilidade, desempenho ou segurança do código.

Nesta demonstração, você irá usar o GitHub Copilot Chat para gerar sugestões que ajudam você a melhorar a qualidade do código em um aplicativo de exemplo.

### Desenvolver solicitações para o GitHub Copilot Chat

Reitere a importância de criar bons prompts.

Os prompts que você escreve para o GitHub Copilot Chat devem fornecer um contexto de *claramente definido* e *intenção*. A *intenção* parte do prompt descreve a meta que você deseja alcançar. Por exemplo, você pode pedir ao GitHub Copilot para "refatorar para melhorar a modularidade do código". O *contexto* parte do prompt informa ao GitHub Copilot quais recursos considerar. Por exemplo, talvez você queira que o GitHub Copilot considere todo o workspace, mas concentre-se em um arquivo ou seção de código específico. Considere as seguintes sugestões ao desenvolver seus prompts:

- Defina um contexto externo com escopo em um nível mais alto do que o código que você deseja atualizar. Por exemplo, se você quiser refatorar um método, especifique a classe ou o arquivo que contém o método como o contexto externo. Identifique o método como um contexto interno.
- Use participantes de chat e variáveis de chat para ajudar a especificar o contexto. Você pode usar as variáveis de chat `#file:` e `#selection` para identificar o código específico no qual você está focado. Você também pode incluir o workspace completo (`@workspace`) quando apropriado. Suponha que você queira refatorar um método em um arquivo específico. Você pode usar a variável de chat `#file:` para informar ao GitHub Copilot qual arquivo examinar. Você pode selecionar o método no editor e usar a variável de chat `#selection` para informar ao GitHub Copilot qual código deseja refatorar. Você também pode usar a variável de chat `@workspace` para informar ao GitHub Copilot para considerar todo o workspace. Reforce o contexto especificado referindo-se à seleção ou arquivo na parte da linguagem natural do prompt. Por exemplo, você pode dizer: "como posso melhorar a legibilidade do código selecionado?"
- A intenção deve ser clara e específica e deve especificar o aspecto de qualidade do código que você deseja melhorar. Por exemplo, você pode perguntar ao GitHub Copilot Chat para "Como posso melhorar a modularidade do código selecionado".

Durante esta parte da demonstração, você revisa o projeto **APL2007M5BankAccount** e cria três prompts para o GitHub Copilot Chat. Os prompts se concentram em melhorar a legibilidade do código, a manutenção e a modularidade.

Use as seguintes etapas para concluir esta parte da demonstração:

1. Abra o aplicativo de exemplo **APL2007M5BankAccount** no Visual Studio Code.

1. Abra o arquivo **Program.cs** e examine o código.

    Este programa é um aplicativo de console que simula um sistema bancário. Aqui estão os principais recursos:

    - Método principal: O método Principal é o ponto de entrada do aplicativo. Ele cria contas bancárias e usa as contas para simular transações.

    - Constantes: O programa define várias constantes na parte superior da classe Program. As constantes incluem coisas como: o número de contas a serem criadas, o número de transações a simular e os limites de transação.

1. Reserve um minuto para escrever alguns prompts que você pode usar para melhorar a legibilidade do código, a manutenção e a modularidade.

    Para o projeto BankAccount, você deve anexar os arquivos BankAccount.cs e/ou Program.cs ao contexto do Chat. O prompt deve ser semelhante aos exemplos a seguir:

    Prompt: `@workspace /explain How can I improve the readability of the [selected code]?`

    Prompt: `@workspace /explain #selection How can I improve the maintainability of the [selected code]?`

    Prompt: `@workspace /explainHow can I improve the modularity of the [selected code]?`

    Prompt: `#selection How can I refactor the [selected code] to improve modularity?`

    Prompt: `@workspace /explain What are some options for simplifying the [selected code]?`

1. Crie três prompts a serem usados durante o restante da demonstração.

### Refatorar seu código usando o GitHub Copilot Chat

Você pode usar o GitHub Copilot Chat para sugerir atualizações de código que refatoram e melhoram seu código. É importante entender seu código e suas metas antes de tomar uma decisão sobre como refatorar o aplicativo.

As sugestões que o GitHub Copilot Chat fornece devem ser revisadas com cuidado. Considere quais sugestões dão suporte às suas metas antes de implementá-las. Para esta demonstração, o seu tempo também pode ser um fator na decisão sobre quais sugestões implementar.

Use as seguintes etapas para concluir esta parte da demonstração:

1. Reserve um minuto para examinar os métodos incluídos no arquivo Program.cs.

    - Método CreateBankAccounts: Esse método cria um número especificado de contas bancárias com saldos iniciais aleatórios, nomes de titulares de conta, tipos de conta e datas de abertura. Ele usa um bloco try-catch para lidar com quaisquer exceções que possam ocorrer durante a criação da conta.

    - Método SimulateTransactions: Esse método simula um número especificado de transações em uma lista de contas bancárias. Ele gera um valor de transação aleatória para cada transação e, em seguida, credita ou debita a conta com esse valor, dependendo se o valor é positivo ou negativo. Ele usa um bloco try-catch para lidar com quaisquer exceções que possam ocorrer durante as transações.

    - Método SimulateTransfers: Esse método é idêntico ao método SimulateTransactions. Parece ser destinado a simular transferências entre contas, mas atualmente apenas simula transações em contas individuais.

    - Método GenerateRandomDollarAmount: Esse método gera um valor de dólar aleatório dentro de um intervalo especificado. Ele usa uma fórmula diferente para gerar o valor dependendo se o valor é para um saldo de conta ou uma transação.

    - Método GenerateRandomAccountHolder: Esse método seleciona um nome de titular de conta aleatório em uma lista predefinida de nomes.

    - Método GenerateRandomAccountType: Esse método seleciona um tipo de conta aleatória em uma lista predefinida de tipos.

    - Método GenerateRandomDateOpened: Esse método gera uma data aleatória dentro de um intervalo especificado de anos de volta da data atual.

1. Verifique se o projeto é compilado e executado sem erros.

1. Escolha seu primeiro prompt nos prompts que você preparou.

1. Selecione o prompt que você deseja melhorar e abra o modo de exibição de Chat.

1. No modo de exibição chat, use o botão **Anexar Contexto** para adicionar arquivos relevantes ao contexto de Chat e, em seguida, insira seu prompt.

    Você também pode demonstrar o uso da operação do tipo "arrastar e soltar" para anexar arquivos do painel Gerenciador de Soluções ao contexto do chat.

1. Examinar as sugestões fornecidas pelo Chat do GitHub Copilot.

    Por exemplo, suponha que você conclua as seguintes ações:

    - Você decide trabalhar no arquivo Program.cs.
    - Escolha o seguinte prompt: `@workspace /explain #selection How can I improve the readability of the GenerateRandomBalance, GenerateRandomAccountHolder, GenerateRandomAccountType, and GenerateRandomDateOpened methods?`
    - Abra o arquivo Program.cs e selecione os seguintes métodos: `GenerateRandomBalance`, `GenerateRandomAccountHolder`, `GenerateRandomAccountType`, `GenerateRandomDateOpened`.
    - Abra o modo de exibição de Chat e anexe os arquivos BankAccount.cs e Program.cs ao Contexto do Chat.
    - Insira o prompt no modo de exibição chat.

    Depois de concluir essas ações, o GitHub Copilot Chat sugere atualizações semelhantes à seguinte resposta:

    *Para melhorar a legibilidade desses métodos, você pode seguir essas etapas:*

    *1. Extraia código repetido em métodos separados: O objeto Random é criado várias vezes em métodos diferentes. Você poderia criar um objeto Random estático no nível da classe e usá-lo em todos os métodos. Isso não apenas melhoraria a legibilidade, mas também proporcionaria uma melhor aleatoriedade.*

    `private static readonly Random random = new Random();`

    *2. Use nomes de variáveis significativos: O nome da variável `range` no método GenerateRandomDateOpened é um pouco vago. Um nome mais descritivo, como daysRange, poderia ser usado.*

    *3. Adicione comentários: Embora o código seja principalmente autoexplicativo, adicionar comentários para explicar o que cada método faz pode ser útil para outros desenvolvedores que leem seu código.*

    *4. Use constantes para números mágicos: No método GenerateRandomDateOpened, o número `10` é usado para representar a quantidade de anos que a data de início pode retroceder. Isso pode ser extraído para uma constante com um nome descritivo, como `MaxYearsBack`.*

    *5. Use a palavra-chave var: No C#, você pode usar a palavra-chave var quando o lado direito da atribuição deixa o tipo óbvio. Isso pode tornar seu código mais limpo e fácil de ler.*

   *Veja como seu código pode ficar após essas melhorias:*

    ```csharp

    private static readonly Random random = new Random();
    private const int MaxYearsBack = 10;
    static double GenerateRandomBalance(double min, double max)
    {
        double balance = random.NextDouble() * (max - min) + min;
        return Math.Round(balance, 2);
    }
    static string GenerateRandomAccountHolder()
    {
        string[] accountHolderNames = {  /* names here */  };
        var accountHolderName = accountHolderNames[random.Next(0, accountHolderNames.Length)];
        return accountHolderName;
    }
    static string GenerateRandomAccountType()
    {
        string[] accountTypes = {  /* types here */  };
        return accountTypes[random.Next(0, accountTypes.Length)];
    }
    static DateTime GenerateRandomDateOpened()
    {
        DateTime startDate = new DateTime(DateTime.Today.Year - MaxYearsBack, 1, 1);
        int daysRange = (DateTime.Today - startDate).Days;
        DateTime randomDate = startDate.AddDays(random.Next(daysRange));
        if (randomDate.Year == DateTime.Today.Year && randomDate >= DateTime.Today)
        {
            randomDate = randomDate.AddDays(-1);
        }
        return randomDate;
    }

    ```

    > [!IMPORTANT]
    > Observe os valores de espaço reservado (como `/* types here */`) nos métodos `GenerateRandomAccountHolder` e `GenerateRandomAccountType`. O GitHub Copilot Chat ocasionalmente substitui os detalhes do código por espaços reservados. Estes são fáceis de detectar se você está prestando atenção. Você precisará substituir os valores de espaço reservado por valores de seu aplicativo ao implementar uma atualização. Se você vir espaços reservados, faça uma cópia do código existente antes de implementar as atualizações sugeridas. Se o bloco de código sugerido se alinhar ao código em seu aplicativo, você poderá usar um comentário em bloco para comentar seu código existente e, em seguida, usar o botão **Inserir no Cursor** para implementar as atualizações sugeridas sem criar um conflito de nomenclatura. Depois de verificar se a atualização sugerida funciona conforme o esperado, você pode remover o comentário do bloco.

1. Implemente as atualizações sugeridas que ajudam a melhorar a legibilidade do código, a manutenção e a modularidade.

    Se você usou comentários de bloco para comentar seu código existente, poderá usar o modo de exibição de chat **Inserir no Cursor** para inserir as atualizações sugeridas. Você também pode usar a opção Copiar e colar a atualização no local de sua escolha.

    Considere os padrões de codificação e as políticas implementadas em seu local de trabalho antes de escolher quais sugestões de atualização implementar.

1. Para garantir que nenhum erro tenha sido introduzido quando você implementou suas atualizações, compile e execute sua solução antes de continuar.

1. Insira seu segundo prompt e examine as atualizações propostas pelo GitHub Copilot Chat.

1. Examinar as sugestões fornecidas pelo Chat do GitHub Copilot.

    Por exemplo, suponha que você conclua as seguintes ações:

    - Implemente as atualizações sugeridas pelo GitHub Copilot Chat para o primeiro prompt de exemplo.
    - Você decide continuar trabalhando no arquivo Program.cs.
    - Escolha o seguinte prompt: `@workspace /explain How can I improve the maintainability of the Main, GenerateRandomBalance, GenerateRandomAccountHolder, GenerateRandomAccountType, and GenerateRandomDateOpened methods?`.
    - Selecione os seguintes métodos: `Main`, `GenerateRandomBalance`, `GenerateRandomAccountHolder`, `GenerateRandomAccountType`, `GenerateRandomDateOpened`.
    - Abra o modo de exibição de Chat e anexe os arquivos BankAccount.cs e Program.cs ao Contexto do Chat.
    - Insira o prompt no modo de exibição chat.

    Depois de concluir essas ações, o GitHub Copilot Chat sugere atualizações semelhantes à seguinte resposta:

    *Para melhorar a manutenibilidade desses métodos, você pode seguir essas etapas:*

    *1. Separação de preocupações: O método Main está fazendo muitas coisas: criando contas, simulando transações e simulando transferências. Essas atividades poderiam ser divididas em métodos separados para melhorar a legibilidade e a manutenção do código.*

    *2. Tratamento de erro: O código utiliza uma Exception genérica para tratamento de erros. Seria melhor criar exceções personalizadas específicas para a aplicação. Isso facilitaria a compreensão e o tratamento de erros.*

    *3. Números mágicos: O código contém números mágicos (como 20 para o número de contas, 100 para o número de transações etc.). Eles devem ser substituídos por constantes nomeadas.*

    *4. Duplicação de código: O código para gerar valores aleatórios está duplicado em vários locais. Isso pode ser refatorado em uma classe ou métodos utilitários.*

    ```csharp

    class Program
    {
        private static readonly Random random = new Random();
        private const int MaxYearsBack = 10;
        private const int NumberOfAccounts = 20;
        private const int NumberOfTransactions = 100;
        static void Main(string[] args)
        {
            List<BankAccount> accounts = CreateBankAccounts(NumberOfAccounts);
            SimulateTransactions(accounts, NumberOfTransactions);
            SimulateTransfers(accounts);
        }
        static List<BankAccount> CreateBankAccounts(int numberOfAccounts)
        {
            List<BankAccount> accounts = new List<BankAccount>();
            int createdAccounts = 0;
            while (createdAccounts < numberOfAccounts)
            {
                try
                {
                    // same code as before...
                }
                catch (Exception ex)
                {
                    Console.WriteLine($"Account creation failed: {ex.Message}");
                }
            }
            return accounts;
        }
        static void SimulateTransactions(List<BankAccount> accounts, int numberOfTransactions)
        {
            // same code as before...
        }
        static void SimulateTransfers(List<BankAccount> accounts)
        {
            // same code as before...
        }
        // same helper methods as before...
    }

    ```

1. Examinar as sugestões fornecidas pelo Chat do GitHub Copilot.

1. Implemente as atualizações sugeridas que ajudam a melhorar a legibilidade do código, a manutenção e a modularidade.

    Se você usou comentários de bloco para comentar seu código existente, poderá usar o modo de exibição de chat **Inserir no Cursor** para inserir as atualizações sugeridas. Você também pode usar a opção Copiar e colar a atualização no local de sua escolha.

1. Para garantir que nenhum erro tenha sido introduzido pelas alterações, crie e execute sua solução antes de continuar.

1. Insira seu terceiro prompt e, em seguida, examine as sugestões.

    Por exemplo, suponha que você conclua as seguintes ações:

    - Implemente as atualizações sugeridas pelo GitHub Copilot Chat para o primeiro e o segundo prompts de exemplo.
    - Você decide continuar trabalhando no arquivo Program.cs.
    - Escolha o seguinte prompt: `@workspace /explain How can I improve the modularity of the Program.cs file?`.
    - Selecione o seguinte código: Selecione todo o arquivo Program.cs.
    - Abra o modo de exibição de Chat e anexe os arquivos BankAccount.cs e Program.cs ao Contexto do Chat.
    - Insira o prompt no modo de exibição chat.

    Depois de concluir essas ações, o GitHub Copilot Chat sugere atualizações semelhantes à seguinte resposta:

    *Para melhorar a modularidade do arquivo Program.cs, siga estas etapas:*

    *1. Preocupações separadas: A classe `Program` está fazendo muita coisa. Está criando contas, simulando transações e gerando dados aleatórios. Cada uma dessas responsabilidades pode ser uma classe separada. Por exemplo, você poderia ter uma classe `BankAccountFactory` responsável por criar contas bancárias, uma classe `TransactionSimulator` para simular transações e uma classe `RandomDataGenerator` para gerar dados aleatórios.*

    *2. Use interfaces: As interfaces podem ser usadas para definir um contrato para classes. Isso pode tornar seu código mais flexível e mais fácil de testar. Por exemplo, você poderia definir uma interface `IAccountFactory` com um método `Create`, e então fazer com que `BankAccountFactory` implemente essa interface.*

    *3. Números mágicos: Há vários "números mágicos" no código (como 10, 50000, -500, 500, etc.). Esses números devem ser substituídos por constantes nomeadas para tornar o código mais legível e fácil de manter.*

    *4. Duplicação: Os métodos `SimulateTransactions` e `SimulateTransfers` têm um código quase idêntico. Essa duplicação pode ser eliminada criando um método comum que ambos os métodos possam chamar.*

   *Veja um exemplo de como você pode refatorar o método CreateBankAccounts:*

    **Snippet de código A: Usar interfaces**

    ```csharp

    interface IAccountFactory
    {
        BankAccount Create(int index);
    }
    class BankAccountFactory : IAccountFactory
    {
        private readonly RandomDataGenerator _randomDataGenerator;
        public BankAccountFactory(RandomDataGenerator randomDataGenerator)
        {
            _randomDataGenerator = randomDataGenerator;
        }
        public BankAccount Create(int index)
        {
            double initialBalance = _randomDataGenerator.GenerateRandomBalance(10, 50000);
            string accountHolderName = _randomDataGenerator.GenerateRandomAccountHolder();
            string accountType = _randomDataGenerator.GenerateRandomAccountType();
            DateTime dateOpened = _randomDataGenerator.GenerateRandomDateOpened();
            return new BankAccount($"Account {index + 1}", initialBalance, accountHolderName, accountType, dateOpened);
        }
    }
    // In the `Program` class, you would then use the `IAccountFactory` to create accounts:
    interface IAccountFactory
    {
        BankAccount Create(int index);
    }
    class BankAccountFactory : IAccountFactory
    {
        private readonly RandomDataGenerator _randomDataGenerator;
        public BankAccountFactory(RandomDataGenerator randomDataGenerator)
        {
            _randomDataGenerator = randomDataGenerator;
        }
        public BankAccount Create(int index)
        {
            double initialBalance = _randomDataGenerator.GenerateRandomBalance(10, 50000);
            string accountHolderName = _randomDataGenerator.GenerateRandomAccountHolder();
            string accountType = _randomDataGenerator.GenerateRandomAccountType();
            DateTime dateOpened = _randomDataGenerator.GenerateRandomDateOpened();
            return new BankAccount($"Account {index + 1}", initialBalance, accountHolderName, accountType, dateOpened);
        }
    }

    ```

    **Snippet de código B: Duplicação**

    ```csharp

    static void SimulateOperations(List<BankAccount> accounts, int numberOfOperations, Action<BankAccount, double> operation)
    {
        foreach (BankAccount account in accounts)
        {
            for (int i = 0; i < numberOfOperations; i++)
            {
                double transactionAmount = GenerateRandomBalance(-500, 500);
                try
                {
                    operation(account, transactionAmount);
                    Console.WriteLine($"Operation: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                }
                catch (Exception ex)
                {
                    Console.WriteLine($"Operation failed: {ex.Message}");
                }
            }
            Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
        }
    }
    // Then you can call this method like this:
    SimulateOperations(accounts, NumberOfTransactions, (account, amount) => {
        if (amount >= 0)
        {
            account.Credit(amount);
        }
        else
        {
            account.Debit(-amount);
        }
    });

    ```

    > [!NOTE]
    > Você não precisa implementar as sugestões de atualização geradas pelo GitHub Copilot do seu terceiro prompt. Examinar as sugestões pode fornecer insights sobre como o processo de melhoria de código progride.

As próximas duas demonstrações abordam os seguintes tópicos:

- Melhorar a confiabilidade e o desempenho do código usando o GitHub Copilot Chat
- Melhorar a segurança de código usando o GitHub Copilot Chat

## Resumo

Nesta demonstração, você usou o GitHub Copilot Chat para gerar sugestões que ajudam a melhorar a qualidade do código em um aplicativo de exemplo. Você desenvolveu prompts que se concentraram em melhorar a legibilidade do código, a manutenção e a modularidade. Você analisou as sugestões fornecidas pelo GitHub Copilot Chat e implementou as atualizações que ajudaram a melhorar a qualidade do código. Você também considerou sugestões adicionais que poderiam melhorar ainda mais seu código.
