# O guia estelar de HTTP

> *Site: [https://app.rocketseat.com.br/node/guia-estelar-de-http](https://app.rocketseat.com.br/node/guia-estelar-de-http)*
> 

Aqui é explorado e desmitificado o básico da comunicação HTTP.

# Entendendo

- **O que é HTTP?**
    
    Hypertext Transfer Protocol, ou seja, é um conjunto de regras que possibilita a transferência de hypertextos. Atualmente esta transferência permite a troca de mensagens e dados na internet. Essas mensagens são basicamente arquivos (.html, .css, .js, .jpeg, etc), ou seja, para cada um desses recursos é realizado uma chamada.
    
- **O que é Hypertexto?**
    
    São textos que possuem recursos a mais, sejam eles, imagens, links, audios, etc.
    
- **Como funciona a comunicação HTTP?**
    
    Basicamente há dois agentes, o cliente e o servidor. Geralmente o cliente é o browser e o servidor pode ser qualquer computador que disponibiliza um serviço na web. Sendo assim, a requisição realizada para um servidor é conhecida como **Request** e a resposta do servidor para o cliente é conhecida como **Response**. E tanto a Request quanto a Response são tratadas como mensagens.
    
    ![O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled.png](O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled.png)
    
    As mensagens, como citado anteriormente podem ser Request e Response.
    
    - **Request** (ou pedido):
        - **Methods** (ou método)
            - define o tipo do pedido, ou seja, qual ação é solicitada ao servidor
            - exemplo, **GET**, que serve para pegar algum recurso do servidor, ou o **POST**, que serve para criar algum recurso no servidor (seja ele, um registro ou qualquer outra coisa).
            
            <aside>
            👉 **Exemplo de utilização de methods
            GET**: [`https://google.com/`](https://google.com/) que retorna uma página.
            **POST**: [`http://localhost:3000/posts?q=oracle`](http://localhost:3000/posts?q=oracle) que cria algum registro no servidor.
            
            </aside>
            
        - **Header** (ou cabeçalho)
            - é um campo informativo que possui propriedades e valores. Basicamente carregam informações sobre o cliente que está enviando a mensagem.
            - por exemplo, possui os campos Content-Type (tipo de conteúdo solicitado), User-Agent (o agente que está enviando a mensagem) e Request URL (a URL solicitada).
        - **Body** (ou corpo)
            - possui o conteúdo explícito da mensagem, seja ele um .html, .json, etc.
        
        Um exemplo de request message.
        
        ```jsx
        GET/index.html HTTP/1.1 // tipo da solicitação; o recurso buscado; versão do HTTP
        User-agent: Mozilla/4.0 // cabeçalho que possui informações do cliente
        Accept:text/html // solicitação explícita (que neste caso é um texto HTML)
        ```
        
    - **Response** (ou resposta):
        - **Status Code** (ou código de estado)
            - é a resposta do servidor sobre o estado do pedido/resposta.
            - por exemplo, o status code pode ser, 200 (simboliza que o pedido está certo), 301 (simboliza que o pedido foi redirecionado), 404 (simboliza que o recurso não foi encontrado), 500 (simboliza que o servidor e o recurso foram encontrados, mas há algum erro interno no servivor).
            
            <aside>
            ⚠️ Para mais informações sobre status code acesse o site do [HTTP Status](https://httpstatuses.com/).
            
            </aside>
            
        - **Header** (ou cabeçalho)
            - é um campo informativo que possui propriedades e valores. Basicamente carregam informações sobre o servidor que está enviando a mensagem.
            - por exemplo, possui os campos Content-Type (tipo de conteúdo solicitado), User-Agent (o agente que está enviando a mensagem) e Request URL (a URL solicitada).
        - **Body** (ou corpo)
            - possui o conteúdo explícito da mensagem, seja ele um .html, .json, etc.
        
        Um exemplo de response message.
        
        ```jsx
        HTTP/1.1 200 OK // recurso solicitado; status code do recurso solicitado
        Server: Express // cabeçalho que possui informações sobre o servidor
        Content-Type: text/html // tipo do conteúdo do body
        
        <html> ... </html> // conteúdo do body
        ```
        
    
    <aside>
    ⚠️ É importante destacar que o **Body** é opcional, sendo ele dependente do tipo de mensagem enviada.
    
    </aside>
    
    O recurso na web é visto como o local que receberá o pedido. Para isso, é utilizado uma URL para acessar este recurso.
    
- **O que é DevTools?**
    
    É uma ferramenta que disponibiliza diversos recursos que auxiliam na análise de comunicações entre cliente e servidor, entre outros recursos também.
    
    Normalmente esta ferramenta pode ser acessada através da tecla de atalho **F12** ou 
    
    ![O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Screenshot_from_2021-04-16_07-29-21.jpg](O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Screenshot_from_2021-04-16_07-29-21.jpg)
    
- **Como funciona o DevTools?**
    
    O DevTools disponibiliza diversas ferramentas que estão disponíveis em formato de abas.
    
    - **Network**
        
        Basicamente, esta ferramenta possibilita gravar os recurso visíveis na rede que passam pelo navegador.
        
        ![O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled%201.png](O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled%201.png)
        
        É possível também filtrar as informações desejadas.
        
        ![O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled%202.png](O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled%202.png)
        
        Clicando em algum recurso capturado por esta ferramenta pode-se visualizar suas informações como o Header, Preview e etc, como deonstrado na imagem abaixo.
        
        ![O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled%203.png](O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled%203.png)
        
- **O que é a ferramenta cURL?**
    
    É uma ferramenta de CLI (Command Line Interface) que possibilita utilizar diversos protocolos. Esta ferramenta já vêem instalado por padrão nos sistema Unix.
    
- **Como funciona o cURL?**
    
    Para fazer alguma solitação HTTP simples, podemos seguir a seguinte sintaxe de comando.
    
    ```bash
    curl <url>
    ```
    
    Para visualizar o header adicionamos a flag `-i`, como no exemplo abaixo.
    
    ```bash
    curl -i https://www.google.com
    ```
    
    Caso queira visualizar todos os headers pode-se utilizar a flag `-v` (verbose).
    
    ```bash
    
    ```
    
    Tendo como resposta algo como,
    
    ![Onde o sinal `>` simboliza os heders enviados e o `<` simboliza os headers recebidos. E o sinal `*` simboliza as informações de conexão.](O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled%204.png)
    
    Onde o sinal `>` simboliza os heders enviados e o `<` simboliza os headers recebidos. E o sinal `*` simboliza as informações de conexão.
    

# Conceitos

- **Quais são os conceitos do HTTP?**
    
    Ele é um protocolo construído para ser **simples** o que o torna legível para qualquer pessoa.
    
    Seu funcionamento é baseado em **cliente/servidor**, ou seja, trabalha com requisições e respostas, semelhante a um pedido em uma pizzaria.
    
    Ele também foi arquitetado para ser **stateless**, ou seja, não guarda estado. Para definir melhor está parte, o protocolo HTTP não guarda informações e não relaciona as conexões existentes. A forma que o browser (por exemplo) têm para guardar informações relacionadas ao HTTP é, através de cookies ou storages.
    
    Ele é um protocolo **extensível**, ou seja, conforme a necessidade, podemos passar diversas informações entre cliente-servidor através do cabeçalho.
    
- **O que é cliente?**
    
    O cliente é o User Agent. Pode ser o Browser, cURL, ou qualquer entidade que dá ínicio a comunicação.
    
    <aside>
    ⚠️ É importante destacar aqui, que o conceito de cliente pode ser diferente dependendo da situação. Por exemplo, às vezes é o servidor que dá ínicio a comunicação.
    
    </aside>
    
    Essa comunicação é iniciada através com ações, que no caso são os methods. Os exemplos mais comuns de methods são, GET (pedir), PUT (enviar), DELETE (deletar) e PUT (atualizar).
    
- **O que é servidor?**
    
    Ele se apresenta como uma máquina localizada em qualquer lugar do mundo. Sendo está máquina preparada para receber e processar os dados, e também responder as solicitações.
    
    As respostas geralmente são enviadas através de headers carregando seu status code. E algumas vezes pode-se enviado também o body como resposta.
    
    Podemos ter uma máquina se apresentando como vários servidores, e também há casos onde um serviço é constituído de vários servidores.
    
- **O que é proxy?**
    
    É visto na rede como representante. Este representado é todo e qualquer dispositivo que fica entre o cliente e o servidor na comunicação. Por exemplo, o roteador é um proxy.
    
    Os proxies auxliam no transporte dos dados através das suas diversas funções:
    
    - cache: para facilitar e agilizar a resposta.
    - filtro: através de controle parental, ou seja, filtro explícito de acesso (como sites, por exemplo).
    - load balancing: distribuição de carga, ou seja, gerencia da melhor forma a distruição de pacotes para que estes sejam entregues da melhor forma.
    - autenticação: para identificar a veracidade do tráfego.
    - autorização: para acesso a rede.

# URI

- **Qual o conceito de URI?**
    
    Uniform Resource Indentifier, serve para identificar um recurso na web, seja pelo nome e/ou pela localização.
    
- **O que é recurso?**
    
    É o alvo do pedido, podendo ele ser qualquer coisa identificavél ou entidade. Por exemplo:
    
    - recurso **digital**: como um e-mail, que utiliza o mailto.
    - recurso **abstrato**: como uma sessão ou recurso de autenticação.
    - recurso **físico**: como produtos e usuários.
    
    Ou seja, se pode ser nomeado (URN), indereçado (URL) ou manipular, pode ser um recurso.
    
- **O que é URL?**
    
    Uniform Resource Locator, é baseado no conceito de Locator, ou seja, localizador. Ou seja, localiza recursos através do endereço.
    
    A URL é composta por alguns componentes sendo dois obrigatórios e cinco opcionais.
    
    **Obrigatórios**
    
    1. **protocolo**, por exemplo, http ou https
        
        ![O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled%205.png](O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled%205.png)
        
    2. **domínio**, por exemplo, [google.com](http://google.com), [rocketseat.com.br](http://rocketseat.com.br)., 177.150.100.13, etc.
        
        ![O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled%206.png](O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled%206.png)
        
    
    **Opcionais**
    
    1. **subdomínio**, por exemplo, www.
        
        ![O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled%207.png](O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled%207.png)
        
    2. **path**, por exemplo, /blog, etc.
        
        ![O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled%208.png](O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled%208.png)
        
    3. **parâmetros**, por exemplo, ?v =xxxx, etc.
        
        ![O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled%209.png](O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled%209.png)
        
    4. **porta**, por exemplo, :3000, etc.
        
        ![O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled%2010.png](O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled%2010.png)
        
        <aside>
        ⚠️ É interessante citar aqui que, quando utilizado o protocolo **HTTP** implicítamente é utilizada a porta **80**, e quando utilizado o protocolo **HTTPS** implicítamente é utilizada a porta **443**.
        
        </aside>
        
    5. **âncora**, por exemplo, #topico1, etc.
        
        ![O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled%2011.png](O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled%2011.png)
        
- **O que é URN?**
    
    A Uniform Resource Name possibilita a localização de um recurso através do nome dele, ou seja, não necessita do conhecimento da localização dele.
    
    Geralmente a URN inicia como `urn:` seguido do nome da indentificação.
    
    ![Neste exemplo é a URN de um livro.](O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled%2012.png)
    
    Neste exemplo é a URN de um livro.
    

# Messages

- **O que são messages?**
    
    É a forma de comunicação utilizada pelo protocolo HTTP. Sendo esta a estrutura utilizada pelos responses e requests.
    
    Na versão do HTTP/1.1 as messages começaram a trabalhar com uma estrutura legível e em texto. Já na versão HTTP/2 as messages foram reestruturadas como binárias, o que torna a comunicação mais leve. E tirando a reestruturação binária das messagens, a arquitetura continua a mesma da versão 1.1.
    
- **O que é Request?**
    
    É o pedido feito por um agente. Este pedido é composto por method, protocol version e URI.
    
    - **method**: é a ação que deseja realizar, ou seja, é a intenção do agente com o recurso buscado.
    - **protocol version**: é a versão do protocolo utilizado para enviar a
    - **URI**: é a identificação do recurso.
    
    ![Visualização de uma requisição utilizando o cURL, onde é apresentado a composição básica do request.](O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled%2013.png)
    
    Visualização de uma requisição utilizando o cURL, onde é apresentado a composição básica do request.
    
    Basicamente toda request possui header, e dependo do method utilizado também é utilizado um body.
    
- **O que é Response?**
    
    É a resposta a um pedido. Essa resposta é composta por protocol version, status code, header e status message.
    
    - **protocol version**: é a versão do protocolo utilizada para responder o pedido.
    - **status code**: é um código que representa a resposta do pedido.
    - **header**: é as informações necessárias do servidor.
    - **status message**: é a messagem que representa os status code.
    
    ![Visualização de informações básicas de uma response.](O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled%2014.png)
    
    Visualização de informações básicas de uma response.
    

# Methods

- **O que são methods?**
    
    São verbos utilizados pelos protocolos, que servem para identificar qual ação deseja ser feita.
    
    Os mais comuns são:
    
    - DELETE
    - GET
    - HEAD
    - OPTIONS
    - PATCH
    - POST
    - PUT
    
    Esses verbos podem ser chamados de Verbos HTTP, sendo que cada um possui sua semântica.
    
    As características básicas dos métodos são:
    
    - nem todos são **seguros**
        
        Ou seja, **não alteram o estado** do servidor, são **somente para leitura**, o cliente **não solicita alterações** no servidor, **não há carga extra** para o servidor, o **servidor é responsável por manter o método seguro**.
        
        Alguns exemplos de métodos com está características são:
        
        - GET
        - HEAD
        - OPTIONS
    - nem todos são **idempotentes**
        
        Ou seja, quando executado o método **a resposta deve ser sempre a mesma**, mas o **status code pode ser diferente**. Sendo que também o **servidor têm a responsabilidade de retornar os dados da mesma maneira**, logo, **essa especificação não é a garantia** de que todos os servidores irão aplicar o conceito corretamente.
        
        Alguns exemplos de métodos com estas características são:
        
        - PUT
        - DELETE
        - e todos os **seguros**
    
    Para não ter dúvidas sobre a idempotencia e ssegurança dos methos segue tabela abaixo.
    
    ![O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled%2015.png](O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled%2015.png)
    
- **O que é JSON Server?**
    
    É um servidor que é especializado em devolver dados em formato JSON.
    
- **Como utilizar o JSON Server?**
    
    Podemos instalar ele localmente seguinte a seguite [documentação](https://github.com/typicode/json-server) ou podemos utilizar ele online através do [JSON Placeholder](https://jsonplaceholder.typicode.com/).
    
    Para instalar na máquina, de forma resumida, é necessário ter o npm instalado locamente. Depois executar o seguinte comando.
    
    ```bash
    npm install -g json-server
    ```
    
    Depois crie um diretório e um arquivo nomeado `db.json` com o seguitente conteúdo. Tudo isso dentro do diretório criado anteriormente.
    
    ```json
    {
      "posts": [
        { "id": 1, "title": "json-server", "author": "typicode" }
      ],
      "comments": [
        { "id": 1, "body": "some comment", "postId": 1 }
      ],
      "profile": { "name": "typicode" }
    }
    ```
    
    Em seguite, inicio o servidor.
    
    ```bash
    json-server --watch db.json
    ```
    
    Para testar o servidor com o cURL execute o seguite comando.
    
    ```bash
    curl http://localhost:3000/posts
    ```
    
- **O que é o method OPTIONS?**
    
    Este method serve para informar as disponibilidade da requisição, ou seja, a disponibilidade dos métodos da requisição.
    
    O OPTIONS possui as seguintes características:
    
    - ele é **seguro**;
    - ele é **idempotente**;
    - **não** **possui body** nem como request e nem como response;
    - **não é cacheable**, ou seja, não guarda informações na memória;
    - **não é utilizado em formulários**, ou seja, é utilizado apenas para verificar informações do servidor.
    
    Esse method pode ser utilizado da seguite maneira utilizando com o cURL e o JSON Server.
    
    ```bash
    curl -X OPTIONS http://localhost:3000/posts -i
    ```
    
    Dessa forma podemos ter a seguinte resposta.
    
    ```bash
    HTTP/1.1 204 No Content
    X-Powered-By: Express
    Vary: Origin, Access-Control-Request-Headers
    Access-Control-Allow-Credentials: true
    Access-Control-Allow-Methods: GET,HEAD,PUT,PATCH,POST,DELETE
    Content-Length: 0
    Date: Sun, 18 Apr 2021 06:23:41 GMT
    Connection: keep-alive
    Keep-Alive: timeout=5
    ```
    
- **O que é o method GET?**
    
    É um method que serve para pegar um recurso, ou seja, ele recebe dados somente.
    
    Suas características são:
    
    - é **seguro**;
    - é **idempotente**;
    - **não possui body na request**, mas dependendo do servidor pode **possui body na response** dependendo;
    - é **cacheable**, ou seja, em casos de agilizar o serviço que é solicitado alguma página por exemplo, é mais rápido e fácil manter a página em cache;
    - pode ser **utilizado em formulários**, como em um formulário de busca por exemplo.
    
    Para testar o method com cURL e JSON Server utilize o seguinte comando.
    
    ```bash
     curl -X GET http://localhost:3000/posts -v
    ```
    
    Podemos obter informações semelhante a seguinte.
    
    ```bash
    *   Trying ::1:3000...
    * connect to ::1 port 3000 failed: Connection refused
    *   Trying 127.0.0.1:3000...
    * Connected to localhost (127.0.0.1) port 3000 (#0)
    > GET /posts HTTP/1.1
    > Host: localhost:3000
    > User-Agent: curl/7.71.1
    > Accept: */*
    > 
    * Mark bundle as not supporting multiuse
    < HTTP/1.1 200 OK
    < X-Powered-By: Express
    < Vary: Origin, Accept-Encoding
    < Access-Control-Allow-Credentials: true
    < Cache-Control: no-cache
    < Pragma: no-cache
    < Expires: -1
    < X-Content-Type-Options: nosniff
    < Content-Type: application/json; charset=utf-8
    < Content-Length: 77
    < ETag: W/"4d-49G7XbVRP2NKipc5uj9Z4hcUq3Y"
    < Date: Sun, 18 Apr 2021 06:36:00 GMT
    < Connection: keep-alive
    < Keep-Alive: timeout=5
    < 
    [
      {
        "id": 1,
        "title": "json-server",
        "author": "typicode"
      }
    * Connection #0 to host localhost left intact
    ```
    
- **O que é o method HEAD?**
    
    É um method semelhante a GET, porém é devolvido somente o cabeçalho.
    
    Suas características são:
    
    - é **seguro**;
    - é **idempontente**;
    - **não possui body na request** e **não possui body na response**, sendo está a maior diferença entre o HEAD e o GET;
    - **não é utilizado em formulários**;
    - é **cacheable**.
    
    Para testar este method com cURL e JSON Server pode utilizar o seguinte comando.
    
    ```bash
    curl -I http://localhost:3000/posts
    ```
    
    Dessa forma é visualizado apenas o head do pedido.
    
- **O que é o method POST?**
    
    É um method com a função de publicar/cadastrar um recurso em um servidor.
    
    Suas características são:
    
    - **não** é **seguro**;
    - **não** é **idempotente**;
    - **possui body na request** e geralmente **possui body na response**;
    - é **utilizado em formulários**;
    - pode ser **cacheable**;
    
    Para testar este method com o cURL e JSON Server pode utilizar o seguinte comando.
    
    ```bash
    curl -d '{ "id": 2, "title": "json-server-2", "author": "thazsobral" }' -H 'Content-type: application/json' -X POST http://localhost:3000/posts
    ```
    
- **O que é o method PUT?**
    
    É o method utilizado para criar um novo ou atualizar algum recurso no servidor. A diferença entre o PUT e o POST é a idempotência, ou seja, o PUT sempre receberá a mesma resposta quando executada o mesmo pedido.
    
    Geralmente o status code utilizada para responder o PUT na ação de criação é o 201, e para a atualização é o 200 ou 204.
    
    Suas características são:
    
    - **não** é **seguro**;
    - é **idempotente**;
    - **possui body no request** mas geralmente **não possui body na response**;
    - normamelmente **não é utilizado em formulários**;
    - **não** é **cacheable**.
    
    Para testar este method com o cURL e JSON Server utilize o seguite comando.
    
    ```bash
    curl -d '{ "name": "thazsobral" }' -H 'Content-type: application/json' -X PUT http://localhost:3000/profile
    ```
    
- **O que** **é o method PATCH?**
    
    É um method que têm a função de fazer uma modificação pacial de um recurso, ou seja, ele é semelhante ao PUT, mas o PUT faz uma alteração completa do recurso enquanto o PATCH faz alteração apenas de uma parte do recurso.
    
    As características deste methos são:
    
    - **não** é **seguro**;
    - pode **não** ser **idempontente**;
    - **possui body na request** e **possui body na response**;
    - normalmente **não é utilizado em formulários**;
    - **não** é **cacheable**.
    
    Para testar este method com o cURL e o JSON Server pode-se utilizar o seguinte comando.
    
    ```bash
    curl -d '{ "title": "my-title" }' -H 'Content-type: application/json' -X PATCH http://localhost:3000/posts/2
    ```
    
- **O que é o method DELETE?**
    
    É o method que serve para remover um recurso. Geralmente este method devolve os seguintes status code:
    
    - 200 se o pedido foi aceito e executado;
    - 202 se ainda não processado mas aceito o pedido;
    - 204 se não possui conteúdo de resposta de body.
    
    Suas características são:
    
    - **não** é **seguro**;
    - é **idempontente**;
    - pode **possuir body na request** e pode **possuir body na response**, vai depender da implementação;
    - normalmente **não é utilizado em formulários**;
    - não é **cacheable**.
    
    Para testar este method com o cURL e JSON Server pode-se utilizar o seguinte comando.
    
    ```bash
    curl -X DELETE http://localhost:3000/posts/2
    ```
    

# Header

- **O que é header?**
    
    Cabeçalho, são informações adicionais para requests e responses, sendo ele geralmente construído utilizando chave e valor, como demonstrado abaixo.
    
    ```bash
    Content-type: application/json
    # ou
    Content-type: text/html
    ```
    
    <aside>
    ⚠️ Vale destacar aqui que o header pode possuir diversas propriedades.
    
    </aside>
    
    O header está presente em 3 contextos de comunicação web, sendo eles:
    
    1. General
    2. Request
    3. Response
    
    Esses contextos podem ser visualizados no DevTools na ferramente network como demonstrado abaixo.
    
    ![O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled%2016.png](O%20guia%20estelar%20de%20HTTP%20fdc320e4111346b49c14305388fbb9fc/Untitled%2016.png)
    
- **O que é Header General?**
    
    É um header generalizado da comunicação ou do pedido. Nele podemos visualizar algumas informações como demonstrado abaixo.
    
    ```bash
    Request URL: https://www.google.com/webhp?hl=pt-BR&sa=X&ved=0ahUKEwi2wY2DpofwAhUZqJUCHazFAB0QPAgI
    Request Method: GET
    Status Code: 200 
    Remote Address: 216.58.202.132:443
    Referrer Policy: origin
    ```
    
    - **Request** **URL** é a URL do pedido
    - **Request Method** é o method do pedido
    - **Status Code** é o status retornado do pedido
    - **Remote Address** é o endereço ip do servidor que respondeu o pedido.
        
        <aside>
        ⚠️ Vale destacar aqui que este endereço é realmente o endereço geográfico do servidor, ou seja, através dele é possível identificar onde está este servidor.
        
        </aside>
        
    - **Referrer Policy** é a política de referência do servidor, ou seja, são as regras estabelecidas no servidor que cita as informações retornadas sobre suas referências.
- **O que é Header Request?**
    
    É o cabeçalho da request e possui algumas informações referentes ao pedido e ao cliente também.
    
    ```bash
    :authority: www.google.com
    :method: GET
    :path: /webhp?hl=pt-BR&sa=X&ved=0ahUKEwi2wY2DpofwAhUZqJUCHazFAB0QPAgI
    :scheme: https
    accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
    accept-encoding: gzip, deflate, br
    accept-language: pt-BR,pt;q=0.9,en-US;q=0.8,en;q=0.7
    cache-control: max-age=0
    cookie: SID=8gdXRiSDklKnOobGZiEJctzbAb7nvN7XqHWki71c3GxtX9MS3Uz7btDRoK_rZY9ZNLxhdw.; __Secure-3PSID=8gdXRiSDklKnOobGZiEJctzbAb7nvN7XqHWki71c3GxtX9MSeUQvpetG-WofxlK8WDhZJQ.; HSID=AHulUASgxFPhFOA25; SSID=AVUiaxj80gMJJJJDy; APISID=VJwQdEB4Ad6LQ37X/Anwa6J4bC4raraWRp; SAPISID=dMjw_6xr1JyUoDc-/ACEtqnbxSTQjlLX5r; __Secure-3PAPISID=dMjw_6xr1JyUoDc-/ACEtqnbxSTQjlLX5r; SEARCH_SAMESITE=CgQIrJIB; NID=213=E2zNMdvz23rmbGjbvAFUjDgJcmp1QHXFp9rNdRMkrfrBCnLZfGzbERZv27gpXKiVXxmYxVzW7IxfreOI95_fRxyuApY7tVKG780M9njO7g4Q1G243CzL26I1Jh-kc-LvDye9022Ec8m8YeZ2lEci5kO6jsn2i-mKa_PICqpTUkl4TF7puMhHi5ecr2wwoK4C3e66nrd_4JiXoqSJOaatsK0ECw03Z1jMzL0RTsePDtilOThPjVlDRDOIHFxZyKMbDmzxjpgwtNOzRy5O8A; 1P_JAR=2021-04-18-07; DV=A_OFB1Ff9PlFACCA_3r72xLkmfs-jtcu3TJpNEbf1gAAACBI3RpFx616zQAAACTWtiY5pKI3QgAAAA; SIDCC=AJi4QfGrztHQSodB67Psml_L2ddmEN0J1Md7RXMsGAKvBZKIgJa4v_aSs2Eim3Wk9Ucr30JdkjY; __Secure-3PSIDCC=AJi4QfF10qnLvtfHomrjD_F7Us1jIC43l7zR3ywFQv5KwdKeFifvPwIZs9wlEk_wv4eW811svA
    dnt: 1
    referer: https://www.google.com/
    sec-ch-ua: " Not A;Brand";v="99", "Chromium";v="90", "Google Chrome";v="90"
    sec-ch-ua-mobile: ?0
    sec-fetch-dest: document
    sec-fetch-mode: navigate
    sec-fetch-site: same-origin
    sec-fetch-user: ?1
    upgrade-insecure-requests: 1
    user-agent: Mozilla/5.0 (X11; Fedora; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/90.0.4430.72 Safari/537.36
    x-client-data: CJC2yQEIpbbJAQipncoBCJasygEI+MfKAQiA0MoBCImDywEIsZrLAQjknMsBCKidywEIoKDLARjgmssBGI6eywE=
    Decoded:
    message ClientVariations {
      // Active client experiment variation IDs.
      repeated int32 variation_id = [3300112, 3300133, 3313321, 3315222, 3318776, 3319808, 3326345, 3329329, 3329636, 3329704, 3330080];
      // Active client experiment variation IDs that trigger server-side behavior.
      repeated int32 trigger_variation_id = [3329376, 3329806];
    }
    ```
    
    Alguns campos acima que são importantes conhecer são:
    
    - **authority** é a autoridade do pedido
    - **method** é o method do pedido
    - **path** é o caminho do pedido
    - **scheme** é o esquema utilizado no pedido
    - **accept** é o que é aceito pelo pedido
    - **accept-encoding** são as codificações ou compactações aceitas
    - **accept-language** são as linguagens aceitas
    - **cache-control** é o controle de cache
    - **cookie** é a forma permitida para deixar "rastros" na web. Dessa forma a comunicação tabmém pode ser facilitada na próxima transação.
    - etc.
- **O que é Header Response?**
    
    É o cabeçalho da response e possui algumas informações sobre o recurso e sobre o servidor.
    
    ```bash
    alt-svc: h3-29=":443"; ma=2592000,h3-T051=":443"; ma=2592000,h3-Q050=":443"; ma=2592000,h3-Q046=":443"; ma=2592000,h3-Q043=":443"; ma=2592000,quic=":443"; ma=2592000; v="46,43"
    cache-control: private, max-age=0
    content-encoding: br
    content-length: 39075
    content-type: text/html; charset=UTF-8
    date: Sun, 18 Apr 2021 07:44:10 GMT
    expires: -1
    server: gws
    set-cookie: 1P_JAR=2021-04-18-07; expires=Tue, 18-May-2021 07:44:10 GMT; path=/; domain=.google.com; Secure; SameSite=none
    set-cookie: SIDCC=AJi4QfGRb-QV_mQGUNz5R36-4_OL488SmC2Tw2QjWs969quj4RtqFZ_oqlm7gO5BGZEnM9SZgIw; expires=Mon, 18-Apr-2022 07:44:10 GMT; path=/; domain=.google.com; priority=high
    set-cookie: __Secure-3PSIDCC=AJi4QfEl0Ww8szP33MO_hDw9H11TkRCXAJeNlMzjs4hPD12PPCeGu-RGv8c0MivpdxxZyHCVFw; expires=Mon, 18-Apr-2022 07:44:10 GMT; path=/; domain=.google.com; Secure; HttpOnly; priority=high; SameSite=none
    strict-transport-security: max-age=31536000
    x-frame-options: SAMEORIGIN
    x-xss-protection: 0
    ```
    
    Alguns campos dos campos acima que são importantes conhecer são:
    
    - **cache-control** é o controle de chache
    - **content-length** é o tamanho do conteúdo (em bytes) da reposta
    - **content-type** é o tipo do conteúdo da resposta
    - **date** é a data da resposta
    - **set-cookie** é valor utilizado pelo cookie para fazer o próximo pedido neste serviço. Desta forma, é possível visualizar a ligação entre os pedidos e respostas da comunicação.
- **Como obter ajuda com Headers?**
    
    Há uma ferramenta web que pode auxíliar muito nas consultas de headers e outros recursos, tecnologias e frameworks.
    
    [DevDocs](https://devdocs.io/) é um tipo de dicionário para devs. Com ele é possível consultar informações sobre frameworks, protocolos, etc.
    

# Status

- **O que é Status Code?**
    
    São códigos retornados pelos servidores relacionando o pedido ao status do recurso.
    
    Dessa forma, a comunicação se torna mais clara entre o servidor e o cliente.
    
    Os códigos mais comuns são:
    
    - `100` que significa que está tudo certo com o pedido sendo possível aqui continuar o encerrar.
    - `200` que significa que está tudo certo com o pedido, comumente utilizado como resposta para os methods de GET e POST .
    - `201` que significa que foi criado o recurso, sendo este mais utilizado para o method PUT.
    - `204` que significa que foi realizado com sucesso o pedido, mas não houve nenhuma resposta explícita. Este código é mais utilizado para os methods DELETE e PUT.
    - `301` que significa que o recurso solicitado foi movido. Sendo que geralmente a nova localização vem na resposta.
    - `302` que significa que o recurso foi movido temporariamente. Está é uma resposta muito comum para o method GET.
    - `307` que significa que o recurso foi movido temporariamente, mas este código é mais utilizado para responder os outros methods menos o GET.
    - `308` que também significa que o recurso foi movido, mas é comumente utilizado como resposta para o method POST.
    - `400` que significa que o pedido está feito de forma incorreta ou foi mal efetuado.
    - `401` que significa que o pedido não foi autorizado.
    - `403` que significa que o pedido específico não foi permitido.
    - `404` que significa que o recurso não foi encontrado.
    - `405` que significa que o method não está permitido.
    - `429` que significa um bloqueio porque o cliente está fazendo muito pedidos.
    - `500` que significa que houve um erro interno no servidor, mas não soube ser informado qual erro.
    - `503` que significa que o serviço não está disponível no momento do pedido.
    
    <aside>
    ⚠️ Para mais informações sobre os status do HTTP acesse o [DevDocs](https://devdocs.io/http-status/).
    
    </aside>