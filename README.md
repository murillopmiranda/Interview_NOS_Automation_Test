# NOS Automation Testing

    Bem vindo ao projeto "NOS Automation Testing". Neste projeto pude realizar o Planejamento e Execução dos Testes para a os endpoints do site https://gorest.co.in/.

    A seguir estão os tópicos solicitados no documento "NOS Automation Testing.pdf".

## 1. Escolher uma ferramenta para automatizar testes à seguinte Api REST, explica o porquê dessa escolha. https://gorest.co.in/

    Para este projeto, escolhi o Postman para a organização do Plano de Testes e para a Automação. Na minha opinião, o Postman oferece uma interface amigável, facilitando a construção e teste de requisições HTTP. Com o Postman posso  criar, salvar e organizar casos de teste rapidamente.

    O Postman permite a automação de testes de API, e eu posso criar coleções de requisições que podem ser executadas em sequência ou em paralelo.


## 2. Explica os use case de teste

O Plano de Teste com os Casos de Teste deste projeto foi criado uma coleção chamada "NOS Automation Testing" na ferramenta Postman.

Dentro da coleção criei duas pastas:
    - Manual Script (Functional Test)
    - Automation Script (Integration Test)

    Na Pasta "Manual Script (Functional Test)" foram criados os casos de testes dos endpoints /users, /posts, /comments e /todos.
    Os casos de testes contidos nesta pasta são para tipos de teste Funcionais e de forma manual pois para cada endpoint os valores devem ser alterados manualmente.
        Casos de Teste:
            - Users/List users: 3 Casos de teste
            - Users/Create users: 15 Casos de teste
            - Users/Get user detail: 2 Casos de teste
            - Users/Update users: 1 Caso de teste
            - Users/Delete users: 2 Casos de teste
            - Posts/List posts: 1 Caso de teste
            - Posts/Create posts: 1 Casos de teste
            - Posts/Get post detail: 2 Casos de teste
            - Posts/Update post: 2 Caso de teste
            - Posts/Delete post: 2 Casos de teste
            - Comments/List comments: 1 Caso de teste
            - Comments/Create comments: 2 Casos de teste
            - Comments/Get comment detail: 2 Casos de teste
            - Comments/Update comment: 2 Caso de teste
            - Comments/Delete comment: 2 Casos de teste
            - ToDo/List ToDo: 1 Caso de teste
            - ToDo/Create ToDo: 2 Casos de teste
            - ToDo/Get ToDo detail: 3 Casos de teste
            - ToDo/Update ToDo: 2 Caso de teste
            - ToDo/Delete ToDo: 2 Casos de teste

            OBS: Não foram criados todos os casos de teste que eu gostaria de sugerir. Entendo que os casos de testes criados no "Users/Create users:" podem estender para os demais creates com suas respectivas regras de parametros.


    Na Pasta "Automation Script (Integration Test)" foram criados os casos de testes dos endpoints /users, /posts, /comments e /todos.
    Os casos de testes contidos nesta pasta são para tipos de teste de integração e de forma automática. Neste script criei variáveis de alguns parametros de responses para que fossem utilizados em outros endpoins.
        Casos de Teste: 20 Casos de teste.    



Passos para executar os testes siga os seguintes passos:

    - Baixe e instale o Postman;
    - Abra o Postman para exportar a coleção;
    - Com o Postman, importe a coleção "" dentro da pasta \NOS Automation Testing\Postman;
    - Com o Postman, clique no menu de três pontos da pasta "Automation Script (Integration Test)" e clique na opção "Run Collection";
    - Para executar todos os casos de teste automaticamente, selecione todos os casos de teste, selecione "Run manually" na aba "Functional" e clique no botão laranja "Run NOS Automation Testing".



## 3. Em automação, com resposta desta API gorest.co.in/public/v2/todos

    A solicitação de automação solicitada no documento do Teste foram criados dentro da aba Scripts nos casos de teste TC13 da pasta "Automation Script (Integration Test)" da collection do Postman.
    
    O código deste script foi adicionado ao seguinte endereço do Github: https://github.com/murillopmiranda/Interview_NOS_Automation_Test

## 4. DevOps, CI/CD.
    
    #4.1. Explica e justifica uma implementação de testes de carga a esta API;

        De acordo com as informações contidas no tópico "Rate Limiting Headers" do site site https://gorest.co.in/:

        - X-RateLimit-Limit: Significa que podemos fazer até 90 requisições por minuto.
        - X-RateLimit-Remaining: Indica quantas requisições restam no período atual.

        Para realizar testes de carga em um endpoint que possui os valores a cima eu sugiro simular a carga enquanto respeita as restrições impostas. 
    
        Ferramentas de Teste de Carga:
            Jmeter ou Postman (com Newman): Útil para rodar coleções de teste em paralelo, mas não é a ferramente ideal para testes de carga em larga escala devido a suas limitações da versão Free e Premium.

        Cenários de Teste Sugerido:
            Teste de Carga Máxima
                Objetivo: Testar a performance da API está sendo usada em sua capacidade máxima permitida;
                Configuração: 90 requisições/minuto;
                Duração: 5 a 10 minutos, para observar a estabilidade;

    #4.2. Como implementarias uma solução de Continuous Testing, justifica;

        Para implementar uma solução de CI/CD (Continuos Testing) eu sugiro que adicione o script da coleção do Postman com Newman e o script do Teste de Carga para que possamos garantir que os casos de testes criados anteriormente estejam funcionando e para controle da performance do sistema.  
        
        Para CI/CD Tool, pode ser utilizado GitLab CI, Jenkins, GitHub Actions, Azure DevOps, etc
