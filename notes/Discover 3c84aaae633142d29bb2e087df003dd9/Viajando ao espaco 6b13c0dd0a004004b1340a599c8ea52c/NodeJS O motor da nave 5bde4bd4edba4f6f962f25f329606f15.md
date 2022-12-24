# NodeJS O motor da nave

> *Site: [https://app.rocketseat.com.br/node/node-js-o-motor-da-nave](https://app.rocketseat.com.br/node/node-js-o-motor-da-nave)*
> 

No back-end da nossa aplicação, nós iremos precisar entender como o JavaScript controla nossa máquina, por isso, aprenderemos as bases de NodeJS e o poder que ele tem na nossa máquina

# Conhecendo o node

- **Para que serve o NodeJS?**
    
    Essa ferramenta permite desenvolver back-end, front-end, microserviços (serviços completos), scripts de automação, AI, APIs (serviço back-end que disponibiliza dados) para mobile, web ou desktop, e diversas outras coisas.
    
    <aside>
    ⚠️ **Não é recomendado** utilizar o NodeJS para sistemas que utiliza **muito** **processamento de dados**. Por exemplo, processamento de vídeos ou fotos.
    
    </aside>
    
- **Quais as vantagens de utilizar o NodeJS?**
    - **Rápido** na **execução** **e prototipação** de sistemas;
    - **Alta escalabilidade**;
    - **Aplicações de ponta** com casos de uso no mercado;
    - **JS everywhere** (utilizar Javascript práticamente em toda parte do sistema, e;
    - **Ecossitema gigante**;
- **Quais o casos de uso com NodeJS?**
    
    Alguns casos de uso são:
    
    - [Netflix](https://www.netflix.com/br/)
    - [Paypal](https://www.paypal.com/us/home)
- **O que é e o que não é o NodeJS?**
    
    **NodeJS é**
    
    - **JS Runtime Enviroment** ( Ambiente de execução Javascript): é uma camada acima do OS (Operating System) que executa Javascript. Dessa forma, é possível passar comandos para o OS que por sua vez pode passar comandos para o Hardware.
    
    **NodeJS não é**
    
    - **Framework**: não é um framework como o React, Vue ou Angular. O framework é um pacote com padrões, regras, etc, o que te obriga a programar da forma que o framework precisa. Já o NodeJS não te obriga a seguir regras como o framework. A única necessidade a seguir no NodeJS é a utilização do Javascript e os módulos (já que o NodeJS é contruído por módulos).
    - **Linguage**: não é uma linguagem, pois a linguagem utilizado no NodeJS é o Javascript.
- **O que é V8?**
    
    Google V8, é um **Javascript Engine** (Máquina Javascript) que compõe o Runtime Enviroment, ou melhor, é a **máquina virtual** que irá **rodar o JS** na máquina.
    
    Está máquina virtual possui as seguintes características:
    
    - O V8 é basicamente um **interpretador JS** para linguagem de máquina, e foi **desenvolvido em C++** (o que facilita a corversão para Assembler).
        
        <aside>
        💡 **Hierárquia de comunicação
        
        V8 → C++ → Assembler → Hardware**
        
        </aside>
        
    - Ele é baseado nas **últimas features do JS**.
    - É **focada na estutura do Chrome** mas tem definido o **cuidado para não quebrar o NodeJS**.
    - Ele por si só **não possui a DOM** (porque a DOM é uma API do browser), **nem console** (porque este está embutido no NodeJS) e **nem File System** (o V8 não trabalha com File System, mas o NodeJS sim).
- **Como é a estrutura do NodeJS?**
    
    ![NodeJS%20O%20motor%20da%20nave%205bde4bd4edba4f6f962f25f329606f15/Untitled.png](NodeJS%20O%20motor%20da%20nave%205bde4bd4edba4f6f962f25f329606f15/Untitled.png)
    
    - **Your Code**: o código escrito em Javascript
    - **V8**: intreperta e modifica o código
    - **Core Modules**: módulos do core do NodeJS
    - **C++ Bindings**: composições do C++
    - **libuv**: responsável pelo Event Loop
    - **c-ares, http ...** : outros módulos que compõem o NodeJS
    - **The Operation System**: O sistema operaticional que conversa diretamente com a máquina.
- **Como funciona o NodeJS de forma simples?**
    
    Para entender melhor como o NodeJS funciona, pode-se fazer uma comparação de características entre o Apache e NodeJS.
    
    Basicamente a diferença entre estes servidores são:
    
    - **Apache** é um servidor **multi-thread** e **síncrono**, enquanto;
    - NodeJS é **single-thread** e **assíncrono**.
    
    Se preferir ver estas características de forma mais lúdica leia e análise as histórias abaixo.
    
    🍝 **Restaurante do Tio Apache**
    
    *Neste restaurante cada cliente têm seu próprio garçom (atendimento exclusivo)*
    
    - Um cliente var fazer um pedido
        - Um garçom é direcionado para sua mesa
        - O garçom pega o pedido e leva até a cozinha para o chefe preparar
        - O chefe (por regra do restaurante) proibi o garçom de voltar a mesa e o bloqueia ali até que o pedido fique pronto
        - O cliente quer muito fazer outros pedidos, mas não pode porque o garçom está bloqueado
        - Após o pedido ficar pronto, o garçom retorna até a mesa para entregar o pedido
        - O cliente foi embora e por regra do restaurante o garçom é despedido
    - Se chegar 100 clientes o Tio Apache contrata 100 garçons
    
    *O serviço é caro e de primeira, mas por conta de bloquear o garçom e contratar um garçom para cada mesa o serviço se torna caro e lento.*
    
    **🍝 Restaurante do Noderson**
    
    *Neste restaurante há um funcionário chamado de Eveneto Lupin (menino ágil este)*
    
    - Cliente da mesa 1 vai fazer um pedido
        - Eveneto Lupin vai atende a mesa e leva o pedido para o chefe
        - E corre para a próxima mesa
    - Clinte da mesa 2 faz um pedido também
        - Eveneto Lupin já pegou o pedido e já levou para o chef também
    - O chefe toca o sininho avisando que o pedido da mesa 1 já está pronto
        - Eveneto Lupin pega o pedido e corre para entregar
    - ....
    
    *O segredo de eveneto é que ele sabe trabalhar de forma assíncrona, fazendo mais uma tarefa de cada vez e não têm nada que o bloqueie. Ele é muito solicitado e faz seu trabalho muito bem.*
    
    **Legenda**
    
    - Tio Apache = Apache
    - Noderson = NodeJS
    - Cliente = Usuário
    - Pedido = Request
    - Garçon = Thread
    - Cozinha = Servidor
    - Chefe = Banco de dados ou outros serviços
    - Eveneto Lupin = Event Loop
    
    > *Ou seja, NodeJS é single-threaded, non-blocking e asynchronous.*
    > 
- **Como funciona o NodeJS de forma técnica?**
    
    ![NodeJS%20O%20motor%20da%20nave%205bde4bd4edba4f6f962f25f329606f15/Untitled%201.png](NodeJS%20O%20motor%20da%20nave%205bde4bd4edba4f6f962f25f329606f15/Untitled%201.png)
    
    Primeiro, existe uma **APPLICATION** desenvolvida com **JAVASCRIPT** que utiliza dos recursos do **V8**. O **V8** trabalhando de forma íntima com os módulos do **NODE.JS BINDINGS** se comunica com a **LIBUV**. A **LIBUV** é uma biblioteca que trabalha diretamente no sistema operacional de forma assíncrona. Dentro da **LIBUV** funciona o tão conhecido **EVENT LOOP**, e este **EVENT LOOP** trabalha gerenciando o **EVENT QUEUE**. Quando há algum tarefa no **EVENT QUEUE** que pode bloquear a aplicação o **EVENT LOOP** à transfere para o **WORKER THREADS** para ser preparada, e quando essa tarefa que agora está no **WORKER THREADS** está pronta ela é movida novamente para o **EVENT QUEUE** (no final da fila) ****pelo **EVENT LOOP**.
    
    Para visualizar o comportamento do sistema acima, pode-se observar o código abaixo e em seguida seu resultado.
    
    ```jsx
    function c() {
    	setTimeout(() => 	console.log('c'), 1000);
    	return;
    }
    
    function c() {
    	console.log('b');
    	return c();
    }
    
    function a() {
    	b();
    	console.log('a');
    	return
    }
    
    a();
    ```
    
- **Como é a história do NodeJS?**
    
    **Ryan Dahl** criou o Nodejs em **2009** para ser um **Runtime Javascript** feito com o motor **V8 do Google**.
    
    Em **2011** foi **lançado o projeto [NPM](https://npmjs.org)** (Node Package Manager). O NPM foi criado para ser a forma **padrão de compartilhamento de bibliotecas** para utilização do Node. O gerenciador de pacotes NPM foi tão bem aceito que foi considerado uma revolução na comunidade do Node, causando assim um marco no **compatilhamento e mantimento de códigos** para o NodeJS, tendo atualmente **mais de 1 milhão e meio de pacotes** criados.
    
    Com a grande aceitação e **popularidade** do NodeJS, foi criado o **Node.js Fundation em 2015**, que inclui algumas empresas como, IBM, Microsoft, Paypal, Groupon, entre outros, passando assim a fazer parte do [**OpenJS Fundation**](https://openjsf.org), onde **é possível tirar até certificados** de técnologias ligadas a Javascript.
    
    Atualmente o código do NodeJS pode ser estudado em seu [**repositório oficial**](https://github.com/nodejs/node). E sua **comunidade** nos dias de hoje vêm **ganhando cada vez mais força e aceitação**.
    

# Configurando o ambiente

- **Como instalar o NodeJS?**
    
    Atualmente existe algumas formas de instalar o NodeJS, as mais básicas são:
    
    - **A forma oficial**
        1. Acesse o [site oficial](https://nodejs.org/en/) do Node
        2. Escolha na versão que mais te agrada. Sendo que, para as versões atuais há duas opções, a LTS (mais testada e mas estável) ou a Current (com mais features, mas não muito testada), sendo a LTS a mais recomendada para ser utilizada.
            
            ![NodeJS%20O%20motor%20da%20nave%205bde4bd4edba4f6f962f25f329606f15/Untitled%202.png](NodeJS%20O%20motor%20da%20nave%205bde4bd4edba4f6f962f25f329606f15/Untitled%202.png)
            
        3. Instale o pacote baixado seguinda a documentação de instalação, seja [via package manager](https://nodejs.org/en/download/package-manager/), [via binary](https://github.com/nodejs/help/wiki/Installation) ou se preferir pode instalar no [windows no modo WSL](https://docs.microsoft.com/en-us/windows/dev-environment/javascript/nodejs-on-wsl).
    - **A forma flexível**
        
        Dentro do opção de instalação via package manager, existe uma forma de instação do NodeJS muito popular e flexível, o NVM (Node Version Manager). Para instalar utilizando está opção pode-se seguir o [guia do site do Node](https://nodejs.org/en/download/package-manager/#nvm) ou seguir o [guia do repositório oficial do projeto](https://github.com/nvm-sh/nvm#installing-and-updating).
        
- **O que é REPL?**
    
    Read-Eval-Print-Loop, é a ferramenta do Node que **possibilita interpretar o JS diretamente no terminal**. Para acessar o REPL basta digitar `node` no terminal.
    
    - **Read**: faz a leitura de comandos e instruções
    - **Eval**: avalia as instruções digitadas
    - **Print**: faz a escrita dos resultados
    - **Loop**: em forma de loop
    
    Toda a **estrutura acessada pelo REPL é a do NodeJS** e não da DOM como é o caso do Javascript no navegador. Por exemplo, no REPL não há o objeto window e nem document. Para o REPL o objeto raiz é o global (que é parte da estrutura do NodeJS).
    
    <aside>
    ⚠️ Para mais informações sobre o REPL acesse a sua [documentação oficial](https://nodejs.org/api/repl.html).
    
    </aside>
    
    Alguns módulos do Node que podem ser acessados pelo REPL são:
    
    - `os`: fornece métodos e propriedades de utilitários relacionados ao sistema operacional.
    - `path`: fornece utilitários para trabalhar com caminhos de arquivo e diretório.
    - `fs`: permite interagir com o sistema de arquivos de uma forma modelada nas funções POSIX padrão.
    - `http`: oferece suporte a muitos recursos do protocolo que são tradicionalmente difíceis de usar.
    - entre outros
    
    <aside>
    ⚠️ Para mais informações sobre os diversos módulos acesse a [documentação oficial](https://nodejs.org/api/documentation.html#documentation_stability_overview).
    
    </aside>
    
    Para sair do REPL basta digitar `.exit`.
    
- **Qual editor utilizar para codificar em NodeJS?**
    
    Qualquer um. Mas para desenvolvedores é recomendável utilizar o [VSCode](https://code.visualstudio.com/), [Atom](https://atom.io/) ou [Sublime Text](https://www.sublimetext.com/).
    

# Iniciando na prática

- **Qual o tipo de arquivo executado no NodeJS?**
    
    Como o NodeJS foi criado para executar **Javascript**, ele naturalmente executa arquivos .js.
    
    Atualmente também é possível utilizar o Typescript, mas é necessário realizar algumas configurações antes de utilizar este superset do Javascript.
    
- **O que são módulos?**
    
    De forma simples, são objetos, que por sua vez possuem métodos e atributos.
    
- **Quais as variáveis globais no NodeJS?**
    
    Para a estrutura gloabal do Node digite `global` no REPL. Para saber mais acesse a [documentação oficial](https://nodejs.org/api/globals.html).
    
    Algumas variáveis globais são:
    
    - `__dirname`: para apresentar o caminho para o diretório atual
    - `__filename`: para apresentar o caminho para o arquivo atual
- **O que é Require?**
    
    É uma função que recebe como argumento o nome do módulo que deseja utilizar.
    
    <aside>
    ⚠️ É importante citar que este módulo passado para o `require` têm que existir dentro da sua máquina.
    
    </aside>
    
    ```jsx
    const path = require("path");
    ```
    
    <aside>
    💡 Vale lembrar que os módulo são apresentados como objetos.
    
    </aside>
    
- **Como criar um módulo para o NodeJS?**
    
    Basicamente, criar módulos significa definir um código em um arquivo separado e defini-lo como exportável. Para fazer isto, basta utilizar o object `module` juntamente como o parâmetro `exports`.
    
    ```jsx
    module.exports = "Código do meu módulo"
    ```
    
    Uma forma muito comum de utilizar o `module.exports` (principalmente para funções) é a seguinte.
    
    ```jsx
    function myFunction() {
    	//meu código
    }
    
    module.exports = myFunction
    ```
    
    Assim, fica definido uma função para ser utilizado pelo módulo exportado, como demonstrado abaixo a utilização do código acima.
    
    ```jsx
    const myFunction = require("./file-module.js")
    
    myFunction()
    ```
    
    Outra forma, é passar para o `module.exports` um objeto, que por sua vez pode conter diversos métodos e atributos. A única diferença dessa forma para a apresentada acima é a forma de utilizar os métodos.
    
    ```jsx
    module.exports = {
    	function myFunction() {
    		//meu código
    	}
    }
    ```
    
    ```jsx
    const myModule = require("./file-module.js")
    
    myModule.myFunction()
    ```
    
    A vantagem da forma apresentada acima é a utilização de vários métodos e atributos dentro de um único módulo.
    
    <aside>
    ⚠️ Existe uma diferença na forma de exportar um módulo próprio e um módulo instalado. Para o **módulo instalado** utilizamos o método `require()` passando como argumento o **nome do módulo**, já para o **módulo próprio**, é definido o método `require()`  mas passando o **caminho do módulo** na máquina.
    
    </aside>
    
- **O que é Process?**
    
    É um objeto que se refere ao processe que está sendo executado no momento pelo Node.
    
    Uma propriedade muito interessante deste objeto é o argv, que traz informações sobre os argumentos de execução do no Node.
    
    ```jsx
    console.log(process.argv);
    ```
    
    Outras informações que são possíveis de visualizar com o objeto process são, o `pid` (id do processo), o `debugPort` (porta que o processo está sendo executado), o `env` (onde está contido as variáveis de ambiente), e diversas outras propriedades, além dos métodos.
    

# NPM - Node Package Manager

- **O que é NPM?**
    
    Basicamente, Node Packege Manager é uma ferramenta que administra pacotes, modulos ou pendências no Javascript Node.js.
    
- **Como verificar se o meu npm está instalado?**
    
    Após baixar e instalar o npm na sua máquina, basta digitar no terminal o comando `npm -v`, se for retornado a versão do seu npm, está tudo certo. Caso seja retornado algum erro no terminal, busque desinstalá-lo e reinstalá-lo.
    
- **Como criar um pacote próprio com o NPM?**
    
    Primeiro, digite o comando `npm init` para gerar um pacote com informações personalizadas ou `npm init -y` para gerar um pacote com informações padrão.
    
    Após criado seu pacote é gerado um arquivo nomeado como package.json. Este arquivo é o pacote gerado, e é nele que está contido todas as informações e configurações importantes para o pacote.
    
- **O que é package.json?**
    
    É um arquivo estruturado como json, e que define um pacote gerenciado pelo NPM.
    
    ```json
    {
      "name": "package_name",
      "version": "1.0.0",
      "description": "",
      "main": "index.js",
      "scripts": {
        "test": "echo \"Error: no test specified\" && exit 1"
      },
      "keywords": [],
      "author": "",
      "license": "ISC"
    }
    ```
    
    - `"name"`: nome do pacote
        
        <aside>
        ⚠️ Se o nome do seu pacote coincidir com algum pacote já existente, poderá ocorrer um erro. Por isso, tome cuidado com o nome dado ao seu pacote.
        
        </aside>
        
    - `"version"`: versão do pacote
    - `"description"`: descrição do pacote
    - `"main"`: o arquivo principal que o Node.js vai executar
    - `"scripts"`: scripts pré-definidos para rodar através do npm.
    - `"test"`: dentro de scripts este parâmetro indica o comando no npm que executa determinado escript. Para executar este comando basta executar o comando `npm run test`
    - `"keywords"`: array contendo palavras-chave que se referem ao pacote
    - `"author"`: nome do autor do pacote
    - `"license"`: licença aplicada ao pacote
- **Como instalar módulos de terceiros?**
    
    Para instalar dependências e módulos de terceiros no seu pacote execute o comando `npm install` seguido do nome do módulo contido no repositório do NPM.
    
    Dessa forma, o módulo e suas dependências serão instalados numa pasta nomeada como node_modules e o módulo será registrado no package-lock.json.
    
    Se for necessário instalar dependências que serão somente utilizadas no momento de desenvolvimento, é possível utilizar a opção `-D` para instalar a dependência como apenas desenvolvimento.
    
    ```bash
    npm install cfonts -D
    ```
    
- **O que é o diretório node_modules?**
    
    É o diretório onde fica armazenado todos módulos de dependências, inclusive as depências deles, ou seja, as dependências das dependências.
    
    Geralmente, este diretório possui um tamanho considerável. E seu tamanho aumenta conformevai sendo instalado mais módulos.
    
    <aside>
    ⚠️ Por boa prática, este diretório não é enviado junto com o seu projeto para o repositório (GitHub, Gitlab, etc). E é utilizando o arquivo .gitignore que este diretório (assim como outros) podem ser igonorados no envio dos arquivos do projeto.
    
    </aside>
    
- **O que é package-lock.json?**
    
    É um arquivo que serve de registro de dependências de módulos para o módulo em questão. Este arquivo permite uma maior e mais simples portabilidade do projeto, já que dentro deste arquivo fica registrado não só todas as depêndencias, mas também todas as informações necessárias para encontrá-las.
    
    De forma simples, este arquivo possui um mapeamento de todas as dependências do projeto.
    
- **Como instalar e atualizar as dependências do projeto?**
    
    Para intalar as dependências registradas no projeto execute o comando `npm install`.
    
    Se o caso for atualização das dependências, execute com comando `npm update`.
    
    Em ambos os casos o npm busca os registros dentro do package.json e depois package-lock.json para instalar as dependências.
    
- **Como criar scripts para rodar com o NPM?**
    
    Para executar scripts com o npm, basta criar um comando dentro da propriedade scripts e executar utilizando o comando `npm run` seguido do comando criado dentro da propriedade scritps.
    
    Geralmente, um dos comandos criados para executar o projeto é o `start`, sendo ele um comando "especial" que pode ser executado sem a necessidade da opção `run`.
    
    ```bash
    npm start
    ```
    
    Todo script criado é utilizando a linguagem shell.
    
- **O que é um pacote global?**
    
    É um módulo instalado de forma que fique disponibilizado no seu computador local, ou seja, este módulo fica disponível para qualquer outro projeto sem a necessidade de baixa-lo novamente.
    
- **Como instalar um pacote de maneira global?**
    
    Basta utilizar a opção `-g` (que simboliza o `--global`) após o comando npm install seguido do módulo desejado.
    
    ```bash
    npm install opn -g
    ```
    
    Para saber onde está instalado seus pacotes globais basta digitar `npm root -g`, que será retornado o caminho para a pasta node_modules de módulo globais.
    
- **Como remover pacotes instalados com NPM?**
    
    De forma simples, utilize a opção unistall seguido do pacote de deseja desinstalar, como demonstrado abaixo.
    
    ```bash
    npm uninstall opn
    ```
    
    A mesma opção é válida para pacotes globais.
    
    ```bash
    npm uninstall opn -g
    ```
    
- **Como funciona as versões?**
    
    Quando nos deparamos com algo parecido com 2.16.2, podemos estranhar a primeira vista, mas entender o que significa cada número deste é importante quando lidamos com desenvolvimento.
    
    Para entender melhor, 2.16.2 pode ser interpretado como **majar**.**minor**.**patch**. Observe uma definição simples do que cada parte do versionamento significa.
    
    - **major**: específica a versão do projeto, e dependendo da versão que estiver pode ocorrer problemas de incompatibilidade com o projeto dependente.
    - **minor**: específica resoluções de bugs ou features que não causam incompatibilidade de versões.
    - **patch**: especifica resolução de algum bug ou feature do pacote.
    
    Geralmente, dentro do package.json é visto algo como ^2.16.2. O sinal `^` significa que se for atualizado a dependência somente será atuliazado o **minor** e **patch**. Já caso seja visto algo como ~2.16.2, significa que será atualizado apenas o **patch**. Agora se for visto o símbolo `*` significa que será atualizado todo o versionamento (**major**, **minor** e **patch**). E se for visto algo como 2.16.2 (sem **nenhum símbolo** na frente) significa que não será atualizado nada.
    
- **Como definir a versão do módulo a ser instalado?**
    
    Para específicar a versão utiize o sinal `@` (arromba), como demonstrado a seguir.
    
    ```bash
    npm install opn@1.0.0
    ```
    
    Assim, o pacote instalado utilizará a versão 1.0.0. Inclusive, dentro do package-lock.json e no node_modules a versão também é atualizada para a nova versão instalado.
    
    Se a intenção é instalar a última versão do pacote, utilize a palavra `latest` após o símbolo `@`.
    
    ```bash
    npm install opn@latest
    ```
    
- **Como obter informações sobre as dependências do projeto?**
    
    Caso queira visuliazar as atualiazações ou outras informações referentes a versionamento de dependências execute o comando `npm outdated` que será retornado algo como
    
    ```bash
    Package  Current  Wanted  Latest  Location             Depended by
    cfonts     1.0.0   1.2.0   2.9.2  node_modules/cfonts  npm
    ```
    
- **Como atualizar todas as dependências?**
    
    Utilize o comando `npm upgrade` para atualizar todas as dependências do seu pacote.
    

# BestMe App: Interagindo com o aplicativo

- **O que é stdout?**
    
    É uma propriedade pertencente ao `process`, e se refere a processo de saída padrão. Um método muito utilizado dessa propriedade é o `write`, que por sua vez é muito semelhante ao método `printf()` do C.
    
    ```bash
    process.stdout.write("Uma mensagem");
    ```
    
    É importante saber que este parâmetro roda por baixo do `console.log()` também.
    
    Este método é visto como um processo síncrono.
    
- **O que é stdin?**
    
    É uma propriedade pertencente ao `process`, e se refere a processo de entrada padrão. O método comumente utilizado desta propriedade é o on(), que por sua vez é semelhante ao método `scanf()` do C também.
    
    É impotante citar que no método on() comumente é utilizado o primeiro parâmetro como `"data"`, que se refere ao tipo de espera do método on. E o segundo parâmetro é uma função.
    
    ```bash
    process.stdio.on("data", data => {
    	process.stdout.write(data);
    });
    ```
    
    Este método é visto como um processo assíncrono.
    
- **Como definir um processo para ficar "escutando" eventos?**
    
    O método `on()` possui a capacidade de ficar monitorando determinados eventos, como visto anteriormente no `process.stdin.on()`.
    
    Relembrando o fluxo do EVENT LOOP, quando um `on()` aparece no EVENT QUEUE e é reconhecido pelo EVENT LOOP ele é movido para o WORKER THREADS até que o evento aguardado aconteça. Assim, quando o evento monitorado é reconhecido o EVENT LOOP move o processo `on()` novamente para o EVENT QUEUE. E esse ciclo se repete até que seja reconhecido algum parâmetro de parada para o processo.
    
    Dessa forma, podemos definir o monitoramento de eventos gatilhos, como por exemplo o `exit()`.
    
    ```bash
    process.stdin.on("data", data => {
    	if(data == "z") {
    	  process.exit();
      } else {
    		process.stdout.write(data.toString().trim());
      }
    });
    
    process.on("exit", () => {
    	process.stdout.write("Bye!");
    });
    ```
    
    Outro exemplo, um pouco mais complexo é:
    
    ```bash
    const questions = [
        "O que aprendi hoje?",
        "O que me deixou aborrecido? E o que eu poderia fazer para melhorar?",
        "O que me deixou mais feliz?",
        "Quantas pessoas eu ajudei hoje?"
    ];
    
    const ask = (index = 0) => {
        return process.stdout.write(`${questions[index]}\n> `);
    };
    
    const answers = []
    
    ask();
    
    process.stdin.on("data", data => {
        answers.push(data.toString().trim());
        if(answers.length < questions.length) {
            ask(answers.length);
        } else {
            process.exit();
        }
    });
    
    process.on("exit", () => {
        process.stdout.write("\n\nMY ANSWERS\n");
        
        for(let cont = 0; cont < answers.length; cont++) {
            process.stdout.write(`>> ${answers[cont]}\n`);
        };
    });
    ```
    
    Pode-se dizer que o `on()` é o culpado pelo assíncronismo de processos.
    
    <aside>
    ⚠️ Para mais informações sobre process, stdin, stdout e on acesse a [documentação oficial do Node.js](https://nodejs.org/api/process.html).
    
    </aside>
    

# Timers

- **Como funciona o setTimeout?**
    
    SetTimeout é uma funçao que executa outra função após um número pré-definido de milessegundos.
    
    Essa função é composta basicamente por dois parâmetros, o primeiro é a função a ser executada e o segundo é o tempo que deve-se esperar para executar a função.
    
    ```jsx
    const timeOut = 3000;
    const finished = () => process.stdout.write("done");
    
    setTimeout(finished, timeOut);
    ```
    
    A função a ser chamada é uma função para callback que será executada depois do tempo determinado no segundo parâmetro.
    
    <aside>
    ⚠️ É interessante citar que as funções de callback como a aplicada no setTImeout é uma função assíncrona, como se pode observar com está modificação no código anterior.
    
    </aside>
    
    ```jsx
    const timeOut = 3000;
    const finished = () => process.stdout.write("done");
    
    setTimeout(finished, timeOut);
    console.log("Bye");
    ```
    
- **Como funciona o clearTimeout?**
    
    Basicamente, a tarefa desta função é cancelar a função setTimeout, ou seja, se antes de ser finalizado o tempo do setTimeout for executado um clearTimeout, é buscado no WORKER THREADS o setTimeout e ele é cancelado.
    
    ```jsx
    const timeOutA = 3000;
    const timeOutB = 4000;
    const finishedA = () => {
        process.stdout.write("done A\n");
        clearTimeout(timerB);
    };
    
    const finishedB = () => process.stdout.write("done B\n");
    
    const timerA = setTimeout(finishedA, timeOutA);
    const timerB = setTimeout(finishedB, timeOutB);
    
    timerB;
    timerA;
    ```
    
- **Como funciona o setInterval?**
    
    Assim como a função `setTimeout()` a `setInterval()` também é um processo assíncrono, mas neste caso, a função função de callack é executada repetidamente com o intervalo de tempo definido.
    
    ```jsx
    const interval = 1000;
    const checker = () => {
        console.log("checking");
    }
    
    setInterval(checker, interval);
    console.log("Start");
    ```
    
    A repetição da função naturalmente não possui limite, dessa forma, deve ser aplicada um `clearInterval()`.
    
- **Como funciona o clearInterval?**
    
    Parecido com a função `clearTimeout()` a função `clearInterval()` serve para cancelar a função `setInterval()`. De forma natural, está é a forma mais comum e correta que têm para interromper a repetição da função `setInterval()`.
    
    ```jsx
    const interval = 1000;
    const checker = () => {
        console.log("checking");
        clearInterval(timer);
    }
    
    const timer = setInterval(checker, interval);
    timer
    console.log("Bye");
    ```
    

# Events

- **O que é Event Module?**
    
    É um módulo contido dentro do core do Node.js, e este seve para, disparar eventos, ouvir eventos e identificar eventos. Além das suas funções básicas, o Event Module é a base para muitos outros módulos como, http, stream, file, system, etc.
    
    Uma das formas  de visualizar o Event Module é importante ele.
    
    ```jsx
    const events = require("events");
    
    console.log(events);
    ```
    
    Dessa forma, a saída para o script acima será algo como demonstrado abaixo.
    
    ```jsx
    <ref *1> [Function: EventEmitter] {
      once: [AsyncFunction: once],
      on: [Function: on],
      getEventListeners: [Function: getEventListeners],
      EventEmitter: [Circular *1],
      usingDomains: false,
      captureRejectionSymbol: Symbol(nodejs.rejection),
      captureRejections: [Getter/Setter],
      errorMonitor: Symbol(events.errorMonitor),
      defaultMaxListeners: [Getter/Setter],
      setMaxListeners: [Function (anonymous)],
      init: [Function (anonymous)],
      listenerCount: [Function (anonymous)]
    }
    ```
    
    <aside>
    ⚠️ Para saber mais sobre as propriedades do Event Module acesse a [documentação oficial do Node.js](https://nodejs.org/api/events.html).
    
    </aside>
    
- **O que é o Event Emitter?**
    
    A função do Event Module é oferecer funcionalidades do Event Module, como já citado antes, o disparar eventos, escutar eventos e reconhecer eventos.
    
    Para acessá-la basta fazer como demonstrado abaixo.
    
    ```jsx
    const {EventEmitter} = require("events");
    
    const emmiter = new EventEmitter();
    ```
    
- **Como disparar eventos?**
    
    Utilizando a função `emit()` é possível disparar eventos dentro do nosso ambiente em execução. Para isso é necessário passar como parâmetro uma string que representa o nome do evento.
    
    ```jsx
    const {EventEmitter} = require("events");
    
    const emitter = new EventEmitter();
    
    emitter.emit("Welcome");
    ```
    
    Também é possível passar argumentos para o evento.
    
    ```jsx
    const {EventEmitter} = require("events");
    
    const emitter = new EventEmitter();
    
    emitter.emit("Welcome", "Argument");
    ```
    
- **Como "escutar" eventos?**
    
    A partir da função `on()` é possível monitorar eventos, sendo necessário apenas passar como primeiro parâmentro o nome do evento que deseja "escutar", e a ação que deseja realizar assim que o evento for detectado.
    
    ```jsx
    const {EventEmitter} = require("events");
    
    const emitter = new EventEmitter();
    
    emitter.on("Welcome", () => {
    	console.log("Hi");
    });
    
    emitter.emit("Welcome");
    ```
    
    Assim como a função `emit()` pode passar argumentos, a função `on()` pode recebe-los.
    
    ```jsx
    const {EventEmitter} = require("events");
    
    const emitter = new EventEmitter();
    
    emitter.on("Welcome", (name) => {
    	console.log("Hi", name);
    });
    
    emitter.emit("Welcome", "João");
    ```
    
    Se caso for necessário detectar o evento uma única vez, pode-se utilizar a função `once()` no lugar da função `on()`.
    
    ```jsx
    const { EventEmitter } = require("events");
    
    const emitter = new EventEmitter();
    
    emitter.once("Welcome", name => {
        console.log("Hy", name);
    });
    
    emitter.on("Goodbye", name => {
        console.log("Bye bye", name);
    });
    
    emitter.emit("Welcome", "Antonio");
    emitter.emit("Welcome", "Julio");
    emitter.emit("Goodbye", "Julio");
    ```
    
- **Como o Event Module é a base para outros módulos?**
    
    O Event Module é um módulo muito importante dentro do ambiente de execução do Node.js, pois ele já possui diversas funcionalidades muito úteis para estes outros módulos, o que faz com que ele seja geralmente herdado por este módulos já que ele que isso é possível.
    
    Para demonstrar como ele pode ser herdado, o código abaixo exemplifica a utilização do `EventEmitter` como classe pai para outra classe (o que acontece com outros módulos também nativos do Node.js). Para demonstrar esta aplicação é utilizado `inherits()` (uma função abstraída do módulo `util`).
    
    ```jsx
    const { EventEmitter } = require("events");
    const { inherits } = require("util");
    
    const soundTime = 2000;
    
    function Character (name) {
        this.name = name;
    };
    
    inherits(Character, EventEmitter);
    
    const chapolin = new Character("Chapolin Colorado");
    
    chapolin.on("help", phrase => {
            console.log(phrase);
    });
    
    console.log("\n\n-Oh! E agora, quem poderá me defender??\n")
    
    setTimeout(() => {
        chapolin.emit("help", `-EEEuuuu o ${chapolin.name}!!`);
    }, soundTime);
    ```
    
    Vale ressaltar aqui que, a função `inherits()` têm a tarefa passar uma classe como herança para outra, como é realizado acima, onde a classe no segundo parâmetro é passado como herança para a classe no primeiro parâmetro.