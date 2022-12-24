# NodeJS EJS HTML inteligente

> *Site: [https://app.rocketseat.com.br/node/node-js-ejs-html-inteligente](https://app.rocketseat.com.br/node/node-js-ejs-html-inteligente)*
> 

Daremos o poder de programar no HTML. Atráves do EJS, aprenderemos como o Javascript irá construir nosso HTML com NodeJS e Express

- **O que é EJS?**
    
    Embedded Javascript Template ou EJS é uma linguagem de modelagem que permite gerar marcação HTML com Javascript, ou seja, o front-end pode ser criado utilizando Javascript simples.
    
    Para utilizar o EJS é necessário primeiro ter o Node.js instalado no computador.
    
    <aside>
    ⚠️ Para mais informações sobre o EJS acesse o [site oficial](https://ejs.co/).
    
    </aside>
    
- **Como utilizar o EJS?**
    
    Para utilizar o EJS é necessário possuir alguns requisitos como:
    
    1. um projeto criado em Node.js;
    2. um arquivo server.js na raiz do projeto conforme especificado no package.json;
    3. uma pasta views dentro da raiz do projeto;
    4. um arquivo index.ejs dentro da pasta views;
    5. a definição de renderização de arquivos .ejs no servidor Node.js.
- **Como criar um servidor para utilizar o EJS?**
    
    Para criar um servidor Node.js basta seguir os passos abaixo.
    
    1. Execute o seguinte comando para gerar um projeto Node.js.
        
        ```bash
        npm init -y
        ```
        
    2. Crie um arquivo com o mesmo definido na propriedade `"main"` do package.json.
    3. Para ficar mais fácil aplicar funções http e outros serviços de rede, pode-se utilizar o módulo express. Para isso insta-le o pacote com o seguinte comando.
        
        ```bash
        npm install express
        ```
        
    4. Agora configure no arquivo definido na propriedade `"main"` do package.json da seguinte forma.
        
        ```jsx
        const express = require("express");
        
        const app = express();
        
        app.listen(8080, () => console.log("Server up in http://localhost:8080"));
        ```
        
    5. Também é necessário especificar no servidor a renderização para ejs. Para isso instale também o módulo do ejs com o seguinte comando
        
        ```bash
        npm install ejs
        ```
        
    6. E defina a rederização para ejs no arquivo do servidor.
        
        ```jsx
        const express = require("express");
        
        const app = express();
        
        app.set("view engine", "ejs");
        
        app.listen(8080, () => console.log("Server up in http://localhost:8080"));
        ```
        
    7. Após preparar o arquivo .ejs pode-se especificar um rota que direciona para o arquivo que será renderizado como EJS, como demonstrado abaixo.
        
        ```jsx
        const express = require("express");
        
        const app = express();
        
        app.set("view engine", "ejs");
        
        app.get("/", function (request, response) {
        	response.render("index.ejs");
        });
        
        app.listen(8080, () => console.log("Server up in http://localhost:8080"));
        ```
        
- **Como preparar o HTML para utilizar o EJS?**
    
    Para estruturar o projeto Node.js para utilizar o ejs é necessário criar na raiz do projeto uma pasta nomeada views, dentro desta, uma outra chamada pages, e dentro desta pasta deve-se criar um arquivo com extensão .ejs, que esteja especificado dentro do código .js do projeto Node.js.
    
    Essa pasta nomeada como views é automaticamente reconhecida quando é definido dentro do arquivo principal do servidor que será utilizado o serviço de renderização.
    
    ```jsx
    const express = require("express");
    
    const app = express();
    
    app.set("view engine", "ejs");
    
    app.get("/", function(request, response) {
    	response.render("pages/index");
    });
    
    app.listen(8080);
    ```
    
    Após criar o arquivo .ejs, pode-se inserir um código de HTML comum, com apenas algumas coisas a mais. Essas coisas a mais são as tags EJS.
    
- **O que é Bootstrap?**
    
    É um pacote CSS que possui diversas classes e estilos pré-configurados, o que facilita muito a criação de páginas HTML sem a necessidade arquivos de estilização.
    
    Para utilizar o Bootstrap, primeiramente é preciso linkar com o cdn oficial ou baixá-lo através do [site oficial](https://getbootstrap.com/).
    
    A utilização das estilizações pré-configuradas diretamente no HTML, é realizada através de classes padrão.
    
    ```html
    <nav class="navbar navbar-expand-lg navbar-light bg-light"></nav>
    ```
    
- **O que é uma rota?**
    
    Basicamente, a rota é o direcionamento definido dentro do código de um servidor para uma determinada rotina. Essa rotina pode ser, o retorno de algo, a gravação de algum no valor no banco de dados, etc. A rotina que será primeiramente definida pelo método definido na rota.
    
    Os métodos de rotas seguem o padrão HTTP, ou seja, GET, POST, PUT e DELETE são os mais básicos.
    
    Sabendo disso, sabe-se que as rotinas seguem primeiramente os métodos definidos nas rotas, depois o caminho da rota (o que vem depois do domínio do servidor) é especificado no primeiro parâmetro delas, e depois a rotina ou instruções que se deve executar em forma de função.
    
    ```jsx
    const express = require("express");
    
    const app = express();
    
    app.get("/", function(request, response) {
    	response.send("Hello");
    });
    ```
    
    Outra coisa que vale citar aqui é que, dentro das função que irão executar as instruções da rota recebem por padrão os parâmetros request (a requisição HTTP) e response (a resposta HTTP), ou seja, são estes parâmetros que facilitam a comunicação entre o cliente e o servidor.  
    
    Dentro das rotas rotas também pode-se incluir midlewares, ou seja, rotinas que devem ser executadas antes da instruções específicas das rotas, como validação de parâmetros passados através da requisição, etc.
    
- **Como componetizar código HTML/EJS?**
    
    Às vezes é necessário reaproveitar pedaços de HTML, como um template. Utilizando o EJS isso é possível, como demonstrado nos passos seguintes:
    
    1. Crie uma pasta nomeada partials dentro da pasta views;
    2. E dentro desta pasta crie o(s) arquivo(s) com o(s) pedaço(s) de HTML desejado(s);
    3. No arquivo onde deseja incluir o HTML componetizado (na pasta pages) inclua no(s) lugar(es) adequado(s) a seguinte tag EJS para referênciar o(s) arquivo(s) dentro de partials.
        
        ```jsx
        <%- include("../partials/nome_arquivo_componetizado"); %>
        ```
        
        <aside>
        ⚠️ Lembre-se de definir o caminho corretamente de acordo com seu OS.
        
        </aside>
        
- **Como passar valores para HTML/EJS filhos?**
    
    Há situações que é necessário passar valores dinâmicos ou até mesmo estáticos para os componentes filhos. Para estes casos o EJS permite passar valores para outras páginas ou templates componetizados, ou seja, entre códigos HTML, como demonstrado abaixo. 
    
    1. Primeiro, defina na page o que deseja passar como segundo parâmetro do `include()` em forma de objeto, onde é passado uma chave e um valor (ou mais, no caso de mais valores).
        
        ```jsx
        <%- include("../partials/arquivo_componente", {val: "valor"} %>
        ```
        
    2. Depois, no componente na pasta partials defina o lugar onde deseja apresentar valor, mas agora mudando o sinal `-` (hífen) para `=` (igual) para o EJS entender que é um valor dinâmico.
        
        ```jsx
        <%= val %>
        ```
        
    
    <aside>
    ⚠️ Deve-se sempre atentar-se que, quando o componente estiver esperando um objeto o valor sempre deve ser passado, caso não seja, a página dará um erro de valor `undefined`.
    
    </aside>
    
    Para corrigir possíveis erros de valores não passados é possível adicionar condições em Javascript, como demonstrado abaixo.
    
    ```jsx
    <%= typeof val != "undefined" ? val : "valor_padrão">
    ```
    
- **Como passar valores para HTML/EJS utilizando o Node.js?**
    
    É possível fazer este tipo de passagem de valor através de parâmetros disponiveis nas rotas, como demonstrado abaixo.
    
    ```jsx
    app.get("/", function(request, response) {
        const items = [
            {
                title: "T",
                message: "udo de bom."
            },
            {
                title: "O",
                message: " melhor modelador de HTML."
            },
            {
                title: "P",
                message: "ronto para a ação!"
            },
        ];
        const subtitle = "EJS is TOP!!!"
    
        response.render("pages/index", {items, subtitle});
    });
    ```
    
    Em seguida pode ser recebido os valores como nas passagens entre HTML e HTML.
    
    ```jsx
    <!DOCTYPE html>
    <html lang="en">
    <%- include("../partials/head"); %>
    <body class="container py-5">
        <%- include("../partials/header"); %>
        <main>
            <div>
                <h1>Node + EJS</h1>
                <p>We are learning with make a page with Node.js and EJS.</p>
            </div>
        </main>
        <ul>
            <% items.forEach(function(item) { %>
            <li>
                <strong><%= item.title %></strong><%= item.message%>
            </li>
            <% }) %>
        </ul>
        <%= subtitle %>
        <%- include("../partials/footer"); %>
    </body>
    </html>
    ```