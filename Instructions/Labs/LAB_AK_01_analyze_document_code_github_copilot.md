---
lab:
  title: 'Laboratório: Acelerar o desenvolvimento de aplicativos usando o GitHub Copilot'
  type: Answer Key
  module: Modules 2-5
---

# Laboratório: Acelerar o desenvolvimento de aplicativos usando o GitHub Copilot
# Chave de respostas do laboratório do aluno

## Part 1: Analisar e documentar código usando as ferramentas do GitHub Copilot

### Antes de começar

#### Visão geral do projeto

Você é um desenvolvedor de software que trabalha para um departamento regional de TI. A maioria dos aplicativos com as quais você trabalha dá suporte à comunidade local. Recentemente, os servidores da biblioteca comunitária foram danificados em um acidente, e levará semanas para obter autorização para substituí-los. Seu departamento precisa desenvolver uma solução temporária que permita que bibliotecários executem funções básicas.

Sua equipe se reuniu com os bibliotecários. Eles precisam de uma solução mínima que lhes permita fornecer aos clientes da biblioteca serviços essenciais, como empréstimos e retornos de livros. Sua equipe investiga os recursos disponíveis e desenvolve um plano. Inicialmente, somente você e outro colega de trabalho serão atribuídos ao projeto. O governo local fechou a biblioteca até que sua solução temporária esteja disponível. Você tem três dias para desenvolver uma solução v1 que permite que a biblioteca reabra.

Enquanto seu colega começa a trabalhar no software, você usa registros de biblioteca para criar arquivos JSON que representam contas patronas, livros e empréstimos de livros da biblioteca. No final do segundo dia, você estará pronto para começar a ajudar com o código. A solução é um aplicativo de console que pode ser executado em um dos computadores portáteis da biblioteca. Os bibliotecários entendem que não há tempo para uma interface bonita, mas enfatizam que o aplicativo deve ser seguro e confiável. Você tem mais um dia antes de precisar demonstrar a versão 1.0 do seu aplicativo.

Você usará o GitHub Copilot para ajudar a realizar o trabalho da maneira mais eficiente possível. Se tudo correr bem, seu aplicativo será usado para dar suporte às unidades de livro da biblioteca e a outras funções fora do local no futuro.

#### Cenário do laboratório (parte 1)

O GitHub Copilot pode ajudar você a entender e documentar uma base de código gerando explicações e documentação.

Na parte 1 deste laboratório, você usará o GitHub Copilot para analisar e documentar o aplicativo da biblioteca. Você também criará um repositório GitHub para o aplicativo de biblioteca e gerará um arquivo LEIAME para o repositório usando o GitHub Copilot.

A Parte 1 inclui os seguintes exercícios:

- Configurar as extensões do GitHub Copilot para Visual Studio Code.
- Usar o GitHub Copilot para explicar a base de código do aplicativo de biblioteca.
- Usar o Visual Studio Code para criar um repositório GitHub para o aplicativo de biblioteca.
- Usar as extensões do GitHub Copilot para criar um arquivo README.md para o repositório.

### Exercício 1: Configurar as extensões do GitHub Copilot para o Visual Studio Code

Você usará sua conta do GitHub para autorizar o Visual Studio Code a verificar sua assinatura do GitHub Copilot.

Siga as etapas abaixo para instalar as extensões do GitHub Copilot:

1. Abra uma janela do navegador.

1. Para abrir o portal do GitHub Enterprise, navegue até a seguinte URL:

    ```plaintext
    https://github.com/enterprises/Microsoft-APL/sso
    ```

1. Entre na sua conta do GitHub usando as seguintes credenciais:

    Email/Nome de usuário: `@lab.CloudPortalCredential(1).Username`

    Senha: `@lab.CloudPortalCredential(1).Password`

1. Abra o Visual Studio Code.

1. No menu esquerdo, selecione **Extensões**.

1. Na caixa de texto Pesquisar extensões no Marketplace, digite **GitHub Copilot** e pressione Enter.

1. Na lista filtrada de extensões, selecione a extensão **GitHub Copilot** criada pelo GitHub.

1. Na página de extensão do GitHub Copilot, selecione **Instalar**.

1. Quando você vir a notificação "Entrar para usar o GitHub Copilot", selecione **Sign in to GitHub**.

    Se você vir uma caixa de diálogo dizendo que o GitHub Copilot deseja fazer login usando o GitHub, selecione **Allow**.

    Como você já está conectado à sua conta do GitHub em uma janela do navegador, uma nova guia Verificar Sessão deve ser aberta na janela do navegador.

1. Na página Verificar Sessão, selecione **Continue**.

1. Na página Autorizar aplicativo, selecione **Authorize Visual Studio Code**.

1. Para retornar ao Visual Studio Code, selecione **Abrir**.

1. Feche e abra novamente o Visual Studio Code.

    Reiniciar o Visual Studio Code ajuda a garantir que o GitHub Copilot esteja integrado à interface do usuário do Visual Studio Code.

1. Observe que o botão **Abrir chat** agora está visível no lado direito do Centro de Comando, na parte superior da janela do Visual Studio Code.

#### Resumo — exercício 1

Neste exercício, você instalou a extensão GitHub Copilot no Visual Studio Code. Você também autorizou o Visual Studio Code a acessar sua conta do GitHub. Agora você está pronto para usar o GitHub Copilot para analisar e documentar a base de código do aplicativo da biblioteca.

### Exercício 2: Analisar a base de código do aplicativo de biblioteca

Antes de criar um repositório de código e um arquivo LEIAME, você deve levar algum tempo para examinar a base de código. É importante entender a arquitetura do aplicativo e os principais recursos antes de documentar o projeto. Você também deve executar o aplicativo para garantir que ele seja executado conforme o esperado.

#### Tarefa 1: Carregar o aplicativo de biblioteca em seu ambiente de desenvolvimento

Seu colega desenvolveu uma versão inicial do aplicativo de biblioteca e o disponibilizou como um arquivo de .zip. Para se preparar para este laboratório, você precisa executar as seguintes ações:

- Baixe um arquivo zip contendo a solução.
- Extraia os arquivos de código.
- Abra o aplicativo de biblioteca no Visual Studio Code e certifique-se que ele compile com sucesso.

Siga as etapas abaixo para preparar o requerimento da biblioteca:

1. Certifique-se de ter o navegador da Web aberto e, em seguida, abra uma nova guia do navegador.

1. Para baixar o arquivo zip que contém seu projeto de código, navegue até a seguinte URL:

    ```plaintext
    https://raw.githubusercontent.com/MicrosoftLearning/APL-2007-Accelerate-app-development-by-using-GitHub-Copilot/master/LearnModuleExercises/Downloads/GuidedProjectApp.zip
    ```

    O arquivo zip que contém o código da solução, GuidedProjectApp.zip, deve ser baixado automaticamente.

1. Quando o download estiver concluído, feche a guia do navegador.

    Mantenha a página do navegador para sua conta do GitHub aberta. Você o usará posteriormente no laboratório.

1. Abra o Explorador de Arquivos do Windows e navegue até a pasta Downloads.

1. Descompacte os arquivos de projeto baixados.

    Descompacte o projeto de código no ambiente de desenvolvimento. Por exemplo:

    1. No computador local, navegue até a pasta Downloads.

    1. Clique com o botão direito do mouse **GuidedProjectApp.zip**e selecione **Extrair todos **.

    1. Selecione **Mostrar os arquivos extraídos ao concluir** e escolha **Extrair**.

    1. Anote o local da pasta extraída.

1. Copie a pasta extraída, AccelerateDevGitHubCopilot, para um local de fácil acesso, como a pasta Windows Desktop.

1. Abra a pasta **AccelerateDevGitHubCopilot** no Visual Studio Code.

    Por exemplo:

    1. Abra o Visual Studio Code no computador.

    1. No Visual Studio Code, no menu **Arquivo**, selecione **Abrir Pasta**.

    1. Navegue até a pasta Windows Desktop e localize a pasta **AccelerateDevGitHubCopilot** .

    1. Selecione **AccelerateDevGitHubCopilot**Copilot e selecione **Selecionar pasta**.

    1. Selecione **Sim, eu confio nos autores**.

    > [!NOTE]
    > Pode levar de 10 a 20 segundos para que o Visual Studio Code carregue os arquivos de projeto e todas as atualizações necessárias do .NET.

1. Na exibição EXPLORER do Visual Studio Code, selecione GERENCIADOR DE SOLUÇÕES e verifique a seguinte estrutura do projeto:

    - AccelerateDevGitHubCopilot\
        - src\
            - Library.ApplicationCore\
            - Library.Console\
            - Library.Infrastructure\
        - tests\
            - UnitTests\

1. Verifique se a solução é compilada com êxito.

    Por exemplo, no modo de exibição GERENCIADOR DE SOLUÇÕES, clique com o botão direito do mouse em **AccelerateDevGitHubCopilot** e selecione **Compilar**.

    Você verá vários **avisos**, mas não deve haver nenhum erro. Você executará o aplicativo posteriormente neste exercício.

    > [!NOTE]
    > Não instale atualizações de carga de trabalho, a menos que seu instrutor o instrua a fazê-lo.

#### Tarefa 2: Usar o GitHub Copilot para explicar a base de código do aplicativo da biblioteca

O GitHub Copilot pode ajudá-lo a entender uma base de código desconhecida gerando explicações nos níveis de solução e recursos.

Use as seguintes etapas para concluir esta seção do exercício:

1. Certifique-se de que você esteja com a solução AccelerateDevGitHubCopilot aberta no Visual Studio Code.

1. Abra o modo de exibição de chat.

    Você pode abrir a visualização de chat das seguintes maneiras:

    - Selecione o botão **Abrir chat** (localizado na parte superior da janela do Visual Studio Code, à direita do centro de comando).
    - Use o atalho de teclado: **Ctrl+Alt+I**.
    - Abra o menu de status do GitHub Copilot e selecione **GitHub Copilot Chat**.

1. Insira um prompt que use o participante **@workspace** do GitHub Copilot para gerar uma descrição do projeto.

    Por exemplo, insira a seguinte solicitação no modo de exibição de chat:

    ```plaintext
    @workspace Describe this project
    ```

    Se você vir uma caixa de diálogo do Visual Studio Code informando que "GitHub Copilot Chat deseja entrar usando o GitHub", selecione **Permitir** e conclua o processo de autorização usando sua conta do GitHub.

1. Reserve um minuto para revisar a resposta gerada pelo GitHub Copilot.

    Você deverá ver uma resposta semelhante à seguinte descrição:

    ```markdown
    This project is a library management system implemented in C#. It consists of three main components:
    
    1. **Library.ApplicationCore**: This is the core application library containing the main business logic, entities, enums, and interfaces. It includes:
        - Entities such as Book, Patron, Loan, etc.
        - Enums like MembershipRenewalStatus, LoanReturnStatus, and LoanExtensionStatus.
        - Services like LoanService and PatronService.
        - Interfaces like ILoanRepository, IPatronRepository, ILoanService, and IPatronService.
    2. **Library.Console**: This is a console application that interacts with the user. It includes:
        - The main entry point in Program.cs.
        - Configuration settings in appSettings.json.
        - Console interaction logic in ConsoleApp.cs.
    3. **Library.Infrastructure**: This library handles data persistence. It includes:
        - JSON-based repositories like JsonPatronRepository and JsonLoanRepository.
        - Data loading and saving logic in JsonData.

    Additionally, there are unit tests located in the UnitTests directory, which test the functionality of the core services using the NSubstitute mocking framework and xUnit.
    
    The project uses .NET 8.0 and is configured to build and test using GitHub Actions as defined in the build-test.yml file. The solution file is AccelerateDevGitHubCopilot.sln, which includes all the projects and their configurations.
    ```

1. Use a exibição do Gerenciador de Soluções do Visual Studio Code para expandir as pastas do projeto.

1. Localize e abra o arquivo **ConsoleApp.cs**.

    O arquivo ConsoleApp.cs está localizado no projeto src/Library.Console.

1. Insira um prompt na exibição de chat que gere uma descrição da classe ConsoleApp.

    Por exemplo, insira a seguinte solicitação no modo de exibição de chat:

    ```plaintext
    @workspace #editor Describe the ConsoleApp class
    ```

1. Reserve alguns minutos para examinar a resposta.

    Você deverá ver uma resposta semelhante à seguinte descrição:

    ```markdown
    The ConsoleApp class in ConsoleApp.cs is responsible for managing the console-based user interface of the library management system. It handles user interactions, processes user inputs, and coordinates actions with the underlying services and repositories.

    ### Fields
    - _currentState: Tracks the current state of the console application.
    - matchingPatrons: A list of patrons that match a search query.
    - selectedPatronDetails: Holds details of the currently selected patron.
    - selectedLoanDetails: Holds details of the currently selected loan.
    - _patronRepository: An instance of IPatronRepository for accessing patron data.
    - _loanRepository: An instance of ILoanRepository for accessing loan data.
    - _loanService: An instance of ILoanService for performing loan-related operations.
    - _patronService: An instance of IPatronService for performing patron-related operations.

    ### Constructor
    - ConsoleApp(ILoanService loanService, IPatronService patronService, IPatronRepository patronRepository, ILoanRepository loanRepository): Initializes the ConsoleApp with the provided services and repositories.

    ### Methods
    - Run(): The main entry point for running the console application.
    - PatronSearch(): Handles the logic for searching patrons.
    - ReadPatronName(): Reads the patron's name from the console input.
    - PrintPatronsList(List<Patron> matchingPatrons): Prints a list of matching patrons to the console.
    - PatronSearchResults(): Handles the logic for displaying and selecting from the search results.
    - ReadInputOptions(CommonActions options, out int optionNumber): Reads input options from the console.
    - WriteInputOptions(CommonActions options): Writes the available input options to the console.
    - PatronDetails(): Displays details of the selected patron.
    - LoanDetails(): Displays details of the selected loan and handles actions like extending or returning the loan.

    The class uses a state machine approach to manage different states of the console application, such as searching for patrons, displaying search results, showing patron details, and handling loan details.
    ```

1. Abra o arquivo **Program.cs**.

1. Insira um prompt na visualização de chat que gere uma descrição do arquivo Program.cs.

    Por exemplo, insira a seguinte solicitação no modo de exibição de chat:

    ```plaintext
    @workspace #editor Describe the Program.cs file
    ```

1. Reserve alguns minutos para examinar a resposta.

    Você deverá ver uma resposta semelhante à seguinte descrição:

    ```markdown
    The Program.cs file is the entry point for the console application. It sets up the dependency injection container, configures services, and starts the ConsoleApp.
    
    1. **Dependency Injection Setup**:
        - Creates a ServiceCollection to register services.
        - Builds a configuration object from the appSettings.json file.
        - Registers various services and repositories with different lifetimes (singleton, scoped).
    
    2. **Service Registration**:
        - Registers the repositories: JsonPatronRepository and JsonLoanRepository.
        - Registers the services: LoanService and PatronService.
        - Registers the JsonData class as a singleton.
        - Registers the ConsoleApp class as a singleton.
    
    3. **Service Provider**:
        - Builds the service provider from the registered services.
        - Retrieves the ConsoleApp service and runs it asynchronously.

    This setup ensures that all dependencies are properly injected and configured before the application starts running.
    ```

1. Expanda o projeto Library.Infrastructure e, em seguida, expanda a pasta Dados.

1. Adicione os arquivos **JsonData.cs**, **JsonLoanRepository.cs** e **JsonPatronRepository.cs** ao contexto do Chat.

    Você pode usar uma operação de arrastar e soltar para adicionar os arquivos do Gerenciador de Soluções ao modo de exibição Chat. Você também pode usar o botão **Attach Context** (clipe de papel) na visualização de chat para adicionar arquivos ao contexto de chat.

1. Insira um prompt no modo de exibição chat que gera uma explicação das classes de acesso a dados.

    Por exemplo, insira a seguinte solicitação no modo de exibição de chat:

    ```plaintext
    @workspace /explain Explain how the data access classes work
    ```

1. Reserve alguns minutos para examinar a resposta.

    Você deverá ver uma resposta semelhante à seguinte descrição:

    ```markdown
    The data access classes in this project are designed to handle the loading, saving, and manipulation of data stored in JSON files. These classes include JsonData, JsonPatronRepository, and JsonLoanRepository. Here's an explanation of how each class works:
    
    ### JsonData Class
    The JsonData class is responsible for loading and saving data from and to JSON files. It also provides methods to populate related entities.
    
    #### Key Responsibilities:
    1. **Loading Data**: The LoadData method loads data from JSON files into in-memory collections (Authors, Books, BookItems, Patrons, Loans).
    2. **Saving Data**: The SaveJson method saves data to JSON files. Specific methods like SaveLoans and SavePatrons handle saving loans and patrons, respectively.
    3. **Ensuring Data is Loaded**: The EnsureDataLoaded method ensures that data is loaded into memory before any operations are performed.
    4. **Populating Related Entities**: Methods like GetPopulatedPatron, GetPopulatedLoan, GetPopulatedBookItem, and GetPopulatedBook populate related entities to provide a complete view of the data.
    
    #### Example Methods:
    - **LoadData**: Loads all data from JSON files.
    - **SaveLoans**: Saves loan data to the JSON file.
    - **GetPopulatedPatron**: Populates a patron with related loans.
    - **SearchBookByTitle**: Searches for a book by its title.
    
    ### JsonPatronRepository Class
    The JsonPatronRepository class implements the IPatronRepository interface and provides methods to interact with patron data.

    #### Key Responsibilities:
    1. **Searching Patrons**: The SearchPatrons method searches for patrons by name. 
    2. **Getting a Patron**: The GetPatron method retrieves a patron by ID and populates related data.
    3. **Updating a Patron**: The UpdatePatron method updates patron information and saves it to the JSON file.
    
    #### Example Methods:
    - **SearchPatrons**: Searches for patrons whose names contain the search input.
    - **GetPatron**: Retrieves a patron by ID and populates related loans.
    - **UpdatePatron**: Updates patron information and saves it to the JSON file.
    
    ### JsonLoanRepository Class
    The JsonLoanRepository class implements the ILoanRepository interface and provides methods to interact with loan data.
    
    #### Key Responsibilities:
    1. **Getting a Loan**: The GetLoan method retrieves a loan by ID and populates related data.
    2. **Updating a Loan**: The UpdateLoan method updates loan information and saves it to the JSON file.
    
    #### Example Methods:
    - **GetLoan**: Retrieves a loan by ID and populates related book items and patrons.
    - **UpdateLoan**: Updates loan information and saves it to the JSON file.
    
    ### How They Work Together
    1. **Loading Data**: When the application starts, the JsonData class loads data from JSON files into memory.
    2. **Searching and Retrieving Data**: The JsonPatronRepository and JsonLoanRepository classes use the JsonData class to search and retrieve data. They ensure data is loaded before performing operations.
    3. **Updating Data**: When data is updated, the repository classes call methods on the JsonData class to save the updated data back to the JSON files.
    4. **Populating Related Entities**: The JsonData class provides methods to populate related entities, ensuring that when a patron or loan is retrieved, it includes related data like loans or book items.
    
    ### Example Workflow
    1. **Search for a Patron**:
        - The SearchPatrons method in JsonPatronRepository calls EnsureDataLoaded to ensure data is loaded.
        - It then searches the Patrons collection for matching names and returns the results.

    2. **Get a Loan**:
       - The GetLoan method in JsonLoanRepository calls EnsureDataLoaded to ensure data is loaded.
       - It retrieves the loan by ID and uses GetPopulatedLoan to include related book items and patrons.

    3. **Update a Patron**:
       - The UpdatePatron method in JsonPatronRepository calls EnsureDataLoaded to ensure data is loaded.
       - It updates the patron information and calls SavePatrons to save the updated data to the JSON file.

    By using these data access classes, the application can efficiently manage data stored in JSON files, ensuring that data is loaded, manipulated, and saved correctly.
    ```

1. Leve alguns minutos para examinar os arquivos de dados JSON usados para simular registros de biblioteca.

    Os arquivos de dados JSON estão localizados na pasta src/Library.Console/Json.

    Os arquivos de dados usam propriedades de ID para vincular entidades. Por exemplo, um objeto Loan tem uma propriedade PatronId que se vincula a um objeto Patron com o mesmo ID. Os arquivos JSON contêm dados para autores, livros, itens de livro, clientes e empréstimos.

    > [!NOTE]
    > Observe que nomes de autor, títulos de livro e nomes de cliente foram anonimizados para fins deste projeto guiado.

#### Tarefa 3: Compilar e executar o aplicativo

A execução do aplicativo ajudará você a entender a interface do usuário, os principais recursos do aplicativo e como os componentes do aplicativo interagem.

Use as seguintes etapas para concluir esta seção do exercício:

1. Verifique se você tem o modo de exibição **Gerenciador de Soluções** aberto.

    A exibição do Gerenciador de Soluções não é a mesma que a exibição do Explorer. A exibição do Gerenciador de Soluções usa arquivos de projeto e solução como nós de “diretório” para exibir a estrutura da solução.

1. Para executar o aplicativo, clique com o botão direito do mouse em **Library.Console**, selecione **Depurar** e, em seguida, selecione **Iniciar Nova Instância**.

    Se as opções **Depurar** e **Iniciar nova instância** não forem exibidas, verifique se você está usando o modo de exibição gerenciador de soluções e não o modo de exibição do Explorer.

    As etapas a seguir orientam você por um caso de uso simples.

1. Quando solicitado a obter um nome de leitor, digite **Um** e, em seguida, pressione Enter.

    > [!NOTE]
    > O aplicativo usa um processo de pesquisa que diferencia maiúsculas de minúsculas. Você deve inserir "One" com "O" maiúsculo.

    Você deverá ver uma lista de leitores que correspondam à consulta da pesquisa.

1. No prompt "Opções de Entrada", digite **2** e, a seguir, pressione Enter.

    Inserir **2** selecionará o segundo leitor da lista.

    Você deverá ver o nome do leitor e o status de filiação seguidos dos detalhes do empréstimo do livro.

1. No prompt “Opções de Entrada”, digite **1** e, a seguir, pressione Enter.

    Inserir **1** selecionará o primeiro livro da lista.

    Você deve ver os detalhes do livro listados, incluindo a data de conclusão e o status de retorno.

1. No prompt “Opções de Entrada”, digite **r** e, a seguir, pressione Enter.

    Inserindo **r** retorna o livro.

1. Verifique se a mensagem "O livro foi devolvido com sucesso" aparece. será exibida.

    A mensagem "O livro foi devolvido com sucesso". deve ser seguida pelos detalhes do livro. Os livros devolvidos são marcados com **Returned: True**.

1. Para iniciar uma nova pesquisa, digite **s** e pressione Enter.

1. Quando solicitado a obter um nome de leitor, digite **Um** e, em seguida, pressione Enter.

1. No prompt “Opções de Entrada”, digite **2** e, a seguir, pressione Enter.

1. Verifique se o primeiro empréstimo de livro está marcado como **Returned: True**.

1. No prompt “Opções de Entrada”, digite **q** e, a seguir, pressione Enter.

1. Interrompa a sessão de depuração.

#### Resumo — exercício 2

Este exercício ajudou você a entender a base de código do aplicativo de biblioteca e como o aplicativo interage com o usuário. Você usou o GitHub Copilot para gerar explicações para a estrutura do projeto, os arquivos selecionados e as classes de acesso a dados. Você também executou o aplicativo para ver como a interface do console funciona e como os componentes do aplicativo interagem.

### Exercício 3: Criar o repositório GitHub e esvaziar o arquivo Leiame

A criação do repositório GitHub para seu código permitirá que você compartilhe seu trabalho com outras pessoas e colabore no projeto.

#### Tarefa 1: Criar um repositório GitHub

Use as seguintes etapas para concluir esta seção do exercício:

1. Certifique-se de que sua conta do GitHub esteja aberta em uma janela do navegador.

    Se necessário, abra uma janela do navegador e use as seguintes informações para fazer login:

    URL: `https://github.com/enterprises/Microsoft-APL/sso`

    Email/Nome de usuário: `@lab.CloudPortalCredential(1).Username`

    Senha: `@lab.CloudPortalCredential(1).Password`

1. Abra o menu da conta do GitHub e selecione **Seus repositórios**.

    Você deve ver uma mensagem indicando que ainda não tem nenhum repositório.

1. Para construir comandos de configuração do Git que usam as credenciais da sua conta do GitHub, abra o **Notepad** e compile os seguintes comandos do Git:

    ```bash
    git config --global user.email "lab assigned email"
    git config --global user.name "user name"
    ```

    Substitua  **"lab assigned email"**  pelo email definido no ambiente do laboratório: `@lab.CloudPortalCredential(1).Username`

    Substitua **"user name"** com o seu nome.

1. Alterne para a janela do Visual Studio Code.

1. Abra o terminal integrado do Visual Studio Code.

    No menu Terminal, selecione **Novo terminal**.

1. Para configurar o Git usando as credenciais associadas à sua conta do GitHub, insira os dois comandos que você construiu no Bloco de Notas.

1. No Visual Studio Code, abra o modo de exibição controle do código-fonte.

1. Clique em **Publicar no GitHub**.

    Se uma caixa de diálogo for aberta solicitando o login usando sua conta do GitHub, conclua as seguintes etapas:

    1. Selecione **Permitir**.
    1. Selecione a conta que você está usando neste ambiente de laboratório.
    1. Se necessário, selecione **Publish to GitHub** novamente.

1. Aceite o nome padrão do repositório (AccelerateDevGitHubCopilot) e selecione **Publish to GitHub private repository**.

    Observe que o Visual Studio Code exibe uma mensagem de status durante o processo de publicação.

    Você pode ser solicitado a autorizar sua conta do GitHub novamente. Nesse caso, siga as instruções na tela para autorizar sua conta no navegador. Isso pode resultar na publicação do seu repositório usando a mensagem de confirmação "primeiro commit".

1. Se o código não foi publicado no repositório e você retornar à exibição Controle do Código-Fonte, insira uma mensagem de confirmação e selecione **Publicar Ramificação**.

    Quando o processo de publicação for concluído, você verá uma mensagem informando que seu código foi publicado com êxito no repositório GitHub especificado.

#### Tarefa 2: Criar um arquivo Leiame vazio no GitHub

Use as seguintes etapas para concluir esta seção do exercício:

1. Alterne para a janela do navegador exibindo sua conta GitHub.

1. Abra o novo repositório AccelerateDevGitHubCopilot em sua conta do GitHub.

    Se você não vir seu repositório AccelerateDevGitHubCopilot, atualize a página. Se você ainda não vir o repositório, tente as seguintes etapas:

    1. Mude para o Visual Studio Code.
    1. Abra suas notificações (uma notificação foi gerada quando o novo repositório foi publicado).
    1. Selecione **Abrir no GitHub** para abrir seu repositório.

1. Na guia Código do repositório AccelerateDevGitHubCopilot, selecione **Adicionar um LEIAME**.

1. No editor de LEIAME.md, digite **Em breve** e selecione **Confirmar alterações**.

1. Na caixa de diálogo Confirmar alterações, selecione **Commit changes**.

#### Tarefa 3: Transferir as alterações para o seu repositório local

Use as seguintes etapas para concluir esta seção do exercício:

1. Alterne para o Visual Studio Code e verifique se o modo de exibição controle do código-fonte está aberto.

1. Abra o menu **More Actions** e selecione **Pull**.

    O menu More Actions pode ser aberto usando as reticências no canto superior direito da visualização de controle de código-fonte.

1. Abra a exibição EXPLORER (recolha o GERENCIADOR DE SOLUÇÕES e use o explorador de arquivos/pastas padrão do Visual Studio Code) e expanda a pasta **AccelerateDevGitHubCopilot**.

1. Abra o arquivo LEIAME.md.

    Você verá a mensagem “Em breve”.

    > [!NOTE]
    > Você poderia ter criado o conteúdo do arquivo Leiame diretamente no Visual Studio Code e, em seguida, enviado as atualizações para o repositório GitHub.

Você usará o GitHub Copilot Chat para atualizar o arquivo Leiame do seu repositório no próximo exercício.

#### Resumo — exercício 3

Este exercício ajudou você a criar um repositório GitHub para o aplicativo de biblioteca e um arquivo Leiame vazio. Você também extraiu as alterações para o repositório local para garantir que você tenha as atualizações mais recentes.

### Exercício 4: Criar a documentação do projeto para o arquivo Leiame

O arquivo LEIAME é uma parte essencial de qualquer repositório GitHub. O LEIAME fornece informações com base nas necessidades do projeto, colaboradores do projeto e stakeholders.

Para este exercício de projeto guiado, seu arquivo LEIAME deve incluir as seguintes seções:

- **Título do projeto**: Um título breve e claro para o projeto.
- **Descrição**: Uma explicação detalhada do que é o projeto e o que ele faz.
- **Estrutura do Projeto**: Um detalhamento da estrutura do projeto, incluindo pastas de chave e arquivos.
- **Classes-chave e interfaces**: Uma lista de classes-chave e interfaces no projeto.
- **Uso**: Instruções sobre como usar o projeto, geralmente incluindo exemplos de código.
- **Licença**: A licença sob a qual o projeto está.

#### Tarefa 1: Usar o GitHub Copilot para gerar a documentação do projeto

Nesta seção do exercício, você usará o GitHub Copilot para criar a documentação do projeto e adicioná-la ao seu arquivo README.md.

Use as seguintes etapas para concluir esta seção do exercício:

1. Abra o modo de exibição de chat.

    Quando estiver interessado em código ou arquivos específicos, você pode usar operações de arrastar e soltar para adicionar arquivos ao contexto do modo de exibição de chat. Nesse caso, você está interessado na solução geral, portanto, usará o participante `@workspace` em vez de adicionar arquivos individuais.

1. Para gerar a documentação do projeto do arquivo LEIAME, insira o seguinte prompt:

    ```plaintext
    @workspace Generate the contents of a README.md file for the code repository. Use "Library App" as the project title. The README file should include the following sections: Description, Project Structure, Key Classes and Interfaces, Usage, License. Format all sections as raw markdown. Use a bullet list with indents to represent the project structure. Do not include ".gitignore" or the ".github", "bin", and "obj" folders.
    ```

    > [!NOTE]
    > Usando vários prompts, um para cada seção do arquivo LEIAME produziria resultados mais detalhados. Um único prompt é usado neste exercício para simplificar o processo.

1. Examine a resposta para garantir que cada seção seja formatada como markdown.

    > [!NOTE]
    > Você pode atualizar as seções README individualmente para fornecer informações mais detalhadas ou se elas não estiverem formatadas corretamente. Você também pode copiar a resposta do GitHub Copilot para o arquivo LEIAME e, em seguida, fazer correções diretamente no arquivo de markdown.

1. Com o arquivo markdown aberto no editor, abra o menu de status do GitHub Copilot e selecione **Enable completions for markdown**.

1. Copie as seções de documentação sugeridas para o arquivo LEIAME.md.

    O GitHub Copilot pode gerar sugestões para a documentação de markdown. Esse recurso pode ajudá-lo a compor e formatar arquivos markdown.

    Por exemplo, você pode selecionar o conteúdo do arquivo README.md, abrir o chat embutido e pedir ao GitHub Copilot para "corrigir a formatação da documentação de markdown".

1. Ajuste a formatação, se necessário, e salve o arquivo README.md atualizado.

    Você deve ter um arquivo README que inclua o título do projeto, descrição, estrutura do projeto, classes e interfaces principais, instruções de uso e informações de licença.

    ```markdown
    # Library App
    
    ## Description
    Library App is a console-based application for managing library operations such as patron management, book loans, and membership renewals. It uses a JSON-based data storage system and provides various services to handle library functionalities.
    
    ## Project Structure
    - AccelerateDevGitHubCopilot.sln
    - README.md
    - src
      - Library.ApplicationCore/
        - Entities/
          - `Author.cs`
          - `Book.cs`
          - `BookItem.cs`
          - `Loan.cs`
          - `Patron.cs`
        - Enums/
          - `LoanExtensionStatus.cs`
          - `LoanReturnStatus.cs`
          - `MembershipRenewalStatus.cs`
        - Interfaces/
          - `IPatronRepository.cs`
          - `IPatronService.cs`
          - `ILoanRepository.cs`
          - `ILoanService.cs`
        - `Library.ApplicationCore.csproj`
        - Services/
          - `PatronService.cs`
          - `LoanService.cs`
      - Library.Console/
        - `appSettings.json`
        - `CommonActions.cs`
        - `ConsoleApp.cs`
        - `ConsoleState.cs`
        - `Library.Console.csproj`
        - `Program.cs`
      - Library.Infrastructure/
        - Data/
          - `JsonData.cs`
          - `JsonLoanRepository.cs`
          - `JsonPatronRepository.cs`
        - `Library.Infrastructure.csproj`
    - tests
      - UnitTests/
        - ApplicationCore/
          - LoanService/
            - `ReturnLoan.cs`
            - `ExtendLoan.cs`
          - PatronService/
            - `RenewMembership.cs`
        - `UnitTests.csproj`
    
    ## Key Classes and Interfaces
    - **Entities**
      - **Author**: Represents an author with properties like Id and Name.
      - **Book**: Represents a book with properties like Id, Title, AuthorId, Genre, ImageName, and ISBN.
      - **BookItem**: Represents a specific copy of a book with properties like Id, BookId, AcquisitionDate, and Condition.
      - **Loan**: Represents a loan with properties like Id, BookItemId, PatronId, LoanDate, DueDate, and ReturnDate.
      - **Patron**: Represents a library patron with properties like Id, Name, MembershipStart, MembershipEnd, and Loans.
    
    - **Enums**
      - **LoanExtensionStatus**: Enum for loan extension statuses.
      - **LoanReturnStatus**: Enum for loan return statuses.
      - **MembershipRenewalStatus**: Enum for membership renewal statuses.
    
    - **Interfaces**
      - **IPatronRepository**: Interface for patron repository with methods like GetPatron, SearchPatrons, and UpdatePatron.
      - **IPatronService**: Interface for patron service with method RenewMembership.
      - **ILoanRepository**: Interface for loan repository with methods like GetLoan and UpdateLoan.
      - **ILoanService**: Interface for loan service with methods like ReturnLoan and ExtendLoan.
    
    - **Services**
      - **PatronService**: Implements IPatronService to handle patron-related operations.
      - **LoanService**: Implements ILoanService to handle loan-related operations.
    
    - **Console**
      - **ConsoleApp**: Main console application class that handles user interactions and application flow.
      - **ConsoleState**: Enum for different states of the console application.
      - **CommonActions**: Enum for common actions in the console application.
    
    - **Infrastructure**
      - **JsonData**: Handles loading and saving data to JSON files.
      - **JsonLoanRepository**: Implements ILoanRepository to manage loan data.
      - **JsonPatronRepository**: Implements IPatronRepository to manage patron data.
    
    ## Usage
    1. Clone the repository.
    2. Open the solution file AccelerateDevGitHubCopilot.sln in Visual Studio.
    3. Build the solution to restore dependencies.
    4. Run the Library.Console project to start the console application.
    5. Follow the on-screen instructions to search for patrons, view patron details, extend loans, return books, and renew memberships.
    
    ## License
    This project is licensed under the MIT License.
    ```

#### Tarefa 2: Confirmar e transmitir as atualizações do arquivo README

Use as seguintes etapas para concluir esta seção do exercício:

1. Abra a exibição Controle de Codigo-Fonte do Visual Studio Code.

1. Para que o GitHub Copilot gere uma mensagem de confirmação, selecione o ícone no lado direito da caixa de mensagem.

    Você deverá ver uma mensagem de confirmação semelhante à seguinte mensagem:

    ```plaintext
    Update README.md with project description, structure, key classes, usage instructions, and license information
    ```

1. Preparar e confirmar as atualizações de arquivo.

1. Sincronize (ou envie por push) suas atualizações para o repositório GitHub.

    Autorize a operação de sincronização/push usando suas credenciais do GitHub, se solicitado.

#### Tarefa 3: Verificar seu trabalho

Para verificar seu trabalho, conclua as seguintes etapas:

1. Abra o repositório GitHub para o projeto AccelerateDevGitHubCopilot.

1. Use a guia **Código** para examinar o arquivo de LEIAME.md atualizado.

    Você pode precisar atualizar o navegador para ver o arquivo README atualizado.

1. Verifique se a estrutura do projeto descrita no arquivo LEIAME alinha a estrutura de pastas do repositório.

    Ao visualizar o arquivo README, você pode usar a árvore de arquivos no lado esquerdo da interface do GitHub para expandir e revisar a estrutura do repositório.

1. Examine o histórico de confirmação e localize a mensagem de confirmação gerada pelo GitHub Copilot.

#### Resumo — exercício 4

Este exercício ajudou você a criar a documentação do projeto para o arquivo README usando o GitHub Copilot. Você usou o GitHub Copilot para gerar a descrição do projeto, a estrutura do projeto, as principais classes e interfaces, as instruções de uso e as informações de licença. Você também confirmou e enviou as atualizações do arquivo README para o repositório GitHub.

## Parte 2: Desenvolver recursos de código usando as ferramentas GitHub Copilot

### Antes de começar

#### Visão geral do projeto

Você e seu colega de trabalho se encontram para conversar sobre seus objetivos para o aplicativo de biblioteca. Você quer aprimorar a experiência do usuário para bibliotecários e leitores. Você aborda vários novos recursos que poderiam ser adicionados ao aplicativo.

Você concorda em trabalhar nos seguintes recursos:

- Disponibilidade de um livro: Permitir que um bibliotecário determine o status de disponibilidade de um livro. Esse recurso deve exibir uma mensagem indicando se um livro está disponível para empréstimo ou a data-limite da devolução se o livro estiver atualmente emprestado para um outro leitor.

- Empréstimos de livros: Permitir que um bibliotecário empreste um livro a um leitor (se o livro estiver disponível). Esse recurso deve exibir a opção para um leitor retirar um livro emprestado, atualizar o arquivo Loans.json com o novo empréstimo e exibir os detalhes do empréstimo atualizados para o leitor.

- Reservas de livros: Permitir que um bibliotecário reserve um livro para um leitor (a menos que o livro já esteja reservado). Esse recurso deve implementar um novo processo de reserva de livro. Esse recurso poderá requerer a criação de um novo arquivo Reservations.json, juntamente com as novas classes e interfaces necessárias para dar suporte ao processo de reserva.

Cada um de vocês irá trabalhar em um dos novos recursos e, em seguida, vocês devem se reunir novamente. Você vai trabalhar no recurso para determinar o status de disponibilidade de um livro. Seu colega de trabalho vai trabalhar no recurso de emprestar um livro a um leitor. O recurso final, reservar um livro para um leitor, será desenvolvido após os outros dois recursos terem sido concluídos.

#### Cenário de laboratório (parte 2)

O GitHub Copilot pode ajudá-lo a desenvolver novos recursos para o aplicativo de biblioteca.

Na parte 2 deste laboratório, você usará o GitHub Copilot para gerar sugestões de código que ajudam a implementar os novos recursos com mais rapidez e precisão.

A Parte 2 inclui os seguintes exercícios:

- Desenvolver um novo recurso de "disponibilidade do livro".
- Mesclar suas alterações na ramificação principal do repositório.

### Exercício 5: Desenvolva um novo recurso de "disponibilidade de livros"

O recurso de disponibilidade do livro deve incluir as seguintes atualizações de código:

- Implemente uma nova ação CommonActions.SearchBooks que permita que um bibliotecário selecione a opção de pesquisar um livro.
- Crie um novo método SearchBooks no ConsoleApp.cs. O método SearchBooks deve ler um título de livro fornecido pelo usuário. Verificar se um livro está disponível para empréstimo e exibir uma mensagem informando "book.title está disponível para empréstimo" ou "book.title está emprestado a outro cliente". A data da devolução é loan.DueDate.

Durante este exercício, você concluirá as seguintes tarefas:

- Criar uma ramificação de "disponibilidade de livros" em seu repositório de códigos.
- Use as sugestões do GitHub Copilot para ajudar a implementar uma nova ação comum do SearchBooks que pode ser selecionada por um bibliotecário.
- Use as sugestões do GitHub Copilot para ajudar a desenvolver o método SearchBooks que lê o título de um livro fornecido pelo usuário, verifica se um livro está disponível para empréstimo e exibe uma mensagem indicando o status de disponibilidade do livro.

#### Tarefa 1: Criar uma nova ramificação no repositório

Antes de começar a desenvolver o novo recurso de "disponibilidade do livro", você precisa criar um novo branch no repositório. Isso permitirá que você trabalhe no novo recurso sem afetar o branch principal do repositório. Você pode mesclar o novo recurso no branch principal quando estiver pronto.

Use as seguintes etapas para concluir esta seção do exercício:

1. Certifique-se de que você esteja com a solução AccelerateDevGitHubCopilot aberta no Visual Studio Code.

1. Selecione o modo de exibição Controle do Código-Fonte e certifique-se de que o repositório local esteja sincronizado com o repositório remoto (Pull ou Sincronização).

1. No canto inferior esquerdo da janela, selecione **principal**.

1. Para criar uma nova ramificação, digite **book availability** e selecione **+ Create new branch**.

1. Para enviar o novo branch por push para o repositório remoto, selecione **Publicar Branch**.

#### Tarefa 2: Implementar uma nova ação comum "SearchBooks"

Nesta seção do exercício, você usa o GitHub Copilot para ajudá-lo a implementar uma opção de menu chamada SearchBooks. Os bibliotecários escolherão a ação SearchBooks para verificar o status de disponibilidade de um livro.

Aqui estão as atualizações de arquivo que você conclui durante esta tarefa:

- Atualizar a enumeração CommonActions em CommonActions.cs: Adicionar uma nova ação SearchBooks à enumeração CommonActions.
- Atualizar o método WriteInputOptions no ConsoleApp.cs: Adicionar suporte para exibir a nova opção CommonActions.SearchBooks.
- Atualizar o método ReadInputOptions no ConsoleApp.cs: Adicionar suporte para leitura (selecionando) a nova opção CommonActions.SearchBooks.
- Atualizar o método PatronDetails no ConsoleApp.cs: Adicionar suporte para processar a nova opção CommonActions.SearchBooks quando selecionada.

Use as seguintes etapas para concluir esta seção do exercício:

1. Abra a exibição do GERENCIADOR DE SOLUÇÕES.

1. Abra o arquivo CommonActions.cs e selecione a enumeração **CommonActions**.

    Você precisa adicionar uma nova ação do SearchBooks a CommonActions.

1. Abra o chat embutido e, a seguir, insira o seguinte prompt:

    ```plaintext
    Update selection to include a new `SearchBooks` action.
    ```

    O GitHub Copilot deve sugerir uma atualização de código que adicione a nova ação SearchBooks à enumeração CommonActions.

1. Reveja a atualização sugerida e, a seguir, selecione **Aceitar**.

    ```csharp

    public enum CommonActions
    {
        Repeat = 0,
        Select = 1,
        Quit = 2,
        SearchPatrons = 4,
        RenewPatronMembership = 8,
        ReturnLoanedBook = 16,
        ExtendLoanedBook = 32,
        SearchBooks = 64
    }

    ```

1. Abra o arquivo ConsoleApp.cs.

1. Localize e selecione o método **WriteInputOptions**.

    Você precisa adicionar suporte para a nova opção CommonActions.SearchBooks. Mostrar a opção para verificar se um livro está disponível para empréstimo.

1. Abra o chat embutido e insira o seguinte prompt:

    ```plaintext
    Update selection to include an option for the `CommonActions.SearchBooks` action. Use the letter "b" and the message "to check for book availability".
    ```

    O GitHub Copilot deverá sugerir uma atualização de código que adicione um novo bloco "if" para a ação SearchBooks.

1. Reveja a atualização sugerida e, a seguir, selecione **Aceitar**.

    A atualização sugerida deve ser semelhante ao seguinte trecho de código:

    ```csharp

    static void WriteInputOptions(CommonActions options)
    {
        Console.WriteLine("Input Options:");
        if (options.HasFlag(CommonActions.ReturnLoanedBook))
        {
            Console.WriteLine(" - \"r\" to mark as returned");
        }
        if (options.HasFlag(CommonActions.ExtendLoanedBook))
        {
            Console.WriteLine(" - \"e\" to extend the book loan");
        }
        if (options.HasFlag(CommonActions.RenewPatronMembership))
        {
            Console.WriteLine(" - \"m\" to extend patron's membership");
        }
        if (options.HasFlag(CommonActions.SearchPatrons))
        {
            Console.WriteLine(" - \"s\" for new search");
        }
        if (options.HasFlag(CommonActions.SearchBooks))
        {
            Console.WriteLine(" - \"b\" to check for book availability");
        }
        if (options.HasFlag(CommonActions.Quit))
        {
            Console.WriteLine(" - \"q\" to quit");
        }
        if (options.HasFlag(CommonActions.Select))
        {
            Console.WriteLine("Or type a number to select a list item.");
        }
    }

    ```

1. Role um pouco para cima para encontrar o método **ReadInputOptions**.

1. Selecione o método **ReadInputOptions**.

    Você precisa adicionar suporte para a nova opção CommonActions.SearchBooks. Inclua um caso que lida com o usuário selecionando a ação SearchBooks.

1. Abra o chat embutido e, a seguir, insira o seguinte prompt:

    ```plaintext
    Update selection to include an option for the `CommonActions.SearchBooks` action.
    ```

    O GitHub Copilot deve sugerir uma atualização de código que adicione um novo "caso" que lida com o usuário selecionando a ação SearchBooks.

1. Reveja a atualização sugerida e, a seguir, selecione **Aceitar**.

    A atualização sugerida deve ser semelhante ao seguinte trecho de código:

    ```csharp

    static CommonActions ReadInputOptions(CommonActions options, out int optionNumber)
    {
        CommonActions action;
        optionNumber = 0;
        do
        {
            Console.WriteLine();
            WriteInputOptions(options);
            string? userInput = Console.ReadLine();
            action = userInput switch
            {
                "q" when options.HasFlag(CommonActions.Quit) => CommonActions.Quit,
                "s" when options.HasFlag(CommonActions.SearchPatrons) => CommonActions.SearchPatrons,
                "m" when options.HasFlag(CommonActions.RenewPatronMembership) => CommonActions.RenewPatronMembership,
                "e" when options.HasFlag(CommonActions.ExtendLoanedBook) => CommonActions.ExtendLoanedBook,
                "r" when options.HasFlag(CommonActions.ReturnLoanedBook) => CommonActions.ReturnLoanedBook,
                "b" when options.HasFlag(CommonActions.SearchBooks) => CommonActions.SearchBooks,
                _ when int.TryParse(userInput, out optionNumber) => CommonActions.Select,
                _ => CommonActions.Repeat
            };
            if (action == CommonActions.Repeat)
            {
                Console.WriteLine("Invalid input. Please try again.");
            }
        } while (action == CommonActions.Repeat);
        return action;
    }

    ```

1. Role para baixo para encontrar e, em seguida, selecione o método **PatronDetails**.

    Existem duas coisas que você precisa fazer:

    - Você precisa adicionar CommonActions.SearchBooks às opções antes de chamar ReadInputOptions.
    - Você também precisa adicionar um else para lidar com a ação SearchBooks. O bloco else if deve chamar um novo método chamado SearchBooks.

    Você pode abordar essas duas coisas juntas.

1. Abra o chat embutido e, a seguir, insira o seguinte prompt:

    ```plaintext
    Update selection to add `CommonActions.SearchBooks` to `options` before calling `ReadInputOptions`. Add an `else if` block to handle the `SearchBooks` action. The `else if` block should call a new method named `SearchBooks`.
    ```

    O GitHub Copilot deve sugerir uma atualização de código que adicione CommonActions.SearchBooks às opções antes de chamar ReadInputOptions.

1. Reveja a atualização sugerida e, a seguir, selecione **Aceitar**.

    ```csharp

    async Task<ConsoleState> PatronDetails()
    {
        Console.WriteLine($"Name: {selectedPatronDetails.Name}");
        Console.WriteLine($"Membership Expiration: {selectedPatronDetails.MembershipEnd}");
        Console.WriteLine();
        Console.WriteLine("Book Loans:");
        int loanNumber = 1;
        foreach (Loan loan in selectedPatronDetails.Loans)
        {
            Console.WriteLine($"{loanNumber}) {loan.BookItem!.Book!.Title} - Due: {loan.DueDate} - Returned: {(loan.ReturnDate != null).ToString()}");
            loanNumber++;
        }
        CommonActions options = CommonActions.SearchPatrons | CommonActions.Quit | CommonActions.Select | CommonActions.RenewPatronMembership | CommonActions.SearchBooks;
        CommonActions action = ReadInputOptions(options, out int selectedLoanNumber);
        if (action == CommonActions.Select)
        {
            if (selectedLoanNumber >= 1 && selectedLoanNumber <= selectedPatronDetails.Loans.Count())
            {
                var selectedLoan = selectedPatronDetails.Loans.ElementAt(selectedLoanNumber - 1);
                selectedLoanDetails = selectedPatronDetails.Loans.Where(l => l.Id == selectedLoan.Id).Single();
                return ConsoleState.LoanDetails;
            }
            else
            {
                Console.WriteLine("Invalid book loan number. Please try again.");
                return ConsoleState.PatronDetails;
            }
        }
        else if (action == CommonActions.Quit)
        {
            return ConsoleState.Quit;
        }
        else if (action == CommonActions.SearchPatrons)
        {
            return ConsoleState.PatronSearch;
        }
        else if (action == CommonActions.RenewPatronMembership)
        {
            var status = await _patronService.RenewMembership(selectedPatronDetails.Id);
            Console.WriteLine(EnumHelper.GetDescription(status));
            // reloading after renewing membership
            selectedPatronDetails = (await _patronRepository.GetPatron(selectedPatronDetails.Id))!;
            return ConsoleState.PatronDetails;
        }
        else if (action == CommonActions.SearchBooks)
        {
            return await SearchBooks();
        }
        throw new InvalidOperationException("An input option is not handled.");
    }

    ```

    > [!NOTE]
    > Sugestões de chat em linha também podem criar código stub para o método SearchBooks.

#### Tarefa 3: Desenvolver o método SearchBooks

Depois de concluído, o método SearchBooks deve ler o título de um livro fornecido pelo usuário, verificar se um livro está disponível para empréstimo e exibir uma mensagem indicando o status de disponibilidade do livro. O método deve usar os arquivos Books.json e Loans.json para localizar o título do livro correspondente e determinar o status de disponibilidade do livro.

Use as seguintes etapas para concluir esta seção do exercício:

1. Reserve um minuto para considerar os requisitos de processo para o método SearchBooks.

    O que o método precisa fazer? O que ele deverá retornar? Isso requer algum parâmetro?

    O método SearchBooks deve implementar o seguinte processo:

    1. Solicitar ao usuário um título de livro.
    1. Ler o título do livro fornecido pelo usuário.
    1. Verificar se um livro está disponível para empréstimo
    1. Exibir uma mensagem informando uma das seguintes opções:

        - "book.title está disponível para empréstimo"
        - "book.title está emprestado a outro cliente." A data da devolução é loan.DueDate.

    Para criar as opções de mensagem, seu código precisará acessar os seguintes arquivos JSON:

    - Books.json é necessário para localizar o Title e o BookId correspondentes.
    - Loans.json é necessário encontrar o ReturnDate e o DueDate para o BookItemId correspondente. O BookItemId é o mesmo que o BookId em Books.json.

1. Certifique-se de ter o seguinte método **SearchBooks** criado no arquivo ConsoleApp.cs:

    ```csharp

    async Task<ConsoleState> SearchBooks()
    {
        return ConsoleState.PatronDetails;
    }

    ```

    > [!NOTE]
    > Certifique-se de remover todos os comentários de código criados pelo GitHub Copilot. Os comentários desnecessários e incorretos podem influenciar as sugestões do GitHub Copilot negativamente.

1. Selecione o método **SearchBooks**.

1. Abra o chat embutido e, a seguir, insira o seguinte prompt:

    ```plaintext
    Update selection to obtain a book title. Prompt the user to "Enter a book title to search for". Read the user input and ensure the book title isn't null.
    ```

    O GitHub Copilot deverá sugerir uma atualização de código que capture o título do livro fornecido pelo usuário.

1. Reveja a atualização sugerida e, a seguir, selecione **Aceitar**.

    ```csharp

    async Task<ConsoleState> SearchBooks()
    {
        string? bookTitle = null;
        while (String.IsNullOrWhiteSpace(bookTitle))
        {
            Console.Write("Enter a book title to search for: ");
            bookTitle = Console.ReadLine();
        }
        // Perform book search logic here
        return ConsoleState.PatronDetails;
    }

    ```

    > [!NOTE]
    > O GitHub Copilot pode criar um método separado para lidar com a entrada do usuário de um título de livro. Você pode aceitar essa sugestão e continuar a desenvolver a lógica primária no método SearchBooks.

1. Exclua todos os comentários de espaço reservado gerados pelo GitHub Copilot e, em seguida, selecione o método **SearchBooks**.

1. Abra o modo de exibição de chat.

1. Adicione os seguintes arquivos ao contexto de chat: ConsoleApp.cs, JsonData.cs, JsonLoanRepository.cs, Books.json, Loans.json e BookItems.json.

1. Digite a seguinte solicitação:

    ```plaintext
    @workspace  Explain how to update the `SearchBooks` method and ConsoleApps class to determine whether a book title is available for loan. Inside the SearchBooks method, use a LINQ query and the user supplied book title to return a matching book. If a book is found, use a LINQ query and Loans.json to check if the book is available for loan. If the book has been returned, display a message stating "`book.title` is available for loan". If the book is on loan, display a message stating "`book.title` is on loan to another patron. The return due date is `loan.DueDate`".
    ```

1. Reserve um minuto para rever as atualizações sugeridas.

    O GitHub Copilot deve propor atualizações semelhantes às seguintes sugestões:

    Para atualizar o método SearchBooks e a classe ConsoleApp para determinar se o título do livro está disponível para empréstimo, siga estas etapas:

    a. Adicione um método para pesquisar livros por título na classe JsonData.
    b. Atualize o método SearchBooks na classe ConsoleApp para usar esse novo método.
    c. Verifique o status do empréstimo do livro e exiba a mensagem apropriada.

    Aqui está o código atualizado:

    Etapa 1: Adicionar um método para pesquisar livros por título na classe JsonData

    ```csharp

    public Book? SearchBookByTitle(string title)
    {
        return Books?.FirstOrDefault(b => b.Title.Equals(title, StringComparison.OrdinalIgnoreCase));
    }

    ```

    Etapa 2: Atualizar o método SearchBooks na classe ConsoleApp

    ```csharp

    async Task<ConsoleState> SearchBooks()
    {
        string bookTitle = ReadBookTitle();
        // ensure data is loaded
        await _jsonData.LoadData();
        // find the book by title
        Book? book = _jsonData.SearchBookByTitle(bookTitle);
        if (book == null)
        {
            Console.WriteLine($"No book found with title: {bookTitle}");
            return ConsoleState.PatronDetails;
        }
        // find the loan status of the book
        Loan? loan = _jsonData.Loans?.FirstOrDefault(l => l.BookItemId == book.Id && l.ReturnDate == null);
        if (loan == null)
        {
            Console.WriteLine($"{book.Title} is available for loan.");
        }
        else
        {
            Console.WriteLine($"{book.Title} is on loan to another patron. The return due date is {loan.DueDate}.");
        }
        return ConsoleState.PatronDetails;
    }

    ```

    Etapa 3: Atualizar o construtor da classe ConsoleApp para incluir JsonData

    ```csharp

    public class ConsoleApp
    {
        // Existing fields...
        JsonData _jsonData;
        public ConsoleApp(ILoanService loanService, IPatronService patronService, IPatronRepository patronRepository, ILoanRepository loanRepository, JsonData jsonData)
        {
            _patronRepository = patronRepository;
            _loanRepository = loanRepository;
            _loanService = loanService;
            _patronService = patronService;
            _jsonData = jsonData;
        }
        // Other methods...

    }

    ```

    Etapa 4: Atualizar o Program.cs para passar JsonData para ConsoleApp

    ```csharp

    using Microsoft.Extensions.DependencyInjection;
    using Library.Infrastructure.Data;
    using Library.ApplicationCore;
    using Microsoft.Extensions.Configuration;
    var services = new ServiceCollection();
    var configuration = new ConfigurationBuilder()
    .SetBasePath(Directory.GetCurrentDirectory())
    .AddJsonFile("appSettings.json")
    .Build();
    services.AddSingleton<IConfiguration>(configuration);
    services.AddScoped<IPatronRepository, JsonPatronRepository>();
    services.AddScoped<ILoanRepository, JsonLoanRepository>();
    services.AddScoped<ILoanService, LoanService>();
    services.AddScoped<IPatronService, PatronService>();
    services.AddSingleton<JsonData>();
    services.AddSingleton<ConsoleApp>();
    var servicesProvider = services.BuildServiceProvider();
    var consoleApp = servicesProvider.GetRequiredService<ConsoleApp>();
    consoleApp.Run().Wait();

    ```

    Com essas alterações, o método SearchBooks na classe ConsoleApp agora pesquisará por um livro usando o título no arquivo Books.json e verificará seu status de empréstimo no arquivo Loans.json. Se o livro estiver disponível para empréstimo, ele exibirá uma mensagem informando que o livro está disponível. Se o livro estiver emprestado, ele exibirá uma mensagem informando que o livro está emprestado e fornecerá a data da devolução.

    > [!NOTE]
    > O GitHub Copilot pode sugerir o uso de consultas LINQ no método SearchBooks para retornar um objeto book em vez de usar um método na classe JsonData. No entanto, também pode sugerir a criação de métodos na classe `JsonData` para retornar o título de um livro e verificar o status do empréstimo (em vez de usar consultas LINQ para o método SearchBooks). As instruções a seguir são baseadas em sugestões do GitHub Copilot que usam uma combinação dessas abordagens.

1. Adicione o método SearchBookByTitle sugerido ao final da classe **JsonData**.

    ```csharp

    public Book? SearchBookByTitle(string title)
    {
        return Books?.FirstOrDefault(b => b.Title.Equals(title, StringComparison.OrdinalIgnoreCase));
    }

    ```

1. Adicione a declaração de campo _jsonData à classe ConsoleApp antes do construtor da classe.

    ```csharp

    JsonData _jsonData;

    ```

1. Adicione um parâmetro JsonData jsonData ao construtor de classe ConsoleApp e use-o para inicializar o campo _jsonData dentro do construtor.

    O construtor da classe atualizado deve se parecer com o seguinte trecho de código:

    ```csharp

    public ConsoleApp(ILoanService loanService, IPatronService patronService, IPatronRepository patronRepository, ILoanRepository loanRepository, JsonData jsonData)
    {
        _patronRepository = patronRepository;
        _loanRepository = loanRepository;
        _loanService = loanService;
        _patronService = patronService;
        _jsonData = jsonData;
    }

    ```

1. Observe que JsonData não é reconhecido na classe ConsoleApp.

    Você precisa adicionar "using Library.Infrastructure.Data;" à parte superior do arquivo ConsoleApp.cs.

1. Certifique-se de que a seguinte instrução "using" seja adicionada à parte superior do arquivo ConsoleApp.cs.

    ```csharp

    using Library.Infrastructure.Data;

    ```

1. Use as sugestões de código para atualizar o método **SearchBooks**:

    O código sugerido deve usar o método SearchBookByTitle (ou uma consulta LINQ) para pesquisar o livro pelo título. Se o livro for encontrado, uma consulta LINQ será usada para determinar se o livro está emprestado. O código também inclui uma lógica para exibir o status de disponibilidade do livro com base nos resultados da pesquisa. A lógica usada para exibir mensagens de resposta pode ser implementada de várias maneiras. Um exemplo é fornecido no trecho de código abaixo.

    O trecho de código a seguir mostra uma possível implementação do método SearchBooks:

    ```csharp

    async Task<ConsoleState> SearchBooks()
    {
        string bookTitle = ReadBookTitle();
        Book? book = _jsonData.SearchBookByTitle(bookTitle);
        if (book == null)
        {
            Console.WriteLine($"No book found with title: {bookTitle}");
            return ConsoleState.PatronDetails;
        }
        Loan? loan = _jsonData.Loans?.FirstOrDefault(l => l.BookItemId == book.Id && l.ReturnDate == null);
        if (loan == null)
        {
            Console.WriteLine($"{book.Title} is available for loan.");
        }
        else
        {
            Console.WriteLine($"{book.Title} is on loan to another patron. The return due date is {loan.DueDate}.");
        }
        return ConsoleState.PatronDetails;
    }

    ```

1. Compare o arquivo **Program.cs** existente com as atualizações sugeridas.

    ```csharp

    using Microsoft.Extensions.DependencyInjection;
    using Library.Infrastructure.Data;
    using Library.ApplicationCore;
    using Microsoft.Extensions.Configuration;
    var services = new ServiceCollection();
    var configuration = new ConfigurationBuilder()
        .SetBasePath(Directory.GetCurrentDirectory())
        .AddJsonFile("appSettings.json")
        .Build();
    services.AddSingleton<IConfiguration>(configuration);
    services.AddScoped<IPatronRepository, JsonPatronRepository>();
    services.AddScoped<ILoanRepository, JsonLoanRepository>();
    services.AddScoped<ILoanService, LoanService>();
    services.AddScoped<IPatronService, PatronService>();
    services.AddSingleton<JsonData>();
    services.AddSingleton<ConsoleApp>();
    var servicesProvider = services.BuildServiceProvider();
    var consoleApp = servicesProvider.GetRequiredService<ConsoleApp>();
    consoleApp.Run().Wait();

    ```

    Nenhuma atualização será necessária se o arquivo Program.cs já incluir o código que manda o sistema de injeção de dependência do ASP.NET Core criar uma única instância da classe JsonData e usar essa mesma instância sempre que um JsonData for solicitado.

1. Selecione o método **SearchBooks**.

1. Abra o modo de exibição de Chat e, em seguida, insira o seguinte prompt:

    ```plaintext
    Explain the LINQ queries and the evaluation of the book's availability status.
    ```

1. Reserve um minuto para rever as explicações fornecidas pelo GitHub Copilot.

    Para a consulta que verifica se o livro está emprestado, você deve ver uma descrição semelhante à seguinte explicação:

    ```markdown
    **Search for the Loan Status of the Book**
    ```

    ```csharp

    Loan? loan = _jsonData.Loans?.FirstOrDefault(l => l.BookItemId == book.Id && l.ReturnDate == null);

    ```

    ```markdown
    - _jsonData.Loans: Accesses the list of loans from the JsonData class.

    - ?.: The null-conditional operator ensures that if _jsonData.Loans is null, the entire expression will return null without throwing a NullReferenceException.

    - FirstOrDefault: A LINQ method that returns the first element in the collection that matches the specified condition, or null if no such element is found.

    - Lambda Expression: l => l.BookItemId == book.Id && l.ReturnDate == null

        - l.BookItemId == book.Id: Checks if the BookItemId of the loan matches the Id of the book being searched.

        - l.ReturnDate == null: Checks if the loan's ReturnDate is null, indicating that the book is currently on loan and has not been returned.

    - Result: If a matching loan is found, it is assigned to the loan variable. If no matching loan is found, loan is null.

    **Evaluation of the Book's Availability Status**

    After executing the LINQ queries, the method evaluates the availability status of the book:

      - If loan is null, the book has been returned. The method prints that the book is available for loan.
      - If loan is not null, the book is currently on loan (no return date). The method prints that the book is on loan and provides the date when the book should be returned.

    ```

1. Verifique a lógica implementada pela consulta **Verificar se o Livro está Emprestado**.

    Operador Condicional Nulo: o operador "?."  é chamado de operador condicional nulo. Isso garante que, se _jsonData.Loans for nulo, toda a expressão será avaliada como nula sem lançar uma NullReferenceException.

    Expressão lambda: a expressão lambda "l => l.BookItemId == book.Id && l.ReturnDate == null" define a condição para o método FirstOrDefault. Ele verifica cada objeto de empréstimo "l" para ver se seu BookItemId corresponde ao Id do objeto de livro e se seu ReturnDate é nulo.

    Este código tenta encontrar o primeiro empréstimo na coleção _jsonData.Loans onde o BookItemId corresponde ao Id do livro fornecido e o ReturnDate é nulo. Se nenhum empréstimo for encontrado ou se "_jsonData.Loans" for nulo, o empréstimo será definido como nulo.

    > [!NOTE]
    > A maioria das bibliotecas modernas tem várias cópias do mesmo livro. Esse código pressupõe que haja apenas uma cópia de cada livro. Se a biblioteca tiver várias cópias do mesmo livro, o código precisará ser atualizado para lidar com vários empréstimos para o mesmo livro. Para os fins desse treinamento, estamos pressupondo que exista apenas uma cópia de cada livro e que a lógica fornecida seja suficiente.

1. Salve seus arquivos de atualizações.

1. Crie a solução para garantir que não haja nenhum erro.

    Você verá mensagens de **aviso**, mas não deve haver nenhum erro.

    Para criar a solução no modo de exibição Gerenciador de Soluções, clique com o botão direito do mouse em **AccelerateDevGitHubCopilot** e, a seguir, selecione **Compilar**.

#### Resumo — exercício 5

Você usou o GitHub Copilot para ajudar a implementar um novo recurso para o aplicativo de biblioteca. Você criou uma nova ramificação no repositório e então usou o GitHub Copilot para gerar sugestões de código que ajudaram a implementar o novo recurso com mais rapidez e precisão. Você adicionou uma nova ação SearchBooks ao CommonActions, atualizou os métodos WriteInputOptions e ReadInputOptions no ConsoleApp.cs e criou um novo método SearchBooks para determinar o status de disponibilidade de um livro.

### Exercício 6: Mescle suas alterações na ramificação principal do repositório

Você criou um novo recurso que permite que um bibliotecário determine o status de disponibilidade de um livro. Agora você precisa verificar se o recurso funciona conforme o esperado e mesclar suas alterações na ramificação principal do repositório.

Durante este exercício, você concluirá as seguintes tarefas:

- Certificar-se de que o novo recurso funcione conforme o esperado
- Sincronizar suas alterações com o repositório remoto
- Criar um pull request para mesclar suas alterações na ramificação principal do repositório

#### Tarefa 1: Verificar se seu novo recurso funciona conforme o esperado

Como você não tem testes automatizados, um teste manual pode ser usado para verificar se o novo recurso funciona conforme o esperado. O uso de uma fonte de dados que possa ser verificada é importante. Nesse caso, use os arquivos Books.json e Loans.json para verificar se o novo recurso informa o status de disponibilidade de um livro corretamente.

Use as seguintes etapas para concluir esta seção do exercício:

1. Abra a exibição do Gerenciador de Soluções.

1. Para executar o aplicativo, clique com o botão direito do mouse em **Library.Console**, selecione **Depurar** e, em seguida, selecione **Iniciar Nova Instância**.

1. Quando solicitado a obter um nome de leitor, digite **Um** e, em seguida, pressione Enter.

    Você deverá ver uma lista de leitores que correspondam à consulta da pesquisa.

1. No prompt "Opções de Entrada", digite **2** e, a seguir, pressione Enter.

    Inserir **2** selecionará o segundo leitor da lista.

    Você deverá ver o nome do leitor e o status de filiação seguidos dos detalhes do empréstimo do livro.

1. No prompt "Opções de Entrada", digite **b** e, a seguir, pressione Enter.

    Inserir **b** seleciona a opção de pesquisar o status de disponibilidade de um livro.

    Você deverá ver um prompt para inserir um título de livro.

1. Digite **Livro 1** e pressione Enter.

    Nos dados originais que você baixou, o **Livro 1** está atualmente emprestado ao **Leitor 49** e, portanto, não deve estar disponível.

1. Certifique-se de que o aplicativo esteja mostrando uma mensagem indicando que o livro está emprestado para outro leitor.

    Talvez seja necessário rolar para cima para ver a mensagem.

1. Certifique-se de que o **Livro 9** foi devolvido pelo **Leitor 1**.

    No exercício anterior, durante um teste do aplicativo Biblioteca, você fez com que o **Leitor 1** devolvesse o **Livro 9**. Se o aplicativo mostrar que o **Livro 9** não foi devolvido pelo **Leitor 1**, use as opções de entrada para selecionar e devolver o **Livro 9** antes de prosseguir.

    > [!NOTE]
    > O arquivo Library.Console.csproj garante que os arquivos de dados JSON sejam copiados para o diretório de saída quando o aplicativo for criado. No entanto, executar as operações Limpar ou Reconstruir irá, essencialmente, redefinir os dados. Operações de compilação repetidas não redefinem os dados no diretório de saída ("/bin/Debug/net8.0/").

1. No prompt "Opções de Entrada", digite **b** e, a seguir, pressione Enter.

1. Digite **Livro 9** e pressione Enter.

1. Certifique-se de que o aplicativo mostre uma mensagem indicando que o livro está disponível para empréstimo.

1. No prompt "Opções de Entrada", digite **q** e, a seguir, pressione Enter.

1. Interrompa a sessão de depuração.

1. Abra o arquivo **Loans.json**.

    O arquivo Loans.json é usado para rastrear o status do empréstimo de cada livro. Você pode usar o arquivo Loans.json para verificar se o status de disponibilidade do Livro Um e do Livro Nove está correto.

    O arquivo Loans.json atualizado deve estar localizado na pasta "Library.Console\bin\Debug\net8.0\Json" ou na pasta "Library.Console\Json".

    - Se você estiver usando o depurador do Visual Studio Code para executar o aplicativo, o arquivo Loans.json atualizado deverá estar localizado na pasta "Library.Console\bin\Debug\net8.0\Json".

    - Se você estiver usando um comando "dotnet run" da pasta "AccelerateDevGitHubCopilot\src\Library.Console" para executar o aplicativo, o arquivo Loans.json atualizado deverá estar localizado na pasta "Library.Console\Json".

1. Verifique se o ID do empréstimo 37 e o ID do empréstimo 46 são ambos para o Livro Um ("BookItemId": 1).

    - O ID do empréstimo 37 deve ter um valor ReturnDate (2024-01-17)
    - O ID do empréstimo 46 não deve ter um valor ReturnDate. O valor ReturnDate deve ser nulo.

    O valor ReturnDate é usado para determinar se o livro está atualmente emprestado. Se o valor ReturnDate for nulo, o livro será considerado emprestado.

1. Verifique se o ID do empréstimo 22 é para o Livro Nove ("BookItemId": 9) e se o valor ReturnDate está definido para a data de hoje.

    Se você estiver executando no depurador e limpar a solução depois de fazer alterações no arquivo Loans.json, essas alterações serão perdidas. Depois de limpar a solução, o arquivo Loans.json será redefinido para os dados originais na próxima vez que você executar o aplicativo. Você pode atualizar manualmente o arquivo Loans.json para testar o status de disponibilidade do Livro Um e do Livro Nove.

#### Tarefa 2: Sincronizar suas alterações com o repositório remoto

Você pode usar a exibição Controle de Código-Fonte no Visual Studio Code para confirmar suas alterações no repositório local. Depois de confirmar suas alterações, você pode sincronizá-las com o repositório remoto.

Use as seguintes etapas para concluir esta seção do exercício:

1. Selecione o modo de exibição Controle do Código-Fonte.

1. Certifique-se de que os arquivos CommonActions.cs, ConsoleApp.cs e JsonData.cs estejam listados em **Alterações**.

    Se o GitHub Copilot usou consultas LINQ para determinar o status de disponibilidade de um livro diretamente no método SearchBooks, você pode não ver JsonData.cs listado em **Alterações**.

1. Use o GitHub Copilot para gerar uma mensagem para o **Commit**.

1. Para preparar e fazer o commit de suas alterações, selecione **Commit** e, a seguir, selecione **Sim**.

1. Faça a sincronização (ou Efetue Push) das alterações para o repositório remoto.

    Se solicitado, use sua conta do GitHub para autenticar e autorizar a sincronização.

#### Tarefa 3: Criar um pull request para mesclar suas alterações na ramificação principal do repositório

Você pode usar um pull request para sugerir alterações no branch principal do repositório. Depois de criar um pull request, você pode revisar as alterações, confirmar se as verificações foram aprovadas e, então, mesclar as alterações na ramificação principal. O GitHub Copilot pode ajudar você a gerar um resumo do pull request para ajudar os revisores a entender suas alterações.

Use as seguintes etapas para concluir esta seção do exercício:

1. Abra seu repositório do GitHub no seu navegador da web.

1. Abra a guia **Solicitações de pull**.

1. Selecione **Nova solicitação de pull**.

1. Em **Comparar alterações**, certifique-se de que a **base** esteja configurada para o branch **principal**.

1. Certifique-se de que **comparar** esteja configurado para o branch **disponibilidade de livros**.

    Após você configurar os branches, uma comparação das alterações entre o branch **principal** e o branch **disponibilidade de livros** será exibida. Você deverá ver as alterações feitas nos arquivos CommonActions.cs, ConsoleApp.cs e JsonDaa.cs.

1. Selecione **Criar solicitação de pull**.

1. Insira um título para o pull request.

    Membros de uma empresa com uma assinatura do GitHub Copilot Enterprise podem usar o GitHub Copilot para gerar uma descrição resumida para um pull request. O resumo detalhado ajuda os revisores a entender suas alterações.

1. Use o GitHub Copilot para gerar um resumo de um pull request.

    Para gerar o resumo, selecione o botão Ações do Copilot e, em seguida, selecione **Resumo**.

    Você pode usar a guia Visualizar para examinar o resumo do pull request gerado pelo GitHub Copilot.

1. Certifique-se de que o título e a descrição reflitam as atualizações do seu código e, a seguir, selecione **Criar uma solicitação de pull**.

1. Aguarde a conclusão das verificações e, a seguir, certifique-se de que todas as verificações tenham sido aprovadas e de que não haja nenhum conflito com o branch base.

    Pode levar um minuto para que as verificações sejam concluídas. Você precisa resolver todos os problemas identificados antes de mesclar as alterações no branch principal.

1. Para mesclar suas alterações no branch principal, selecione **Mesclar solicitação de pull** e, a seguir, selecione **Confirmar mesclagem**.

    Observe que você pode excluir a ramificação book-availability após mesclar as alterações.

1. Abra o Visual Studio Code.

1. Alterne para o branch **principal** do repositório.

1. **Efetue pull** das alterações a partir do repositório remoto.

    Se solicitado, use sua conta do GitHub para autenticar e autorizar o pull.

1. Certifique-se de que as alterações que você fez no branch **disponibilidade de livros** agora estejam no branch **principal**.

    As alterações feitas nos arquivos CommonActions.cs e ConsoleApp.cs devem estar presentes na ramificação principal.

#### Resumo — exercício 6

Neste exercício, você testou o código e, em seguida, mesclou suas alterações na ramificação principal do repositório. Você confirmou suas alterações no repositório local, sincronizou-as com o repositório remoto e então criou um pull request para mesclar suas alterações na ramificação principal do repositório. Você usou o GitHub Copilot para gerar um resumo do pull request para ajudar os revisores a entender suas alterações.

## Parte 3: Desenvolver testes de unidade usando ferramentas do GitHub Copilot

### Antes de começar

#### Visão geral do projeto

Seu colega criou um projeto de teste chamado UnitTests. Os testes de unidade existentes abrangem parcialmente as classes de serviço no projeto Library.ApplicationCore. O projeto Library.ApplicationCore contém a lógica de negócios para um sistema de gerenciamento de biblioteca. O projeto UnitTests usa a estrutura xUnit para escrever e executar testes de unidade. O projeto também usa a biblioteca NSubstitute para criar objetos fictícios para teste.

Você precisa estender o projeto UnitTests para cobrir as classes de acesso a dados no projeto Library.Infrastructure.

#### Cenário do laboratório (parte 3)

O GitHub Copilot pode ajudar você a escrever testes de unidade para seu código. Há várias maneiras de usar o GitHub Copilot para gerar testes de unidade:

- **Gerar casos de teste**: Você pode usar o GitHub Copilot para gerar casos de teste para seu código. O Copilot pode sugerir casos de teste com base no código que você escreveu. Em seguida, você pode usar esses casos de teste para criar testes de unidade para seu código.
- **Gerar métodos de teste**: O Copilot também pode gerar métodos de teste para seu código. Você pode usar esses métodos de teste para criar testes de unidade para seu código.
- **Gerar asserções de teste**: O Copilot pode sugerir asserções que você pode usar em seus testes de unidade. Essas asserções podem ajudar você a verificar o comportamento do código.
- **Gerar simulações de teste**: O Copilot pode gerar objetos de simulação que você pode usar em seus testes de unidade. Esses objetos de simulação podem ajudar você a isolar o código que você está testando de suas dependências.
- **Gerar dados de teste**: O Copilot pode gerar dados de teste que você pode usar em seus testes de unidade. Esses dados de teste podem ajudar você a testar seu código com entradas diferentes.
- **Gerar código de configuração do teste**: O Copilot pode gerar o código de configuração para seus testes de unidade. Esse código pode ajudar você a configurar o ambiente de teste antes de executar seus testes.
- **Gerar código de desinstalação do teste**: O Copilot pode gerar o código de desinstalação de seus testes de unidade. Esse código pode ajudar você a limpar o ambiente de teste depois de executar seus testes.

Na parte 3 deste laboratório, você desenvolverá testes de unidade para o projeto Library.Infrastructure.

A parte inclui o seguinte exercício:

- Use o GitHub Copilot para avaliar e estender o projeto UnitTests.

### Exercício 7: Usar o GitHub Copilot para avaliar e estender o projeto UnitTests

Neste exercício, você vai usar o GitHub Copilot para realizar as seguintes tarefas:

1. Use o GitHub Copilot para avaliar o projeto UnitTests existente.

1. Estender o projeto UnitTests para começar a testar as classes de acesso aos dados.

#### Tarefa 1: Usar o GitHub Copilot para avaliar o projeto UnitTests existente

O projeto UnitTests atualmente implementa a seguinte estrutura de pastas:

- UnitTests\
  - ApplicationCore\
    - LoanService\
      - ExtendLoan.cs
      - ReturnLoan.cs
    - PatronService\
      - RenewMembership.cs
  - LoanFactory.cs
  - PatronFactory.cs

Essa estrutura espelha e dá suporte à parte de Serviços do projeto ApplicationCore.

- ApplicationCore\
  - Services\
    - LoanService.cs: contém os métodos ExtendLoan e ReturnLoan.
    - PatronService.cs: Contém o método RenewMembership.

Avaliar os testes de unidade existentes ajudará você a desenvolver testes de unidade para as classes de acesso a dados no projeto Library.Infrastructure.

Use as seguintes etapas para concluir esta seção do exercício:

1. Feche todos os arquivos abertos no editor.

1. Abra o modo de exibição de chat.

1. Adicione os seguintes arquivos ao contexto do Chat: **LoanFactory.cs**, **PatronFactory.cs**, **ExtendLoan.cs**, **ReturnLoan.cs**, **RenewMembership.cs**, **LoanService.cs**, **PatronService.cs**.

    Os arquivos estão localizados nas pastas "tests/UnitTests", "tests/UnitTests/ApplicationCore/LoanService", "tests/UnitTests/ApplicationCore/PatronService" e "src/Library.ApplicationCore/Services".

1. Digite a seguinte solicitação:

    ```plaintext
    @workspace Explain the approach to unit testing that's been implemented in this workspace.
    ```

    Essa solicitação pede ao GitHub Copilot que explique a abordagem para o teste de unidade no contexto do workspace. Vários arquivos são incluídos na solicitação para fornecer contexto para a resposta.

1. Reserve um minuto para examinar a resposta do GitHub Copilot.

    Você deve ver uma explicação semelhante à seguinte descrição:

    - Dependências simuladas: Os testes usam o NSubstitute para criar implementações simuladas de interfaces.
    - Organização de teste: Os testes são organizados em arquivos separados com base nos métodos que estão sendo testados. Por exemplo, os métodos ExtendLoan e ReturnLoan são testados em arquivos separados na pasta LoanService.
    - Asserções: As asserções são usadas para verificar o resultado esperado de cada teste.
    - Cenários de teste: Os testes abrangem vários cenários para cada método, como o retorno de status diferentes com base na entrada.
    - Isolamento: Cada teste é isolado de outros para evitar efeitos colaterais.
    - Métodos de fábrica: Os métodos de fábrica são usados para criar dados de teste consistentemente.

1. Digite a seguinte solicitação:

    ```plaintext
    @workspace What are the benefits of this approach to unit testing?
    ```

1. Reserve um minuto para examinar a resposta do GitHub Copilot.

    Você deverá ver uma explicação que identifica uma lista de benefícios semelhante à seguinte lista:

    - Isolamento de dependências: Usar simulações isola a unidade de trabalho de suas dependências.
    - Repetibilidade e consistência: Os métodos de fábrica fornecem uma maneira consistente de criar dados de teste.
    - Legibilidade e manutenção: Os métodos de teste descritivos e a disposição clara das etapas de teste melhoram a legibilidade dos testes.
    - Cobertura abrangente: Testar vários cenários garante que o código seja robusto e lide com diferentes casos de borda.
    - Separação de preocupações: A separação da criação de dados de teste da lógica de teste em si mantém os testes limpos e focados no comportamento que está sendo testado.
    - Comentários imediatos: A execução de testes de unidade fornece comentários imediatos sobre a correção do código.

1. Adicione os seguintes arquivos ao contexto do Chat: **ExtendLoan.cs**, **ReturnLoan.cs**, **RenewMembership.cs**, **LoanFactory.cs**, **PatronFactory.cs**, **LoanService.cs**, **PatronService.cs**.

1. Digite a seguinte solicitação:

    ```plaintext
    @workspace How can I extend the `UnitTests` project to begin testing methods in the `Library.Infrastructure` project? Provide a process overview.
    ```

    Este prompt solicita que o GitHub Copilot forneça uma visão geral do processo para estender o projeto UnitTests para começar a testar métodos no projeto Library.Infrastructure. Vários arquivos são incluídos na solicitação para fornecer contexto para a resposta.

1. Reserve um minuto para examinar a resposta do GitHub Copilot.

    Você deve ver uma explicação semelhante à seguinte descrição:

    ```markdown
    1. Add Project Reference:

      - Open the UnitTests.csproj file located at tests/UnitTests/UnitTests.csproj.
      - Add a reference to the Library.Infrastructure project.

    2. Identify methods to test:

      - Identify the methods in the Library.Infrastructure project that need to be tested. For example, if you want to test the LoanService class, identify the methods in the LoanService class that need to be tested.

    3. Create Test Classes:

      - Create new test classes in the tests/UnitTests directory to test the methods in the Library.Infrastructure project. For example, if you want to test LoanService, create a file named LoanServiceTests.cs.

    4. Write Unit Tests:

      - In the newly created test classes, write unit tests for the methods in the Library.Infrastructure project. Use the xUnit framework for writing tests and NSubstitute for mocking dependencies.

    5. Run Tests:

      - Use Visual Studio Code's integrated terminal or the Test Explorer to run the tests.
      - Ensure that the tests are discovered and executed correctly.
    ```

#### Tarefa 2: Estender o projeto UnitTests para começar a testar classes de acesso a dados

Nesta seção do exercício, você usará o GitHub Copilot para ajudá-lo a criar testes de unidade para o projeto Library.Infrastructure.

O projeto Library.Infrastructure contém classes de acesso a dados que interagem com o sistema de arquivos para carregar e salvar dados. O projeto inclui as seguintes classes:

- JsonData: Uma classe que carrega e salva dados JSON.
- JsonLoanRepository: Uma classe que implementa a interface ILoanRepository e usa a classe JsonData para carregar e salvar dados de empréstimo.
- JsonPatronRepository: Uma classe que implementa a interface IPatronRepository e usa a classe JsonData para carregar e salvar dados de leitores.

Você começará escrevendo testes de unidade para a classe JsonLoanRepository.

Use as seguintes etapas para concluir esta seção do exercício:

1. Adicione o seguinte arquivo de projeto ao contexto de chat: **UnitTests.csproj**.

1. Insira a seguinte solicitação no modo de exibição de chat:

    ```plaintext
    @workspace Explain how to add a reference to the Library.Infrastructure project inside `UnitTests.csproj`.
    ```

    Este prompt pede ao GitHub Copilot para explicar como adicionar uma referência ao projeto Library.Infrastructure dentro do arquivo UnitTests.csproj.

1. Use a resposta do GitHub Copilot para atualizar o arquivo UnitTests.csproj.

    O arquivo UnitTests.csproj atualizado deve ser semelhante ao seguinte código XML:

    ```xml

    <Project Sdk="Microsoft.NET.Sdk">
      <PropertyGroup>
        <TargetFramework>net8.0</TargetFramework>
        <ImplicitUsings>enable</ImplicitUsings>
        <Nullable>enable</Nullable>
        <IsPackable>false</IsPackable>
        <IsTestProject>true</IsTestProject>
      </PropertyGroup>
      <ItemGroup>
        <PackageReference Include="coverlet.collector" Version="6.0.0" />
        <PackageReference Include="Microsoft.NET.Test.Sdk" Version="17.8.0" />
        <PackageReference Include="NSubstitute" Version="5.1.0" />
        <PackageReference Include="xunit" Version="2.5.3" />
        <PackageReference Include="xunit.runner.visualstudio" Version="2.5.3" />
      </ItemGroup>
      <ItemGroup>
        <Using Include="Xunit" />
      </ItemGroup>
      <ItemGroup>
        <ProjectReference Include="..\..\src\Library.ApplicationCore\Library.ApplicationCore.csproj" />
        <ProjectReference Include="..\..\src\Library.Infrastructure\Library.Infrastructure.csproj" />
      </ItemGroup>
    </Project>

    ```

1. Abra o arquivo **JsonLoanRepository.cs**.

    JsonLoanRepository.cs está localizado na pasta "src/Library.Infrastructure/Data/".

1. Reserve um minuto para revisar o arquivo **JsonLoanRepository.cs**.

    ```csharp

    using Library.ApplicationCore;
    using Library.ApplicationCore.Entities;
    namespace Library.Infrastructure.Data;
    public class JsonLoanRepository : ILoanRepository
    {
        private readonly JsonData _jsonData;
        public JsonLoanRepository(JsonData jsonData)
        {
            _jsonData = jsonData;
        }
        public async Task<Loan?> GetLoan(int id)
        {
            await _jsonData.EnsureDataLoaded();
    
            foreach (Loan loan in _jsonData.Loans!)
            {
                if (loan.Id == id)
                {
                    Loan populated = _jsonData.GetPopulatedLoan(loan);
                    return populated;
                }
            }
            return null;
        }
        public async Task UpdateLoan(Loan loan)
        {
            Loan? existingLoan = null;
            foreach (Loan l in _jsonData.Loans!)
            {
                if (l.Id == loan.Id)
                {
                    existingLoan = l;
                    break;
                }
            }
            if (existingLoan != null)
            {
                existingLoan.BookItemId = loan.BookItemId;
                existingLoan.PatronId = loan.PatronId;
                existingLoan.LoanDate = loan.LoanDate;
                existingLoan.DueDate = loan.DueDate;
                existingLoan.ReturnDate = loan.ReturnDate;
                await _jsonData.SaveLoans(_jsonData.Loans!);
                await _jsonData.LoadData();
            }
        }
    }

    ```

1. Observe os seguintes detalhes sobre a classe **JsonLoanRepository**:

    - A classe JsonLoanRepository contém dois métodos: GetLoan e UpdateLoan.
    - A classe JsonLoanRepository usa um objeto JsonData para carregar e salvar dados de empréstimo.

    Você começará escrevendo testes de unidade para o método GetLoan.

1. Crie a seguinte estrutura de pastas no projeto **UnitTests**.

    - Infrastructure\
        - JsonLoanRepository\

    Esta estrutura de pastas reflete a abordagem usada para os testes de unidade de Library.ApplicationCore.

1. Crie um arquivo de classe chamado **GetLoan** na pasta JsonLoanRepository.

1. Reserve um minuto para considerar os requisitos do construtor de campo e classe para os testes de unidade GetLoan.

    O método JsonLoanRepository.GetLoan recebe um parâmetro de ID de empréstimo quando é chamado. O método usa "_jsonData.EnsureDataLoaded" para obter os dados JSON mais recentes e "_jsonData.Loans" para procurar um empréstimo correspondente. Se o método encontrar um ID de empréstimo correspondente, ele retornará um objeto de empréstimo preenchido (preenchido). Se o método não conseguir encontrar um ID de empréstimo correspondente, ele retornará nulo.

    Para os testes de unidade GetLoan:

    - Você pode usar um objeto de repositório de empréstimo simulado ("_mockLoanRepository") para ajudar a testar o caso em que um ID correspondente é encontrado. Carregue a simulação com a ID que você deseja encontrar. A classe ReturnLoanTest demonstra como simular a interface ILoanRepository e instanciar um objeto de repositório de empréstimo simulado.

    - Você pode usar um objeto de repositório de empréstimo não simulado ("_jsonLoanRepository") para testar o caso em que nenhum ID correspondente é encontrado. Basta especificar uma ID de empréstimo que você sabe que não está no arquivo (qualquer coisa acima de 100 deve funcionar).

    - Você precisará de um objeto JsonData para criar um objeto JsonLoanRepository não simulado. Como o projeto UnitTests não tem acesso ao objeto JsonData criado pelo projeto ConsoleApp, você precisará criar um usando a interface IConfiguration.

1. Adicione os seguintes arquivos ao contexto do Chat: **JsonLoanRepository.cs**, **ReturnLoan.cs**, **LoanService.cs**, **LoanFactory.cs**, **JsonData.cs**.

1. Digite a seguinte solicitação:

    ```plaintext
    @workspace Create fields and a class constructor for the `GetLoan.cs` file. The class will be used to create unit tests for the GetLoan method in the `JsonLoanRepository.cs` file. Create the following private readonly fields: `_mockLoanRepository`, `_jsonLoanRepository`, `_configuration`, and `_jsonData`. Instantiate the fields in the `GetLoanTest` constructor. Use `ConfigurationBuilder` to create a `_configuration` object that can be used to instantiate the JsonData object.
    ```

    Essa solicitação pede ao GitHub Copilot que sugira campos e um construtor de classe.

1. Reserve um minuto para examinar a resposta do GitHub Copilot.

    Você deve ver uma sugestão de código semelhante ao seguinte snippet de código:

    ```csharp

    using NSubstitute;
    using Library.ApplicationCore;
    using Library.ApplicationCore.Entities;
    using Library.ApplicationCore.Interfaces;
    using Library.Infrastructure.Data;
    using Microsoft.Extensions.Configuration;
    namespace UnitTests.Infrastructure.JsonLoanRepository;
    public class GetLoanTest
    {
        private readonly ILoanRepository _mockLoanRepository;
        private readonly JsonLoanRepository _jsonLoanRepository;
        private readonly IConfiguration _configuration;
        private readonly JsonData _jsonData;
        public GetLoanTest()
        {
            _mockLoanRepository = Substitute.For<ILoanRepository>();
            _configuration = new ConfigurationBuilder()
                .AddJsonFile("appsettings.json")
                .Build();
            _jsonData = new JsonData(_configuration);
            _jsonLoanRepository = new JsonLoanRepository(_jsonData);
        }
        // Add test methods here
    }

    ```

1. Use a sugestão de código fornecida pelo GitHub Copilot para atualizar **GetLoan.cs**.

1. Observe os seguintes problemas:

    - Há um conflito entre o namespace e o uso de JsonLoanRepository no código. Você deve atualizar o namespace em GetLoans.cs para seguir o padrão usado nos arquivos ReturnLoan.cs e RenewMembership.cs.

    - Se ILoanRepository não for reconhecido no seu código, talvez seja necessário adicionar uma diretiva using para Library.ApplicationCore no topo do arquivo.

    - Se o objeto _configuration não for instanciado corretamente, talvez seja necessário atualizar a linha de código que contém o ConfigurationBuilder. Você pode simplificar o código usando "_configuration = new ConfigurationBuilder().Build();".

    - Se "using Library.ApplicationCore.Interfaces" for sugerido pelo GitHub Copilot, você pode excluí-lo do topo do arquivo.

1. Atualize o arquivo **GetLoan.cs** para corresponder ao seguinte trecho de código:

    ```csharp

    using NSubstitute;
    using Library.ApplicationCore;
    using Library.ApplicationCore.Entities;
    using Library.Infrastructure.Data;
    using Microsoft.Extensions.Configuration;
    namespace UnitTests.Infrastructure.JsonLoanRepositoryTests;
    public class GetLoanTest
    {
        private readonly ILoanRepository _mockLoanRepository;
        private readonly JsonLoanRepository _jsonLoanRepository;
        private readonly IConfiguration _configuration;
        private readonly JsonData _jsonData;
        public GetLoanTest()
        {
            _mockLoanRepository = Substitute.For<ILoanRepository>();
            _configuration = new ConfigurationBuilder().Build();
            _jsonData = new JsonData(_configuration);
            _jsonLoanRepository = new JsonLoanRepository(_jsonData);
        }
    }

    ```

    As atualizações de código abordam os problemas identificados na etapa anterior. A compilação do projeto resolverá os problemas identificados no editor.

1. Adicione os seguintes arquivos ao contexto do Chat: **JsonLoanRepository.cs**, **ReturnLoan.cs**, **LoanService.cs**, **LoanFactory.cs**, **JsonData.cs**, **Loans.json**.

1. Selecione o conteúdo do arquivo GetLoan.cs e insira o seguinte prompt na visualização de chat:

    ```plaintext
    @workspace Update the selection to include a unit test for the `JsonLoanRepository.GetLoan` method. The unit test should test the case where a loan ID is found in the data. Use `_mockLoanRepository` to arrange the expected return loan. Use `_jsonLoanRepository` to return an actual loan. Asserts should verify that the return loan ID matches the expected loan ID. Use a loan ID that exists in the `Loans.json` file.
    ```

    Este prompt pede ao GitHub Copilot para sugerir um teste de unidade para o método JsonLoanRepository.GetLoan. O teste de unidade deve testar o caso em que uma ID de empréstimo é encontrada nos dados. O teste deve usar "_mockLoanRepository" para organizar o empréstimo de retorno esperado, "_jsonLoanRepository" para retornar um empréstimo real e afirma verificar se o ID do empréstimo de retorno corresponde ao ID do empréstimo esperado. O ID do empréstimo deve existir no arquivo Loans.json.

1. Reserve um minuto para examinar a resposta do GitHub Copilot.

    Você deve ver uma sugestão de código semelhante ao seguinte snippet de código:

    ```csharp

    using NSubstitute;
    using Library.ApplicationCore;
    using Library.ApplicationCore.Entities;
    using Library.Infrastructure.Data;
    using Microsoft.Extensions.Configuration;
    using Xunit;
    namespace UnitTests.Infrastructure.JsonLoanRepositoryTests;
    public class GetLoanTest
    {
        private readonly ILoanRepository _mockLoanRepository;
        private readonly JsonLoanRepository _jsonLoanRepository;
        private readonly IConfiguration _configuration;
        private readonly JsonData _jsonData;
        public GetLoanTest()
        {
            _mockLoanRepository = Substitute.For<ILoanRepository>();
            _configuration = new ConfigurationBuilder().Build();
            _jsonData = new JsonData(_configuration);
            _jsonLoanRepository = new JsonLoanRepository(_jsonData);
        }
        [Fact(DisplayName = "JsonLoanRepository.GetLoan: Returns loan when loan ID is found")]
        public async Task GetLoan_ReturnsLoanWhenLoanIdIsFound()
        {
            // Arrange
            var loanId = 1; // Use a loan ID that exists in the Loans.json file
            var expectedLoan = new Loan { Id = loanId, BookItemId = 101, PatronId = 202, LoanDate = DateTime.Now, DueDate = DateTime.Now.AddDays(14) };
            _mockLoanRepository.GetLoan(loanId).Returns(expectedLoan);
            await _jsonData.EnsureDataLoaded(); // Ensure data is loaded
            // Act
            var actualLoan = await _jsonLoanRepository.GetLoan(loanId);
            // Assert
            Assert.NotNull(actualLoan);
            Assert.Equal(expectedLoan.Id, actualLoan?.Id);
        }
    }

    ```

1. Use a sugestão de código fornecida pelo GitHub Copilot para atualizar **GetLoan.cs**.

    O método JsonLoanRepository.GetLoan chama "_jsonData.EnsureDataLoaded" para garantir que os dados JSON sejam carregados. Você pode excluir a linha de código que chama "_jsonData.EnsureDataLoaded" no método de teste, se ela estiver incluída.

    Se a classe Loan não for reconhecida no seu código, certifique-se de ter uma instrução "using Library.ApplicationCore.Entities" no topo do arquivo GetLoan.cs. A classe Loan está localizada no namespace Library.ApplicationCore.Entities.

1. Compile a solução AccelerateDevGitHubCopilot para garantir que não haja erros.

1. Use o recurso de preenchimento automático do GitHub Copilot para criar um teste para o caso em que a ID do empréstimo não for encontrada.

    Crie uma linha em branco após o método GetLoan_ReturnsLoanWhenLoanIdIsFound.

    Aceite as sugestões de preenchimento automático para criar um novo método de teste.

1. Reserve um minuto para examinar a resposta do GitHub Copilot.

    O recurso de preenchimento automático do GitHub Copilot provavelmente simulará um empréstimo esperado, mesmo se não for necessário. Você pode excluir o código que simula um empréstimo esperado, mas precisa de um ID de empréstimo que não exista no arquivo Loans.json.

    Você deve ver uma sugestão de código semelhante a um dos seguintes snippets de código:

    ```csharp

    [Fact(DisplayName = "JsonLoanRepository.GetLoan: Returns null when loan ID is not found")]
    public async Task GetLoan_ReturnsNullWhenLoanIdIsNotFound()
    {
        // Arrange
        var loanId = 999; // Use a loan ID that does not exist in the Loans.json file
        var expectedLoan = new Loan { Id = loanId, BookItemId = 101, PatronId = 202, LoanDate = DateTime.Now, DueDate = DateTime.Now.AddDays(14) };
        _mockLoanRepository.GetLoan(loanId).Returns(expectedLoan);
        // Act
        var actualLoan = await _jsonLoanRepository.GetLoan(loanId);
        // Assert
        Assert.Null(actualLoan);
    }

    ```

1. Aceite a sugestão de preenchimento automático que atribui um valor loanId que não está no conjunto de dados.

    Se nenhuma das sugestões atribuir números loanId que não estejam no conjunto de dados, você pode usar o atalho de teclado **Ctrl+Enter** para listar sugestões adicionais.

1. Observe que os testes de unidade exigem acesso aos arquivos de dados JSON.

    O método JsonLoanRepository.GetLoan usa um objeto JsonData para carregar e salvar dados de empréstimo.

    Os arquivos de dados JSON estão localizados na pasta "Library.Console\Json". Você precisa atualizar o arquivo UnitTests.csproj para incluir esses arquivos no projeto de teste.

1. Adicione o seguinte trecho de XML ao arquivo **UnitTests.csproj** :

    ```xml

    <ItemGroup>
        <None Include="..\..\src\Library.Console\Json\**\*">
            <Link>Json\%(RecursiveDir)%(FileName)%(Extension)</Link>
            <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
        </None>
    </ItemGroup>

    ```

    Isso garante que os arquivos de dados JSON sejam copiados para o diretório de saída quando os testes forem executados.

#### Tarefa 3: Verificar seu trabalho

Há várias maneiras de executar os testes de unidade para a classe JsonLoanRepository. Você pode usar o Gerenciador de Testes do Visual Studio Code, o terminal integrado ou o comando "dotnet test".

Use as seguintes etapas para concluir esta seção do exercício:

1. Verifique se você abriu o arquivo GetLoans.cs no editor.

1. Compile a solução e verifique se não há nenhum erro.

    Clique com o botão direito do mouse em **AccelerateDevGitHubCopilot** e selecione **Compilar**.

1. Observe o "botão de reprodução verde" à esquerda dos métodos de teste.

1. Abra a exibição do Editor de Lista de Testes no Visual Studio Code.

    Para abrir o modo de exibição do Editor de Lista de Testes, selecione o ícone em forma de béquer na barra de atividades do lado esquerdo. O Editor de Lista de Testes é rotulado como "Teste" na interface do usuário.

    O Editor de Lista de Testes é no modo de exibição de árvore para mostrar todos os casos de teste no seu workspace. Você pode executar/depurar seus casos de teste e ver seus resultados de teste usando o Editor de Lista de Testes.

1. Expanda **UnitTests** e os nós subjacentes para localizar **GetLoanTest**.

1. Execute o caso de teste **JsonLoanRepository.GetLoan: Retorna o empréstimo quando a ID do empréstimo é encontrada**.

    > [!NOTE]
    > O GitHub Copilot pode ter nomeado o método de teste de forma diferente. Execute o método de teste que usa uma ID de empréstimo que existe nos dados.

1. Observe os resultados de teste no modo de exibição no Editor de Lista de Testes e no Editor.

    Você deve ver uma marca de seleção verde que indica que o teste foi aprovado.

1. Use o Editor para executar o caso de teste **JsonLoanRepository.GetLoan: Retorna nulo quando a ID do empréstimo não é encontrada**.

1. Observe os resultados de teste no modo de exibição no Editor de Lista de Testes e no Editor.

    Para executar o teste no Editor, selecione o botão de reprodução verde à esquerda do método de teste.

1. Verifique se o teste **JsonLoanRepository.GetLoan: Retorna nulo quando a ID do empréstimo não é encontrada** é aprovado.

    Você deverá ver uma marca de seleção verde à esquerda de ambos os testes.

#### Resumo — exercício 7

Neste exercício, você usou o GitHub Copilot para avaliar o projeto UnitTests existente e estendê-lo para começar a testar as classes de acesso a dados no projeto Library.Infrastructure. Você adicionou uma referência ao projeto Library.Infrastructure no arquivo UnitTests.csproj e criou testes de unidade para a classe JsonLoanRepository. Você usou o GitHub Copilot para ajudar a escrever os testes de unidade para o método GetLoan na classe JsonLoanRepository. Você executou os testes de unidade usando o Gerenciador de Testes do Visual Studio Code e verificou se os testes foram aprovados.

## Parte 4: Refatorar e melhorar seções de código usando ferramentas do GitHub Copilot

### Antes de começar

#### Visão geral do projeto

Você e seu colega de trabalho concluíram a fase inicial de desenvolvimento do projeto e agora estão investigando maneiras de refatorar e melhorar sua base de código.

A refatoração de código é um processo que reestrutura o código existente sem alterar seu comportamento externo. A refatoração geralmente é usada para melhorar um aspecto específico do código. O GitHub Copilot pode ajudar você a refatorar seu código sugerindo alterações que melhoram a qualidade, a confiabilidade, o desempenho e a segurança do código.

#### Cenário de laboratório (parte 4)

Na parte 4 deste laboratório, você usará o GitHub Copilot para refatorar as seguintes seções de código:

- Você refatora a classe EnumHelper para usar dicionários em vez de reflexão. O uso de dicionários melhora o desempenho reduzindo a sobrecarga de reflexão. Eliminar a reflexão também melhora a legibilidade, a manutenção e a segurança do código.

- Você refatora os métodos de acesso a dados para usar a LINQ (Consulta Integrada à Linguagem) em vez de loops foreach. O uso da LINQ fornece uma maneira mais concisa e legível de consultar coleções, bancos de dados e documentos XML. O uso da LINQ pode melhorar a legibilidade, manutenção e desempenho do código.

A parte inclui os seguintes exercícios:

- Usar o GitHub Copilot para refatorar a classe EnumHelper.
- Use o GitHub Copilot para melhorar as classes de acesso a dados com o LINQ.

### Exercício 8: Usar o GitHub Copilot para refatorar a classe EnumHelper

Reflexão é um recurso poderoso que permite inspecionar e manipular objetos em runtime. No entanto, a reflexão pode ser lenta e há possíveis riscos de segurança associados à reflexão que devem ser considerados.

A classe EnumHelper existente usa reflexão para recuperar o atributo de descrição de um valor de enumeração. Você pode refatorar a classe EnumHelper para usar dicionários em vez de reflexão. O uso de dicionários pode melhorar o desempenho e eliminar qualquer preocupação de segurança associada ao uso de reflexão.

Neste exercício, você usará o GitHub Copilot para refatorar a classe EnumHelper.

Use as seguintes etapas para concluir este exercício:

1. Use a exibição do Gerenciador de Soluções para abrir o arquivo EnumHelper.cs.

    EnumHelper.cs está localizado na pasta "src/Library.ApplicationCore/Enums".

    ```csharp

    using System.ComponentModel;
    using System.Reflection;
    namespace Library.ApplicationCore.Enums;
    public static class EnumHelper
    {
        public static string GetDescription(Enum value)
        {
            if (value == null)
                return string.Empty;
            FieldInfo fieldInfo = value.GetType().GetField(value.ToString())!;
            DescriptionAttribute[] attributes =
                (DescriptionAttribute[])fieldInfo.GetCustomAttributes(typeof(DescriptionAttribute), false);
            if (attributes != null && attributes.Length > 0)
            {
                return attributes[0].Description;
            }
            else
            {
                return value.ToString();
            }
        }
    }

    ```

1. Abra a visualização de chat e adicione os seguintes arquivos ao contexto de chat: **EnumHelper.cs**, **LoanExtensionStatus.cs**, **LoanReturnStatus.cs**, **MembershipRenewalStatus.cs**.

1. Digite a seguinte solicitação:

    ```plaintext
    @workspace I want to refactor the `EnumHelper` class using dictionaries rather than reflection to get enum description attributes. I want a separate dictionary for each enum. The enum values are in the `LoanExtensionStatus.cs`, `LoanReturnStatus.cs`, and `MembershipRenewalStatus.cs` files. Explain how to update the EnumHelper class to use dictionaries and provide the updated code.
    ```

    Esta solicitação pede que o GitHub Copilot forneça uma explicação de como atualizar a classe EnumHelper para usar dicionários em vez de reflexão. Ele também solicita o código atualizado que usa dicionários para cada valor de enumeração.

1. Reserve um minuto para examinar a explicação fornecida pelo GitHub Copilot.

    A explicação deve ser semelhante à seguinte descrição:

    ```markdown
    To refactor the EnumHelper class to use dictionaries for each enum, you need to create a dictionary for each enum type that maps the enum values to their descriptions. This will eliminate the need for reflection at runtime.

    Here's how you can update the EnumHelper class:

    1. Create dictionaries for each enum type.
    2. Populate these dictionaries with the enum values and their corresponding descriptions.
    3. Update the GetDescription method to use these dictionaries.

    Below is the updated code for the EnumHelper class:

    ```

    ```csharp

    using System.ComponentModel;
    using System.Collections.Generic;
    namespace Library.ApplicationCore.Enums
    {
        public static class EnumHelper
        {
            private static readonly Dictionary<MembershipRenewalStatus, string> MembershipRenewalStatusDescriptions = new()
            {
                { MembershipRenewalStatus.Success, "Membership renewal was successful." },
                { MembershipRenewalStatus.PatronNotFound, "Patron not found." },
                { MembershipRenewalStatus.TooEarlyToRenew, "It is too early to renew the membership." },
                { MembershipRenewalStatus.LoanNotReturned, "Cannot renew membership due to an outstanding loan." },
                { MembershipRenewalStatus.Error, "Cannot renew membership due to an error." }
            };
            private static readonly Dictionary<LoanReturnStatus, string> LoanReturnStatusDescriptions = new()
            {
                { LoanReturnStatus.Success, "Book was successfully returned." },
                { LoanReturnStatus.LoanNotFound, "Loan not found." },
                { LoanReturnStatus.AlreadyReturned, "Cannot return book as the book is already returned." },
                { LoanReturnStatus.Error, "Cannot return book due to an error." }
            };
            private static readonly Dictionary<LoanExtensionStatus, string> LoanExtensionStatusDescriptions = new()
            {
                { LoanExtensionStatus.Success, "Book loan extension was successful." },
                { LoanExtensionStatus.LoanNotFound, "Loan not found." },
                { LoanExtensionStatus.LoanExpired, "Cannot extend book loan as it already has expired. Return the book instead." },
                { LoanExtensionStatus.MembershipExpired, "Cannot extend book loan due to expired patron's membership." },
                { LoanExtensionStatus.LoanReturned, "Cannot extend book loan as the book is already returned." },
                { LoanExtensionStatus.Error, "Cannot extend book loan due to an error." }
            };
            public static string GetDescription(Enum value)
            {
                if (value == null)
                    return string.Empty;
                return value switch
                {
                    MembershipRenewalStatus status => MembershipRenewalStatusDescriptions[status],
                    LoanReturnStatus status => LoanReturnStatusDescriptions[status],
                    LoanExtensionStatus status => LoanExtensionStatusDescriptions[status],
                    _ => value.ToString()
                };
            }
        }
    }

    ```

    ```markdown

    This refactored EnumHelper class uses dictionaries to store the descriptions for each enum type. The GetDescription method now uses pattern matching to determine the type of the enum and retrieves the description from the appropriate dictionary. This approach avoids the use of reflection and improves performance.

    ```

    > [!NOTE]
    > Se o GitHub Copilot não preencher os dicionários com as descrições corretas, verifique se a extensão do GitHub Copilot não está solicitando uma reinicialização. Se estiver, reinicie a extensão e tente a solicitação novamente.

1. Use a classe EnumHelper sugerida pelo GitHub Copilot para atualizar seu arquivo EnumHelper.cs.

1. Certifique-se de que sua classe EnumHelper atualizada esteja usando os valores de enumeração dos arquivos LoanExtensionStatus.cs, LoanReturnStatus.cs e MembershipRenewalStatus.cs.

    Abra cada um dos arquivos de enumeração e verifique se os valores de enumeração nos dicionários estão corretos. Se houver discrepâncias, o GitHub Copilot atualizará os dicionários para cada enumeração individualmente. Por exemplo, você pode usar o seguinte prompt para a enumeração LoanExtensionStatus:

    ```plaintext
    @workspace Use the description values in LoanExtensionStatus.cs to update the LoanExtensionStatus dictionary in the EnumHelper class. Provide the updated code for the LoanExtensionStatus dictionary in the EnumHelper class.
    ```

    Se necessário, use a mesma abordagem para as enumerações LoanReturnStatus e MembershipRenewalStatus.

1. Reserve um minuto para revisar o método **GetDescription**.

    ```csharp

    public static string GetDescription(Enum value)
    {
        if (value == null)
            return string.Empty;
        return value switch
        {
            MembershipRenewalStatus status => MembershipRenewalStatusDescriptions[status],
            LoanReturnStatus status => LoanReturnStatusDescriptions[status],
            LoanExtensionStatus status => LoanExtensionStatusDescriptions[status],
            _ => value.ToString()
        };
    }

    ```

    Esse código usa os padrões correspondentes para determinar o tipo da enumeração e recuperar a descrição do dicionário apropriado. A instrução switch verifica o tipo do valor da enumeração e retorna a descrição correspondente do dicionário. Se o valor da enumeração não for encontrado no dicionário, o método retornará o valor de enumeração como uma cadeia de caracteres.

    Se você pedir ao GitHub Copilot para refatorar esse código e eliminar as expressões lambda, fica mais fácil ler:

    ```csharp

    public static string GetDescription(Enum value)
    {
        if (value == null)
            return string.Empty;
        switch (value)
        {
            case MembershipRenewalStatus status:
                return MembershipRenewalStatusDescriptions[status];
            case LoanReturnStatus status:
                return LoanReturnStatusDescriptions[status];
            case LoanExtensionStatus status:
                return LoanExtensionStatusDescriptions[status];
            default:
                return value.ToString();
        }
    }

    ```

1. Salve suas alterações no arquivo EnumHelper.cs.

1. Crie sua solução para garantir que não haja erros.

    Você verá avisos. Você pode ignorá-los por enquanto.

#### Resumo — exercício 8

Neste exercício, você usou o GitHub Copilot para refatorar a classe EnumHelper para usar dicionários em vez de reflexão. O uso de dicionários melhora o desempenho reduzindo a sobrecarga de reflexão. Eliminar a reflexão também melhora a legibilidade, a manutenção e a segurança do código.

### Exercício 9: Usar o GitHub Copilot para melhorar as classes de acesso a dados com LINQ

LINQ (Consulta Integrada à Linguagem) é um recurso avançado em C# que permite consultar coleções, bancos de dados e documentos XML de maneira uniforme. A LINQ fornece uma maneira mais concisa e legível de consultar dados em comparação com loops foreach tradicionais.

Esse exercício inclui as seguintes tarefas:

- Refatorar os métodos em JsonData.cs para usar LINQ.
- Refatorar os métodos em JsonLoanRepository.cs para usar LINQ.
- Refatorar os métodos em JsonPatronRepository.cs para usar LINQ.

#### Tarefa 1: Refatorar os métodos em JsonData.cs para usar LINQ

A classe JsonData inclui os seguintes métodos de acesso aos dados: GetPopulatedPatron, GetPopulatedLoan, GetPopulatedBookItem e GetPopulatedBook. Esses métodos usam loops foreach para iterar em coleções e preencher objetos. Você pode refatorar esses métodos para usar LINQ para melhorar a legibilidade e a manutenção do código.

Use as seguintes etapas para concluir esta seção do exercício:

1. Abra o arquivo JsonData.cs.

1. Selecione o método **GetPopulatedPatron**.

    O método GetPopulatedPatron foi projetado para criar um objeto Patron totalmente preenchido. Ele copia as propriedades básicas do Patron e preenche sua coleção Loans com objetos Loan detalhados.

    ```csharp

    public Patron GetPopulatedPatron(Patron p)
    {
        Patron populated = new Patron
        {
            Id = p.Id,
            Name = p.Name,
            ImageName = p.ImageName,
            MembershipStart = p.MembershipStart,
            MembershipEnd = p.MembershipEnd,
            Loans = new List<Loan>()
        };
        foreach (Loan loan in Loans!)
        {
            if (loan.PatronId == p.Id)
            {
                populated.Loans.Add(GetPopulatedLoan(loan));
            }
        }
        return populated;
    }

    ```

1. Abra um chat embutido e insira uma solicitação que refatore o método usando LINQ.

    ```plaintext
    #selection refactor selection to `return new Patron` using LINQ
    ```

1. Reserve um minuto para examinar a atualização sugerida.

    A atualização sugerida será semelhante ao código a seguir:

    ```csharp

    public Patron GetPopulatedPatron(Patron p)
    {
        return new Patron
        {
            Id = p.Id,
            Name = p.Name,
            ImageName = p.ImageName,
            MembershipStart = p.MembershipStart,
            MembershipEnd = p.MembershipEnd,
            Loans = Loans!
                .Where(loan => loan.PatronId == p.Id)
                .Select(GetPopulatedLoan)
                .ToList()
        };
    }

    ```

    Primeiro, uma consulta LINQ é usada para substituir o loop "foreach (Loan loan in Loans!)". Com o código LINQ em vigor, você pode usar um inicializador de objeto para atribuir propriedades de objeto ao novo objeto Patron. Isso alivia a necessidade de uma instância preenchida separada do objeto Patron. No geral, o código atualizado é mais curto e mais legível.

    O código usa o Patron de entrada "p" para atribuir algumas propriedades básicas ao novo objeto Patron. Em seguida, ele preenche a coleção Loans com empréstimos associados ao Patron de entrada, transformando cada empréstimo usando o método GetPopulatedLoan.

    Você pode dividir a linha de código LINQ que preenche a coleção Loans:

    - `Loans!`: A expressão "Loans!" acessa a coleção Loans. O operador "!" é um operador com suporte a nulos, indicando que o desenvolvedor está confiante de que Loans não é nulo. Você deve garantir que Loans seja inicializado corretamente antes de chamar o método GetPopulatedPatron.
    - `.Where(loan => loan.PatronId == p.Id)`: este código filtra os empréstimos para incluir apenas aqueles que pertencem ao Patron de entrada "p".
    - `.Select(GetPopulatedLoan)`: este código transforma cada empréstimo filtrado usando o método GetPopulatedLoan.
    - `.ToList()`: converte o resultado em uma lista de objetos Loan.

1. Para aceitar a atualização sugerida, selecione **Aceitar**.

    Agora que você viu como refatorar o método GetPopulatedPatron, você pode refatorar os métodos GetPopulatedLoan, GetPopulatedBookItem e GetPopulatedBook para usar LINQ também.

1. Refatore os métodos **GetPopulatedLoan**, **GetPopulatedBookItem** e **GetPopulatedBook** usando a mesma abordagem.

    Por exemplo, use as seguintes solicitações para refatorar os três métodos:

    Para o método **GetPopulatedLoan**:

    ```plaintext
    #selection refactor selection to `return new Loan` using LINQ. Use `GetPopulatedBookItem` for the `BookItem` property. Use `Single` for BookItem and Patron properties.
    ```

    Para o método **GetPopulatedBookItem**:

    ```plaintext
    #selection refactor selection to `return new BookItem` using LINQ. Use `GetPopulatedBook` and `Single` for the `BookItem` property.
    ```

    Para o método **GetPopulatedBook**:

    ```plaintext
    #selection refactor selection to `return new Book` using LINQ. Use `Where` and `Select` for `Author` property. Use `First` author.
    ```

1. Depois de aceitar as atualizações sugeridas, reserve um minuto para examinar as alterações de código.

    Seu código atualizado deverá ser semelhante ao seguinte código:

    ```csharp

    public Loan GetPopulatedLoan(Loan l)
    {
        return new Loan
        {
            Id = l.Id,
            BookItemId = l.BookItemId,
            PatronId = l.PatronId,
            LoanDate = l.LoanDate,
            DueDate = l.DueDate,
            ReturnDate = l.ReturnDate,
            BookItem = GetPopulatedBookItem(BookItems!.Single(bi => bi.Id == l.BookItemId)),
            Patron = Patrons!.Single(p => p.Id == l.PatronId)
        };
    }
    public BookItem GetPopulatedBookItem(BookItem bi)
    {
        return new BookItem
        {
            Id = bi.Id,
            BookId = bi.BookId,
            AcquisitionDate = bi.AcquisitionDate,
            Condition = bi.Condition,
            Book = GetPopulatedBook(Books!.Single(b => b.Id == bi.BookId))
        };
    }
    public Book GetPopulatedBook(Book b)
    {
        return new Book
        {
            Id = b.Id,
            Title = b.Title,
            AuthorId = b.AuthorId,
            Genre = b.Genre,
            ISBN = b.ISBN,
            ImageName = b.ImageName,
            Author = Authors!.Where(a => a.Id == b.AuthorId).Select(a => new Author {
                Id = a.Id,
                Name = a.Name
            }).First()
        };
    }

    ```

1. Use a ação inteligente **Explicar** para ver uma explicação das consultas LINQ.

    A ação inteligente **Explicar** fornece uma explicação detalhada das consultas LINQ usadas no código.

    Por exemplo, você pode usar a ação inteligente **Explain** no método GetPopulatedBook para ver uma explicação da consulta LINQ usada para preencher a propriedade Author do objeto Book.

    ```csharp

    Author = Authors!.Where(a => a.Id == b.AuthorId).Select(a => new Author {
        Id = a.Id,
        Name = a.Name
    }).First()

    ```

    A ação inteligente **Explain** fornece uma explicação detalhada da consulta LINQ usada para preencher a propriedade Author do objeto Book.

    Por exemplo, a explicação pode ser semelhante a:

    ```plaintext
    The active selection is a C# code snippet that assigns a value to the Author property. This value is derived from a collection of Author objects named Authors. The code uses LINQ (Language Integrated Query) to filter and transform the data within this collection.
    
    First, the Authors! expression uses the null-forgiving operator (!) to indicate that Authors is not null, even if the compiler might think otherwise. This is a way to suppress nullable warnings. The Where method is then called on the Authors collection to filter the elements. The lambda expression a => a.Id == b.AuthorId is used to find all Author objects where the Id matches the AuthorId property of another object b.
    
    After filtering, the Select method is used to project each filtered Author object into a new Author object. This is done by creating a new instance of the Author class and copying the Id and Name properties from the original Author object.
    
    Finally, the First method is called to retrieve the first element from the resulting sequence. This means that the Author property will be assigned the first Author object that matches the filter criteria and has been projected into a new Author instance.
    
    This approach ensures that the Author property is set to a new Author object with the same Id and Name as the first matching Author in the Authors collection.
    ```

1. Salve suas alterações no arquivo JsonData.cs.

1. Crie sua solução para garantir que não haja erros.

    Você verá avisos. Você pode ignorá-los por enquanto.

#### Tarefa 2: Refatorar os métodos em JsonLoanRepository.cs para usar LINQ

A classe JsonLoanRepository inclui os métodos de acesso a dados GetLoan e UpdateLoan. Você refatora esses dois métodos, substituindo loops foreach por LINQ para melhorar a legibilidade e a manutenção do código.

Use as seguintes etapas para concluir esta seção do exercício:

1. Abra o arquivo **JsonLoanRepository.cs**.

1. Selecione o método **GetLoan**.

    O método GetLoan foi projetado para recuperar um empréstimo pelo seu ID.

    ```csharp

    public async Task<Loan?> GetLoan(int id)
    {
        await _jsonData.EnsureDataLoaded();
        foreach (Loan loan in _jsonData.Loans!)
        {
            if (loan.Id == id)
            {
                Loan populated = _jsonData.GetPopulatedLoan(loan);
                return populated;
            }
        }
        return null;
    }

    ```

1. Abra o chat embutido e insira uma solicitação que refatore o método usando LINQ.

    Por exemplo, insira a solicitação a seguir:

    ```plaintext
    #selection refactor selection using LINQ with `_jsonData.Loans!. Use `Where`, `Select` and `GetPopulatedLoan` to return `FirstOrDefault`.
    ```

1. Reserve um minuto para examinar a atualização sugerida.

    A atualização sugerida será semelhante ao código a seguir:

    ```csharp

    public async Task<Loan?> GetLoan(int id)
    {
        await _jsonData.EnsureDataLoaded();
        Loan? loan = _jsonData.Loans!
            .Where(l => l.Id == id)
            .Select(l => _jsonData.GetPopulatedLoan(l))
            .FirstOrDefault();
        return loan;
    }

    ```

    O código atualizado usa LINQ para filtrar a coleção de empréstimos para incluir apenas o empréstimo com a ID especificada. Observe que o empréstimo deve ser declarado como anulável (`Loan? loan`). Em seguida, ele transforma o empréstimo usando o método GetPopulatedLoan e retorna o primeiro resultado. Se nenhum empréstimo correspondente for encontrado, FirstOrDefault retornará nulo. O método então retorna este objeto de empréstimo, que pode ser nulo se não existir nenhum empréstimo com o "id" especificado. Essa abordagem garante que o empréstimo retornado seja totalmente preenchido com todos os dados relacionados necessários, fornecendo uma visão abrangente do registro de empréstimo.

    Esse código pode ser simplificado ainda mais:

    ```csharp

    public async Task<Loan?> GetLoan(int id)
    {
        await _jsonData.EnsureDataLoaded();
        return _jsonData.Loans!
            .Where(l => l.Id == id)
            .Select(l => _jsonData.GetPopulatedLoan(l))
            .FirstOrDefault();
    }

    ```

1. Para aceitar o método GetLoan atualizado, selecione **Aceitar**.

1. Selecione o método **UpdateLoan**.

    ```csharp

    public async Task UpdateLoan(Loan loan)
    {
        Loan? existingLoan = null;
        foreach (Loan l in _jsonData.Loans!)
        {
            if (l.Id == loan.Id)
            {
                existingLoan = l;
                break;
            }
        }
        if (existingLoan != null)
        {
            existingLoan.BookItemId = loan.BookItemId;
            existingLoan.PatronId = loan.PatronId;
            existingLoan.LoanDate = loan.LoanDate;
            existingLoan.DueDate = loan.DueDate;
            existingLoan.ReturnDate = loan.ReturnDate;
            await _jsonData.SaveLoans(_jsonData.Loans!);
            await _jsonData.LoadData();
        }
    }

    ```

1. Abra o chat embutido e insira uma solicitação que refatore o método usando LINQ.

    Por exemplo, insira a solicitação a seguir:

    ```plaintext
    #selection refactor selection using LINQ find an existing loan `_jsonData.Loans!. Replace existing loan.
    ```

1. Reserve um minuto para examinar a atualização sugerida.

    A atualização sugerida será semelhante ao código a seguir:

    ```csharp

    public async Task UpdateLoan(Loan loan)
    {
        Loan? existingLoan = _jsonData.Loans!.FirstOrDefault(l => l.Id == loan.Id);
        if (existingLoan != null)
        {
            existingLoan.BookItemId = loan.BookItemId;
            existingLoan.PatronId = loan.PatronId;
            existingLoan.LoanDate = loan.LoanDate;
            existingLoan.DueDate = loan.DueDate;
            existingLoan.ReturnDate = loan.ReturnDate;
            await _jsonData.SaveLoans(_jsonData.Loans!);
            await _jsonData.LoadData();
        }
    }

    ```

    O código atualizado usa LINQ para encontrar o empréstimo existente na coleção de empréstimos. Em seguida, atualiza o empréstimo existente com os novos dados de empréstimo. Em seguida, o método salva a coleção de empréstimos atualizada e recarrega os dados. Essa abordagem garante que os dados do empréstimo sejam atualizados corretamente e que as alterações sejam mantidas no armazenamento de dados.

    Você também pode adicionar o código para garantir que os dados sejam carregados antes que o método seja executado:

    ```csharp

    public async Task UpdateLoan(Loan loan)
    {
        await _jsonData.EnsureDataLoaded();
        Loan? existingLoan = _jsonData.Loans!.FirstOrDefault(l => l.Id == loan.Id);
        if (existingLoan != null)
        {
            existingLoan.BookItemId = loan.BookItemId;
            existingLoan.PatronId = loan.PatronId;
            existingLoan.LoanDate = loan.LoanDate;
            existingLoan.DueDate = loan.DueDate;
            existingLoan.ReturnDate = loan.ReturnDate;
            await _jsonData.SaveLoans(_jsonData.Loans!);
            await _jsonData.LoadData();
        }
    }

    ```

1. Para aceitar o método UpdateLoan atualizado, selecione **Aceitar**.

1. Salve suas alterações no arquivo JsonLoanRepository.cs.

1. Crie sua solução para garantir que não haja erros.

    Você verá avisos. Você pode ignorá-los por enquanto.

#### Tarefa 3: Refatorar os métodos em JsonPatronRepository para usar LINQ

A classe JsonPatronRepository inclui os métodos SearchPatrons, GetPatron e UpdatePatron e é uma ótima candidata para otimização. Você refatora esses métodos, substituindo loops foreach por LINQ para melhorar a legibilidade e a manutenção do código.

Use as seguintes etapas para concluir esta seção do exercício:

1. Abra o arquivo **JsonPatronRepository.cs**.

1. Selecione o método **SearchPatrons**.

    O método SearchPatrons foi projetado para pesquisar clientes por nome.

    ```csharp

    public async Task<List<Patron>> SearchPatrons(string searchInput)
    {
        await _jsonData.EnsureDataLoaded();
        List<Patron> searchResults = new List<Patron>();
        foreach (Patron patron in _jsonData.Patrons)
        {
            if (patron.Name.Contains(searchInput))
            {
                searchResults.Add(patron);
            }
        }
        searchResults.Sort((p1, p2) => String.Compare(p1.Name, p2.Name));
        searchResults = _jsonData.GetPopulatedPatrons(searchResults);
        return searchResults;
    }

    ```

1. Abra o chat embutido e insira uma solicitação que refatore o método usando LINQ.

    Por exemplo, insira a solicitação a seguir:

    ```plaintext
    #selection refactor selection using LINQ with `_jsonData.Patrons!. Replace the loop with `Where`, `OrderBy`, and `GetPopulatedPatrons`.
    ```

1. Reserve um minuto para examinar a atualização sugerida.

    A atualização sugerida será semelhante ao código a seguir:

    ```csharp

    public async Task<List<Patron>> SearchPatrons(string searchInput)
    {
        await _jsonData.EnsureDataLoaded();
        List<Patron> searchResults = _jsonData.Patrons!
            .Where(patron => patron.Name.Contains(searchInput))
            .OrderBy(patron => patron.Name)
            .ToList();
        searchResults = _jsonData.GetPopulatedPatrons(searchResults);
        return searchResults;
    }

    ```

1. Para aceitar o método SearchPatrons atualizado, selecione **Aceitar**.

1. Selecione o método **GetPatron**.

    O método GetPatron foi projetado para retornar o cliente correspondente ao "id" especificado.

    ```csharp

    public async Task<Patron?> GetPatron(int id)
    {
        await _jsonData.EnsureDataLoaded();
        foreach (Patron patron in _jsonData.Patrons!)
        {
            if (patron.Id == id)
            {
                Patron populated = _jsonData.GetPopulatedPatron(patron);
                return populated;
            }
        }
        return null;
    }

    ```

1. Abra o chat embutido e insira uma solicitação que refatore o método usando LINQ.

    Por exemplo, insira a solicitação a seguir:

    ```plaintext
    #selection refactor selection using LINQ with `_jsonData.Patrons!. Use `Where`, `Select` and `GetPopulatedPatron` to return `FirstOrDefault`
    ```

1. Reserve um minuto para examinar a atualização sugerida.

    A atualização sugerida será semelhante ao código a seguir:

    ```csharp

    public async Task<Patron?> GetPatron(int id)
    {
        await _jsonData.EnsureDataLoaded();
        var patron = _jsonData.Patrons!
            .Where(p => p.Id == id)
            .Select(p => _jsonData.GetPopulatedPatron(p))
            .FirstOrDefault();
        return patron;
    }

    ```

    Esse código pode ser simplificado ainda mais:

    ```C#

    public async Task<Patron?> GetPatron(int id)
    {
        await _jsonData.EnsureDataLoaded();
        return _jsonData.Patrons!
            .Where(p => p.Id == id)
            .Select(p => _jsonData.GetPopulatedPatron(p))
            .FirstOrDefault();
    }

    ```

1. Para aceitar o método GetPatron atualizado, selecione **Aceitar**.

1. Selecione o método **UpdatePatron**.

    O método UpdatePatron foi projetado para atualizar o cliente com o "id" especificado.

    ```csharp

    public async Task UpdatePatron(Patron patron)
    {
        await _jsonData.EnsureDataLoaded();
        var patrons = _jsonData.Patrons!;
        Patron existingPatron = null;
        foreach (var p in patrons)
        {
            if (p.Id == patron.Id)
            {
                existingPatron = p;
                break;
            }
        }
        if (existingPatron != null)
        {
            existingPatron.Name = patron.Name;
            existingPatron.ImageName = patron.ImageName;
            existingPatron.MembershipStart = patron.MembershipStart;
            existingPatron.MembershipEnd = patron.MembershipEnd;
            existingPatron.Loans = patron.Loans;
            await _jsonData.SavePatrons(patrons);
            await _jsonData.LoadData();
        }
    }

    ```

1. Abra o chat embutido e insira uma solicitação que refatore o método usando LINQ.

    Por exemplo, insira a solicitação a seguir:

    ```plaintext
    #selection refactor selection using LINQ to find `patron` in `_jsonData.Patrons!. Replace existing patron with `patron`.
    ```

1. Reserve um minuto para examinar a atualização sugerida.

    A atualização sugerida será semelhante ao código a seguir:

    ```csharp

    public async Task UpdatePatron(Patron patron)
    {
        await _jsonData.EnsureDataLoaded();
        var patrons = _jsonData.Patrons!;
        var existingPatron = patrons.FirstOrDefault(p => p.Id == patron.Id);
        if (existingPatron != null)
        {
            existingPatron.Name = patron.Name;
            existingPatron.ImageName = patron.ImageName;
            existingPatron.MembershipStart = patron.MembershipStart;
            existingPatron.MembershipEnd = patron.MembershipEnd;
            existingPatron.Loans = patron.Loans;
            await _jsonData.SavePatrons(patrons);
            await _jsonData.LoadData();
        }
    }

    ```

1. Para aceitar o método UpdatePatron atualizado, selecione **Aceitar**.

#### Tarefa 4: Verifique seu trabalho

Use as etapas a seguir para verificar seu trabalho:

1. Para limpar a solução, clique com o botão direito do mouse em **AccelerateAppDevGitHubCopilot** e selecione **Limpar**.

    Essa ação remove quaisquer artefatos de build do build anterior. A limpeza da solução redefinirá efetivamente os arquivos de dados JSON para seus valores originais durante (no diretório de saída).

1. Compile o aplicativo e verifique se não há erros.

1. Execute o aplicativo.

    Você pode executar o aplicativo na exibição do Gerenciador de Soluções clicando com o botão direito do mouse no projeto **Library.Console**, selecionando **Depuração** e, em seguida, selecionando **Iniciar nova instância**.

1. Quando solicitado a obter um nome de leitor, digite **One** e pressione Enter.

1. Na solicitação "Leitores Correspondentes", digite **2** e pressione Enter.

1. Na solicitação "Usuários Correspondentes", digite **1** e pressione Enter.

1. Na solicitação "Opções de Entrada", digite **r** e pressione Enter.

1. Verifique se a mensagem  **"O livro foi devolvido com sucesso."** será exibida.

1. Para iniciar uma nova pesquisa, digite **s** e pressione Enter.

1. Quando solicitado a obter um nome de leitor, digite **One** e pressione Enter.

1. Na solicitação "Leitores Correspondentes", digite **2** e pressione Enter.

1. Verifique se o primeiro empréstimo de livro está marcado como **Returned: True**.

1. Na solicitação "Opções de Entrada", digite **q** e, a seguir, pressione Enter.

1. Pare o aplicativo.

#### Resumo — exercício 9

Neste exercício, você refatorou os métodos de acesso a dados nas classes JsonData, JsonLoanRepository e JsonPatronRepository para usar LINQ. Essas alterações melhoram a legibilidade, a manutenção e o desempenho do código.
