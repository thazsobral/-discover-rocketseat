# O guia estelar de CSS

> *Site: [https://app.rocketseat.com.br/node/o-guia-estelar-de-css](https://app.rocketseat.com.br/node/o-guia-estelar-de-css)*
> 

É hora de conhecer os conceitos da estilização do seu HTML e explorar os fundamentos do CSS.

- **O que é CSS?**
    
    CSS ( Cascating Style Sheets) é uma linguagem de estilização, sendo ela utilizada para criar estilos para o HTML (Hypertext Markup Language).
    
- **O que são comentários no CSS?**
    
    São escritas ou códigos que não afetam o resultado escrito no documento, sendo eles indicados por `/*` e `*/`.
    
    ```css
    /* Isso é um comentário*/
    ```
    
- **Como é a anatômia do CSS?**
    
    Primeiro definimos um *selector* (a tag HTML que desejamos estilizar), a *declaration* (local onde será definido as propriedades e valores para de estilização da tag), as *properties* (as propriedades de estilização) e *property* *value* (o valor de cada propriedade definida). Essa anatômia é exemplificada a seguir.
    
    ```css
    h1 {
    	color: red;
    	font-size: 10px
    }
    ```
    
- **O que são seletores?**
    
    É a conexão do elemento HTML com o CSS. Essa conexão pode ser feita de várias formas:
    
    - **Global selector** que indica a conexão com todos os elementos e é definida pelo carácter `*`.
    - **Element/Type Selector** que indica a conexão com elementos especificos e é definida por uma ou mais tags. Por exemplo `h1`, `p`, `div`, etc.
    - **ID Selector** que indica a conexão com a tag que contém o indentificar definido. Essa conexão é feita através do `#` seguido do nome do identificado, como por exemplo `#identificador`.
    - **Class Selector** que indica a conexão com todas as tags que contém a classe definida, ou seja, todas as tags que possuem a classe recebem a estilização definida na declaração do CSS. Essa conexão é feita através do `.` seguido do nome da classe, como por exemplo `.classe`.
    - e diversos outros que podem ser observados no [MDN](https://developer.mozilla.org/pt-BR/docs/Web/CSS/Getting_Started/Seletores).
- **O que é Box Model?**
    
    É o conceito trabalho no CSS, onde todo elemento é trabalhado dentro de uma caixa, onde possui largura, altura, limites internos e externos, como demonstrado a seguir.
    
    ![O%20guia%20estelar%20de%20CSS%20f4c10c42855143839ee54ceb1dadf805/Untitled.png](O%20guia%20estelar%20de%20CSS%20f4c10c42855143839ee54ceb1dadf805/Untitled.png)
    
- **Como adicionar o CSS no HTML?**
    
    Temos básicamente quatro formas de estilizar o HTML utilizando CSS:
    
    - **inline** é quando injetamos a estilização dentro da própria tag
        
        ```html
        <h1 style="color: red; font-size: 100px">Meu título</h1>
        ```
        
    - **style** é quando escrevemos a estilização dentro da tag `<head>`
        
        ```html
        <head>
        	<style>
        		h1 {
        			color: blue;
        			font-size: 20px
        		}
        	</style>
        </head>
        ```
        
    - **link** é quando definimos um link para o documento .css qua contém a estilização que desejamos acrescentar na página
        
        ```html
        <head>
        	<link rel="stylesheet" href="caminho-do-documento/documento.css" />
        </head>
        ```
        
    - **import** é quando definimos dentro do documento/trecho que estilização a fonte de materiais que desejamos importar
        
        ```css
        @import url('https://fonts.googleapis.com/css2?family=Reggae+One&display=swap');
        
        h1 {
        	font-family:'Reggae One'
        }
        ```
        
- **O que é o conteito de cascata?**
    
    Cascata é o conceito de leitura que o browser aplica na leitura do documento .css, o que defini qual regra aplicar na interpretação do elemento que possui muitas regras de estilização.
    
    A leitura do documento .css é feita de cima para baixo, ou seja, se houver uma proprieda definida em uma tag e depois a mesma propriedade for definida de forma diferente mais a baixo, a última definição é que será apresentada na página
    
    ```css
    h1 {
    	color: red
    }
    
    h1 {
    	color: blue
    }
    ```
    
    e é leva 3 fatores em consideração:
    
    - **Origem do estilo**, onde é definido a força de cada tipo de declaração como demonstrado abaixo onde os métodos mais a esquerda são mais fortes do que os da direita.
        
        <aside>
        ⚠️ **inline → tag style → linl**
        
        </aside>
        
    - **Especificidade**, onde é um cálculo matemático, onde, cada tipo de seletor e origem de estilo, possuem valores a serem considerados, ou seja, cada tipo de seletor e origem defini um peso para a declaração como demonstrado na tabela abaixo.
        
        [Foças de especificidade](O%20guia%20estelar%20de%20CSS%20f4c10c42855143839ee54ceb1dadf805/Foc%CC%A7as%20de%20especificidade%2011cbfa6849584d0b93f7585aa13832bc.csv)
        
        Dessa a declaração onde o valor de seleção/origem for maior será a escolhida para ser apresentada na página.
        
        No caso de combinações de seletores é realizado a soma de seus pesos, por exemplo, temos `body h1` (**element type selector + element type selector**) onde a soma de seus pesos (**1+1**) é **2** `h1.title#my-title` (**element type selector + class + id**) que por sua vez têm a soma (**1+10+100**) que resulta em **111**. Dessa forma a segunda declaração sobrepõe a primeira.
        
    - **Importância** é uma regra que quebra o fluxo natural da cascata, ou seja, ela sobrescrevendo qualquer declaração onde ela é referenciada. Para aplicar essa regra basta utilizar `!important` na frente da prorpriedade que deseja definir, como demonstrado abaixo.
        
        ```css
        h1 {
        	color: blue !important
        }
        ```
        
        Dessa forma, qualquer que seja a força aplicada sobre `h1` a propriedade definida como `!important` é a que vai ser representada na página.
        
        Esse regra deve ser evitado de ser usado, pois também não é considerado uma boa prática. Sendo essa prática somente indicada em casos de definição de elementos pertencentes a bibliotecas que não está sendo sendo possível alterar.
        
    - ***Links extras***
        
        [Type selectors](https://developer.mozilla.org/pt-BR/docs/Web/CSS/Type_selectors)
        
        [CSS Pseudo-elements](https://www.w3schools.com/css/css_pseudo_elements.asp)
        
        [CSS Attribute Selector](https://www.w3schools.com/css/css_attribute_selectors.asp)
        
        [CSS :not Selector](https://www.w3schools.com/cssref/sel_not.asp)
        
        [CSS Combinators](https://www.w3schools.com/css/css_combinators.asp)
        
- **O que é At Rules?**
    
    São sinais que se relacionam ao comportamento do CSS, sendo eles representados pelo `@` seguido do indentificador e valor. Alguns tipos de At Rules são:
    
    - `@import` que inclui um CSS externo.
        
        ```css
        @import "https://local.com/style.css";
        /*ou*/
        @import url("https://local.com/style.css");
        ```
        
    - `@media` que defini regras condicionais para dispositivos.
        
        ```css
        @media (min-width: 500px) {
        	/*declarações para dispositivos com no mínimo 500px de largura*/
        }
        ```
        
    - `@font-face` que defini fontes externas.
        
        ```css
        @font-face {
        	/*declarações relacionadas a fontes externas*/
        }
        ```
        
    - `@keyframes` que defini animações.
        
        ```css
        @keyframes nomedaanimação {
        	/*declarações relacionadas a animação definida*/
        }
        ```
        
    - entre outras.
- **O que é Shorthand?**
    
    Shorthand é uma forma de junção de propriedades, sendo essa uma forma resumida e legível de definições de propriedades. Por exemplo, no caso da propriedade background
    
    ```css
    {
    	background-color:white;
    	background-image: url(images/bg.gif);
    	background-repeat: no-repeat;
    	background-position: left top
    }
    ```
    
    podemos utilizar sua forma shorthand.
    
    ```css
    {
    	background: white url(images/bg.gif) no-repeat left top;
    }
    ```
    
    Outro exemplo é a fonte
    
    ```css
    {
    	font-style: italic;
    	font-wight: bold;
    	font-size: .8em;
    	font-height: 1.2;
    	font-family:Arial, sans-serif
    }
    ```
    
    onde sua shorthand é a seguinte.
    
    ```css
    {
    	font: italic bold .8em/1.2 Arial, sans-serif;
    }
    ```
    
    É importante ressalta que a forma shorthand sobrescreve as declarações definidas para o elemento e propriedades anteriormente.
    
    Valores não declarados assumem os valores padrão da propriedade, sendo também importante definirmos os valores na ordem correta (mesmo que às vezes não influência no resultado).
    
    Algumas propriedades que aceitam o shorthand são:
    
    <aside>
    ✏️ animation, background, border, border-style, border-radius, border-width, border-color, border-left, border-right, border-bottom, border-top, column-rule, columns, flex, flex-flow, font, grid, grid-area, grid-column, grid-row, grid-template, list-style, margin, offset, outline, overflow, padding, place-content, place-items, place-self, text-decoration, trasition
    
    </aside>
    
    - **Links extras**
        
        [Shorthand properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Shorthand_properties)
        
- **Como são as funções no CSS?**
    
    As funções no CSS são um tipo de valor, sendo estes comoposto pela nome da função seguido de `(` e `)`, e recebendo argumentos (como em algumas linguagens de programação). Por exemplo
    
    ```css
    @import url("http://urlaqui.com/style.css")
    /*ou*/
    {
    	color: rgb(255, 0, 0);
    }
    /*ou*/
    {
    	width: calc(100% - 10px);
    }
    ```
    
- **O que DevTools?**
    
    É uma kit de ferramentas utilizado por desenvolvedores e outros profissionais de tecnologia. O kit mais conhecido atualmente é o do próprio navegador, sendo este acessado *Customize and control Google Chrome → More tools → Developer tools* ou **F12.
    
    Através desse kit podemos acessar os arquivos .html, .css. e .js da página, entre outras ferramentas relacionadas a desenvolvimento web.
    
- **Quais cuidados com a escrita de um código CSS devemos ter?**
    
    A formatação na escrita do CSS assim como outros aquivos de código é muito importante, pois além de manter a escrita organizada e visualmente agradável, a formatação nos ajuda a evitar erros de lógica, semântica e outros fatores importantes para a construção de um bom código.
    
    Pontos importantes para se ter atenção no código são a sintaxe, identação e em alguns casos o espaçamento.
    
- **O que é Vendor Prefixes?**
    
    Vendor Prefixes permite que browsers adicione *features* a fim de colocar alguma novidade que vemos no CSS, fazendo assim que diversos browsers possam utilizar essas novas features. Para exemplificar melhor podemos adicionar a feature `backgroud-clip` para dispositivos diferentes através das seguintes propriedades:
    
    ```css
    p {
    	-webkit-background-clip: text; /*Chrome, Safari, iOS e Android*/
    	-moz-background-clip: text; /*Mozilla (Firefox)*/
    	-ms-background-clip: text; /*Internet Explorer*/
    	-o-background-clip: text; /*Opera*/
    }
    ```
    
    Para utilizar da melhor forma o Vendor Prefixes podemos buscar no [Which Vendor Prefix](http://ireade.github.io/which-vendor-prefix/) quais browsers têm ou não suporte a feature, e também temos o [Can I Use](https://caniuse.com/) que nos permite ter essas informações, mas com mais apresentação.