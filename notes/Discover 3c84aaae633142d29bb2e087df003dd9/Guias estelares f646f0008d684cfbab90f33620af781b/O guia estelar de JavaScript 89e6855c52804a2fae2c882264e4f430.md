# O guia estelar de JavaScript

> *Site: [https://app.rocketseat.com.br/node/o-guia-estelar-de-java-script](https://app.rocketseat.com.br/node/o-guia-estelar-de-java-script)*
> 

Este tópico é fundamental para conhecer todo o básico de Javascript e o básico do seu poder dentro da web.

### Introdução

- **O que é JavaScript Core?**
    
    É uma linguagem de programação que roda dentro do browser do usuário (front-end), permitindo que quando o usuário possa interagir com a página, seja clicando num botão, passando o ponteiro do mouse em determinada parte da página, etc. E pode rodar também no computador (back-end) realizando tarefas como gerenciamento de filas, inserindo registros em banco de dados, entre outras tarefas.
    
    Atualmente com essa linguagem podemos criar aplicações web, mobile, desktop, e para diversos outros fins.
    

### Primeiros passos

- **Como funciona a sintaxe do JavaScript?**
    
    A sintaxe é a escrita correta de uma linguagem, ou seja, a estrutura da escrita de uma linguagem.
    
    > Toda linguagem têm sintaxe!
    > 
    
    Podemos analisar a sintaxe do Javascript atavés do comando abaixo.
    
    ```jsx
    console.log("Hello world") //comando para exibir Hello World na tela
    ```
    
    Apartir da escrita acima podemos ter erros comuns de sintaxe que podem impedir do funcionamento correto do nosso código. Esses **erros** podem ser:
    
    ```jsx
    consolelog("Hello world")
    //ou
    console.log("
    Hello World")
    //ou
    console.log("Hello"world")
    ```
    
    > Uma boa comunicação necessita de uma boa sintaxe.
    > 
- **Como executar o o Javascript?**
    
    Temos 3 formas básicas de executar códigos em Javascript como demonstrado abaixo.
    
    1. através de browser, ou melhor, o devtools. Para executar nosso javascript no devtools podemos acessá-lo com F12 e ir na aba console.
        
        ![O%20guia%20estelar%20de%20JavaScript%2089e6855c52804a2fae2c882264e4f430/Captura_de_Tela_rea_de_Seleo_20210217174948.png](O%20guia%20estelar%20de%20JavaScript%2089e6855c52804a2fae2c882264e4f430/Captura_de_Tela_rea_de_Seleo_20210217174948.png)
        
    2. através da ferramenta [Codepen.io](https://codepen.io/pen) que basicamente é um editor online, onde você pode escrever códigos HTML, CSS e Javascript e já visualizar o resultado na área de preview.
    3. outra forma é através do [VSCode](https://code.visualstudio.com/). Dessa forma você instala o editor/IDE VSCode na sua máquina e trabalha com os códigos locais, criando diretórios, arquivos, etc.
    4. Entre outras formas como [Gipod](https://www.gitpod.io/), [CodeSpaces](https://github.com/features/codespaces), etc.
- **Como adicionar um arquivos JS em nosso projeto?**
    
    Para adicionar arquivos Javascript no projeto temos que definir dois pontos básicos, "em qual momento queremos que rode nosso script?" e "nosso script vai ser local ou externo?".
    
    Para definirmos o momento de execução do script, é importante citar que a leitura dos scripts *.js* é feito da mesma forma que no documento *.html* (de cima para baixo). Dessa forma se quisermos que o nosso script execute quando começar a carregar a página adicionamos a tag `<script>` dentro da tag `<header>` no nosso documento .html.
    
    ```jsx
    <header>
    	<meta charset="UTF-8">
    	<title>Minha página</title>
    	<script>
    		console.log("Carregando minha página ...")	
    	</script>
    </header>
    ```
    
    Mas se quisermos que o escript execute em outro momento do carregamento do documento, a tag `<script>` e definida dentro da tag `<body>` no momento que desejado.
    
    ```jsx
    <body>
    	<h1>Corpo da minha página</h1>
    	<script>
    		console.log("Página caregada.")
    	</script>
    </body>
    ```
    
    E para definirmos o local do script precisar ter atenção para referênciar corretamente o script, para isso podemos fazê-lo de duas formas, como exemplificado abaixo:
    
    - **script local**
        
        ```jsx
        <script>
        	console.log('Hello world')
        </script>
        ```
        
    - **script externo**
        
        ```jsx
        <script src="script.js">
        </script>
        ```
        
    
    Outro ponto bacana de se manter na criação de arquivos, seja eles Javascript ou não, é a padronização nos nomes e a não utilização de caracteres especiais e números.
    
- **Como criar um comentário em JS?**
    
    Comentários em Javascript são importantes para escrever anotações dentro do seu documento *.js* ou até mesmo ignorar trechos do script. Os comentários em JS podem ser feitos de duas formas, em linha ou me bloco.
    
    - **em linha**, nos utilizamos o `//` para definir que tudo que vier após esse sinal é comentário
        
        ```jsx
        // isso é um comentário
        ```
        
    - **em bloco**, onde utilizamos o `/*` no início  e `*/` no final. Dessa forma tudo o que estiver dentro desses sinais é comentário.
        
        ```jsx
        /*
         Isso também é um comentário
        */
        ```
        

### Tipos de dados

- **Quais os tipos de dados da linguagem Javascript?**
    
    Os tipos de dados são estruturas básicas de dados, onde cada estrutura recebe um tipo diferente de valor.
    
    Em muitos lugares geralmente temos 9 tipos de dados, sendo estes podendo ser divididos em 3 categorias:
    
    - **Primitives/Primitive value**, sendo que estes os tipos contidos nessa categoria não são objetos e seus valores são imutáveis, ou seja, cada tipo possui seu valor de forma única, sendo que uma *string* só pode ser string e seus valores são únicos ("ABC" é diferente de "abc") e o mesmo vale para outros tipos.
        - **String**
        - **Number**
        - **Boolean**
        - **Undefined**
        - **Symbol**
        - **BigInt**
    - **Structural**, sendo que esta categoria define que os seus tipos possuem estruturas definidas
        - **Object**, este de dado possui propriedades/atributos e funcionalidades/métodos.
            - **Array**
            - **Map**
            - **Set**
            - **Date**
            - entre outros [**Standard Objects**](https://developer.mozilla.org/pt-PT/docs/Web/JavaScript/Reference/Global_Objects).
        - **Function**
    - **Structural Primitive/Structural Root Premitive**, sendo que este tipo possui uma estrutura definida (como um obejto) e possui seu valor imutável.
        - **Null**
    
    Mas essa definição de divisão possui várias versões, conforme a fonte e evolução da linguagem. Para mais informações acesse os links abaixo.
    
    - ***Links extras***
        
        [ECMAScript Language Specification - ECMA-262 Edition 5.1](https://262.ecma-international.org/5.1/#sec-4.3.2)
        
        [Estrutura de dados do Javascript](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Data_structures)
        
        [Recursos de linguagem JavaScript](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Language_Resources)
        
    
    > É possível aprender 80% de uma língua, com cerca de 20% do seu vocabulário.
    > 
- **O que é String?**
    
    É uma cadeia de caracteres, como `abc`, `ABC`, `@B$`, etc. Dessa forma podemos definir *string* sequencia de letras, palavras, entre outros.
    
    Na linguagem Javascript a *string* está contida dentro de aspas duplas`"`, aspas simpes`'` ou *template literals* ``` (também chamada de *template string*), como representado abaixo.
    
    ```jsx
    "Isso é uma string"
    // ou
    'Isso é uma string'
    //ou
    `Isso é uma string`
    ```
    
    Um caso muito comum de se utilizar a *string* no Javascript é no comando `console.log` (que mostra uma saída), como o exemplo abaixo.
    
    ```jsx
    console.log("Hello world")
    ```
    
    Uma dúvida muito comum na utilização das aspas, é qual e quando utilizar. Para essa dúvida o ideal é análisar a string que deseja aplicar, por exemplo, no caso de uma *string* que vai ser mostrada aspas duplas, o ideal é envolver a *string* em aspas simples, e o mesmo para o contrário.
    
    ```jsx
    console.log("I'm a developer.")
    // ou
    console.log('Eu estou "ligado".')
    ```
    
    No caso da utilização do *template literals* obtemos mais algumas vantagens como:
    
    - **multi-linhas**
        
        ```jsx
        console.log(`
        Isso está na primeira linha
        
        e
        
        isso está na quinta linha`),
        ```
        
    - utilização de **aspas duplas e simples** na mesma *string*
        
        ```jsx
        console.log(`Posso fazer "qualquer" coisa dentro dessa string kkk'.`)
        ```
        
    - **aplicação de expressões** dentro da *string* de forma simples
        
        ```jsx
        idade = 26
        console.log(`Minha idade é ${idade}.`)
        // ou
        console.log(`Minha idade é ${idade - 1}.`)
        ```
        
- **O que é Number no JS?**
    
    *Number* significa números, e dentro do Javascript (como em outras linguagens) podemos ter subtipos dentro desse tipo como:
    
    - **Integer**, que são números inteiros. Por exemplo `1`, `100`, `26`, etc.
    - **Float**, que são números reais. Por exemplo `0.3`, `1.6`, `17.59`, `101.526`, etc.
    - **NaN** (Not a Number), que simboliza valores que não são reconhecidos como números. Uma situação que pode resulta nesse tipo de dados é
        
        ```jsx
        console.log(12 / 'hello')
        ```
        
    - **Infinity**, que representa valores infinitos.
- **O que é Boolean?**
    
    É um tipo de dado que contém apenas dois valores, `true` (verdadeiro) e `false` (falso). Esse tipo de valor pode ser declarado
    
    ```jsx
    verdadeiro = true
    //ou
    falso = false
    ```
    
    ou pode ser obtido através de uma expressão de comparação.
    
    ```jsx
    idade = 19
    adulto = idade > 18
    ```
    
- **O que é Undefined e qual a sua diferença com Null?**
    
    O *undefined* é um tipo de dado indefinido, ou seja, não existe.
    
    O *null* representa o valor nulo, ou seja, é um objeto que não há nada dentro dele.
    
    > Comparando isso *undefined* e *null* são diferentes.
    > 
    
    Para explicar melhor, *undefined* é **algo que não existe** na linguagem e *null* é algo que existe na linguagem mas **não há nenhum valor dentro**.
    
    Podemos fazer uma análogia com uma **caixa**. A caixa representa um tipo de dado ou objeto. No caso de um tipo *number*, existe uma caixa com um número dentro. No *null* existe uma **caixa vázia** (ou seja, sem valor) e no caso do *undefined* **não existe caixa**.
    
    - Prefere uma imagem para ilustrar?
        
        ![O%20guia%20estelar%20de%20JavaScript%2089e6855c52804a2fae2c882264e4f430/Untitled.png](O%20guia%20estelar%20de%20JavaScript%2089e6855c52804a2fae2c882264e4f430/Untitled.png)
        
- **O que é Object?**
    
    É um tipo de dado estrutural, sendo que ele contém **propriedades/atributos** e **funcionalidades/métodos**.
    
    Podemos comparar *object* com objetos reais, por exemplo um celular:
    
    <aside>
    📱 **propriedades /atributos**: tamanho, peso, cor, marca, etc.
    **funcionalidades/métodos**: realiza ligações, manda mensagens, etc.
    
    </aside>
    
    Dessa forma cada propriedade/atributo possui um valor e cada funcionalidade/método possui uma descrição lógica de passos.
    
    Para criar um objeto no Javascript fazemos da seguinte forma `{priopriedade: "valor", funcionalidade: nomedafuncionalidade(){ ... } }`, como exemplificado abaixo.
    
    ```jsx
    {
    	name: "Fulano",
    	idade: 20,
    	andar: function() {
    		console.log("andando")
    		// sequência de instruções para andar
    	}
    }
    ```
    
- **O que é Array?**
    
    Array ou vetor é um tipo de dado estrutural  que agrupa dados como uma lista. Os valores contidos dentro um *array* podem ser *numbers*, *strings*, *objects*, *booleans*, outros *arrays*, entre outros, mas sempre separados por vírgulo, como demonstrado abaixo.
    
    ```jsx
    [1001, "Hello", {nome: "Pedro", idade: 10}, true]
    ```
    

### Variáveis

- **O que são variáveis no JS?**
    
    Váriaveis de forma geral são "espaços" que armazenam dados em algum tipo de memória.
    
    No Javascript (como em outras linguagens), variáveis (ou *identifier*) são nomes simbólicos que recebem algum tipo de dado ou serve como atalho para algum código.
    
    Para criarmos variáveis no JS podemos utilizar a palavra reservada `var` seguindo a seguinte sintaxe:
    
    <aside>
    ✏️ <tipo da variàvel> + <nome da variável>
    
    </aside>
    
    Já no script pode ser feito da seguinte forma:
    
    ```jsx
    var idade
    ```
    
    Já para declarar uma variável atribuindo um valor podemos seguir o exemplo abaixo:
    
    ```jsx
    var idade = 20
    ```
    
    Outro ponto interessante sobre variáveis no JS é que a linguagem é fracamente tipada e dinâmica, ou seja, as váriaveis podem mudar de tipo a qualquer momento, como demonstrado abaixo:
    
    ```jsx
    var valor = "Hello"
    varlor = 16
    ```
    
    Temos também outras palavras reservadas assim como `var` para declarar diferentes tipos de variáveis, sendo essas palavras a `let` e `const`, sendo que as palavras `var` e `let` simbolizam explicitamente variáveis e a palavra `const` simboliza um dado constante, ou seja, uma vez atribuído um valor a esse tipo não pode mais ser alterado.
    
- **Qual a diferença de var, let e const?**
    
    A diferença básica dos diferentes tipos de variáveis (`var`, `let` e `const`) é o escopo. O escopo (ou *scope*) é o que determina a visibilidade de uma variável dentro da linguagem.
    
    O conceito de escopo dentro das linguagens programação segue as definições de *Block statement* (ou declaração de bloco), onde cada bloco define um escopo (também conhecido como escopo de bloco ou *block-scoped*). O *block-scoped* é iniciado com o sinal de `{` (chave de abertura) e finalizado com o sinal de `}` (chave de fechamento), como demonstrado abaixo:
    
    ```jsx
    { // início do bloco
    	// espaço para o código pertencente ao bloco
    } // final do bloco
    ```
    
    No caso do Javascript tipos de váriaveis seguem as seguintes definições de escopo:
    
    - `var` é uma variável global e local, ou seja, ela é visível para o escopo global e também para o escopo em que foi declarado. Para entendermos melhor estas definições temos os exemplos a seguir.
        
        ```jsx
        { //início do escopo global
        	{ // início do escopo local
        		var x = 1
        		console.log("X existe?", x)
        	} // fim do escopo local
        } // fim do escopo global
        ```
        
        ```jsx
        { //início do escopo global
        	console.log("X existe?",x)
        	{ // início do escopo local
        		var x = 1
        	} // fim do escopo local
        } // fim do escopo global
        ```
        
        ```jsx
        { //início do escopo global
        	{ // início do escopo local
        		var x = 1
        	} // fim do escopo local
        	console.log("X existe?",x)
        } // fim do escopo global
        ```
        
    - `let` é uma variável local, ou seja, só é visível dentro do escopo em que foi declarada e escopos filhos. Para entender a situaçao da `let` basta analisar as seguintes situações.
        
        ```jsx
        { //início do escopo global
        	{ // início do escopo local
        		let x = 1
        		console.log("X existe?", x)
        	} // fim do escopo local
        } // fim do escopo global
        ```
        
        ```jsx
        { //início do escopo global
        	{ // início do escopo local
        		console.log("X existe?", x)
        		let x = 1
        	} // fim do escopo local
        } // fim do escopo global
        ```
        
        ```jsx
        { //início do escopo global
        	console.log("X existe?", x)
        	{ // início do escopo local
        		let x = 1
        	} // fim do escopo local
        } // fim do escopo global
        ```
        
        ```jsx
        { //início do escopo global
        	{ // início do escopo local
        		let x = 1
        	} // fim do escopo local
        	console.log("X existe?", x)
        } // fim do escopo global
        ```
        
        ```jsx
        { //início do escopo global
        	let x = 1
        	{ // início do escopo local
        		console.log("X existe?", x)
        		x = 0
        	} // fim do escopo local
        	console.log("X existe?", x)
        } // fim do escopo global
        ```
        
    - `const` é uma variável local, ou seja, só é visível dentro do escopo em que foi declarada como já demonstrado nos exemplos acima, com a ressalva de que mesmo a variável sendo reconhecida em escopos filhos, seu valor não pode ser alterado, pois esse tipo não é uma variável e sim uma constante. Para entender melhor olhe os exemplos abaixo.
        
        ```jsx
        { //início do escopo global
        	const x = 1
        	{ // início do escopo local
        		console.log("X existe?", x)
        		x = 0
        	} // fim do escopo local
        } // fim do escopo global
        ```
        
        Mas caso seja necessário atribuir este novo valor para uma constante com este mesmo nome, podemos criar uma nova constante com o mesmo nome no outro escopo, como demonstrado abaixo.
        
        ```jsx
        { //início do escopo global
        	const x = 1
        	{ // início do escopo local
        		const x = 0
        	} // fim do escopo local
        } // fim do escopo global
        ```
        
- **Como nomear variáveis?**
    
    Dar nomes para variáveis é uma prática muito importante e necessária, o que pode facilitar muito na leitura do código e manutenção do mesmo.
    
    Alguns pontos necessários para nomear variáveis em Javascript são:
    
    - O JS segue o conceito de **Case Sensitive**, ou seja, ele difere caracteres maiúsculas de  minúsculas, como também de caracteres com acentuação e sem acentuação.
    - O JS **aceita caracteres Unicode**, ou seja, as variáveis podem conter aspas, acentuações, [entre outros](https://unicode-table.com/pt/#latin-1-supplement), mesmo que não seja indicado.
    
    Sabendo desses pontos podemos definir algumas coisas que eu **posso fazer**
    
    - iniciar os nomes de variáveis com `$` e `_`.
    - iniciar os nomes com com letras
    - colocar acentos nos nomes
    
    e algumas coisas que eu **não posso fazer**
    
    - iniciar os nomes de variáveis com números
    - utilizar espaços em branco no nome
    
    Dessa forma o aconselhável para criar nomes de variáveis no Javascript é:
    
    - criar nomes que fazem sentido para o código como `nomeCliente` para atribuir o nome de um cliente do seu sistema. Dessa forma o próprio nome explica o que a variável é ou faz.
    - se possível utilizar nomes em inglês, já que a maior parte do mundo da proramação está em inglês. Dessa forma há uma grande chance de outros desevolvedores compreenderem seu código. É claro, esse conselho não se aplica a casos isolados como o projeto de uma empresa onde só trabalha chineses por exemplo.
    - utilizar [Camel Case](https://pt.wikipedia.org/wiki/CamelCase) ou [Snake Case](https://en.wikipedia.org/wiki/Snake_case), para que assim os nomes das variáves do seu código se mantenham padronizados.

### Praticando e avançando

- **Como é declaro uma variável e como é atribuído um valor a ela?**
    
    Para declarar uma variável decidimos primeiro o tipo dela e em seguida o nome dela. Para atribuir um valor a ela utilizamos o sinal `=` e o valor que queremos armazenar nela, como é mostrado a seguir.
    
    ```jsx
    // <tipo da variável> <nome da variável> = <valor da variável>
    let idade = 30
    ```
    
- **Pode declarar mais de uma variável na mesma linha?**
    
    Sim, mas na mesma linha só é possível declarar variáveis do mesmo tipo, sendo elas separadas por `,` (vírgula). Caso queira declarar mais um tipo de variável é necessário utilizar outras linhas para declarar as outras variáveis, como visto abaixo.
    
    ```jsx
    var name, age, address
    let isHuman, isWoman, isOld
    const pi, company
    ```
    
- **Como concatenar variáveis no JS?**
    
    Concatenar é juntar duas coisas. Para juntarmos ou concatenarmos variáveis da forma mais simples é utilizando o sinal de + (soma) como demonstrado abaixo.
    
    ```jsx
    {
    	var nome = "Fulano", idade = 21
    	var texto = "O "+nome+" têm "+idade+" anos."
    	console.log(texto)
    }
    ```
    
    O mesmo posso ser feito da seguinte forma
    
    ```jsx
    {
    	var nome = "Fulano", idade = 21
    	console.log("O "+nome+" têm "+idade+" anos.")
    }
    ```
    
    A concatenação é muito útil quando temos um modelo de texto (por exemplo) e queremos apenas variar alguns pontos nesse texto, como nomes, endereços, etc.
    
- **Como interpolar variáveis?**
    
    A interpolação é bem parecida com a concatenação, mas insere diretamente a variável utilizando a *[string literals](O%20guia%20estelar%20de%20JavaScript%2089e6855c52804a2fae2c882264e4f430.md)* como demosntrado a seguir.
    
    ```jsx
    {
    	var nome = "Fulano", idade = 21
    	console.log(`O ${nome} têm ${idade} anos.`)
    }
    ```
    
- **Como utilizar um Objects?**
    
    Para utilizar um objeto primeiro é necessário armazer esse objeto como o exemplo a seguir
    
    ```jsx
    const person = {
    	name: "Fulano",
    	age: 22,
    	address: "Algum lugar"
    }
    ```
    
    após isso temos a possibilidade de acesso a atributos/métodos desse objeto   utilizando o `.` (ponto) e nome do atributo/método após o nome do objeto
    
    ```jsx
    console.log(`O ${person.name} têm ${person.age} anos.`)
    ```
    
- **Como trabalhar com Arrays?**
    
    Array é um object, e como sabemos os objects possuem atributos e métodos, mas um conceito importante para trabalhar com arrays é posição de valores. Para acessar um determinado valor dentro de um array utilizamos o índice de cada valor (sendo que cada valor possui um índice único no momento de acesso ao valor onde o menor índice é 0). Para referênciarmos estes indices no JS utilizamos o valor do índice entre `[` (abre colchetes) e `]` (fecha colchetes) como podemos observar abaixo.
    
    ```jsx
    {
    	var animals = ["Tiger", "Lion", "Dog", "Cat"]
    	console.log(animals[1])
    }
    ```
    
    Vale citar aqui que um atributo de array interessante para ser utilizado é o `length` que nos retorna a quantidade de dados contidos no array. Para exemplificar o acesso ao length temos o exemplo abaixo.
    
    ```jsx
    {
    	var animals = ["Tiger", "Lion", "Dog", "Cat"]
    	console.log(animals.length)
    }
    ```
    

### Funções

- **O que são Functions no Javascript?**
    
    Functions é um escopo declarado que pode ser utilizado para guardar instruções que seram executadas em outros momentos ou em mais de uma vez. As Functios basicamente servem como atalhos para escopos separados, dessa forma há uma melhor visibilidade e melhor controle do código. Assim podemos aumentar o controle do sistema e facilitar a manunteção do código fonte.
    
    Por convenção o nome de uma Function deve retratar o significa dela.
    
- **Como é declarada uma Function?**
    
    Há várias formas de declarar uma função:
    
    - **Função (explícita)**: É uma função nomeada e explicita para o escopo em que está inserida. É declarada com a palavra reservada `fuction`, o nome da função (por convenção o nome da função deve explicar o que a função faz),o símbolo `(` (para abrir o escopo de parâmetro de entrada), os parâmetros para a função (se necessário), o símbolo `)` (para fechar o escopo de parâmetro de entrada), o símbolo `{` (para abrir o escopo), o código que desaja armazenar no escopo da função e o símbolo `}` (para fechar o escopo).
        
        ```jsx
        function minhaFuncao(meusArgumentos) {
        	// código
        }
        ```
        
        Esse tipo de função é chamada simplesmente pelo nome e passagem dos argumentos, como `minhaFuncao(passandoArgumentos)`. Sendo que na chamada de uma função passamos parâmetros e já na função os argumentos se tornam parâmentros.
        
    - **Function Anonymous ou Function Expression**: É uma função atribuída a uma constante ou variável. Para declarar essa função primeiro declaramos uma constante ou variável atribuindo a ela uma função como o exemplo acima mas sem o nome da função.
        
        ```jsx
        const sum = function(num1, num2) {
        	result = num1 + num2
        	return result
        }
        ```
        
        Para chamar uma functions expression utilizamos básicamente a mesma técnica, o nome da função passando os argumentos.
        
- **O que é Return?**
    
    O `return` dento de uma função serve basicamente para retornar um valor ou expressões para o ponto de chamada da função. Quando o a execução do código encontra a palavra reservada return a execução dentro do escopo da função para e retorna também para o ponto de chamada da função.
    
- **O que é Function Scope?**
    
    É o conceito do escopo pertencente a uma função. O escopo de uma função têm o mesmo comportamento explicado [anteriormente](O%20guia%20estelar%20de%20JavaScript%2089e6855c52804a2fae2c882264e4f430.md).
    
    Mas quando não passamos o tipo da variável ela pode ser considerada global, como exemplificado abaixo.
    
    ```jsx
    let subject
    
    function createThink() {
    	subject = 'study'
    }
    
    console.log(subject)
    createThink()
    console.log(subject)
    ```
    
    Dessa forma é aconselhável sempre declarar o tipo de variável que será utilizada.
    
- **Acontece hosting em Functions?**
    
    Sim, mas apenas em funções explícitas, ou seja, em functions anonymous não. Um exmplo explicando o hosting é demonstrado abaixo.
    
    ```jsx
    myFunction()
    
    function myFunction () {
    	console.log('hello')
    }
    ```
    
- **O que é Arrow Function?**
    
    É uma função que pode ser atribuída a uma variável ou passada como expressão. Melhor explicando o que é uma Arrow Function, é basicamente uma Function expression de uma forma mais compacta, como demonstrado abaixo.
    
    ```jsx
    const myFunction = () => {
    	console.log('This is my function.')
    }
    ```
    
- **O que é Callback Function?**
    
    Callback Function é uma função chamada por outra função, ou seja, basicamente uma função é passada para outra como argumento e dentro dessa função que recebeu esse argumento, a função passada é chamada. O exemplo abaixo exemplifica isso.
    
    ```jsx
    function sayMyName(name) {
    	name()
    }
    
    sayMyName(
    	() => {
    		console.log('My name is Fulano.')
    	}
    )
    ```
    
    O funcionamento de callback é simples, mas sua explicação não é tão simples. Para melhorar as tentativas acima podemos analisar o passo a passo abaixo.
    
    1. declaração da função a ser passada
        
        ```jsx
        sayMyName(
        	() => {
        		console.log('My name is Fulano.')
        	}
        )
        ```
        
    2. chamada da função que vai conter o callback
        
        ```jsx
        function sayMyName(name) {
        	name()
        }
        ```
        
    3. o que acontece por baixo
        
        ```jsx
        function sayMyName() {
        	function name() {
        		console.log('My name is Fulano.')
        	}
        }
        
        sayMyName()
        ```
        
    
    Dessa forma pode-se executar o código abaixo para entender isso.
    
    ```jsx
    function callCallbackFunction(name) {
    	console.log('antes de executar a função callback')
    	name()
    	console.log('depois de executar a função callback')
    }
    
    callCallbackFunction(
    	() => {
    		console.log('executando a função callback')
    	}
    )
    ```
    
- **O que é uma Function Constructor?**
    
    É uma função que quando chamada com a palavra reservada `new` antes cria ou instanciar um novo objeto, como o exemplo abaixo demonstra.
    
    ```jsx
    function Person() {}
    const person1 = new Person()
    ```
    
    > Cada objeto é único.
    > 
    
    Uma função pode ser utilizada para criar diversos objetos, sendo que cada um possui seus próprios atributos com seus próprios valores. Assim para referênciar o próprio objeto utilizamos a paralavras reservada `this`, dessa forma quando utilizamos o `this` estamos nos referindo ao próprio objeto, como exemplificado no código a seguir.
    
    ```jsx
    function Person(name) {
    	this.name = name
    }
    
    const person1 = new Person('João')
    const person2 = new Person('Marcos')
    ```
    
    Outro ponto interessante no Javascript é que ele por si só já possui diversos construtores como, o `String()`, `Date()`, etc. o interessante desses construtores é que cada um possui diversas funções e atributos internos que servem como rescursos facilitadores. E para utilizar esses contrutores fazemos da mesma forma que demonstrado acima, basta adicionar a palavra reservada `new` antes do construtor.
    

### Manipulando dados

- **O que é Prototype?**
    
    A linguagem Javascript é conhecida por ser uma linguagem baseada em protótipos, ou seja, todo objeto existente ou criado no javascript herda um objeto `__proto__` que previamente possui diversas funcionalidades, que pode herda também outros prototypes.
    
    Para visualizar essas funcionalidade basta acessar o atributo `__proto__` em qualquer objeto, como demonstrada abaixo.
    
    ```jsx
    "Fulano".__proto__
    ```
    
    Um ponto interessante é que todos os valores declarados são automaticamente "embrulhados" em um objeto, como demonstrado acima no script.
    
- **O que é Type Conversion e Type Coersion?**
    
    Ambas são para utilizadas para alterar um tipo de dado para outro tipo de dado. Basicamente o Type Coersion é o JS forçando a conversão dos dados e o Type Conversion é a conversão sendo realizada pelo código explicitamente. O exemplo abaixo demonstra isso.
    
    ```jsx
    console.log('9' + 0)
    ```
    
    ```jsx
    console.log(Number('9') + 0)
    ```
    
- **Como contar caracteres e números no Javascritp?**
    
    Um método simples server para contar ambas as coisas, podemos sempre buscar ter uma string e utilizar o parâmetro `length` como exemplificado abaixo.
    
    ```jsx
    "Fulano".length
    ```
    
    ```jsx
    String(100).length
    ```
    
- **Como definir casas decimais para números?**
    
    Para limitar o número de casas decimais basta utilizar o método `toFixed()` do objeto Number como demonstrado abaixo.
    
    ```jsx
    let number = 1231231.12321
    console.log(number.toFixed(2))
    ```
    
- **Como trocar ponto por vírgula?**
    
    Basta utilizar o método `replace()` que faz a substituição de uma string para outra, como demonstrado no exemplo a seguir.
    
    ```jsx
    let number = 34312.12312
    console.log(number.toFixed(2).replace(".", ","))
    ```
    
    Mas é importante destacar que quando aplicamos o método `replace()` automaticamente o número se transforma em string. Caso fosse necessário manter o resultado como um número não seria possível manter com vírgula para casas decimais.
    
- **Como transformar letras minúsculas em maiúsculas e vice-versa?**
    
    Para a manipulação de nível de caixa de carácteres é aplicado o método `toUpperCase()` (alterar para caixa alta) e `toLowerCase()` (alterar para caixa baixa). Observe o exemplo a seguir.
    
    ```jsx
    let word = "Programar é top!"
    console.log(word.toUpperCase())
    console.log(word.toLowerCase())
    ```
    
- **Como localizar strings dentro de strings?**
    
    Para essa tarefa é utilizado o método `includes()`, mas é importante atentar para o nível de caixa da string, pois o `includes()` é **Case Sensitive**.
    
    ```jsx
    let phrase = "I love you!"
    console.log(phrase.includes("Love"))
    ```
    
    Para resolver o problema de Case Sensitive para o método `includes()` é comum alterar todo o nível da string que contém a string buscada, como demonstrado no exemplo abaixo.
    
    ```jsx
    let phrase = "I love you!"
    console.log(phrase.toLowerCase().includes("love"))
    ```
    
- **Como dividir uma string em um array?**
    
    Para dividir uma string em elementos dentro um array é utilizado a função split() do objeto String, onde é passado para a função o caracter que será utilizado como "separador" da string, como demonstrado abaixo.
    
    ```jsx
    "hello my friend".split(' ')
    ```
    
- **Como juntar as strings de um array em um string única?**
    
    Para fazer essa junção de elementos de um array é utilizado a função join() do objeto String, onde é passado como parâmetro para a função a string que será utilizada para juntar esse elementos, como demonstrado abaixo.
    
    ```jsx
    ['hello', 'my', 'friend'].join(' ')
    ```
    
- **Como criar um array com constructor?**
    
    Pode-se criar um array utilizando o constructor de duas formas básicas:
    
    - Passando o número de elementos, onde é passado para o objeto array o número de elementos (sendo que não haverá elementos apenas espaços definidos para eles).
        
        ```jsx
        let myArray = new Array(10)
        ```
        
    - Passando os elementos, onde é passado os elementos que é desejado armazenar inicialmente no array.
        
        ```jsx
        let myArray = new Array('a', 'b', 'c')
        ```
        
- **Como contar elementos de um array?**
    
    Essa atributo é muito útil para manipular um array com base em seu tamanho, além de ser muito simples de utilizar.
    
    ```jsx
    array.length
    ```
    
- **Como transformar uma string em um array?**
    
    Essa função permite repartir uma String em elementos de um array de forma simples.
    
    ```jsx
    let word = "palavra"
    word.split("")
    ```
    
    Também podemos realizar essa tarefa de uma maneira mais simples, através do método `from()` do objeto `Array`.
    
    ```jsx
    Array.from(word)
    ```
    
- **Quais outros tipos de manipulação podemos ter no array?**
    
    Podemos adicionar elementos no fim do array.
    
    ```jsx
    let array = []
    array.push(1)
    ```
    
    Podemos também adicionar elementos no início do array.
    
    ```jsx
    array.unshift("real")
    ```
    
    Podemos remover elementos do fim.
    
    ```jsx
    array.pop()
    ```
    
    Podemos remover elementos do começo.
    
    ```jsx
    array.shift()
    ```
    
    Podemos pegar somente alguns elementos do array.
    
    ```jsx
    array.slice(1, 5)
    ```
    
    Podemos remover 1 ou mais elementos de diferentes posições do array.
    
    ```jsx
    array.splice()
    ```
    
    E podemos encontrar a posição de um determinado elemento do array.
    
    ```jsx
    array.indeof('a')
    ```
    

### Expressões e operadores

- **O que são funções auto-executáveis?**
    
    A função auto-executável ou auto-invocável permite um trecho de execução automática dentro de uma função. Ela também permite que o código seja gravado sem preocupaçã de como as varáveis são nomeadas em outros blocos de código.
    
    ```jsx
    (functions() {
    	//isntruções
    })
    ```
    
- **O que são expressões?**
    
    Expressões é qualquer trecho de código que determina uma relação ou uma ação. Ela pode ser caracterizada pelo final de `;` no final da expressão. Mas para o Javascript na maioria das vezes não é necessário a utilização do `;`.
    
- **O que são operadores?**
    
    Os operadores definem uma operação como o próprio nome já diz.
    
    As operações podem ter diferentes formas:
    
    - Binária (*Binary*) que possui a formação de um operador e dois valores para a operação.
        
        ```jsx
        number1 + number2
        ```
        
    - Unária (*Unary*) que possui a formação de apenas um valor ( geralmente variável).
        
        ```jsx
        value++
        ```
        
    - Ternária (*Ternary*), este basicamente se refere a uma expressão de comparação direcionada a uma decisão caso verdade e outra caso falso.
        
        ```jsx
        1 > 2 ? true : false
        ```
        
- **O que é a expressão new?**
    
    De forma complicada é uma left-hand-side expression que simplesmente define a criação de um novo objeto.
    
    ```jsx
    let name = new String('fulano')
    ```
    
    Um ponto interessante para explorar nos objetos é a propriedade `__proto__`, que retorna todas as propriedades do objeto.
    
- **Quais os exemplos de operadores unários em JS?**
    
    Como exemplo temos o `delete` e o `typeof`.
    
    O delete remove a propriedade de um objeto.
    
    ```jsx
    delete person.name
    ```
    
    E o typeof retorna o tipo de objeto que é a variável passada a frente do operador.
    
    ```jsx
    typeof name
    ```
    
- **Quais são os operadores aritméticos em JS?**
    
    Nos operadores aritméticos temos:
    
    - Soma
        
        ```jsx
        a + b
        ```
        
    - Subtração
        
        ```jsx
        a - b
        ```
        
    - Multplicação
        
        ```jsx
        a * b
        ```
        
    - Divisão
        
        ```jsx
        a / b
        ```
        
    - Resto da divisão
        
        ```jsx
        a % b
        ```
        
    - Incremento
        
        ```jsx
        a++
        ```
        
        que também pode ser
        
        ```jsx
        ++a
        ```
        
    - Decremento
        
        ```jsx
        a--
        ```
        
        que também pode ser
        
        ```jsx
        --a
        ```
        
    - Exponenciação
        
        ```jsx
        a ** b
        ```
        
- **O que é Grouping operator?**
    
    É um operador que serve para agrupar expressões. Este operador é representado pelos parênteses (`()`). Dessa forma é possível alterar ordens de precedência das operações.
    
- **Quais são os operadores de comparação em JS?**
    
    Os operadores de comparação servem basicamente realizar comparações entre valores ou expressões. O resultado dessas comparações são `true` ou `false`.
    
    Os operadores são:
    
    - Igual
        
        ```jsx
        1 == 1
        //ou
        1 == "1"
        ```
        
    - Diferente
        
        ```jsx
        1 != "1"
        2 != "1"
        ```
        
    - Estritamente igual
        
        ```jsx
        a === b
        ```
        
    - Estritamente diferente
        
        ```jsx
        a !== b
        ```
        
    - Maior
        
        ```jsx
        a > b
        ```
        
    - Menor
        
        ```jsx
        a < b
        ```
        
    - Maior ou Igual
        
        ```jsx
        a >= b
        ```
        
    - Menor ou Igual
        
        ```jsx
        a <= b
        ```
        
- **Quais são os operadores de atribuição em JS?**
    
    Assignment é o significado de atribuição. Esse operadores servem basicamente para atribuir valores à uma variável.
    
    Há diferentes tipos de operadores de atribuição, que também possibilitam uma operação seguida de atribuição:
    
    - Atribuição ou assignment
        
        ```jsx
        x = 1
        ```
        
    - Addition assignment
        
        ```jsx
        x += 1
        ```
        
    - subtraction assignment
        
        ```jsx
        x -= 1
        ```
        
    - division assignment
        
        ```jsx
        x /= 1
        ```
        
    - multiplication assignment
        
        ```jsx
        x *= 1
        ```
        
    - remainder assignment
        
        ```jsx
        x %= 1
        ```
        
    - exponentiation assignment
        
        ```jsx
        x **= 1
        ```
        
- **Quais são os operadores lógicos em JS?**
    
    Logical operators são operadores de comparação para valores booleanos, que quando verificados retornam `true` ou `false`.
    
    - AND só retorna `true` se as duas expressões retornarem `true`.
        
        ```jsx
        a && b
        ```
        
    - OR retorna `true` se pela menos uma das duas expressões retornarem `true`.
        
        ```jsx
        a || b
        ```
        
    - NOT serve para negar uma expressão
        
        ```jsx
        !a
        ```
        
    
- **Como funciona o operador ternário em JS?**
    
    Basicamente se compõe da seguinte forma.
    
    <aside>
    👉 condition ? if_true : if_false
    
    </aside>
    
    Dessa forma podemos observar os seguintes exemplos.
    
    ```jsx
    let bread = true
    let cheese = true
    
    const niceBreakfast = bread && cheese ? "Nice" : "Bad"
    ```
    
- **O que são String Operators?**
    
    São operadores aplicáveis à Strings.
    
    - Concatenação
        
        ```jsx
        "a" + "b"
        ```
        
- **O que é Falsy e Truthy?**
    
    Interligados com os conceitos de Type Conversion e Type Coersion.
    
    <aside>
    👌 **Type Conversion** (ou typecasting): é a conversão de tipo de dados feito explicitamente pelo desenvolvedor.
    **Type Coersion**: é a conversão de tipo de dados feito pelo Javascript.
    
    </aside>
    
    Falsy é quando o valor é considerado `false` em contexto onde o valor booleano é obrigatório (condicionais e loops).  Então para ser considerado false o valor nestes contextos ele deve estar nas seguintes condições, `false`, `0`, `-0`, `""`, `null`, `undefined` ou `NaN`. Por exemplo:
    
    ```jsx
    false ? "true" : "false"
    // ou
    0 ? "true" : "false"
    // ou
    -0 ? "true" : "false"
    // ou
    "" ? "true" : "false"
    // ou
    null ? "true" : "false"
    // ou
    undefined ? "true" : "false"
    // ou
    NaN ? "true" : "false"
    ```
    
    Como inverso do Falsy, o Truthy é onde o valor é considerado `true` em contextos onde o valor booleano é obrigatório. E para esse caso o valor pode ser `true`, `{}`, `[]`, `1`, `2.3`, `"0"`, `"false"`, `-1`, `Infinity`, `-Infinity`, etc.
    
    ```jsx
    true ? "true" : "false"
    // ou
    {} ? "true" : "false"
    // ou
    [] ? "true" : "false"
    // ou
    1 ? "true" : "false"
    // ou
    2.3 ? "true" : "false"
    // ou
    "0" ? "true" : "false"
    // ou
    "false" ? "true" : "false"
    // ou
    -1 ? "true" : "false"
    // ou
    Infinity ? "true" : "false"
    // ou
    -Infinity ? "true" : "false"
    ```
    
- **O que é Operator Pracedence?**
    
    Conhecido como procedência de operadores.
    
    Em operações matemáticas temos as regras de procedência, e nas expressões no Javascript não é diferente seguinda a lógica abaixo.
    
    <aside>
    ⚠️ `()` ⇒ `!`, `++`, `--e` ⇒ `*`, `/` ⇒ `+`, `-` ⇒ `<`, `<=`, `=>`, `>` ⇒ `==`, `!=`, `===`, `!==` ⇒ `&&` ⇒ `!!` ⇒ `?:` ⇒ `=`, `+=`, `-=`, `*=`
    
    </aside>
    
    Podemos expor a procedência como uma lista, onde o valor mais acima têm mais valor de procedência.
    
    1. `()` grouping
    2. `!`, `++`, `--` negation and increment
    3. `*`, `/` multiplication and division
    4. `+`, `-` add and subtration
    5. `<`, `<=`, `=>`, `>` relational
    6. `==`, `!=`, `===`, `!==` equal
    7. `&&` and
    8. `!!` or
    9. `?:` ternary
    10. `=`, `+=`, `-=`, `*=` assignment

### Condicionais e controle de fluxo

- **O que é If e Else no JS?**
    
    Uma das estruturas básicas do Control Flow, o If e Else permite controlar fluxos diferentes de acordo com a condição que as variaveis ou valores estejam no momento da execução.
    
    ```jsx
    if(conditional == true) {
    	// instruções
    } else {
    	// instruções
    }
    ```
    
    Podemos também utilizar apenas o `if` ou se preferir utilizar condições composta ou aninhadas.
    
    ```jsx
    if(conditional == true) {
    	// instruções
    }
    
    // ou composta
    
    if(conditional == true && otherConditional == true) {
    	// instruções
    } else if(conditional == true || otherConditional == true) {
    	// instruções
    } else {
    	// instruções
    }
    
    // ou aninhada
    
    if(conditional == true && otherConditional == true) {
    	if(otherCondional > conditional) {
    			// instruções
    	}
    else {
    	// instruções
    }
    ```
    
    Uma dica bacana é transformar variáveis em condicionais, como demostra o código abaixo.let 
    
    ```jsx
    let highValue = value > maxValue
    let lowValue = value < minValue 
    
    if(highValue) {
    	// instruções
    } else if(lowValue) {
    	// instruções
    } else {
    	// instruções
    }
    ```
    
- **O que é Swtch no JS?**
    
    É um método de derivar fluxos de acordo com resultado de uma expressão. Os caminhos que podem ser seguidos dentro do `switch()` são definidos pela palavra `case`, que expressa o resultado obtido através da expressão. Dentro do `switch()` também temos a palavra `default` que define um caminho caso nenhum dos caminhos anteriores sejam satisfeitos.
    
    Outro ponto importante é a utilização do comando `break`, que por sua vez define a parada da instrução, ou seja, quando acessado o escopo de acordo com o resultado da expressão, é desejável que finalize a execução do `switch()` e é para isso que o `break` serve, para definir um ponto de parada da execução das instruçẽos do escopo do `switch()`. Caso o `break` não seja definido a execução do código avança para o próximo escopo. Assim a utilização do `break` faz parte das boas práticas.
    
    ```jsx
    switch(expression) {
    	case 'a':
    		// instruções
    		break
    	case 'b':
    		// instruções
    		break
    	case 'c':
    		// instruções
    		break
    	default:
    		// instruções
    		break
    }
    ```
    
- **O que é Throw e Try/Catch no JS?**
    
    Esse é um conceito de controle de erros no código.
    
    Primeiro tentamos (`try`) executar uma função/método. Dentro dessa função podemos verificar um erro e caso esse erro seja verificado ele é lançado (`throw`) e interrompido a execução do código, e depois é "pego" (`catch`) ou recebido para ser tratado.
    
    Com esse breve resumo do fluxo fica mais fácil de ler o código abaixo.
    
    ```jsx
    function sayMyName(name) {
    	if(name == "") {
    		throw "O nome é obrigatório"
    	}
    	// não é executado mais nada após o throw
    }
    
    try {
    	sayMyName("")
    } catch (error) {
    	console.log(error)
    }
    // com try catch o código ainda é executado
    ```
    
    A utilização de `try`/`catch` é uma boa prática em sistema que não podem parar mesmo com erros. Pois como o erro já é tratado o sistema não para.
    
    Em casos de não ter o `try`/`catch` o sistema é interrompido.
    

### Estruturas de repetição

- **Como funciona o For em JS?**
    
    For é uma estrutura de repetição, onde é definido um contado, uma condição de parada e um método de continuidade do loop.
    
    A condição de parada serve para definir até quando o loop deve continuar, ou seja, quando a condição não for mais satisfeita não há mais repetição.
    
    O método de conditnuidade define o que deve ser feito depois que a rodada finalizar, ou seja, para cada vez que executar as isntruções dentro do `for` é executado um método de continuidade.
    
    ```jsx
    for(let connt = 0; cont < 10; cont++) {
    	// instruções
    }
    ```
    
    Podemos também utilizar o comando `break` dentro do `for`, sendo que quando executado este comando toda a repetição é interropida.
    
    E também temos o `continue` que não interrompe o `for`, mas ignora o código depois daquele ponto mas continua dentro do `for`.
    
    ```jsx
    for(let connt = 0; cont < 10; cont++) {
    	if (i == 5) {
    		continue
    	}
    	if (i == 8) {
    		break
    	}
    	// instruções
    }
    ```
    
- **Como funciona o While em JS?**
    
    É uma outra estrutura de repetição onde é definido uma condição de repetição. Essa estrutura é interessante de ser utilizada quando não temos uma quantidade específica de rodadas para um loop.
    
    ```jsx
    while(condition) {
    	// instruções
    }
    ```
    
- **Como funciona o For Of?**
    
    Mesmo sendo uma estrutura de repetição não é utilizada condições para manter um loop. Nessa função é utilizado elementos de String ou Array para serem trabalhados.
    
    Dessa forma se passado um objeto que contém diversos elementos, o `for of` executa suas instruções com base no valor do elemento.
    
    ```jsx
    let name = "MY NAME"
    for(let char of name) {
    	console.log(char) // é impresso o valor de cada elemento do Array ou String passado
    }
    ```
    
- **Como funciona o For In?**
    
    Esta função é semelhante com o for of na forma de empregá-la, mas na sua execução o conceito é diferente. Onde o `for of` trabalha com os valores de Strings e Array, o `for in` trabalha com as propriedades.
    
    Dessa forma quando aplicado a uma String ou Array é trabalho os índices que são o atributo, e quando aplicado a um objeto é trabalho as suas propriedades.
    
    ```jsx
    let name = "MyName"
    for(let char in name) {
    	console.log(char)
    }
    let ages = [12, 3, 80, 30]
    for(let age in ages) {
    	console.log(age)
    }
    let person = {name: "Fulano", age: 24}
    for(let atr in person) {
    	console.log(atr)
    }
    ```
    
    Assim o `for in` é ideial para trabalhar com propriedades.
    
    Caso seja necessário acessar os valores das propriedades basta utilizar o colchetes (`[]`) indicado a propriedade.
    
    ```jsx
    let name = "MyName"
    for(let char in name) {
    	console.log(name[char])
    }
    let ages = [12, 3, 80, 30]
    for(let age in ages) {
    	console.log(ages[age])
    }
    let person = {name: "Fulano", age: 24}
    for(let atr in person) {
    	console.log(person[atr])
    }
    ```
    

### Consolidando

```jsx
//Ranqueamento de notas
function checkScore(score) {
	// define conditionals
  let scoreA = score >= 90
  let scoreB = score >= 80 && score <= 89
  let scoreC = score >= 70 && score <= 79
  let scoreD = score >= 60 && score <= 69
  let scoreF = score < 60
  
	// verify conditionals
  if(scoreA) {
    return "A"
  } else if(scoreB) {
    return "B"
  } else if(scoreC) {
    return "C"
  } else if(scoreD) {
    return "D"
  } else if(scoreF) {
    return "F"
  } else {
    return "Erro"
  }
}

// execute function
console.log(checkScore(50)) // "F"
console.log(checkScore(-1)) // "F"
console.log(checkScore(0)) // "F"
console.log(checkScore(30)) // "F"
console.log(checkScore(100)) // "A"
console.log(checkScore("a")) // "Erro"
console.log(checkScore(true)) // "F"
console.log(checkScore(false)) // "F"
console.log(checkScore(4.6)) //  "F"
```

```jsx
// Calcule balanço da família
// valores de receita e despesas
const incomes = [100, 26, 10000, 2300]
const expenses = [12, 86, 488, 62, 17, 89, 34, 55, 100, 48]

// calculo da família:
// receita - despesas
function calculateBalance(incomes, expenses) {
   return sum(incomes) - sum(expenses)
}

// somar elementos do array
function sum(array) {
  let total = 0
  for(let value of array) {
    total += value
  }
  return total
}

console.log(calculateBalance(incomes, expenses)) // 11435
```

```jsx
// transformar celcius em fahrenheit e vice-versa
function transformDegree(degree) {
  const celciusExists = degree.toLowerCase().includes("c")
  const fahrenheitExists = degree.toLowerCase().includes("f")
  
  if (!celciusExists && !fahrenheitExists){
    throw new Error("Grau não identificado.")
  }
  let oldSignalDegree, newSignalDegree
  let formule
  
  if(celciusExists) {
    oldSignalDegree = "c"
    newSignalDegree = "f"
    formule = (value) => (value - 32) * 5 / 9
  } else {
    oldSignalDegree = "f"
    newSignalDegree = "c"
    formule = (value) => value * 9 / 5 + 32
  }
  
  let valueDegree = getValue(degree, oldSignalDegree)
  return formule(valueDegree) + newSignalDegree.toUpperCase()
  
}

function getValue(degree, signal) {
  return Number(degree.toLowerCase().replace(signal, ""))
} 

try {
  console.log(transformDegree("30F")) //"86C"
  console.log(transformDegree("60F")) //"15.555555555555555F"
  console.log(transformDegree("30H")) //"Grau não identificado."
} catch(error) {
  console.log(error.message)
}
```

```jsx
// buscando e contando dados em Array
const booksByCategory = [
  {
    category: "Riqueza" ,
    books: [
      {
        title: "Os segredos da mente milionária",
        author: "T. Harv Eker"
      },
      {
        title: "O homem mais rico da Babilônia",
        author: "George S. Clauson"
      },
      {
        title: "Pai rico, pai pobre",
        author: "Robert T. Kiyosaki e Sharon L. Lechter"
      }
    ]
  },
  {
    category: "Inteligencia Emocional" ,
    books: [
      {
        title: "Você é insubstituivel",
        author: "Augusto Cury"
      },
      {
        title: "Ansiedade - Como enfrentar o mal do século",
        author: "Augusto Cury"
      },
      {
        title: "Os 7 hábitos das pessoas altamente eficiêntes",
        author: "Stephen R. Covey"
      }
    ]
  }
]
//
// conte o número de categorias
console.log("Total de categorias:", booksByCategory.length)
//
// conte o numero de livro para cada categoria
for(let category of booksByCategory) {
  console.log("Para a categoria:", category.category)
  console.log("Total de livros:", category.books.length)
}
//
// conte o número de autores
let authors = []

for(let category of booksByCategory) {
  for(let book of category.books) {
    if(authors.indexOf(book.author) == -1) {
      authors.push(book.author)
    }
  }
}

console.log("O número de autores é:", authors.length)
//
// mostrar livros do autor August Cury
// transformar a função para buscar os livros de qualquer autor
function booksOfAuthor(author, booksByCategory) {
  let booksByAuthor = []
  
  for(let category of booksByCategory) {
    for(let book of category.books) {
      if(book.author.toLowerCase() == author.toLowerCase()) {
        booksByAuthor.push(book.title)
      }
    }
  }
  
  return booksByAuthor
}

let author = "Augusto Cury"
console.log(`Os livros de ${author} são ${booksOfAuthor(author, booksByCategory).join(", ")}`)
```