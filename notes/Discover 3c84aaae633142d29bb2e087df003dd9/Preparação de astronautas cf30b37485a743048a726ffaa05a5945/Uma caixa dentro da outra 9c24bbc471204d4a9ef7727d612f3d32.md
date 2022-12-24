# Uma caixa dentro da outra

> *Site: [https://app.rocketseat.com.br/node/uma-caixa-dentro-da-outra](https://app.rocketseat.com.br/node/uma-caixa-dentro-da-outra)*
> 

Um dos conceitos mais importantes do CSS, o Box Model, traz sentido para como muitas regras de posicionamento funcionam.

- **O que é Box Model?**
    
    É o conceito fudamental para fazer layouts para a web, pois ele traz uma maior facilidade de aplicar o CSS.
    
    Basicamente, Box Model é uma caixa retangular (em 2D) que envolve todo elemento HTML. Toda caixa possuem propriedades como:
    
    - `width` (largura);
    - `height` (altura);
    - `content` (conteúdo);
    - `boder` (bordas);
    - `padding` (preenchimento interno), e;
    - `margin` (espaços fora da caixa).
        
        ![https://miro.medium.com/max/1450/1*2jZwpWH9XO_QllhEpyGqMA.png](https://miro.medium.com/max/1450/1*2jZwpWH9XO_QllhEpyGqMA.png)
        
- **O que é box-sizing?**
    
    É a propriedade que realiza a padronização de calculo tamanho da caixa do elemento através do CSS, ou seja, é a partir desta propriedade que pode ser padronizado o calculo para o CSS das propriedades que influenciam diretamente no Box Model.
    
    O box-sizing pode conter dois valores:
    
    - `content-box`, que se baseia apenas no conteúdo para calcular tamanho do Box Model para que o conteúdo tenha o tamanho definido.
    - `border-box`, que se baseia a partir da bordar para calcular tamanho do Box Model para que a caixa tenha o tamanho definido.
    
    ```bash
    div {
    	width: 100px;
    	height: 100px;
    	border: 1px solid red;
    	margin: 10%
    	padding: 0 20px;
    	box-sizing: border-box;
    }
    ```
    
    <aside>
    ⚠️ Utilizar `border-sizing` é o mais indicado, pois através dele é possível calcular o valor do Box Model a partir da borda, o que possibilita calculos mais simples e evita problemas com tamanho de elementos no futuro.
    
    </aside>
    
- **O que é display?**
    
    É a propriedade que define como as caixas se comportam em relação às outras caixas, ou seja, como as caixas vão se ajustar dentro da tela relacionando uma a outra.
    
    Para isso temos dois principais tipos:
    
    - `block`, faz com que a caixa ocupe toda linha, colocando assim as próximas caixas abaixo dela. Dessa forma, o width e o height serão respeitados e o padding, margin e border irão funcionar normalmente.
    - `inline`, faz com que as caixas tentem ocupar a mesma linha, ou seja, uma caixa ao lado da outra. Assim, o width e o height não funcionam corretamente. Também, somente o padding, margin e border **horizontal** funcionam corretamente.
    
    É importante saber que, todo elemento já possue um comportamento padrão, alguns possuem o comportamento `block` e outros `inline`. Por exemplo:
    
    - block: `<p>`, `<div>`, `<section>`, `<h1>`, ...
    - inline: `<a>`, `<strong>`, `<spam>`, `<em>`, ...
- **Como funciona o margin?**
    
    Margin é os espaços entre os elementos e pode ser definido para cada lado (`top`, `rigth`, `bottom` e `left`) da caixa do elemento.
    
    Os type values que o margin aceita são basicamente o **length**, **percentage** e **auto.**
    
    <aside>
    ⚠️ O value **auto** no `display: block` se aplica somente a distância horizontal (não a vertical)
    
    </aside>
    
    <aside>
    💡 É importante citar que a propriedade margin utiliza shorthand.
    
    </aside>
    
    <aside>
    ⚠️ É importante citar que, por padrão a página já possui `8px` de margin.
    
    </aside>
    
    <aside>
    ⚠️ Evite margin collapsing!
    
    </aside>
    
- **O que é shorthand?**
    
    Algumas propriedades aceitam a definição de seus valores de forma resumida, o que permite uma estilização mais limpa. As propriedades principais que aceitam o shorthand são o margin e o padding.
    
    Para entender o conceito de shorthand, pode utilizar as proprieades citadas acima onde estas funcionam semelhante a um relógio.
    
    ![Uma%20caixa%20dentro%20da%20outra%209c24bbc471204d4a9ef7727d612f3d32/Untitled.png](Uma%20caixa%20dentro%20da%20outra%209c24bbc471204d4a9ef7727d612f3d32/Untitled.png)
    
    Para casos de shorthand de valores apenas, pode-se utilizar de quatro formas, como demonstrado abaixo:
    
    - 4 values
        
        ```css
        margin: 1px 2px 3px 4px;
        /*ou seja, top, right, bottom e left*/
        ```
        
    - 3 values
        
        ```css
        margin: 1px 2px 3px;
        /*ou seja, top, horizontal e bottom*/
        ```
        
    - 2 values
        
        ```css
        margin: 1px 2px;
        /*ou seja, vertical e horizontal*/
        ```
        
    - 1 value
        
        ```css
        margin: 1px;
        /*ou seja, all sides*/
        ```
        
    
    <aside>
    ⚠️ Para mais informações acesse a [documentação do MDN](https://developer.mozilla.org/pt-BR/docs/Web/CSS/Shorthand_properties).
    
    </aside>
    
- **O que é margin collapsing?**
    
    É a colisão da priedade margin de dois ou mais elementos, ou seja, em alguns casos (principlamente no display block) os element podem utilizar a propriedade margin de forma inesperado, fazendo com que a margem seja aplicada de forma ajustada e não explicita.
    
    Para explicar melhor, observe o exemplo abaixo.
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <link rel="stylesheet" href="style.css">
        <title>Document</title>
    </head>
    <body>
        <div>Conteúdo 1</div>
        <div>Conteúdo 2</div>
    </body>
    </html>
    ```
    
    ```css
    div {
    	border: 1px solid;
    	height: 100px;
    	width: 100px;
    	margin: 10px 10px;
    }
    ```
    
    Por padrão, com o `display: block` o primeiro elemento vai possuir uma margem em cima de `10px`, entre os elementos `10px` também e em baixo `10px`.
    
    ![Uma%20caixa%20dentro%20da%20outra%209c24bbc471204d4a9ef7727d612f3d32/Untitled%201.png](Uma%20caixa%20dentro%20da%20outra%209c24bbc471204d4a9ef7727d612f3d32/Untitled%201.png)
    
    No caso de aplicar o `display: inline`, as magens laterais são somadas resultando em `20px`.
    
    ![Uma%20caixa%20dentro%20da%20outra%209c24bbc471204d4a9ef7727d612f3d32/Untitled%202.png](Uma%20caixa%20dentro%20da%20outra%209c24bbc471204d4a9ef7727d612f3d32/Untitled%202.png)
    
    Assim, pode-se perceber que as margens podem colidar de forma que o cálculo resulte em um resultado explícito.
    
- **Como funciona o padding?**
    
    Muito semelhante ao margin, padding também recebe shorthand e pode receber valores length e pecentage (neste caso o auto não funciona).
    
    Como também explicado em box-sizing, a propriedade padding pode causar diferença na largura e altura de um elemento, ou seja, ao acrescentar o padding a um elemento pode haver diferença na cálculo do valor definido para a largura e altura deste.
    
- **Como funciona o border?**
    
    Basicamente este define a borda de uma caixa. Seus valores são a **style**, **width** e **color**.
    
    A propriedade border pode receber o formato shorthand utilizando os valores citados acima.
    
    ```css
    border: solid 1px red;
    ```
    
    Por padrão propriedade border aplica os valores as quatro bordas, caso se necessário definir para algum canto específico precisa-se utiizar o indicativo de lado, ou seja, `border-top`, `border-rigth`, `border-bottom` e `border-left`. Pode-se também mesclar alguns destes dependendo da necessidade como, `border-top-left`.
    
    Os types aceitos para cada valor desta propriedade são:
    
    - **style**: define o estilo e aceita os valores reservados `solid`, `dotted`, `double`, `groove`, `ridge`, `inset` e `outset`;
    - **width**: aceita valores do tipo length, e;
    - **color**: aceita todos os valores colors.
    
    <aside>
    ⚠️ O border também afeta o tamanho da caixa, ou seja, a espessura da bordar é somada ao tamanho da caixa, pois esta espessura é adicionada na parte externa da caixa. E como citado anteriormente, se o interesse for manter os valores de altura e largura já definidos, utilize o `box-sizing: border-box`. Assim, a espessura da bordar é adicionada para o lado interno da caixa.
    
    </aside>
    
    <aside>
    ⚠️ Para mais informações sobre o border acesse a [documentação do MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/border).
    
    </aside>
    
- **Como funciona o outline?**
    
    É uma propriedade que por padrão adiciona um tipo de bordar na parte externa da caixa, ou seja, está propriedade não afeta o tamanho da caixa em si porque não faz parte do Box Model.
    
    O outline também é muito utilizado pelo user-agent para questões de acesssibilidade.
    
    ```css
    outline: solid 1px yellow;
    ```
    
    Outro ponto é, o outline têm a desvantagem se comparado ao border de não ter ajuste individuais, como seria o caso do `border-top`, `border-left` e etc.