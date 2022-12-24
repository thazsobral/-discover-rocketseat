# Nem tudo são pixels

> *Site: [https://app.rocketseat.com.br/node/nem-tudo-sao-pixels](https://app.rocketseat.com.br/node/nem-tudo-sao-pixels)*
> 

Aplicações modernas não utilizam apenas uma unidade de medida e, por isso, vamos aprender sobre todas unidades e possibilidades.

- **O que são valores e unidades de medidas no CSS?**
    
    Toda propriedade possui valores, e dependendo do valor é aplicado uma medida a ele. É através dessas medidas que possível especificar com precisão o valor passado.
    
    ```css
    property: value;
    ```
    
    <aside>
    ⚠️ Para mais informações acesse a [documentação do MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Values_and_Units).
    
    </aside>
    
    Os valores ou data types aplicados no CSS podem ser dos tipos:
    
    - numéricos, ou;
    - unidades comuns;
- **Quais são os valores numéricos?**
    
    Os valores do tipo numérico são:
    
    - **integer**, são números inteiros como -10 ou 223
    - **number**, são números decimais como -2.1, 42 ou 0.333
    - **dimension**, é um **number** com uma unidade junto, por exemplo, 90deg, 2s, 9px
    - **percentagem**, representa a fração de outro número, por exemplo, 12%
- **Quais são os valores de unidades comuns?**
    
    Os valores do tipo unidade comum são:
    
    - **length**, representa um valor de distância como, px, em, vw
    - **angle**, representa um valor de ângulo como, deg, rad, turn
    - **time**, representa um valor de tempo como, s, ms
    - **resolution**, representa um valor de resolução para dispositivos como, dpi
- **O que são distâncias absolutas?**
    
    São unidades utilizadas no data type **length**. Seus valores são fixos e não se alteram, ou seja, será o mesmo valor aplicado independente da tela, dispositivo, etc.
    
    Essas unidades são:
    
    - `cm` (centímetros), para enter melhor, 1cm é igual a 96px/2.54
    - `in` (inches ou polegadas), para enter melhor, 1in é igual a 2.54cm que é o mesmo que 96px
    - `px` (pixels), para enter melhor, 1px é igual a 1/96th de in
    
    <aside>
    ⚠️ A unidade mais comum de se utilizar é o `px`, sendo o `cm` o menos indicado para se utilizar.
    
    </aside>
    
- **O que são distâncias relativas?**
    
    São unidades utilizadas do data type length. Mas diferente do tópico acima, esses valores são relativos a algum outro valor de referência. Esse valor de referência pode ser o elemento pai, elemento root ou o tamanho da própria tela.
    
    A maior vantagem de se utiizar este tipo de unidade é a sua adaptabilidade aos tipos e mananhos de tela.
    
    Essas unidades são:
    
    - `em`, é uma medida relativa ao tamanho do elemento pai, ou seja, dependo do tamanho definido para o elemento pai o elemente apontado terá um tamanho
    - `rem`, é uma medida relativa ao tamanho do elemento raiz (root/html)
    - `vw`, é a medida relativa ao tamanho da width (largura) da viewport (janela). Para cada `1vw` é trabalha 1% da largura da janela.
    - `vh`, é a medida relativa ao tamanho da heigth (altura) da viewport (janela). Para cada 1vh é trabalha 1% da altura da janela.
- **Como funciona as porcentagem?**
    
    Está unidade de medida de `%` (porcentagem) sempre têm seu tamanho relativo ao elemento pai.
    
- **Como funciona as positions?**
    
    Os valores de posições representam um conjunto de posições em 2D (top, right, bottom, left e center).
    
    <aside>
    ⚠️ Este valor não pode ser confundido com a propriedade postion.
    
    </aside>
    
    ```css
    target_class {
    	heigth: 400px;
    	width: 500px;
    	background-image:url(http://source.unsplash.com/random);
    	background-repeat: no-repeat;
    	background-position: center 50px;
    }
    ```
    
- **O que é função no CSS?**
    
    Funções assim como em outras liguagens (principalmente em programação) têm o objetivo de reaproveitar código.
    
    As funções mais comuns no CSS são:
    
    - `rgb()`, têm como objetivo retornar uma cor de acordo com a combinação de valores que representam as cores RED (vermelhor), GREEN (verde) e BLUE (azul).
        
        ```css
        selector { 
        	color: rgb(255, 255, 255); 
        }
        ```
        
    - `hsl()`, têm como objetivo retornar uma cor de acordo com a combinação de valores que representam RUE (tom), SATURATION (saturação) e LIGHTNESS (luminosidade).
        
        ```css
        selector { 
        	color: hsl(120, 75%, 50%); 
        }
        ```
        
    - `hsla()`, têm como objetivo retornar uma cor de acordo com a combinação de valores que representam RUE (tom), SATURATION (saturação), LIGHTNESS (luminosidade) e ALPHA-OPACITY (opacidade alfa).
        
        ```css
        selector { 
        	color: hsla(120, 80, 35%, 0.4%); 
        }
        ```
        
    - `rgba()`, têm como objetivo retornar uma cor de acordo com a combinação de valores que representam as cores RED (vermelhor), GREEN (verde), BLUE (azul) e ALPHA-OPACITY (opacidade alfa).
        
        ```css
        selector { 
        	background: linear-gradient(to bottom, rgba(0, 0, 0, 0.8), transparent)};
        }
        ```
        
    - `url()`, têm como objetivo retornar o conteúdo (geralmente imagem) da URL passada.
        
        ```css
        selector { 
        	background-image:url(http://source.unsplash.com/random);
        }
        ```
        
    - `calc()`, têm como objetivo retornar valores através de calculos realizados através das próprias propriedades do CSS.
        
        ```css
        html {
        	height: 100vh;
        }
        selector {
        	height: calc(100% - 20px);
        }
        ```
        
- **O que são strings no CSS?**
    
    São valores de texto envolvidos em `"` (aspas).
    
    ```css
    .box::after {
    	content: "Uma mensagem para a box";
    	color: red;
    }
    ```
    
- **O que são identificadores no CSS?**
    
    São valores pré definidos que já possuem um determinado significado para a linguagem CSS. Por exemplo, o `red` é um identificador da cor vermelha.