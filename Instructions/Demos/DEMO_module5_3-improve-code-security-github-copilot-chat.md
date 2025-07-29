---
demo:
  title: 'Demonstração: Melhorar a segurança de código usando o GitHub Copilot Chat'
  module: 'Module 5: Implement code improvements using GitHub Copilot tools'
---

# Demonstração: Melhorar a segurança de código usando o GitHub Copilot Chat

## Instruções

As atividades de demonstração são projetadas para um ambiente que inclui os seguintes recursos:

- Visual Studio Code.
- A extensão do kit de desenvolvimento em C# para o Visual Studio Code.
- As extensões do GitHub Copilot e do GitHub Copilot Chat para Visual Studio Code. É necessária uma conta do GitHub com uma assinatura ativa do GitHub Copilot.
- Projetos de amostras de código criadas usando C#.

**OBSERVAÇÃO**: Recomendamos que os instrutores considerem usar sua própria conta do GitHub e a assinatura do GitHub Copilot para as demonstrações. Isso irá permitir que você controle e personalize seu ambiente de desenvolvimento. Também facilitará o ajuste das demonstrações para atender às necessidades de suas salas de aula.

**IMPORTANTE**: Se você optar por executar as demonstrações no ambiente de laboratório hospedado em vez do seu computador de instrutor, poderá descompactar os aplicativos de exemplo no ambiente hospedado. Você precisará configurar as extensões do GitHub Copilot no ambiente hospedado antes de executar as demonstrações. Você pode perceber que o ambiente hospedado é mais lento do que o seu ambiente local, então talvez precise ajustar o ritmo das demonstrações de acordo.

### Apresentar a demonstração

A segurança de código refere-se às medidas tomadas para proteger o software contra acesso não autorizado, violações de dados e outras ameaças à segurança. A segurança de código é um aspecto essencial do desenvolvimento de software que envolve a proteção de aplicativos e sistemas contra ameaças à segurança. Melhorar a segurança de código pode ajudar você a proteger seus aplicativos e sistemas contra ameaças à segurança.

> [!IMPORTANT]
> Explique aos alunos que esta demonstração não trata das melhores práticas para desenvolver um código seguro. Ele se concentra em como usar o Chat do GitHub Copilot para gerar sugestões para melhorar a segurança do código em um aplicativo de exemplo. As sugestões não representam melhores práticas ou soluções abrangentes para o desenvolvimento de código seguro. Os desenvolvedores devem usar seu julgamento e experiência para avaliar e implementar as sugestões fornecidas pelo Chat do GitHub Copilot. A implementação de sugestões propostas pelo GitHub Copilot não substitui a necessidade de testes e revisões de código completos.

#### Segurança do código

Garantir a segurança do código é responsabilidade de todos, não apenas do desenvolvedor. No entanto, os desenvolvedores desempenham um papel crucial ao garantir que o código que escrevem segue práticas de codificação seguras. As práticas de codificação segura ajudam a garantir que as vulnerabilidades do software não possam ser exploradas por invasores. Seguindo as práticas de codificação segura, os desenvolvedores podem ajudar a proteger o software contra ameaças à segurança e garantir que ele seja seguro e confiável.

As seções a seguir apresentam uma visão geral dos processos de segurança de código que seus alunos devem conhecer.

##### Avaliar a segurança do código usando uma abordagem abrangente

Ao avaliar a segurança do código, é importante considerar uma abordagem abrangente que englobe vários aspectos do ciclo de vida de desenvolvimento do software. Aqui estão algumas considerações importantes:

- Práticas de codificação segura: Aderir a padrões e diretrizes de codificação seguros para evitar vulnerabilidades.
- Ferramentas de análise de código: Usar ferramentas de análise de código estáticas e dinâmicas para detectar falhas de segurança.
- Gerenciamento de dependências: Garantir que bibliotecas e dependências de terceiros estejam atualizadas e livres de vulnerabilidades conhecidas.
- Autenticação e autorização: Implementar mecanismos robustos de autenticação e autorização para proteger contra acesso não autorizado.
- Proteção de dados: Criptografar dados confidenciais em repouso e em trânsito para evitar violações de dados.
- Tratamento de erro: Desenvolver procedimentos seguros de tratamento de erro que não exponham informações confidenciais.
- Teste de segurança: Realizar testes de segurança completos, incluindo testes de penetração e avaliações de vulnerabilidade.
- Conformidade: Garantir que o código esteja em conformidade com os padrões e regulamentos de segurança relevantes.
- Educação e treinamento: Fornecer aos desenvolvedores educação e treinamento contínuos de segurança para mantê-los informados sobre as ameaças e as melhores práticas mais recentes.
- Resposta a incidentes: Ter um plano de resposta a incidentes bem definido preparado. Se ocorrer uma falha de segurança, o plano de resposta a incidentes deverá estar acessível.

Considerar esses fatores e integrar as melhores práticas de segurança em seu processo de desenvolvimento contribui para a criação de conteúdo e aplicativos seguros.

##### Realizar análise de segurança de código

Ao trabalhar para garantir que o código seja seguro, os desenvolvedores devem revisar os seguintes aspectos do código:

- Precisão: Verifique se o código está livre de erros lógicos e defeitos que podem levar a vulnerabilidades de segurança.
- Segurança: Certifique-se de que o código siga as melhores práticas de segurança e não contenha vulnerabilidades.
- Diagnóstico: Inclua recursos adequados de registro e diagnóstico para detectar e responder a incidentes de segurança.
- Erros de design ou limitações: Examine o design do código para garantir que não haja falhas ou limitações que possam ser exploradas.
- Escala e desempenho: Considere o desempenho e a escalabilidade do código. O baixo desempenho e a escalabilidade podem afetar a segurança em cenários de alta carga.
- Localização: Certifique-se de que o código lide com segurança em diferentes localidades, o que pode afetar a formatação e a representação dos dados.
- Acessibilidade (UX): Verifique se as medidas de segurança não afetam negativamente a acessibilidade e a experiência do usuário.
- Teste: Examine as estratégias de teste e verifique se o teste de segurança é completo e abrange todos os aspectos do código.
- Instrumentação: Verifique se o código é instrumentado de forma a dar suporte ao monitoramento de segurança e à detecção de ameaças.
- Convenções de estilo de código e consistência: Mantenha um estilo de codificação consistente que siga diretrizes e padrões de codificação seguros.

Quando os desenvolvedores revisam esses aspectos do código, eles podem aumentar significativamente a segurança do código. As revisões de código ajudam os desenvolvedores a contribuir para a postura geral de segurança do software que desenvolvem.

##### Analisar vulnerabilidades de código

Certas partes de um aplicativo são mais vulneráveis a ataques de segurança e é crucial focar na segurança dessas áreas. Aqui estão algumas das áreas mais vulneráveis:

- Pontos de integração: As revisões do projeto de segurança devem ser realizadas para pontos de integração com equipes de produtos dependentes. As revisões são essenciais para produtos que lidam com dados de alto impacto nos negócios (HBI) ou aplicativos e serviços empresariais.
- Sistemas internos: Os incidentes internos são uma causa comum de violações de segurança, especialmente em pequenas empresas.
- Sistemas de email: Os servidores de email, especialmente aqueles sem suporte ou sem correção, são persistentemente vulneráveis.
- Bancos de dados e armazenamento: Os bancos de dados que esperam que os dados confidenciais sejam pré-criptografados antes do armazenamento podem ficar vulneráveis se os dados não forem criptografados conforme o esperado.
- Ambiente de runtime: Tecnologias como o Runtime Application Self-Protection (RASP) podem detectar ataques a um aplicativo em tempo real, tornando o ambiente de runtime uma área crítica a ser protegida.
- Aplicativos Web: Os aplicativos da Web costumam ser alvo de invasores que usam métodos como injeção de SQL, cross-site scripting (XSS) e estouros de buffer.
- Pontos de extremidade: Dispositivos e aplicativos correm risco de ataques cibernéticos. É essencial reduzir a superfície de ataque usando recursos como mitigação de ransomware, controle de aplicativos, proteção da Web e firewall de rede.

Os desenvolvedores e as equipes de segurança devem priorizar essas áreas e implementar fortes medidas de segurança para proteção contra possíveis ataques. Revisões regulares de segurança, atualizações e adesão de melhores práticas podem ajudar a mitigar essas vulnerabilidades.

##### Pesquisar falhas de segurança comuns

Os desenvolvedores podem encontrar várias falhas de segurança em seus códigos, que podem levar a vulnerabilidades se não forem tratadas adequadamente. Algumas falhas de segurança típicas incluem:

- Falhas de injeção: Como a injeção de SQL, NoSQL, SO e LDAP, em que dados não confiáveis são enviados a um interpretador como parte de um comando ou consulta.
- Autenticação interrompida: Quando a autenticação e o gerenciamento de sessão são implementados incorretamente, a autenticação pode ser interrompida. Boas implementações garantem que senhas, chaves e tokens de sessão não sejam comprometidos por invasores.
- Exposição de dados confidenciais: A proteção inadequada de dados confidenciais pode levar à exposição durante a transferência pela rede ou em repouso.
- Controle de acesso interrompido: As restrições que controlam o acesso concedido aos usuários autenticados não estão sendo aplicadas corretamente.
- Cross-site scripting (XSS): As falhas de XSS ocorrem sempre que um aplicativo inclui dados não confiáveis em uma página da Web sem validação ou escape adequado.
- Desserialização desprotegida: Isso pode levar à execução remota de código, ataques de reprodução, ataques de injeção e ataques de escalonamento de privilégio.
- Registro em log e monitoramento insuficientes: O registro em log e o monitoramento insuficientes, juntamente com a integração ausente ou ineficaz com a resposta a incidentes, permitem ataques contínuos.
- Insecure Direct Object References (IDOR): Um tipo de problema de controle de acesso que surge quando um aplicativo fornece acesso direto a objetos com base na entrada fornecida pelo usuário.
- Controle de acesso no nível da função ausente: Às vezes, um aplicativo não protege adequadamente os controles de acesso no nível de função, permitindo que invasores falsifiquem solicitações de acesso à funcionalidade sem a devida autorização.

Muitas outras falhas de segurança podem ser encontradas no código. É importante que os desenvolvedores usem ferramentas e práticas recomendadas para identificar e corrigir esses problemas proativamente.

### Desenvolver solicitações para o GitHub Copilot Chat

As solicitações que você escreve para o GitHub Copilot Chat devem fornecer um contexto e uma intenção claramente definidos. Considere as seguintes sugestões ao desenvolver suas solicitações:

- Defina um contexto externo com escopo em um nível mais alto do que o código que você deseja atualizar. Por exemplo, se você quiser melhorar um método, especifique a classe ou o arquivo que inclui o método como o contexto externo. Identifique o método como um contexto interno.
- Use participantes de chat e variáveis de chat para ajudar a especificar o contexto. Você pode usar as variáveis de chat `#file:` e `#selection` para identificar o código específico no qual você está focado. Você também pode incluir o workspace completo (`@workspace`) quando apropriado. Consulte a seleção de arquivo ou código na parte de linguagem natural da sua solicitação.
- A intenção deve ser clara, concisa e específica. Sua solicitação deve especificar o tipo de melhoria que você deseja obter.

Nesta parte da demonstração, você revisa o projeto **APL2007M5BankAccount-Security** e cria três solicitações para o Chat do GitHub Copilot. As solicitações se concentram na melhoria da segurança de código.

Use as seguintes etapas para concluir esta parte da demonstração:

1. Abra o projeto **APL2007M5BankAccount-Security** e examine os arquivos do código **Program.cs** e **BankAccount.cs**.

    O arquivo **Program.cs** contém o código de um aplicativo bancário simples que simula a criação de contas, transações e transferências bancárias.

    O arquivo **BankAccount.cs** contém o código da classe `BankAccount`, que representa uma conta bancária com funcionalidades básicas, como depósito, saque e consulta de saldo.

1. Reserve um minuto para descrever alguns prompts que podem ser usados para melhorar a segurança do código.

    Neste projeto, você pode usar as seguintes solicitações para gerar sugestões para melhorar a segurança do código:

    Prompt: `@workspace /explain How can I implement authentication in the [selected code]?` (anexar BankAccount.cs ao Contexto de Chat)

    Prompt: `@workspace /explain How can I protect sensitive data in the [selected code]?` (anexar BankAccount.cs ao Contexto de Chat)

    Prompt: `@workspace /explain How can I implement logging of suspicious account activities of the [selected code]?` (anexar BankAccount.cs ao Contexto de Chat)

    Prompt: `@workspace /explain How can I improve the security of exception handling in the [selected code]?` (anexar BankAccount.cs ao Contexto de Chat)

    Prompt: `@workspace /explain How can I improve the security of the [selected code]?` (anexar BankAccount.cs ao Contexto de Chat)

    Prompt: `@workspace /explain How can I improve the security of the [selected code]?` (anexar Program.cs ao Contexto de Chat)

1. Selecione três prompts a serem usados durante o restante da demonstração.

    Tente selecionar duas solicitações que resolvam problemas de segurança no arquivo BankAccount.cs e uma para o arquivo Program.cs. Nesta demonstração, a classe BankAccount representa seu "produto". O arquivo Program.cs usa a classe BankAccount para simular atividades e transações da conta.

### Melhorar a segurança do código da classe BankAccount usando o Chat do GitHub Copilot

O desenvolvimento de código seguro é essencial para qualquer projeto de software. O nível de segurança necessário depende da natureza do aplicativo e dos dados que ele processa.

Nesta demonstração, você usará o GitHub Copilot Chat para gerar sugestões para melhorar a segurança da classe BankAccount no projeto **APL2007M5BankAccount-Security**.

O Chat do GitHub Copilot pode ser usado para ajudar a melhorar a segurança do código. Suas solicitações podem direcionar o GitHub Copilot para gerar sugestões para melhorar a autenticação, a proteção de dados, o registro em log e dezenas de outros tópicos. Você também pode criar solicitações de escopo amplo que solicitam sugestões gerais para melhorar a segurança do código. Uma combinação de solicitações específicas e gerais pode ajudar você a identificar as áreas que precisam de melhoria e implementar as alterações necessárias.

> [!TIP]
> Implementar e testar as atualizações sugeridas leva tempo, e o tempo pode ser um fator durante esta demonstração. Selecionar solicitações que se concentram em áreas específicas de melhoria pode ajudá-lo a gerenciar seu tempo. Solicitações muito amplas podem gerar um grande número de sugestões ou sugestões complexas que são difíceis de avaliar e implementar em um curto período de tempo. Depois de começar, você poderá atualizar suas solicitações com detalhes mais específicos se descobrir que as atualizações sugeridas têm escopo muito amplo ou muito complexo.

1. Verifique se o projeto é compilado e executado sem erros.

    Os avisos são aceitáveis desde que o aplicativo seja executado, mas os erros devem ser resolvidos antes de você começar a trabalhar com o GitHub Copilot Chat.

1. Abra o arquivo BankAccount.cs no Visual Studio Code e selecione todo o código no arquivo.

1. Abra o modo de exibição de chat.

1. No modo de exibição chat, use o botão **Anexar Contexto** para adicionar arquivos relevantes ao contexto de Chat e, em seguida, insira seu prompt.

1. Examinar as sugestões fornecidas pelo Chat do GitHub Copilot.

    Por exemplo, suponha que você conclua as seguintes ações:

    - Abra o arquivo BankAccount.cs e selecione todo o código.
    - Escolha o seguinte prompt: `@workspace /explain How can I implement authentication in the BankAccount.cs file?`
    - Abra o modo de exibição chat e anexe os arquivos BankAccount.cs e Program.cs ao contexto do Chat.
    - Insira o prompt no modo de exibição chat.

    Nesse caso, o Chat do GitHub Copilot sugere atualizações semelhantes à seguinte resposta:

    *A implementação da autenticação nesse contexto normalmente envolveria a adição de um método à classe BankAccount que verifica a identidade do titular da conta antes de permitir determinadas operações. Isso pode ser feito usando uma senha, um PIN ou alguma outra forma de autenticação.*

    *Aqui está um exemplo simples de como você pode adicionar autenticação baseada em senha à classe BankAccount:*

    ```csharp

    public class BankAccount
    {
        // Existing code...
        private string password;
        public BankAccount(string accountNumber, double initialBalance, string accountHolderName, string accountType, DateTime dateOpened, string password)
        {
            // Existing code...
    
            this.password = password;
        }
        public bool Authenticate(string password)
        {
            return this.password == password;
        }
        public void Credit(double amount, string password)
        {
            if (!Authenticate(password))
            {
                throw new Exception("Authentication failed.");
            }
            // Existing code...
        }
        // Similar changes would be made to the Debit, Transfer, and other methods...
    }

    ```

    *Neste exemplo, uma senha é adicionada como um parâmetro ao construtor BankAccount e armazenada em um campo privado. Um método Authenticate é adicionado e ele verifica se a senha fornecida corresponde à senha armazenada. O método Credit (e outros métodos que devem exigir autenticação) é modificado para usar uma senha como argumento e chamar Authenticate antes de executar a operação.*

    *Essa é uma forma muito básica de autenticação e não seria segura o suficiente para um aplicativo bancário real. Em um aplicativo real, você aplicaria hash e incluiria sal à senha antes de armazená-la e utilizaria métodos seguros para transmiti-la do usuário para o aplicativo. Talvez você também consideraria usar a autenticação de dois fatores ou outros métodos mais seguros.*

1. Implemente as atualizações sugeridas que ajudam a melhorar a segurança do código para sua classe `BankAccount`.

    O arquivo Program.cs deve ser atualizado para usar a senha e a autenticação adicionadas à classe BankAccount. Você pode usar o GitHub Copilot Chat para gerar sugestões para atualizar o arquivo Program.cs.

    1. Selecione o conteúdo do arquivo Program.cs, anexe os arquivos Program.cs e BankAccount.cs ao Contexto do Chat e, em seguida, insira o seguinte prompt no modo de exibição chat:

        ```plaintext
        @workspace /Explain How can I update the Program.cs file to use the password and authentication added to BankAccount.cs?
        ```

    1. Revise as sugestões fornecidas pelo GitHub Copilot Chat e implemente as atualizações sugeridas.

    1. Para garantir que nenhum erro tenha sido introduzido pelas alterações, crie e execute sua solução antes de continuar.

        Use o GitHub Copilot para ajudar a resolver quaisquer problemas identificados durante o processo de compilação.

    > [!IMPORTANT]
    > Verifique se os alunos entendem que essa forma básica de autenticação não é segura o suficiente para aplicativos reais. Em um aplicativo real, você provavelmente gostaria de usar hash e sal na senha antes de armazená-la, e você precisaria usar métodos seguros para transmitir a senha do usuário para o aplicativo. Talvez você também consideraria usar a autenticação de dois fatores ou outros métodos mais seguros.

1. Verifique se o aplicativo é compilado e executado antes de continuar.

1. Selecione todo o código no arquivo BankAccount.cs e, em seguida, insira sua segunda solicitação no modo de exibição do chat.

1. Examinar as sugestões fornecidas pelo Chat do GitHub Copilot.

    Por exemplo, suponha que você conclua as seguintes ações:

    - Abra o arquivo BankAccount.cs e selecione todo o código.
    - Escolha o seguinte prompt: `@workspace /explain How can I protect account numbers and account holder names in the selected code?`
    - Abra o modo de exibição chat e anexe os arquivos BankAccount.cs e Program.cs ao contexto do Chat.
    - Insira o prompt no modo de exibição chat.

    Nesse caso, o Chat do GitHub Copilot sugere atualizações semelhantes à seguinte resposta:

    *Para proteger dados confidenciais, como números de contas e nomes de titulares de contas na sua classe BankAccount, você pode seguir as seguintes etapas:*

    *1. Use Encapsulamento:*

    * –Torne as propriedades confidenciais privadas e forneça acesso controlado por meio de métodos.*

    *2. Criptografe Dados Confidenciais:*

    *– Use criptografia para armazenar dados confidenciais com segurança.*

    *3. Evite Armazenamento em Texto Não Criptografado:*

    *– Garanta que dados confidenciais não sejam armazenados ou transmitidos em texto simples.*

    *Implementação Atualizado*

    *Aqui está uma versão atualizada do BankAccount.cs que usa criptografia para números de conta e nomes de titulares de conta:*

    ```csharp

    using System;
    using System.Security.Cryptography;
    using System.Text;
    namespace BankAccountApp
    {
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
        public class InvalidAccountTypeException : Exception
        {
            public string AccountType { get; }
            public InvalidAccountTypeException(string accountType)
                : base($"Invalid account type: {accountType}.")
            {
                AccountType = accountType;
            }
        }
        public class InvalidAccountNumberException : Exception
        {
            public string AccountNumber { get; }
            public InvalidAccountNumberException(string accountNumber)
                : base($"Invalid account number: {accountNumber}.")
            {
                AccountNumber = accountNumber;
            }
        }
        public class InvalidAccountHolderNameException : Exception
        {
            public string AccountHolderName { get; }
            public InvalidAccountHolderNameException(string accountHolderName)
                : base($"Invalid account holder name: {accountHolderName}.")
            {
                AccountHolderName = accountHolderName;
            }
        }
        public class InvalidDateOpenedException : Exception
        {
            public DateTime DateOpened { get; }
            public InvalidDateOpenedException(DateTime dateOpened)
                : base($"Invalid date opened: {dateOpened}.")
            {
                DateOpened = dateOpened;
            }
        }
        public class InvalidInitialBalanceException : Exception
        {
            public double InitialBalance { get; }
            public InvalidInitialBalanceException(double initialBalance)
                : base($"Invalid initial balance: {initialBalance}.")
            {
                InitialBalance = initialBalance;
            }
        }
        public class InvalidInterestRateException : Exception
        {
            public double InterestRate { get; }
            public InvalidInterestRateException(double interestRate)
                : base($"Invalid interest rate: {interestRate}.")
            {
                InterestRate = interestRate;
            }
        }
        public class InvalidTransferAmountException : Exception
        {
            public double TransferAmount { get; }
            public InvalidTransferAmountException(double transferAmount)
                : base($"Invalid transfer amount: {transferAmount}.")
            {
                TransferAmount = transferAmount;
            }
        }
        public class InvalidCreditAmountException : Exception
        {
            public double CreditAmount { get; }
            public InvalidCreditAmountException(double creditAmount)
                : base($"Invalid credit amount: {creditAmount}.")
            {
                CreditAmount = creditAmount;
            }
        }
        public class InvalidDebitAmountException : Exception
        {
            public double DebitAmount { get; }
            public InvalidDebitAmountException(double debitAmount)
                : base($"Invalid debit amount: {debitAmount}.")
            {
                DebitAmount = debitAmount;
            }
        }
        public class AuthenticationException : Exception
        {
            public AuthenticationException(string message) : base(message) { }
        }
        public class BankAccount
        {
            public enum AccountTypes
            {
                Savings,
                Checking,
                MoneyMarket,
                CertificateOfDeposit,
                Retirement
            }
            private string EncryptedAccountNumber { get; }
            private string EncryptedAccountHolderName { get; }
            public double Balance { get; private set; }
            public AccountTypes AccountType { get; }
            public DateTime DateOpened { get; }
            private const double MaxTransferAmountForDifferentOwners = 500;
            private string Username { get; }
            private string Password { get; }
            public BankAccount(string accountNumber, double initialBalance, string accountHolderName, string accountType, DateTime dateOpened, string username, string password)
            {
                if (accountNumber.Length != 10)
                {
                    throw new InvalidAccountNumberException(accountNumber);
                }
                if (initialBalance < 0)
                {
                    throw new InvalidInitialBalanceException(initialBalance);
                }
                if (accountHolderName.Length < 2)
                {
                    throw new InvalidAccountHolderNameException(accountHolderName);
                }
                if (dateOpened > DateTime.Now)
                {
                    throw new InvalidDateOpenedException(dateOpened);
                }
                EncryptedAccountNumber = Encrypt(accountNumber);
                EncryptedAccountHolderName = Encrypt(accountHolderName);
                Balance = initialBalance;
                AccountType = (AccountTypes)Enum.Parse(typeof(AccountTypes), accountType);
                DateOpened = dateOpened;
                Username = username;
                Password = password;
            }
            public void Credit(double amount)
            {
                if (amount < 0)
                {
                    throw new InvalidCreditAmountException(amount);
                }
                Balance += amount;
            }
            public void Debit(double amount)
            {
                if (amount < 0)
                {
                    throw new InvalidDebitAmountException(amount);
                }
                if (Balance >= amount)
                {
                    Balance -= amount;
                }
                else
                {
                    throw new InsufficientFundsException(amount, Balance);
                }
            }
            public double GetBalance()
            {
                return Balance;
            }
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
                if (Decrypt(EncryptedAccountHolderName) != Decrypt(toAccount.EncryptedAccountHolderName) && amount > MaxTransferAmountForDifferentOwners)
                {
                    throw new Exception("Transfer amount exceeds maximum limit for different account owners.");
                }
            }
            public void PrintStatement()
            {
                Console.WriteLine($"Account Number: {Decrypt(EncryptedAccountNumber)}, Balance: {Balance}");
            }
            public double CalculateInterest(double interestRate)
            {
                if (interestRate < 0)
                {
                    throw new InvalidInterestRateException(interestRate);
                }
                return Balance * interestRate;
            }
            public void Authenticate(string username, string password)
            {
                if (Username != username || Password != password)
                {
                    throw new AuthenticationException("Invalid username or password.");
                }
            }
            private string Encrypt(string plainText)
            {
                using (Aes aes = Aes.Create())
                {
                    aes.Key = Encoding.UTF8.GetBytes("A very strong key"); // Use a secure key
                    aes.IV = Encoding.UTF8.GetBytes("A strong IV123456"); // Use a secure IV
                    ICryptoTransform encryptor = aes.CreateEncryptor(aes.Key, aes.IV);
                    using (var ms = new System.IO.MemoryStream())
                    {
                        using (var cs = new CryptoStream(ms, encryptor, CryptoStreamMode.Write))
                        {
                            using (var sw = new System.IO.StreamWriter(cs))
                            {
                                sw.Write(plainText);
                            }
                        }
                        return Convert.ToBase64String(ms.ToArray());
                    }
                }
            }
            private string Decrypt(string cipherText)
            {
                using (Aes aes = Aes.Create())
                {
                    aes.Key = Encoding.UTF8.GetBytes("A very strong key"); // Use a secure key
                    aes.IV = Encoding.UTF8.GetBytes("A strong IV123456"); // Use a secure IV
                    ICryptoTransform decryptor = aes.CreateDecryptor(aes.Key, aes.IV);
                    using (var ms = new System.IO.MemoryStream(Convert.FromBase64String(cipherText)))
                    {
                        using (var cs = new CryptoStream(ms, decryptor, CryptoStreamMode.Read))
                        {
                            using (var sr = new System.IO.StreamReader(cs))
                            {
                                return sr.ReadToEnd();
                            }
                        }
                    }
                }
            }
        }
    }

    ```

    *Uso:*

    *– Verifique se você tem as bibliotecas criptográficas necessárias disponíveis. O exemplo acima usa criptografia AES com uma chave codificada e IV para simplificar. Em um aplicativo do mundo real, você deve gerenciar chaves e IVs com segurança, possivelmente usando um serviço de gerenciamento de chaves.*

    > [!IMPORTANT]
    > Em um aplicativo do mundo real, você deve gerenciar chaves e IVs com segurança, possivelmente usando um serviço de gerenciamento de chaves. Os exemplos fornecidos neste treinamento identificam áreas para melhoria, mas não representam as melhores práticas para criptografia segura. Você pode usar o GitHub Copilot Chat para obter sugestões adicionais para melhorar a criptografia e a proteção de dados em seu aplicativo.

1. Não é necessário implementar as atualizações sugeridas para o segundo prompt.

    No exemplo, as atualizações sugeridas ajudariam a melhorar a segurança do aplicativo, mas exigem configurações significativas e alterações no código do Program.cs que estão fora do escopo desta demonstração.

### Melhorar a segurança de código da classe Program usando o Chat do GitHub Copilot

1. Abra o arquivo Program.cs no Visual Studio Code e selecione todo o código no arquivo.

1. Abra o modo de exibição do chat e, em seguida, insira a primeira solicitação que você preparou para a classe Program.

1. Examinar as sugestões fornecidas pelo Chat do GitHub Copilot.

    Por exemplo, suponha que você conclua as seguintes ações:

    - Abra o arquivo Program.cs e selecione todo o código.
    - Escolha o seguinte prompt: `@workspace /explain How can I improve the security of the Program.cs file?`
    - Abra o modo de exibição chat e anexe os arquivos BankAccount.cs e Program.cs ao contexto do Chat.
    - Insira o prompt no modo de exibição chat.

    Nesse caso, o Chat do GitHub Copilot sugere atualizações semelhantes à seguinte resposta:

    *Para melhorar a segurança do arquivo Program.cs, você deve se concentrar nas seguintes áreas:*

    *1. Tratamento Seguro de Senha:*

    *– Use hash seguro para senhas e evite armazená-las em texto não criptografado.*
    *– Use uma biblioteca como a BCrypt.Net para aplicar hash às senhas.*

    *2. Criptografe Dados Confidenciais:*

    *– Criptografe dados confidenciais, como números de contas e nomes dos titulares das contas.*

    *3. Evite Senhas Codificadas:*

    *– Evite o uso de senhas codificadas diretamente no código. Em vez disso, gere senhas fortes e aleatórias ou solicite que os usuários criem as suas próprias.*

    *4. Use Geração de Número Aleatório Segura: *

    *– Use um gerador de número aleatório criptograficamente seguro para gerar dados confidenciais.*

    *Implementação Atualizado*

    *Aqui está uma versão atualizada do Program.cs que incorpora essas melhorias:*

    ```csharp

    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Security.Cryptography;
    using System.Text;
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
            static async Task Main()
            {
                List<BankAccount> accounts = CreateBankAccounts(NumberOfAccounts);
                await SimulateTransactionsAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
                await SimulateTransfersAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
            }
            static List<BankAccount> CreateBankAccounts(int numberOfAccounts)
            {
                List<BankAccount> accounts = new();
                int createdAccounts = 0;
                while (createdAccounts < numberOfAccounts)
                {
                    try
                    {
                        double initialBalance = GenerateRandomDollarAmount(true, minAccountStart, maxAccountStart);
                        string accountHolderName = GenerateRandomAccountHolder();
                        string accountType = GenerateRandomAccountType();
                        DateTime dateOpened = GenerateRandomDateOpened();
                        string accountNumber = "102000" + random.Next(1000, 9999).ToString();
                        string username = "user" + createdAccounts;
                        string password = GenerateSecurePassword();
                        BankAccount account = new(accountNumber, initialBalance, accountHolderName, accountType, dateOpened, username, password);
                        accounts.Add(account);
                        createdAccounts++;
                    }
                    catch (ArgumentException ex)
                    {
                        Console.WriteLine($"Account creation failed due to invalid argument: {ex.Message}");
                        // Log the exception
                    }
                    catch (Exception ex)
                    {
                        Console.WriteLine($"Account creation failed: {ex.Message}");
                        // Log the exception
                    }
                    finally
                    {
                        // Any cleanup code would go here.
                    }
                }
                return accounts;
            }
            static async Task SimulateTransactionsAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                var tasks = accounts.Select(async account =>
                {
                    for (int i = 0; i < numberOfTransactions; i++)
                    {
                        double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                        try
                        {
                            account.Authenticate(account.Username, account.Password); // Authenticate before transaction
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
                    }
                    Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                });
                await Task.WhenAll(tasks);
            }
            static async Task SimulateTransfersAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                var tasks = accounts.Select(async account =>
                {
                    for (int i = 0; i < numberOfTransactions; i++)
                    {
                        double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                        try
                        {
                            account.Authenticate(account.Username, account.Password); // Authenticate before transfer
                            BankAccount toAccount = accounts[random.Next(accounts.Count)];
                            toAccount.Authenticate(toAccount.Username, toAccount.Password); // Authenticate target account
                            account.Transfer(toAccount, transactionAmount);
                            Console.WriteLine($"Transfer: {transactionAmount}, From: {account.AccountNumber}, To: {toAccount.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                        }
                        catch (Exception ex)
                        {
                            Console.WriteLine($"Transfer failed: {ex.Message}");
                        }
                    }
                    Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                });
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
                DateTime startDate = new(DateTime.Today.Year - MaxYearsBack, 1, 1);
                int daysRange = (DateTime.Today - startDate).Days;
                DateTime randomDate = startDate.AddDays(random.Next(daysRange));
                if (randomDate.Year == DateTime.Today.Year && randomDate >= DateTime.Today)
                {
                    randomDate = randomDate.AddDays(-1);
                }
                return randomDate;
            }
            static string GenerateSecurePassword()
            {
                const int passwordLength = 12;
                const string validChars = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ1234567890!@#$%^&*()";
                StringBuilder password = new StringBuilder();
                using (RNGCryptoServiceProvider rng = new RNGCryptoServiceProvider())
                {
                    byte[] uintBuffer = new byte[sizeof(uint)];
                    while (passwordLength > password.Length)
                    {
                        rng.GetBytes(uintBuffer);
                        uint num = BitConverter.ToUInt32(uintBuffer, 0);
                        password.Append(validChars[(int)(num % (uint)validChars.Length)]);
                    }
                }
                return password.ToString();
            }
        }
    }

    ```

1. Observe que as atualizações para Program.cs focadas na geração de números aleatórios seguros.

    As outras sugestões se aplicam à classe BankAccount, e a implementação está além do escopo deste treinamento.

1. Construa um prompt adicional para Program.cs que busca proteger o tratamento de exceções.

1. Examine as sugestões fornecidas pelo GitHub Copilot Chat.

    Por exemplo, se você inserir `@workspace /explain How can I implement secure exception handling in the Program.cs file?` no modo de exibição de chat, o GitHub Copilot Chat sugerirá atualizações semelhantes à seguinte resposta:

    *Para implementar o tratamento seguro de exceções no arquivo Program.cs, siga estas práticas recomendadas:*

    *1. Capture Exceções Específicas:*

    *– Capture exceções específicas em vez de usar um bloco genérico catch (Exception ex). Isso ajuda a entender e lidar adequadamente com diferentes tipos de erros.*

    *2. Registre Exceções com Segurança:*

    *– Registre exceções com segurança sem expor informações confidenciais. Use uma estrutura de registro para gerenciar logs.*

    *3. Forneça ao Usuário Mensagens Fáceis de Entender:*

    *– Forneça ao usuário mensagens fáceis de entender, sem revelar detalhes da internet.*

    *4. Use Blocos por Fim para Limpeza:*

    *– Use blocos por fim para garantir que qualquer limpeza necessária seja executada, independentemente de uma exceção ter sido gerada.*

    *5. Evite Capturar Exceções Não Críticas:*

    *– Evite capturar exceções que devem ter permissão para se propagar, como OutOfMemoryException ou StackOverflowException.*

    *Aqui está uma versão atualizada do Program.cs com tratamento seguro de exceção:*

    ```csharp

    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Security.Cryptography;
    using System.Text;
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
            static async Task Main()
            {
                List<BankAccount> accounts = CreateBankAccounts(NumberOfAccounts);
                await SimulateTransactionsAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
                await SimulateTransfersAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
            }
            static List<BankAccount> CreateBankAccounts(int numberOfAccounts)
            {
                List<BankAccount> accounts = new();
                int createdAccounts = 0;
                while (createdAccounts < numberOfAccounts)
                {
                    try
                    {
                        double initialBalance = GenerateRandomDollarAmount(true, minAccountStart, maxAccountStart);
                        string accountHolderName = GenerateRandomAccountHolder();
                        string accountType = GenerateRandomAccountType();
                        DateTime dateOpened = GenerateRandomDateOpened();
                        string accountNumber = "102000" + random.Next(1000, 9999).ToString();
                        string username = "user" + createdAccounts;
                        string password = GenerateSecurePassword();
                        BankAccount account = new(accountNumber, initialBalance, accountHolderName, accountType, dateOpened, username, password);
                        accounts.Add(account);
                        createdAccounts++;
                    }
                    catch (ArgumentException ex)
                    {
                        Console.WriteLine($"Account creation failed due to invalid argument: {ex.Message}");
                        // Log the exception securely
                        LogException(ex);
                    }
                    catch (Exception ex)
                    {
                        Console.WriteLine($"Account creation failed: {ex.Message}");
                        // Log the exception securely
                        LogException(ex);
                    }
                    finally
                    {
                        // Any cleanup code would go here.
                    }
                }
                return accounts;
            }
            static async Task SimulateTransactionsAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                var tasks = accounts.Select(async account =>
                {
                    for (int i = 0; i < numberOfTransactions; i++)
                    {
                        double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                        try
                        {
                            account.Authenticate(account.Username, account.Password); // Authenticate before transaction
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
                        catch (InvalidCreditAmountException ex)
                        {
                            Console.WriteLine($"Invalid credit amount: {ex.Message}");
                            LogException(ex);
                        }
                        catch (InvalidDebitAmountException ex)
                        {
                            Console.WriteLine($"Invalid debit amount: {ex.Message}");
                            LogException(ex);
                        }
                        catch (InsufficientFundsException ex)
                        {
                            Console.WriteLine($"Insufficient funds: {ex.Message}");
                            LogException(ex);
                        }
                        catch (AuthenticationException ex)
                        {
                            Console.WriteLine($"Authentication failed: {ex.Message}");
                            LogException(ex);
                        }
                        catch (Exception ex)
                        {
                            Console.WriteLine($"Transaction failed: {ex.Message}");
                            LogException(ex);
                        }
                    }
                    Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                });
                await Task.WhenAll(tasks);
            }
            static async Task SimulateTransfersAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                var tasks = accounts.Select(async account =>
                {
                    for (int i = 0; i < numberOfTransactions; i++)
                    {
                        double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                        try
                        {
                            account.Authenticate(account.Username, account.Password); // Authenticate before transfer
                            BankAccount toAccount = accounts[random.Next(accounts.Count)];
                            toAccount.Authenticate(toAccount.Username, toAccount.Password); // Authenticate target account
                            account.Transfer(toAccount, transactionAmount);
                            Console.WriteLine($"Transfer: {transactionAmount}, From: {account.AccountNumber}, To: {toAccount.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                        }
                        catch (InvalidTransferAmountException ex)
                        {
                            Console.WriteLine($"Invalid transfer amount: {ex.Message}");
                            LogException(ex);
                        }
                        catch (InsufficientFundsException ex)
                        {
                            Console.WriteLine($"Insufficient funds: {ex.Message}");
                            LogException(ex);
                        }
                        catch (AuthenticationException ex)
                        {
                            Console.WriteLine($"Authentication failed: {ex.Message}");
                            LogException(ex);
                        }
                        catch (Exception ex)
                        {
                            Console.WriteLine($"Transfer failed: {ex.Message}");
                            LogException(ex);
                        }
                    }
                    Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                });
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
                DateTime startDate = new(DateTime.Today.Year - MaxYearsBack, 1, 1);
                int daysRange = (DateTime.Today - startDate).Days;
                DateTime randomDate = startDate.AddDays(random.Next(daysRange));
                if (randomDate.Year == DateTime.Today.Year && randomDate >= DateTime.Today)
                {
                    randomDate = randomDate.AddDays(-1);
                }
                return randomDate;
            }
            static string GenerateSecurePassword()
            {
                const int passwordLength = 12;
                const string validChars = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ1234567890!@#$%^&*()";
                StringBuilder password = new StringBuilder();
                using (RNGCryptoServiceProvider rng = new RNGCryptoServiceProvider())
                {
                    byte[] uintBuffer = new byte[sizeof(uint)];
                    while (passwordLength > password.Length)
                    {
                        rng.GetBytes(uintBuffer);
                        uint num = BitConverter.ToUInt32(uintBuffer, 0);
                        password.Append(validChars[(int)(num % (uint)validChars.Length)]);
                    }
                }
                return password.ToString();
            }
            static void LogException(Exception ex)
            {
                // Implement a secure logging mechanism here
                // For example, log to a file, database, or external logging service
                Console.WriteLine($"Logged exception: {ex.Message}");
            }
        }
    }

    ```

1. Implemente as atualizações sugeridas que ajudam a melhorar a segurança do código para sua classe `Program.cs`.

1. Para garantir que nenhum erro tenha sido introduzido pelas alterações, crie e execute sua solução.

## Resumo

Nesta demonstração, você usou o GitHub Copilot Chat para gerar sugestões para melhorar a segurança do código em um aplicativo de exemplo. Você desenvolveu solicitações que orientaram o GitHub Copilot a fornecer sugestões para melhorar a autenticação, a proteção de dados, o registro em log e outros tópicos relacionados à segurança. Você implementou as atualizações sugeridas para melhorar a segurança das classes BankAccount e Program no projeto **APL2007M5BankAccount-Security**.
