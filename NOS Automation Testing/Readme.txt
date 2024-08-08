# NOS Automation Testing

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


    Na Pasta "Automation Script (Integration Test)" foram criados os casos de testes dos endpoints /users, /posts, /comments e /todos.
    Os casos de testes contidos nesta pasta são para tipos de teste de integração e de forma automática. Neste script criei variáveis de alguns parametros de responses para que fossem utilizados em outros endpoins.
    



Passos para executar os testes siga os seguintes passos:

    - Baixe e instale o Postman;
    - Abra o Postman para exportar a coleção;
    - Com o Postman, importe a coleção "" dentro da pasta \NOS Automation Testing\Postman;
    - Com o Postman, clique no menu de três pontos da pasta "Automation Script (Integration Test)" e clique na opção "Run Collection";
    - Para executar todos os casos de teste automaticamente, selecione todos os casos de teste, selecione "Run manually" na aba "Functional" e clique no botão laranja "Run NOS Automation Testing".



## 3. Em automação, com resposta desta API gorest.co.in/public/v2/todos

    A solicitação de automação solicitada no documento do Teste foram criados dentro da aba Scripts nos casos de teste TC13 da pasta "Automation Script (Integration Test)" da collection do Postman.
    
    O código deste script foi adicionado ao seguinte endereço do Github: 

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