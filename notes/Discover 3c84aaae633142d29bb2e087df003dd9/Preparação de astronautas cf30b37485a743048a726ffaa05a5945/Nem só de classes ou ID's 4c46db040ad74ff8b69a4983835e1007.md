# Nem só de classes ou ID's

> *Site: [https://app.rocketseat.com.br/node/nem-so-de-classes-ou-i-ds](https://app.rocketseat.com.br/node/nem-so-de-classes-ou-i-ds)*
> 

Existem muitas formas de selecionarmos o elemento do HTML para aplicarmos regras de CSS e vamos conhecer todas elas agora.

# Selectors and Combinators

- **O que é seletor no CSS?**
    
    É a conexão entre o elemento HTML e o CSS afim de alterá-lo
    
    Pode-se utilizar alguns seletores:
    
    - **Element selector**, que representam elementos HTML
        
        ```css
        p {
        	color: blue;
        }
        ```
        
    - **ID selector**, que representa o atributo `id` de um elemento HTML.
        
        ```css
        #id_element {
        	height: 50%;
        }
        ```
        
        <aside>
        ⚠️ É de boa prática fazer com que cada ID seja único, ou seja, deverá existir apenas um ID para o elemento HTML identificado.
        
        </aside>
        
    - **Class selector**, que representam o atributo `class` de um ou mais elementos.
        
        ```css
        .class_element {
        	margin: 2%;
        }
        ```
        
    - **Attribute selector**, que representam atributos específicos de elementos HTML.
        
        ```css
        [atribute_elemetnt] {
        	color: red;
        }
        ```
        
    - **Pseudo-class selector**, que representa os elementos que possuem um estado específico, ou seja, quando determinado elemento estiver no estado específicado a pseudo-classe vai ter efeito.
        
        ```css
        h1:hover {
        	color: red;
        }
        ```
        
    
    Pode-se também selecionar multiplos elementos utilizando o CSS separando eles por vírgula.
    
    ```css
    p, h1, h2 {
    	color: green;
    }
    ```
    
- **O que são combinators?**
    
    São formas de buscar e combinar elementos seletores a fim de aplicar a regra CSS a eles.
    
    Alguns combinators mais conhecidos são:
    
    - **Descendant combinator**, é representado pelo espaço em branco e é utilizado para específicar o caminho para a seleção.
        
        ```css
        body div h1 {
        	color: red;
        }
        ```
        
    - **Child combinator**, é representado pelo `>` (sinal de maior), sendo ele a indicação que o elemento a direita deve ser filho direto do elemento a esquerda para receber a regra. Dessa forma, o mesmo caso acima seria escrito da forma abaixo.
        
        ```css
        body > ul > li {
        	color: red;
        }
        ```
        
    - **Adjacent sibling combinator**, é representado pelo `+` (sinal de soma) e aplica a regra somente ao do lado direito, mas que tenha um irmão direto (na hirearquia) específicado do lado esquerdo, ou seja, só vai ser aplicado ao seletor do lado direito se ele o seletor do lado esquerdo for seu irmão direto (ou seja, o primeiro irmão seguinte).
        
        ```css
        button + button {
        	margin: 2px;
        }
        ```
        
        Caso seja necessário aplicar a regra a todos os irmãos (hierarquicos) é utilizado o `~` (til).
        
        ```css
        h1 ~ h2 {
        	color: red;
        }
        ```
        
    
    É importante citar que pode-se utilizar combinações dos combinators, como demonstrado abaixo.
    
    ```css
    ul > li[class="red"] {
    	color: red;
    }
    ```
    
    <aside>
    ⚠️ Seletores muito específicos causam dificuldade de reuso de regras. Por isso, é indicado aplicar regras simples, como a utilização de classes.
    
    </aside>
    

# Pseudo-classes

- **O que são pseudo-classes?**
    
    São palavras reservadas que representam um determinado estado, sendo elas utilizadas após um seletor. Dessa forma, apenas o seletor que estiver no estado específico vai receber a regra.
    
    A pseudo-classe é representado por `:` (dois pontos) seguido do nome da pseudo-classe.
    
    Alguns exemplos de pseudo-classes são:
    
    - `:first-child`, aplica a regra apenas ao primeiro filho do seletor
        
        ```css
        ul li:first-child {
        	font-weight: bold;
        }
        ```
        
    - `:nth-of-type()`, é uma função que aplica a regra ao seletor que for da posição específicado como parâmetro do **nth-of-type**.
        
        ```css
        ul li:nth-of-type(2) {
        	font-weight: bold;
        }
        ```
        
    - `:nth-child`, também é uma função que aplica a regra ao seletor que for filho direto (e específicado como parâmetro) do seletor anterior.
        
        ```css
        ul li:nth-child(3) {
        	font-weight: bold;
        }
        ```
        
        Pode-se também passar como parâmetro algumas palavras reservadas para a função **nth-child**, como `odd` (que representa elementos em posição ímpar) e `even` (que representa elementos em posição par).
        
        ```css
        ul li:nth-child(odd) {
        	color: red;
        }
        
        ul li:nth-child(even) {
        	color: gray;
        }
        ```
        
    - `:hover`, representa o estado do ponteiro do mouse em cima do elemento.
        
        ```css
        a:hover {
        	color: red;
        }
        ```
        
    - `:focus`, representa o estado que o elemento está em focu. Este estado é comum para o elemento `<input>`, pois ele recebe uma seleção focada.
        
        ```css
        input:focus {
        	border-color: red;
        	outline: none;
        }
        ```
        
    - `:disable`, representa o seletor que estiver no estado desabilitado.
        
        ```css
        input:disable {
        	display: none;
        }
        ```
        
    - `:required`, representa o seletor que tiver o atributo required, ou seja, necessário.
        
        ```css
        input:required {
        	background-color: red;
        }
        ```
        
    
    <aside>
    ⚠️ Para mais informações sobre pseudo-classes acesse a [documentação do MDN](https://developer.mozilla.org/pt-BR/docs/Web/CSS/Pseudo-classes).
    
    </aside>
    

# Pseudo-elements

- **O que são pseudo-elements?**
    
    Nos permite adicionar elementos HTML através do CSS, sendo seu comportamento semelhante ao pseudo-class, mas ao invés de se utilizar `:` (dois pontos) é utilizado `::` (duas vezes dois pontos).
    
    Os pseudo-elements mais comuns são:
    
    - `::before`, representa a posição anterior ao elemento
        
        ```css
        ul li::before {
        	content: ">"
        }
        ```
        
        <aside>
        ⚠️ É necessário aplicar a propriedade `content`
        
        </aside>
        
    - ::after, representa a posição seguinte ao elemento
        
        ```css
        ul li::after {
        	content: ";"
        }
        ```
        
        <aside>
        ⚠️ É necessário aplicar a propriedade `content`
        
        </aside>
        
    - `::first-line`, representa a primeira linha do seletor, ou seja, apenas na primeira linha do seletor é aplicada a regra.
        
        ```css
        p::first-line {
        	font-weight: bold;
        }
        ```
        
    
    <aside>
    ⚠️ Para mais informações sobre pseudo-elements consulte a [documentação do MDN](https://developer.mozilla.org/pt-BR/docs/Web/CSS/Pseudo-elements).
    
    </aside>