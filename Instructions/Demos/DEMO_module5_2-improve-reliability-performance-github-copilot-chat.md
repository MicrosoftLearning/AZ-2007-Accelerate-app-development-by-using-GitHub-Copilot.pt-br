---
demo:
  title: 'Demonstração: Melhorar a confiabilidade e o desempenho do código usando o GitHub Copilot Chat'
  module: 'Module 5: Implement code improvements using GitHub Copilot tools'
---

# Demonstração: Melhorar a confiabilidade e o desempenho do código usando o GitHub Copilot Chat

## Instruções

As atividades de demonstração são projetadas para um ambiente que inclui os seguintes recursos:

- Visual Studio Code.
- A extensão do kit de desenvolvimento em C# para o Visual Studio Code.
- As extensões do GitHub Copilot e do GitHub Copilot Chat para Visual Studio Code. É necessária uma conta do GitHub com uma assinatura ativa do GitHub Copilot.
- Projetos de amostras de código criadas usando C#.

**OBSERVAÇÃO**: Recomendamos que os instrutores considerem usar sua própria conta do GitHub e a assinatura do GitHub Copilot para as demonstrações. Isso irá permitir que você controle e personalize seu ambiente de desenvolvimento. Também facilitará o ajuste das demonstrações para atender às necessidades de suas salas de aula.

**IMPORTANTE**: Se você optar por executar as demonstrações no ambiente de laboratório hospedado em vez do seu computador de instrutor, poderá descompactar os aplicativos de exemplo no ambiente hospedado. Você precisará configurar as extensões do GitHub Copilot no ambiente hospedado antes de executar as demonstrações. Você pode perceber que o ambiente hospedado é mais lento do que o seu ambiente local, então talvez precise ajustar o ritmo das demonstrações de acordo.

### Apresentar a demonstração

A confiabilidade e o desempenho do código estão intimamente relacionados a aspectos da qualidade do software. Eles são interdependentes das seguintes maneiras:

- Melhorias em uma área podem afetar positivamente a outra.
- As deficiências em uma área podem levar a problemas com a outra.

> [!IMPORTANT]
> Explique aos alunos que esta demonstração não tem como foco as melhores práticas para desenvolver código confiável ou de alto desempenho. Em vez disso, ele se concentra em como usar o GitHub Copilot Chat para gerar sugestões para melhorar a segurança do código em um aplicativo de exemplo. As sugestões não representam as melhores práticas ou as soluções mais abrangentes para confiabilidade e desempenho de código. Os desenvolvedores devem usar seu julgamento e experiência para avaliar e implementar as sugestões fornecidas pelo GitHub Copilot Chat. A implementação de sugestões propostas pelo GitHub Copilot não substitui a necessidade de testes e revisões detalhadas de código.

#### Confiabilidade e desempenho do código

Os desenvolvedores devem se esforçar para alcançar um equilíbrio entre a confiabilidade e o desempenho do código. Um equilíbrio bem-sucedido produz os seguintes resultados mutuamente benéficos:

- Aplicativos que atendem aos requisitos funcionais.
- Aplicativos que oferecem uma experiência de usuário perfeita e eficiente.

As seções a seguir fornecem uma visão geral sobre confiabilidade e desempenho do código, além de outros fatores que seus alunos devem conhecer.

##### Examinar a confiabilidade do código

A confiabilidade do código refere-se à probabilidade de que o software funcione corretamente em condições específicas e por um determinado período de tempo. Melhorar a confiabilidade do código ajuda a garantir que o software seja executado conforme o esperado e atenda aos requisitos do usuário.

Os desenvolvedores podem considerar os seguintes fatores ao trabalhar em melhorias na confiabilidade de código:

- Possíveis problemas: Identificar possíveis problemas no código pode ajudar a impedir que bugs e erros ocorram. Identificar possíveis problemas deve incluir a revisão do código para identificar armadilhas comuns e endereçá-las proativamente.
- Testes: Testes adequados são cruciais para identificar e corrigir bugs antes que o produto seja lançado. Os testes adequados devem incluir teste de unidade, teste de integração, teste de sistema e teste de aceitação.
- Tratamento de exceções: Mecanismos adequados de tratamento de exceção podem impedir que um sistema falhe quando ocorrem condições inesperadas.

> [!NOTE]
> Verifique se a qualidade do código é alta antes de começar a trabalhar na confiabilidade do código. A refatoração de código, juntamente com padrões e diretrizes, pode ajudar a garantir um código de alta qualidade.

Há outros fatores que afetam a confiabilidade do código. Alguns desses fatores não são de responsabilidade do desenvolvedor, enquanto outros devem ser considerados antes ou depois da confiabilidade do código. Esses outros fatores incluem:

- Práticas de desenvolvimento: Seguir as melhores práticas no desenvolvimento do software, como revisões de código, programação em par e aderir aos padrões de codificação, pode levar a um código mais confiável.
- Metas e métricas de confiabilidade: Definir metas claras de confiabilidade e ter métricas para medi-las pode orientar o processo de desenvolvimento para criar um software mais confiável.
- Documentação: Uma documentação abrangente pode ajudar a entender o sistema e seus componentes, o que é essencial para manter e solucionar problemas do sistema.
- Dependências: Bibliotecas e serviços externos dos quais o código depende podem afetar sua confiabilidade. Se um serviço de terceiros falhar, isso também poderá fazer com que o sistema dependente falhe.
- Desempenho: Problemas de desempenho também podem afetar a confiabilidade. Garantir que o sistema tenha um bom desempenho sob cargas diferentes é importante.
- Monitoramento e solução de problemas: O monitoramento contínuo e um guia de solução de problemas confiável podem ajudar a manter a confiabilidade de um serviço identificando e resolvendo problemas rapidamente.
- Design e arquitetura: Um sistema bem projetado com uma arquitetura sólida pode lidar com erros normalmente e manter a funcionalidade mesmo quando alguns componentes falham.
- Fatores externos: Problemas de confiabilidade pós-lançamento podem surgir devido a fatores externos, como atualizações de hardware e do sistema operacional, que podem introduzir problemas de compatibilidade ou falhas no sistema.

Melhorar a confiabilidade do código pode ajudá-lo a reduzir a probabilidade de bugs, erros e comportamentos inesperados.

##### Examinar o desempenho do código

O desempenho do código refere-se à eficiência com que um programa ou aplicativo é executado, especialmente em termos de velocidade, uso de memória e consumo geral de recursos. Para garantir ou melhorar o desempenho do código, os desenvolvedores podem executar várias ações:

Os desenvolvedores devem considerar os seguintes fatores ao trabalhar em melhorias no desempenho de código:

- Otimizar algoritmos: Escolha os algoritmos e estruturas de dados mais eficientes para a tarefa em questão. Mesmo pequenas melhorias podem ter um impacto significativo no desempenho.
- Evitar cálculos desnecessários: Armazene em cache os resultados de operações dispendiosas quando possível e evite cálculos redundantes.
- Usar programação multithreading e assíncrona: Aproveite as arquiteturas modernas da CPU paralelizando tarefas e executando operações de E/S de forma assíncrona.
- Minimizar as operações de E/S: As operações de E/S do disco e da rede podem estar lentas, portanto, é importante minimizar essas operações ou executá-las de forma assíncrona para evitar o bloqueio do thread de execução principal.

> [!NOTE]
> Verifique se a qualidade do código é alta antes de começar a trabalhar no desempenho do código. A refatoração de código, juntamente com padrões e diretrizes, pode ajudar a garantir um código de alta qualidade.

Há outros fatores que afetam o desempenho do código. Alguns desses fatores não são de responsabilidade do desenvolvedor, enquanto outros devem ser considerados antes ou depois de trabalhar no desempenho do código. Esses outros fatores incluem:

- Perfil e parâmetro de comparação: Use ferramentas de criação de perfil para identificar gargalos de desempenho. Avaliar o desempenho antes e depois de fazer alterações pode quantificar o impacto das otimizações.
- Gerenciar a memória com eficiência: Use ferramentas de criação de perfil de memória para detectar vazamentos e garantir que a memória esteja sendo alocada e desalocada corretamente.
- Otimizar interações de banco de dados: Use consultas eficientes, indexação adequada e cache de banco de dados para minimizar a sobrecarga do desempenho das interações de banco de dados.
- Revisões de código: Examine regularmente o código para identificar problemas de desempenho. As revisões em pares podem ajudar a detectar ineficiências que o desenvolvedor original pode ter perdido.
- Manter-se atualizado: Use as versões mais recentes de linguagens, bibliotecas e estruturas, pois elas geralmente incluem melhorias de desempenho.
- Educar e colaborar: Mantenha-se informado sobre as melhores práticas para otimização de desempenho e colabore com outros desenvolvedores para aprender com suas experiências.

Quando os desenvolvedores se concentram nessas áreas, eles podem melhorar significativamente o desempenho de seu código, levando a aplicativos mais rápidos e responsivos. A otimização de desempenho é um processo contínuo e é importante monitorar e melhorar continuamente o desempenho de seus aplicativos.

O GitHub Copilot Chat pode ajudá-lo a melhorar o desempenho do código fornecendo sugestões para otimizar algoritmos, reduzir cálculos desnecessários, usar programação multithreading e assíncrona e minimizar as operações de E/S.

### Desenvolver solicitações para o GitHub Copilot Chat

As solicitações que você escreve para o GitHub Copilot Chat devem fornecer um contexto e uma intenção claramente definidos. Considere as seguintes sugestões ao desenvolver suas solicitações:

- Defina um contexto externo com escopo em um nível mais alto do que o código que você deseja atualizar. Por exemplo, se você quiser melhorar um método, especifique a classe ou o arquivo que inclui o método como o contexto externo. Identifique o método como um contexto interno.
- Use participantes de chat e variáveis de chat para ajudar a especificar o contexto. Você pode usar as variáveis de chat `#file:` e `#selection` para identificar o código específico no qual você está focado. Você também pode incluir o workspace completo (`@workspace`) quando apropriado. Consulte a seleção de arquivo ou código na parte de linguagem natural da sua solicitação.
- A intenção deve ser clara, concisa e específica. Sua solicitação deve especificar o tipo de melhoria que você deseja obter.

Durante essa parte da demonstração, você revisa o **projeto APL2007M5BankAccount-Reliability** e cria três prompts para o GitHub Copilot Chat. As solicitações se concentram em melhorar a confiabilidade e o desempenho do código.

Use as seguintes etapas para concluir esta parte da demonstração:

1. Abra o aplicativo de exemplo **APL2007M5BankAccount-Reliability** no Visual Studio Code.

1. Abra a exibição do Gerenciador de Soluções.

1. Expanda o projeto **BankAccount** e examine os arquivos de código **BankAccount.cs** e **Program.cs**.

    O arquivo **BankAccount.cs** contém o código da classe `BankAccount`, que representa uma conta bancária com propriedades como AccountNumber, Balance, AccountHolderName, AccountType e DateOpened. Ele contém os seguintes métodos:

    - Credit(valor duplo): Esse método aumenta o saldo da conta pelo valor especificado.
    - Debit(valor duplo): Esse método diminui o saldo da conta pelo valor especificado. Se o saldo for menor que o valor, ele gerará uma exceção com a mensagem "Saldo insuficiente para débito".
    - GetBalance(): Esse método retorna o saldo atual da conta.
    - Transfer(BankAccount toAccount, valor duplo): Esse método transfere um valor especificado da conta atual para o toAccount. Se o saldo for inferior ao valor, uma exceção é lançada com a mensagem "Saldo insuficiente para transferência." Se AccountHolderName for diferente e o valor for maior que 500, uma exceção é lançada com a mensagem "O valor da transferência excede o limite máximo para proprietários de contas diferentes."
    - PrintStatement(): Esse método imprime o AccountNumber e o saldo da conta no console.
    - CalculateInterest(interestRate duplo): Esse método calcula os juros no saldo atual da conta usando a interestRate especificada.

    O arquivo **Program.cs** contém um aplicativo de console que simula um sistema bancário. Ele inclui os seguintes itens:

    - Método Main: O ponto de entrada do aplicativo. Ele cria uma lista de contas bancárias e simula transações e transferências nessas contas.
    - Método CreateBankAccounts: Esse método cria um número especificado de contas bancárias com saldos iniciais aleatórios, nomes de titulares de conta, tipos de conta e datas de abertura. Ele usa um bloco try-catch para lidar com quaisquer exceções que possam ocorrer durante a criação da conta.
    - Método SimulateTransactions: Esse método simula um número especificado de transações em cada conta na lista fornecida. Cada transação é um valor aleatório em dólar e pode ser um crédito (depósito) ou um débito (retirada), dependendo se o valor é positivo ou negativo.
    - Método SimulateTransfers: Esse método é idêntico ao SimulateTransactions. Parece que se destina a simular transferências entre contas, mas, no momento, está apenas duplicando a funcionalidade do método SimulateTransactions.
    - Método GenerateRandomDollarAmount: Esse método gera um valor de dólar aleatório dentro de um intervalo especificado. O intervalo e o método de cálculo diferem dependendo se o valor é para um saldo de conta ou uma transação
    - Método GenerateRandomAccountHolder: Esse método seleciona um nome de titular de conta aleatório em uma lista predefinida.
    - Método GenerateRandomAccountType: Esse método seleciona um tipo de conta aleatória em uma lista predefinida.
    - Método GenerateRandomDateOpened: Esse método gera uma data aleatória dentro de um intervalo especificado para a data de abertura da conta.

1. Reserve um minuto para descrever os prompts que podem ajudá-lo a melhorar a confiabilidade e o desempenho do código.

    Desenvolva solicitações para a classe BankAccount e a classe Program. Considere os seguintes fatores de confiabilidade e desempenho ao desenvolver suas solicitações:

    - Possíveis problemas: Identificar possíveis problemas no código pode ajudar a impedir que bugs e erros ocorram. Isso inclui revisar o código para detectar armadilhas comuns e endereçá-las proativamente.
    - Testes: Testes adequados são cruciais para identificar e corrigir bugs antes que o produto seja lançado. Isso inclui teste de unidade, teste de integração, teste de sistema e teste de aceitação.
    - Tratamento de exceções: Mecanismos adequados de tratamento de exceção podem impedir que um sistema falhe quando ocorrem condições inesperadas.

    - Otimizar algoritmos: Escolha os algoritmos e estruturas de dados mais eficientes para a tarefa em questão. Mesmo pequenas melhorias podem ter um impacto significativo no desempenho.
    - Evitar Cálculos Desnecessários: Armazene em cache os resultados de operações dispendiosas quando possível e evite cálculos redundantes.
    - Usar Programação Multithreading e Assíncrona: Aproveite as arquiteturas modernas da CPU paralelizando tarefas e executando operações de E/S de forma assíncrona.
    - Minimizar Operações de E/S: As operações de E/S do disco e da rede podem estar lentas, portanto, é importante minimizar essas operações ou executá-las de forma assíncrona para evitar o bloqueio do thread de execução principal.

    Para este projeto, você pode usar as seguintes solicitações para gerar sugestões para melhorar a confiabilidade do código:

    Prompt: `@workspace /explain How can I improve exception handling the [selected code]?` (anexar BankAccount.cs ao Contexto de Chat)

    Prompt: `@workspace /explain How can I reduce unexpected issues for the [selected code]?` (anexar BankAccount.cs ao Contexto de Chat)

    Prompt: `@workspace /explain How can I improve unit test support for the [selected code]?` (anexar BankAccount.cs ao Contexto de Chat)

    Prompt: `@workspace /explain How can I avoid future bugs or issues in the [selected code]?` (anexar Program.cs ao Contexto de Chat)

    Prompt: `@workspace /explain How can I improve exception handling for the [selected code]?` (anexar Program.cs ao Contexto de Chat)

    Prompt: `@workspace /explain How can I improve the efficiency of algorithms or data structures for the [selected code]?` (anexar Program.cs ao Contexto de Chat)

    Prompt: `@workspace /explain How can I improve performance with asynchronous tasks or methods in the [selected code]?` (anexar Program.cs ao Contexto de Chat)

    Prompt: `@workspace /explain How can I improve unit test support for the [selected code]?` (anexar BankAccountTests.cs e BankAccount.cs ao Contexto de Chat)

1. Selecione dois prompts que você pode usar para melhorar a classe BankAccount durante esta demonstração.

    Para a classe BankAccount, tente selecionar solicitações que se concentram na confiabilidade.

1. Selecione dois prompts que você pode usar para melhorar a classe Program durante esta demonstração.

    Para a classe Program, tente selecionar uma solicitação que se concentre na confiabilidade e uma que se concentre no desempenho.

### Melhorar a confiabilidade do código da classe BankAccount usando o GitHub Copilot Chat

Garantir a confiabilidade do código de produção é essencial para qualquer projeto de software. O aplicativo de exemplo APL2007M5BankAccount-Reliability usa a classe Program para simular o cenário bancário, mas é a classe BankAccount que é implantada em um ambiente de produção. Melhorar a confiabilidade da classe BankAccount ajuda a garantir que ela seja executada conforme o esperado e atenda aos requisitos do usuário.

O GitHub Copilot Chat pode ser usado para ajudar a melhorar a confiabilidade do código. Suas solicitações podem direcionar o GitHub Copilot para gerar sugestões que melhorem o tratamento de exceções, reduzam problemas inesperados e melhoram o suporte ao teste de unidade. Você também pode criar solicitações de escopo amplo que solicitem sugestões gerais para melhorar a confiabilidade do código. Uma combinação de solicitações específicas e gerais pode ajudá-lo a identificar áreas que precisam de melhoria e implementar as alterações necessárias.

> [!NOTE]
> Implementar e testar as atualizações sugeridas leva tempo, e o tempo pode ser um fator durante esta demonstração. Selecionar solicitações que se concentram em áreas específicas de melhoria pode ajudá-lo a gerenciar seu tempo. Solicitações muito amplas podem gerar um grande número de sugestões ou sugestões complexas que são difíceis de avaliar e implementar em um curto período de tempo. Depois de começar, você poderá atualizar suas solicitações com detalhes mais específicos se descobrir que as atualizações sugeridas têm escopo muito amplo ou muito complexo.

Use as seguintes etapas para concluir esta parte da demonstração:

1. Verifique se o projeto é compilado e executado sem erros.

    Os avisos são aceitáveis desde que o aplicativo seja executado, mas os erros devem ser resolvidos antes de você começar a trabalhar com o Chat do GitHub Copilot.

1. Abra o arquivo BankAccount.cs no Visual Studio Code e selecione todo o código no arquivo.

1. Abra o modo de exibição de chat.

1. No modo de exibição de Chat, adicione os arquivos relevantes ao contexto do chat e, em seguida, insira seu prompt.

1. Examinar as sugestões fornecidas pelo Chat do GitHub Copilot.

    Por exemplo, suponha que você conclua as seguintes ações:

    - Abra o arquivo BankAccount.cs e selecione todo o código.
    - Escolha o seguinte prompt: `@workspace /explain How can I improve exception handling in the BankAccount.cs file?`
    - Abra o modo de exibição chat e anexe os arquivos BankAccount.cs e Program.cs ao contexto do Chat.
    - Insira o prompt no modo de exibição chat.

    Nesse caso, o Chat do GitHub Copilot sugere atualizações semelhantes à seguinte resposta:

    *Para melhorar o tratamento de exceções no arquivo BankAccount.cs, considere as seguintes sugestões: *

    *1. **Use exceções específicas**: Em vez de lançar a classe `Exception` base, use exceções mais específicas. Isso facilita para o código que chama compreender e tratar tipos específicos de erros. Por exemplo, você poderia lançar uma InvalidOperationException ao tentar debitar ou transferir com fundos insuficientes.*

    *2. **Inclua mais informações nas mensagens de exceção**: As mensagens de exceção podem fornecer mais detalhes sobre a operação que falhou. Por exemplo, no método `Debit`, a mensagem de exceção pode incluir o valor da tentativa de débito e o saldo atual.*

    *3. **Considere criar exceções personalizadas**: Se houver condições de erro específicas que sejam exclusivas do seu aplicativo, talvez você queira criar classes de exceção personalizadas. Criar exceções personalizadas permite encapsular mais informações sobre a condição de erro e torna seu código mais autoexplicativo.*

    *Veja como você pode melhorar o método `Debit` com estas sugestões:*

    ```csharp

    public void Debit(double amount)
    {
        if (Balance >= amount)
        {
            Balance -= amount;
        }
        else
        {
            throw new InvalidOperationException($"Insufficient balance for debit. Attempted to debit {amount}, but current balance is {Balance}.");
        }
    }

    ```

    *E aqui está um exemplo de uma classe de exceção personalizada:*

    ```csharp

    public class InsufficientFundsException : Exception
    {
        public double AttemptedAmount { get; }
        public double CurrentBalance { get; }
        public InsufficientFundsException(double attemptedAmount, double currentBalance)
            : base($"Insufficient balance for debit. Attempted to debit {attemptedAmount}, but current balance is {currentBalance}.")
        {
            AttemptedAmount = attemptedAmount;
            CurrentBalance = currentBalance;
        }
    }

    ```

    *Em seguida, você pode lançar essa exceção personalizada no método Debit:*

    ```csharp

    public void Debit(double amount)
    {
        if (Balance >= amount)
        {
            Balance -= amount;
        }
        else
        {
            throw new InsufficientFundsException(amount, Balance);
        }
    }

    ```

    *Dessa forma, o código de chamada pode capturar InsufficientFundsException e ter acesso às propriedades AttemptedAmount e CurrentBalance para lidar com a condição de erro com mais eficiência.*

1. Implemente as atualizações sugeridas que ajudam a melhorar a confiabilidade do código para sua classe `BankAccount`.

1. Para garantir que nenhum erro tenha sido introduzido pelas alterações, crie e execute sua solução antes de continuar.

    > [!TIP]
    > No exemplo acima, o modo de exibição de chat forneceu snippets de código que implementam um exemplo da atualização sugerida (usando exceções específicas, incluindo mais informações na mensagem de exceção e criando exceções personalizadas). Depois de implementar as sugestões, tente usar preenchimentos de linha de código para gerar um novo código que duplica a atualização. No caso deste exemplo, os preenchimentos de linha de código podem ser usadas para criar classes de exceção mais personalizadas. Em seguida, você pode usar preenchimentos de linha de código para atualizar os outros métodos com as novas exceções personalizadas. Você também pode executar novamente a solicitação original para ver outras sugestões.

1. Selecione todo o códiogo no arquivo BankAccount.cs.

1. Abra o modo de exibição de chat.

1. No modo de exibição chat, use o botão **Anexar Contexto** para adicionar arquivos relevantes ao contexto de Chat e, em seguida, insira seu prompt.

1. Examine as sugestões fornecidas pelo GitHub Copilot Chat.

    Por exemplo, se você inserir `@workspace /explain How can I reduce unexpected issues for the selected code?` no modo de exibição de chat, o GitHub Copilot Chat sugerirá atualizações semelhantes à seguinte resposta:

    *Para reduzir problemas inesperados na classe BankAccount, você pode implementar as seguintes melhorias:*

    *1. Use enumeração para tipo de conta: Em vez de usar uma cadeia de caracteres para o tipo de conta e verificar se ela é "Poupança" ou "Corrente", considere usar uma enumeração. Isso evitaria possíveis problemas com comparação de cadeia de caracteres (como sensibilidade a maiúsculas e minúsculas) e limitaria o tipo de conta a valores predefinidos.*

    ```csharp

    public enum AccountType
    {
        Savings,
        Current
    }

    ```

    *2. Usar decimal para valores monetários: Geralmente, é recomendável usar o tipo decimal em vez de dobrar para valores monetários para evitar erros de arredondamento.*

    *3. Adicione mais validações: Você pode adicionar mais validações em seus métodos. Por exemplo, no método Transfer, você poderia verificar se o toAccount não é nulo antes de prosseguir com a transferência.*

    *4. Use constantes para números mágicos: No método Transfer, há um número mágico 500. Seria melhor defini-lo como uma constante com um nome significativo no início da sua classe.*

    ```csharp
    private const double MaxTransferAmountForDifferentOwners = 500;
    ```

    *5. Exceção personalizada para o limite de transferência: Em vez de gerar uma exceção geral quando o valor da transferência exceder o limite para diferentes proprietários de conta, considere criar uma exceção personalizada como ExceededTransferLimitException.*

    *6. Registre em log: Considere adicionar o registro em log ao seu aplicativo. Isso pode ajudá-lo a entender o fluxo do aplicativo e diagnosticar problemas.*

    *7. Testes de unidade: Escreva testes de unidade para seus métodos para garantir que eles se comportem conforme o esperado em vários cenários. Isso pode ajudar a detectar problemas no início do processo de desenvolvimento.*

1. Considere o escopo e a amplitude das sugestões fornecidas pelo GitHub Copilot Chat.

    Algumas solicitações podem gerar um grande número de sugestões que afetam um escopo amplo. Se isso acontecer, verifique se um único item de sugestão pode ser usado para definir uma nova solicitação que forneça uma intenção e/ou contexto mais específicos.

1. Use a lista de sugestões para construir uma solicitação que inclua uma intenção e/ou contexto mais detalhados.

    Cada uma das sugestões fornecidas pelo GitHub Copilot Chat pode ser investigada e implementada separadamente. Começar na parte superior da lista e ir descendo pode ajudá-lo a se concentrar em uma melhoria de cada vez.

1. Insira sua solicitação detalhada no modo de exibição de chat e examine as sugestões fornecidas pelo GitHub Copilot Chat.

    Suponha que você tenha usado o segundo exemplo de solicitação de confiabilidade. A resposta do GitHub Copilot Chat inclui o seguinte item de sugestão:

    *Adicione mais validações: Você pode adicionar mais validações em seus métodos. Por exemplo, no método Transfer, você poderia verificar se o toAccount não é nulo antes de prosseguir com a transferência.*

    Você pode usar essa sugestão para criar uma nova solicitação que se concentre em adicionar mais validações ao método Transfer. Você pode selecionar o método Transfer e, em seguida, inserir a seguinte solicitação no modo de exibição de chat:

    `@workspace /explain #file:BankAccount.cs How can I improve method validations for the selected code?`

    Nesse caso, o GitHub Copilot Chat sugere atualizações semelhantes à seguinte resposta:

    *O código que você forneceu está bem estruturado e segue boas práticas para tratamento de exceções. No entanto, há algumas áreas em que você pode fazer melhorias:*

    *1. Consolide a lógica de validação: Você pode criar uma classe ou método de validação separado para lidar com toda a lógica de validação. Isso tornaria sua classe BankAccount mais limpa e mais focada em suas principais responsabilidades.*

    *2. Use atributos de validação personalizados: Para algumas das validações, você pode usar atributos de validação personalizados. Isso permitiria que você anotasse as propriedades que precisam de validação e mantivesse a lógica de validação separada da lógica de negócio.*

    *3. Use a validação fluente: Fluent Validation é uma biblioteca .NET que usa uma interface fluente e expressões lambda para construir regras de validação. Isso pode tornar seu código de validação mais intuitivo e mais fácil de ler.*

    *4. Evite números mágicos: No método Transfer, você tem um valor codificado de 500. Geralmente, é uma boa prática evitar "números mágicos" e defini-los como constantes com nomes significativos no início da sua classe.*

    Aqui está um exemplo de como você pode implementar algumas dessas sugestões:

    ```csharp

    public class BankAccount
    {
        private const double MaxTransferAmountForDifferentOwners = 500;
        // ...
        public void Transfer(BankAccount toAccount, double amount)
        {
            ValidateTransferAmount(amount);
            ValidateTransferLimitForDifferentOwners(toAccount, amount);
    
            if (Balance >= amount)
            {
                Debit(amount);
                toAccount.Credit(amount);
            }
            else
            {
                throw new InsufficientFundsException(amount, Balance);
            }
        }
        private void ValidateTransferAmount(double amount)
        {
            if (amount < 0)
            {
                throw new InvalidTransferAmountException(amount);
            }
        }
        private void ValidateTransferLimitForDifferentOwners(BankAccount toAccount, double amount)
        {
            if (AccountHolderName != toAccount.AccountHolderName && amount > MaxTransferAmountForDifferentOwners)
            {
                throw new Exception("Transfer amount exceeds maximum limit for different account owners.");
            }
        }
    }

    ```

    Você pode continuar trabalhando nas sugestões fornecidas pelo GitHub Copilot Chat até implementar todas as melhorias que você considera necessárias.

1. Implemente as atualizações sugeridas e, em seguida, crie e execute sua solução antes de continuar.

    Corrija os erros introduzidos pelas alterações antes de continuar.

### Melhorar a confiabilidade do código e o desempenho da classe Program usando o GitHub Copilot Chat

1. Abra o arquivo Program.cs no Visual Studio Code e selecione todo o código no arquivo.

1. Abra o arquivo Program.cs no Visual Studio Code e selecione todo o código no arquivo.

1. Abra o modo de exibição de chat.

1. No modo de exibição chat, use o botão **Anexar Contexto** para adicionar arquivos relevantes ao contexto de Chat e, em seguida, insira seu prompt.

1. Examine as sugestões fornecidas pelo GitHub Copilot Chat.

    Por exemplo, se você inserir `@workspace /explain How can I improve performance with asynchronous tasks or methods in the Program.cs file?` no modo de exibição de chat, o GitHub Copilot Chat sugerirá atualizações semelhantes à seguinte resposta:

    *Para melhorar o desempenho com tarefas ou métodos assíncronos no arquivo Program.cs, você pode usar programação assíncrona com as palavras-chave async e await. Isso permitirá que o programa execute operações de E/S sem bloquear o thread principal, tornando-o mais responsivo e eficiente.*

    *Aqui está uma versão aprimorada do arquivo Program.cs com métodos assíncronos:*

    ```csharp

    using System;
    using System.Collections.Generic;
    using System.Threading.Tasks;
    namespace BankAccountApp
    {
        class Program
        {
            private static readonly Random random = new Random();
            private const int MaxYearsBack = 10;
            private const int NumberOfAccounts = 20;
            private const int NumberOfTransactions = 100;
            private const double minTransactionAmount = -500.0;
            private const double maxTransactionAmount = 500.0;
            private const double minAccountStart = 200.0;
            private const double maxAccountStart = 1000.0;
            static async Task Main(string[] args)
            {
                List<BankAccount> accounts = await CreateBankAccountsAsync(NumberOfAccounts);
                await SimulateTransactionsAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
                await SimulateTransfersAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
            }
            static async Task<List<BankAccount>> CreateBankAccountsAsync(int numberOfAccounts)
            {
                List<BankAccount> accounts = new List<BankAccount>();
                int createdAccounts = 0;
                while (createdAccounts < numberOfAccounts)
                {
                    try
                    {
                        double initialBalance = GenerateRandomDollarAmount(true, minAccountStart, maxAccountStart);
                        string accountHolderName = GenerateRandomAccountHolder();
                        string accountType = GenerateRandomAccountType();
                        DateTime dateOpened = GenerateRandomDateOpened();
                        BankAccount account = new BankAccount($"Account {createdAccounts + 1}", initialBalance, accountHolderName, accountType, dateOpened);
                        accounts.Add(account);
                        createdAccounts++;
                    }
                    catch (Exception ex)
                    {
                        Console.WriteLine($"Account creation failed: {ex.Message}");
                    }
                    await Task.Yield(); // Yield control to allow other tasks to run
                }
                return accounts;
            }
            static async Task SimulateTransactionsAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                List<Task> tasks = new List<Task>();
                foreach (BankAccount account in accounts)
                {
                    tasks.Add(Task.Run(async () =>
                    {
                        for (int i = 0; i < numberOfTransactions; i++)
                        {
                            double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                            try
                            {
                                if (transactionAmount >= 0)
                                {
                                    account.Credit(transactionAmount);
                                    Console.WriteLine($"Credit: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                                }
                                else
                                {
                                    account.Debit(-transactionAmount);
                                    Console.WriteLine($"Debit: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                                }
                            }
                            catch (Exception ex)
                            {
                                Console.WriteLine($"Transaction failed: {ex.Message}");
                            }
                            await Task.Yield(); // Yield control to allow other tasks to run
                        }
                        Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                    }));
                }
                await Task.WhenAll(tasks);
            }
            static async Task SimulateTransfersAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                List<Task> tasks = new List<Task>();
                foreach (BankAccount account in accounts)
                {
                    tasks.Add(Task.Run(async () =>
                    {
                        for (int i = 0; i < numberOfTransactions; i++)
                        {
                            double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                            try
                            {
                                if (transactionAmount >= 0)
                                {
                                    account.Credit(transactionAmount);
                                    Console.WriteLine($"Credit: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                                }
                                else
                                {
                                    account.Debit(-transactionAmount);
                                    Console.WriteLine($"Debit: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                                }
                            }
                            catch (Exception ex)
                            {
                                Console.WriteLine($"Transaction failed: {ex.Message}");
                            }
                            await Task.Yield(); // Yield control to allow other tasks to run
                        }
                        Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                    }));
                }
                await Task.WhenAll(tasks);
            }
            static double GenerateRandomDollarAmount(bool isAccount, double min, double max)
            {
                if (isAccount)
                {
                    double accountStartingValue = random.NextDouble() * (max - min) + min;
                    return Math.Round(accountStartingValue, 2);
                }
                else
                {
                    double transactionAmount = random.NextDouble() * random.Next((int)min, (int)max) + random.NextDouble();
                    return Math.Round(transactionAmount, 2);
                }
            }
            static string GenerateRandomAccountHolder()
            {
                string[] accountHolderNames = { "John Smith", "Maria Garcia", "Mohammed Khan", "Sophie Dubois", "Liam Johnson", "Emma Martinez", "Noah Lee", "Olivia Kim", "William Chen", "Ava Wang", "James Brown", "Isabella Nguyen", "Benjamin Wilson", "Mia Li", "Lucas Anderson", "Charlotte Liu", "Alexander Taylor", "Amelia Patel", "Daniel Garcia", "Sophia Kim" };
                var accountHolderName = accountHolderNames[random.Next(0, accountHolderNames.Length)];
                return accountHolderName;
            }
            static string GenerateRandomAccountType()
            {
                string[] accountTypes = { "Savings", "Checking", "Money Market", "Certificate of Deposit", "Retirement" };
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
        }
    }

    ```

1. Implemente as atualizações sugeridas que ajudam a melhorar o desempenho do código (ou a confiabilidade) da sua classe `Program`.

1. Para garantir que nenhum erro tenha sido introduzido pelas alterações, crie e execute sua solução antes de continuar.

1. Selecione todo o código no arquivo Program.cs e, em seguida, insira a solicitação de "confiabilidade" no modo de exibição de chat.

1. Examine as sugestões fornecidas pelo GitHub Copilot Chat.

    > [!NOTE]
    > Você não precisa implementar as sugestões de atualização geradas pelo GitHub Copilot a partir deste quarta solicitação, mas deve examinar as sugestões.

    Por exemplo, se você inserir `@workspace /explain How can I improve exception handling for the selected code?` no modo de exibição de chat, o GitHub Copilot Chat sugerirá atualizações semelhantes à seguinte resposta:

    *Para melhorar o tratamento de exceções no arquivo Program.cs, considere as seguintes sugestões: *

    *1. Use Tipos de Exceção Específicos: em vez de capturar exceções genéricas, capture exceções específicas sempre que possível.*

    *2. Adicionar Mais Contexto a Exceções: Forneça mais contexto nas mensagens de exceção para facilitar a depuração.*

    *3. Registre Exceções: em vez de apenas imprimir exceções no console, considere registrá-las para melhor rastreabilidade.*

    *Aqui está uma versão melhorada do arquivo Program.cs com melhor tratamento de exceções:*

    ```csharp

    using System;
    using System.Collections.Generic;
    using System.Threading.Tasks;
    namespace BankAccountApp
    {
        class Program
        {
            private static readonly Random random = new Random();
            private const int MaxYearsBack = 10;
            private const int NumberOfAccounts = 20;
            private const int NumberOfTransactions = 100;
            private const double minTransactionAmount = -500.0;
            private const double maxTransactionAmount = 500.0;
            private const double minAccountStart = 200.0;
            private const double maxAccountStart = 1000.0;
            static async Task Main(string[] args)
            {
                List<BankAccount> accounts = await CreateBankAccountsAsync(NumberOfAccounts);
                await SimulateTransactionsAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
                await SimulateTransfersAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
            }
            static async Task<List<BankAccount>> CreateBankAccountsAsync(int numberOfAccounts)
            {
                List<BankAccount> accounts = new List<BankAccount>();
                int createdAccounts = 0;
                while (createdAccounts < numberOfAccounts)
                {
                    try
                    {
                        double initialBalance = GenerateRandomDollarAmount(true, minAccountStart, maxAccountStart);
                        string accountHolderName = GenerateRandomAccountHolder();
                        string accountType = GenerateRandomAccountType();
                        DateTime dateOpened = GenerateRandomDateOpened();
                        BankAccount account = new BankAccount($"Account {createdAccounts + 1}", initialBalance, accountHolderName, accountType, dateOpened);
                        accounts.Add(account);
                        createdAccounts++;
                    }
                    catch (ArgumentException ex)
                    {
                        Console.WriteLine($"Account creation failed due to invalid argument: {ex.Message}");
                    }
                    catch (Exception ex)
                    {
                        Console.WriteLine($"Account creation failed: {ex.Message}");
                    }
                    await Task.Yield(); // Yield control to allow other tasks to run
                }
                return accounts;
            }
            static async Task SimulateTransactionsAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                List<Task> tasks = new List<Task>();
                foreach (BankAccount account in accounts)
                {
                    tasks.Add(Task.Run(async () =>
                    {
                        for (int i = 0; i < numberOfTransactions; i++)
                        {
                            double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                            try
                            {
                                if (transactionAmount >= 0)
                                {
                                    account.Credit(transactionAmount);
                                    Console.WriteLine($"Credit: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                                }
                                else
                                {
                                    account.Debit(-transactionAmount);
                                    Console.WriteLine($"Debit: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                                }
                            }
                            catch (ArgumentException ex)
                            {
                                Console.WriteLine($"Transaction failed due to invalid argument: {ex.Message}");
                            }
                            catch (InsufficientBalanceException ex)
                            {
                                Console.WriteLine($"Transaction failed due to insufficient balance: {ex.Message}");
                            }
                            catch (Exception ex)
                            {
                                Console.WriteLine($"Transaction failed: {ex.Message}");
                            }
                            await Task.Yield(); // Yield control to allow other tasks to run
                        }
                        Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                    }));
                }
                await Task.WhenAll(tasks);
            }
            static async Task SimulateTransfersAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                List<Task> tasks = new List<Task>();
                foreach (BankAccount account in accounts)
                {
                    tasks.Add(Task.Run(async () =>
                    {
                        for (int i = 0; i < numberOfTransactions; i++)
                        {
                            double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                            try
                            {
                                if (transactionAmount >= 0)
                                {
                                    account.Credit(transactionAmount);
                                    Console.WriteLine($"Credit: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                                }
                                else
                                {
                                    account.Debit(-transactionAmount);
                                    Console.WriteLine($"Debit: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                                }
                            }
                            catch (ArgumentException ex)
                            {
                                Console.WriteLine($"Transaction failed due to invalid argument: {ex.Message}");
                            }
                            catch (InsufficientBalanceException ex)
                            {
                                Console.WriteLine($"Transaction failed due to insufficient balance: {ex.Message}");
                            }
                            catch (Exception ex)
                            {
                                Console.WriteLine($"Transaction failed: {ex.Message}");
                            }
                            await Task.Yield(); // Yield control to allow other tasks to run
                        }
                        Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                    }));
                }
                await Task.WhenAll(tasks);
            }
            static double GenerateRandomDollarAmount(bool isAccount, double min, double max)
            {
                if (isAccount)
                {
                    double accountStartingValue = random.NextDouble() * (max - min) + min;
                    return Math.Round(accountStartingValue, 2);
                }
                else
                {
                    double transactionAmount = random.NextDouble() * random.Next((int)min, (int)max) + random.NextDouble();
                    return Math.Round(transactionAmount, 2);
                }
            }
            static string GenerateRandomAccountHolder()
            {
                string[] accountHolderNames = { "John Smith", "Maria Garcia", "Mohammed Khan", "Sophie Dubois", "Liam Johnson", "Emma Martinez", "Noah Lee", "Olivia Kim", "William Chen", "Ava Wang", "James Brown", "Isabella Nguyen", "Benjamin Wilson", "Mia Li", "Lucas Anderson", "Charlotte Liu", "Alexander Taylor", "Amelia Patel", "Daniel Garcia", "Sophia Kim" };
                var accountHolderName = accountHolderNames[random.Next(0, accountHolderNames.Length)];
                return accountHolderName;
            }
            static string GenerateRandomAccountType()
            {
                string[] accountTypes = { "Savings", "Checking", "Money Market", "Certificate of Deposit", "Retirement" };
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
        }
    }

    ```

## Resumo

Nesta demonstração, você usou o GitHub Copilot Chat para gerar sugestões que ajudam você a melhorar a confiabilidade e o desempenho do código em um aplicativo de exemplo. Você desenvolveu solicitações que orientaram o GitHub Copilot a fornecer sugestões que melhoram o tratamento de exceções, reduzem problemas inesperados e melhoram o suporte ao teste de unidade. Você também criou solicitações que se concentraram em melhorar o desempenho com tarefas ou métodos assíncronos.
