# Pilotando com o DOM

> *Site: [https://app.rocketseat.com.br/node/pilotando-com-a-dom](https://app.rocketseat.com.br/node/pilotando-com-a-dom)*
> 

Para um controle completo do HTML via JavaScript, nós precisamos dessa API chamada DOM!

# Introdução

- **O que é e para que serve a DOM?**
    
    Basicamente, Document Object Model é o HTML convertido para um objeto Javascript, ou seja, ela é uma API que interage com o HTML.
    
    A DOM é uma estrutura de dados do tipo árvore criada pelo browser, e por ser um objeto também possui atributos e métodos.
    
- **Para que utilizar a DOM?**
    
    Com o Javascript é possível utilizar a DOM para se conectar com o HTML. O que também tornar possível manipular o HTML, ou seja, torna possível a programação web.
    
    <aside>
    ⚠️ Uma forma de manipular a DOM na prática é utilizando um script Javascript que pode estar contido na tag `<script>`.
    
    </aside>
    
- **Como é a DOM?**
    
    Uma representação simples da DOM pode ser observada na imagem abaixo.
    
    ![Pilotando%20com%20o%20DOM%20e57cce922a584bab94d5143e0058d026/Untitled.png](Pilotando%20com%20o%20DOM%20e57cce922a584bab94d5143e0058d026/Untitled.png)
    
    Outra representação da estrutura acime é:
    
    - `DOCUMENT` é a página em si.
        - `<html>` é o nó (pai) principal do documento.
            - `<head>` é um nó (filho) principal do documento.
                - `<title>` é um nó (filho de `<head>`)
                    - `"Documento HTML Teste"` é um nó (folha/filho)
                - `<meta>` é um nó (filho de `<head>`)
            - `<body>` é um nó (filho) principal do documento.
                - `<form id="j6">` é um nó (filho de `<body>`)
                    - `<div id="j6:j7">` é um nó (filho de `<form id="j6">`)
                        - `<div id="j6:j7_header">` é um nó (filho de `<div id="j6:j7">`)
                            - `"Documento HTML Teste"`, é um nó (folha/filho)
                        - `<div id="j6:j7_content">` é um nó (filho de `<div id="j6:j7">`)
                            - `<button id="j6:j9">` é um nó (filho de `<div id="j6:j7_content">`)
                                - `"Pesquisar"`, é um nó (folha/filho)

# Selecionando elementos

- **O que é getElementById?**
    
    É um método de captura do objeto document. Com ele é possível **capturar um elemento** do HTML **através do ID** do elemento.
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width= , initial-scale=1.0">
        <title>Meu blog</title>
    </head>
    <body>
        <h1 id="my-blog">Meu blog</h1>
        <script src="script.js"></script>
    </body>
    </html>
    ```
    
    ```jsx
    const element = document.getElementById("my-blog");
    console.log(element)
    ```
    
    Dessa forma é possível manipular este elemento e seus filhos posteriormente.
    
- **O que é getElementsByClassName?**
    
    É um método com a mesma finalidade que o `document.getElementById()`, mas neste caso ao invés de ser retornado um elemento, será **retornado** um `HTMLCollection` de **elementos que possuem a classe** específicada.
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width= , initial-scale=1.0">
        <title>Meu blog</title>
    </head>
    <body>
        <h1 id="my-blog">Meu blog</h1>
        <h2 class="posts">Post 1</h2>
        <h2 class="posts">Post 2</h2>
        
        <script src="script.js"></script>
    </body>
    </html>
    ```
    
    ```jsx
    const elements = document.getElementsByClassName("posts");
    console.log(elements)
    ```
    
    <aside>
    ⚠️ Para mais informações sobre `HTMLCollection` acesse o seguinte [documento do MDN](https://developer.mozilla.org/pt-BR/docs/Web/API/HTMLCollection).
    
    </aside>
    
- **O que é getElementsByTagName?**
    
    É um método muito parecido com `document.getElementsByClassName()`, mas nesse caso é buscado os **elementos** através do **nome da tag** e não do valor da classe.
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width= , initial-scale=1.0">
        <title>Meu blog</title>
    </head>
    <body>
        <h1 id="my-blog">Meu blog</h1>
        <script src="script.js"></script>
    </body>
    </html>
    ```
    
    ```jsx
    const elements = document.getElementsByTagName("meta");
    console.log(elements)
    ```
    
- **O que é querySelector?**
    
    É um método de captura de elementos utilizando o seletor (o mesmo mecanismo de busca utilizado pelo CSS). Nesse método é retornado apenas o primeiro elemento que possui o seletor buscado.
    
    Para melhor entendimento, os seletores podem ser, o nome da tag, o valor da classe, o valor do id, atributos, etc.
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width= , initial-scale=1.0">
        <title>Meu blog</title>
    </head>
    <body>
        <h1 id="my-blog">Meu blog</h1>
        <h2 class="posts">Post 1</h2>
        <h2 class="posts">Post 2</h2>
        
        <script src="script.js"></script>
    </body>
    </html>
    ```
    
    ```jsx
    const element = document.querySelector(".posts");
    console.log(element)
    ```
    
    Outros exemplos de parâmetros de busca são:
    
    - `"#valor_id"` para buscar pelo id;
    - `".valor_class"` para buscar pela classe;
    - `"nome_tag"` para buscar pela tag, e;
    - `"[nome_atributo]"` para buscar pelo atributo.
    - `"identificador_elemento indentificador_elemento_interno"` para definir um caminho de busca entre os elementos
    
    <aside>
    ⚠️ Para mais informações sobre o método `document.querySelector()` acesse a [documentação do MDN](https://developer.mozilla.org/pt-BR/docs/Web/API/Document/querySelector) e para mais informações sobre selectors acesse o seguinte [documento do MDN](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors).
    
    </aside>
    
- **O que é querySelectorAll?**
    
    É muito parecido com o método `document.querySelector()`, mas neste caso é retornado um `NodeList`.
    
    <aside>
    ⚠️ Para mais informações sobre `NodeList` Acesse seguinte [documentação do MDN](https://developer.mozilla.org/pt-BR/docs/Web/API/NodeList).
    
    </aside>
    
- **Qual é o melhor método de seleção de elementos?**
    
    A resposta direta é, depende. Depende da necessidade. Para clarear um pouco mais a resposta, pode-se guiar a escolha pelo retorno de cada método.
    
    - `document.getElementById()` retorna um **element**.
    - `document.getElementsByClassName()` retorna um **HTMLCollection**.
    - `document.getElementsByTagName()` retorna um **HTMLCollection**.
    - `document.querySelector()` retorna um **element**.
    - `document.querySelectorAll()` retorna um **NodeList**.
    
    Agora só depende da necessidade!
    

# Manipulando conteúdos

- **O que é textContent?**
    
    É o atributo que indica qual o conteúdo de texto aplicado ao elemento ou aplicado aos seus filhos, o que torna possível alterar ou manipular este valor com Javascript.
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Document</title>
    </head>
    <body>
        <h1>Hello</h1>
        <script src="./script.js"></script>
    </body>
    </html>
    ```
    
    ```jsx
    const element = document.querySelector("h1")
    element.textContent += " brothers"
    ```
    
    O interessante do `textContent` é que, ao capturar trabalhar com este atributo, é utilizado todo o texto contido no elemento, ou seja, **mesmo que o conteúdo não seja visível**, ele **será retornado** para o `textContent`. Como demonstrado abaixo.
    
    ```html
    <body>
        <h1>
            <span>Hello
                <span style="display: none;">
                    World
                </span>
            </span>
        </h1>
        <script src="./dom/dom.js"></script>
    </body>
    ```
    
    ```jsx
    const element = document.querySelector("h1");
    console.log(element.textContent);
    ```
    
    ![Console](Pilotando%20com%20o%20DOM%20e57cce922a584bab94d5143e0058d026/Untitled%201.png)
    
    Console
    
- **O que é innerText?**
    
    É parecido com textContent, mas este atributo trabalha somente com o texto vísivel, ou seja, não aplica espaços, tabulações ou qualquer outro conteúdo implícito, **apenas conteúdo explícito**.
    
    ```html
    <body>
        <h1>
            <span>Hello
                <span style="display: none;">
                    World
                </span>
            </span>
        </h1>
        <script src="./script.js"></script>
    </body>
    ```
    
    ```jsx
    const element = document.querySelector("h1");
    console.log(element.innerText);
    ```
    
    ![Console](Pilotando%20com%20o%20DOM%20e57cce922a584bab94d5143e0058d026/Untitled%202.png)
    
    Console
    
- **O que é innerHTML?**
    
    É o atributo que define o HTML interno de um elemento. Dessa forma, é possível manipular todo o HTML contido no elemento, seja alterando o HTML já existente ou adicionando outras tags.
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Document</title>
    </head>
    <body>
        <h1>
            Hello
        </h1>
        <script src="./script.js"></script>
    </body>
    </html>
    ```
    
    ```jsx
    const element = document.querySelector("h1");
    element.innerHTML += "<h3> Brother </h3>"
    ```
    
    ![Output](Pilotando%20com%20o%20DOM%20e57cce922a584bab94d5143e0058d026/Untitled%203.png)
    
    Output
    
- **O que é Value?**
    
    É o atributo que permite manipular o valor de tags que possuem valores de entrada, como é o caso da tag `<input>`. Além disso pode-se também manipular valores dos atributos do elemento, como demonstrado abaixo.
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Document</title>
    </head>
    <body>
        <span class="a b c"></span>
        <script src="./script.js"></script>
    </body>
    </html>
    ```
    
    ```jsx
    const span = document.querySelector("span");
    const classes = span.classList;
    span.textContent = classes.value;
    ```
    
    ![Output](Pilotando%20com%20o%20DOM%20e57cce922a584bab94d5143e0058d026/Untitled%204.png)
    
    Output
    
- **Como manipular os atributos do elemento?**
    
    Para está tarefa utilizamos o método `setAttribute()`, passando para ele o nome do atributo e seu novo valor. Um fato interessante sobre este método é que, caso não haja o atributo no elemento, o atributo é criado e também é atributo o valor passado.
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Document</title>
    </head>
    <body>
        <h1>Hello</h1>
        <script src="./script.js"></script>
    </body>
    </html>
    ```
    
    ```jsx
    const element = document.querySelector("h1")
    element.setAttribute("id", "header")
    
    const newElement = document.querySelector("#header")
    newElement.innerText += " Brother"
    ```
    
    <aside>
    ⚠️ Para mais informações sobre este método acesse a [documentação do MDN](https://developer.mozilla.org/pt-BR/docs/Web/API/Element/setAttribute).
    
    </aside>
    
    Pode-se também utilizar o método `getAttribute()` para capturar os valores de um atributo do elemento.
    
    ```jsx
    const element = document.querySelector("h1")
    element.setAttribute("id", "header")
    
    const newElement = document.querySelector("#header")
    newElement.getAttribute("id")
    ```
    
    Ou pode-se também remover atributos do elemento utilizando o método `removeAttribute()`.
    
    ```jsx
    const element = document.querySelector("h1")
    element.setAttribute("id", "header")
    
    element.remove("id")
    ```
    

# Manipulando estilos e classes

- **Como alterar estilos utilizando Javascript?**
    
    É possível alterar os estilos utilizando a propriedade style do elemento. Dessa forma, basta acessar a propriedade e definir qual atributo deseja alterar e informar um valor para este atributo.
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Document</title>
    </head>
    <body>
        <h1>Hello Brother</h1>
        <script src="./script.js"></script>
    </body>
    </html>
    ```
    
    ```jsx
    const element = document.querySelector("body")
    element.style.backgroundColor = "#B13"
    ```
    
    Como essa manipulação é realizada através de uma propriedade, é possível realizar todo tipo de manipulação com os atributos de estilo. 
    
- **O que é classList?**
    
    É uma propriedade que possui uma coleção dos atributos de classes ativas de um determinado elemento, ou seja, através do `classList` pode-se manipular as classes de um elemento.
    
    Para realizar a manipulação do elemento podem ser utilizados os seguintes métodos:
    
    - `add()` para adicionar uma classe. Caso a classe já exista a adição é ignorada.
        
        ```jsx
        const element = document.querySelector("h1")
        element.classList.add("bye")
        ```
        
    - `remove()` para remover uma classe específica. Caso a classe não exista a operação é ignorada.
        
        ```jsx
        const element = document.querySelector("h1")
        element.classList.remove("bye")
        ```
        
    - `item()` para capturar o valor da classe através do índice da coleção.
        
        ```jsx
        const element = document.querySelector("h1")
        console.log(element.classList.item(0))
        ```
        
    - `toggle()` para remover (caso exista) ou adicionar (caso não exista) o valor da class. Para este método pode ser passado dois argumentos, o primeiro indica o valor da classe a ser buscada e o segundo uma condicional para a execução da operação.
        
        ```jsx
        const element = document.querySelector("h1")
        element.classList.toggle("bye", 1 < 10)
        ```
        
    - `contains()` para verificar se há a classe especificada no `classList`.
        
        ```jsx
        const element = document.querySelector("h1")
        console.log(element.classList.contains("bye"))
        ```
        

# Navegando pelos elementos

- **Como navegar pelos elementos da DOM?**
    
    Pode-se **navegar de três formas** entre os elementos:
    
    - A primeira é **navegar para o elemento pai** (parentElement ou parentNode). Para isso inicialmente precisa-se **capturar um elemento**.
        
        ```jsx
        const element = document.querySelector("body");
        ```
        
        Depois basta mostrar o elemento pai do elemento capturado anteriormente.
        
        ```jsx
        console.log(element.parentElement);
        // ou
        console.log(element.parentNode);
        ```
        
        <aside>
        ⚠️ O **parentElement** e **parentNode** têm basicamente a mesma função. A diferença básica está no nível de navegação necessário. Por exemplo, quando se está dentro do elemento `<html>` tanto o **parentElement** quanto o **parentNode** **funcionam bem** (sempre lembrando que **parentElement** busca **elementos** e **parentNode** busca **nós**), mas para caso onde está acima do elemento `<html>` o **parentElement** retorna `null` e **parentNode** retorna o **nó pai** do `<html>`.
        
        </aside>
        
    - A segunda forma é **navegar para os elementos filhos** (childNodes e children). Para capturar estes elementos, como na etapa anterior é necessário capturar um elemento antes.
        
        ```jsx
        const element = document.querySelector("body");
        ```
        
        E depois mostrar os elementos filhos, que serão mostrados em forma de lista.
        
        ```jsx
        console.log(element.childNodes);
        // ou
        console.log(element.children);
        ```
        
        <aside>
        ⚠️ O childNodes e children têm a mesma função, capturar os elementos filhos de um determinado elemento. Há diferença básica entre eles está no retorno. O **childNodes** captura todos os **nós filhos** de um elemento, inclusive os espaços dados no documento original (como indentação, etc.) e retorna uma **NodeList**. O **children** retorna um **HTMLCollection** com apenas os elementos contidos no elemento atual.
        
        </aside>
        
        Há também as propriedades de captura do **primeiro filho**:
        
        - `firstChild`, que retorna o primeiro nó encontrado
            
            ```jsx
            console.log(element.fistChild)
            ```
            
        - `firstElementChild`, que retorna o primeiro elemento encontrado
            
            ```jsx
            console.log(element.fistElementChild)
            ```
            
        
        E també há as propriedades de captura do **último filho**:
        
        - `lastChild`, que retorna o último nó encontrado
            
            ```jsx
            console.log(element.lastChild)
            ```
            
        - `lastElementChild`, que retorna o último elemento encontrado
            
            ```jsx
            console.log(element.lastElementChild)
            ```
            
    - A terceira forma **navegar entre os elementos irmãos**:
        - `nextSibling`, que retorna o próximo nó encontrado
            
            ```jsx
            console.log(element.nextSibling)
            ```
            
        - `nextElementSibling`, que retorna o próximo elemento encontrado
            
            ```jsx
            console.log(element.nextElementSibling)
            ```
            
        - `previousSibling`, que retorna o nó anterior (encontrado)
            
            ```jsx
            console.log(element.previousSibling)
            ```
            
        - `previousElementSibling`, que retorna o elemento anterior (encontrado)
            
            ```jsx
            console.log(element.previousElementSibling)
            ```
            

# Criando e adicionando elementos na página

- **Como criar elementos na página?**
    
    Para a tarefa de criar um elemento utilizamos o método createElement. Para sua utilização é necessário passar o nome do elemento a ser criado como parâmetro
    
    ```jsx
    const div = document.createElement("div");
    ```
    
    Agora com o elemento criado é possível adicionar texto dentro do elemento.
    
    ```jsx
    div.innerText = "Minha Div"
    ```
    
    Pode-se também realizar outras manipulações neste elemento.
    
- **Como adicionar elementos na página?**
    
    Para realizar a tarefa de adição de elementos utiliza-se basicamente os métodos append (adiciona depois) e prepend (adiciona antes). Para isso primero é necessário capturar um elemento de referência.
    
    ```jsx
    const element = document.querySelector("header");
    ```
    
    Depois basta utilizar o método para adicionar o elemento desejado ao elemento capturado. Para isso 
    
    ```jsx
    const div = document.createElement("div");
    div.innerText = "Minha Div";
    
    element.append(div);
    // ou
    element.prepend(div);
    ```
    
    Pode-se também utilizar métodos como o insertBefore para adicionar o elemento entre outros elementos. Para isso é necessário passar como parâmetro para o método inserBefore o nome do elemento que deseja adicionar e também o nome do elemento de referência, ou seja, **o elemento é adicionado antes de outro elemento referenciado**.
    
    ```jsx
    const div = document.createElement("div");
    const footer = document.querySelector("footer");
    
    element.insertBefore(div, footer);
    ```
    
    Se for necessário adicionar o elemento após um determinado elemento basta utilizar o parâmetro nextElementSibling ou nextSibling como referência do elemento a ser adicionado.
    
    ```jsx
    element.insertBefore(div, footer.nextElementSibling);
    // ou
    element.insertBefore(div, footer.nextSibling );
    
    ```
    

# Eventos

- **Como adicionar eventos a um elemento?**
    
    O Javascript na DOM é direcionado a eventos. Por isso saber utiliza-los é fundamental.
    
    Pode-se adicionar eventos a elementos de forma direta, indicando o **evento como um atributo** no elemento.
    
    Praticamente, é possível adicionar todo tipo de gatilho de evento, seja ele de mouse ou de teclado, como:
    
    - `onclick` (dar um clique em cima no elemento);
    - `ondbclick` (dar um clique duplo em cima do elemento);
    - `ondrag` (quando arrastar o elemento);
    - `ondraged` (quando terminar de arrastar o elemento);
    - `onblur` (quando sair da seleção);
    - `onabort` (quando abortar uma operação);
    - `onkeyup` (quando clicar e soltar a seta para cima);
    - `onkeydown` (quando clicar e soltar a seta para baixo);
    - `onkeypress` (quando clicar e soltar qualquer tecla sem ser teclas de controle);
    - `mouseover` (quando passar o mouse por cima);
    - `mouseout` (quando tirar o mouse de cima);
    - etc;
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width= , initial-scale=1.0">
        <title>Meu blog</title>
    </head>
    <body>
        <header>
            <h1 onclick="print()">Blog</h1>
        </header>
        <script src="script.js"></script>
    </body>
    </html>
    ```
    
    ```jsx
    function print() {
        console.log("Printei!")
    }
    ```
    
- **Como adicionar eventos via JS?**
    
    Pode-se também **adicionar um evento via Javascript** utilizando o método `addEventListener()`. Para utilizar este método deve ser passado dois parâmetros, o primeiro é o tipo de evento que será escutado como gatilho e o outro é a função que será executada caso o gatilho seja disparado.
    
    <aside>
    ⚠️ Lembrando que, caso a função seja definida utilizando os parênteses a função já será executada ao carregar a página. Então se a intenção for executar a função sem após o disparo do gatilho deve-se definir a função sem os parênteses.
    
    </aside>
    
    ```jsx
    const h1 = document.querySelector("h1");
    h1.addEventListener("click", print);
    
    function print() {
        console.log("Printei!");
    }
    ```
    
    Outro forma de definir eventos via Javascript é **definir diretamente o parâmetro** que deseja adicionar o evento.
    
    ```jsx
    const h1 = document.querySelector("h1");
    h1.onclick = print
    
    function print() {
        console.log("Printei!");
    }
    ```
    
    <aside>
    ⚠️ Basicamente a diferença entre as duas formas de definir eventos é, a primeira forma permite adicionar mais eventos posteriormente, já a segunda só permite definir o evento uma única vez.
    
    </aside>
    
    <aside>
    ⚠️ Um fator interessante sobre definir eventos via Javascript ou via HTML, é que via Javascript o método não será mostrado no documento HTML. Já a definição diretamente no HTML o método estará exposto no documento.
    
    </aside>
    
- **O que é o parâmentro event?**
    
    Este parâmetro é um objeto do evento em si, ou seja, todos atributos e métodos relacionadas ao evento estão disponíveis neste objeto.
    
    ```jsx
    const h1 = document.querySelector("h1");
    h1.addEventListener("click", (event) => {
    	console.log(event);
    }
    ```
    

# Praticando

- **O que será práticado?**
    
    O desafio é fazer um botão que quando clicado desaparece e faz aparecer uma caixa com uma mensagem na frente. E também quando a caixa com a mensagem estiver visível é necessário apertar a tecla ESC para ela desaparecer e fazer aparecer o botão novamente.
    
    ```jsx
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <link rel="stylesheet" href="https://unpkg.com/tailwindcss/dist/tailwind.min.css">
        <title>Modal</title>
    </head>
    <body class="h-screen bg-purple-100 flex flex-col items-center justify-center">
        <button id="openModal" class="bg-purple-700 text-white py-2 px-4 rounded">
            Open Window
        </button>
    
        <div class="modal-wrapper invisible fixed bg-gray-500 w-screen h-screen flex items-center justify-center">
            <div class="p-8 bg-white text-center rounded">
                Press ESC to close
            </div>
        </div>
        
        <script src="script.js"></script>
    </body>
    </html>
    ```
    
    ```jsx
    const button = document.querySelector("#openModal")
    const div = document.querySelector("div")
    
    button.addEventListener("click", () => {
        toggleVisibleDivAndButton()
    })
    
    document.addEventListener("keydown", (event) => {
        if (event.key === "Escape") {
            toggleVisibleDivAndButton()
        }
    })
    
    function toggleVisibleDivAndButton() {
        div.classList.toggle("invisible");
        button.classList.toggle("invisible");
    }
    ```
    

<aside>
⚠️ Para mais informações sobre o objeto DOM acesse a [documentação do MDN](https://developer.mozilla.org/pt-BR/docs/Web/API/Document_Object_Model).

</aside>