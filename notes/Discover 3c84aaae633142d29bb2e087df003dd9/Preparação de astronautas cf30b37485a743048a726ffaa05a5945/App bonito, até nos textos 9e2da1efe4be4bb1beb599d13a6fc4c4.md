# App bonito, até nos textos

> *Site: [https://app.rocketseat.com.br/node/app-bonito-ate-nos-textos](https://app.rocketseat.com.br/node/app-bonito-ate-nos-textos)*
> 

Não adianta a aplicação estar linda, mas usando Comic Sans como fonte e, por isso, vamos aprender sobre tipografia na web com CSS.

# Trabalhando com fontes

- **Por que trabalhar com fontes?**
    
    Toda tipo fonte têm o poder de transmitir uma mensagem, seja através de seu estilo, cor, tamanho, etc.
    
    De forma resumida, cada tipografia transmite um significado diferente. Por isso, é importante definir antecipadamente qual mensagem é desejada ser transmitida para o usuário.
    
- **Quais são as propriedades básicas de fontes no CSS?**
    
    Basicamente são, `font-family`, `font-wigth`, `font-style` e `font-size`.
    
- **O que é font-family?**
    
    É o familia da fonte que será aplicada, sendo estas listadas de forma de prioridade, ou seja, será aplicada a fonte que vier primeiro, caso está não esteja disposnível será aplicada a seguinte, e assim por diante.
    
    <aside>
    ⚠️ Esse conceito de prioridade é conhecido como **fallback**.
    
    </aside>
    
    ```css
    p {
    	font-family: "Times New Roman", Times, serif;
    }
    ```
    
    <aside>
    ⚠️ Para mais informações sobre font-family acesse a [documentação do MDN](https://developer.mozilla.org/pt-BR/docs/Web/CSS/font-family).
    
    </aside>
    
- **Qual a diferença das fontes com serif, sans serif e slab serif?**
    
    Dentro das disciplinas básicas de tipográfia temos resumidademente este três tipos de fontes.
    
    ![App%20bonito,%20ate%CC%81%20nos%20textos%209e2da1efe4be4bb1beb599d13a6fc4c4/Untitled.png](App%20bonito,%20ate%CC%81%20nos%20textos%209e2da1efe4be4bb1beb599d13a6fc4c4/Untitled.png)
    
    - **San Serif** (Questa Sans), não possui estilização na tipografia;
    - **Serif** (Questa), possui estilização nas bordas da tipografia, e;
    - **Slab Serif** (Questa Slab), possui uma estilização retângular na tipografia.
- **O que é font-weight?**
    
    É definido como o peso da fonte, ou seja, a espessura da fonte.
    
    Os valores básicos para esta propriedade são:
    
    - `bolder`, para definir a espessura da fonte como a mais grossa possível;
    - `bold`, para definir a espessura da fonte como mais grossa;
    - `normal`, para definir a espessura da fonte como normal;
    - `ligther`, para definir a fonte mais fina, e;
    - valores numéricos.
    
    ```css
    p {
    	font-weight: bold;
    }
    ```
    
    Dependendo da font-family utilizada a quantidade de pesos da fonte pode se limitar.
    
    <aside>
    ⚠️ Para aprender mais sobre font-weigth acesse a [documentação do MDN](https://developer.mozilla.org/pt-BR/docs/Web/CSS/font-weight).
    
    </aside>
    
    <aside>
    ⚠️ Para simular e aprender mais sobre font-wigth acesse o [simulador do W3C School](https://www.w3schools.com/cssref/playit.asp?filename=playcss_font-weight).
    
    </aside>
    
- **O que é font-style?**
    
    É a propriedade que defini o estilo da fonte, ou seja, se é itálico, oblíquo, etc.
    
    As propriedades básicas são `normal`, `italic`, `oblique` e `oblique 40deg`.
    
    ```css
    p {
    	font-style: oblique;
    }
    ```
    
    <aside>
    ⚠️ Está propriedade também depende da familia da fonte utilizada.
    
    </aside>
    
    <aside>
    ⚠️ Para mais informações acesse a [documentação do MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/font-style).
    
    </aside>
    
- **O que é font-size?**
    
    É a propriedade que define o tamanho da fonte.
    
    <aside>
    ⚠️ Para mais informações consulte a [documentação do MDN](https://developer.mozilla.org/pt-BR/docs/Web/CSS/font-size).
    
    </aside>
    
- **O que é web-fonts?**
    
    Há fontes do sistema e fontes da web. As fontes do sistema são aquela instaladas localmente, mas com o risco de não haver a mesma fonte em todos os computadores pode-se preferir utilizar as fontes da web.
    
    Para utilizar estas fontes da web, o CSS permite aplicá-las basicamente de três formas:
    
    - **font-face**, é utiliza para específicar uma font personalizada para aplicar a algum texto. Pode-se aplicar a função `local()` para buscar no computador local ou `url()` para buscar remotamente.
        
        É necessário passar o nome da fonte, o local a ser buscado e o formato (nem sempre é necessário).
        
        ```css
        @font-face {
          font-family: "Open Sans";
          src: url("/fonts/OpenSans-Regular-webfont.woff2") format("woff2"),
               url("/fonts/OpenSans-Regular-webfont.woff") format("woff");
        }
        ```
        
        <aside>
        ⚠️ Para mais informações sobre font-face acesse a [documentação do MDN](https://developer.mozilla.org/pt-BR/docs/Web/CSS/@font-face).
        
        </aside>
        
    - **import**, é utilizada para aplicar regras de estilo de documentos externos.
        
        ```css
        @import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');
        ```
        
        <aside>
        ⚠️ Para mais informações sobre import acesse a [documentação do MDN](https://developer.mozilla.org/pt-BR/docs/Web/CSS/@import).
        
        </aside>
        
    - **link**, onde é importado como link no html a fonte desejada.
        
        ```html
        <link rel="preconnect" href="https://fonts.gstatic.com">
        <link href="https://fonts.googleapis.com/css2?family=Roboto&display=swap"
        rel="stylesheet">
        ```
        
        <aside>
        ⚠️ Para mais informações sobre link para CSS acesse a [documentação do W3C](https://www.w3schools.com/tags/tag_link.asp).
        
        </aside>
        
    
    Para facilitar está tarefa o Google disponibiliza o site do [Google Fonts](https://fonts.google.com/) com algumas fontes grátis e de fácil importação.
    

# Mais estilos para textos

- **O que é font-variant?**
    
    É uma propriedade que permite uma maior estilização contrastando as letras maiúsculas e deixando as minúsculas menores do que o tamanho padrão da fonte.
    
    Para aplicar basta utilizar o valor small-caps para a propriedade.
    
    ```css
    p {
        font-variant: small-caps;
    }
    ```
    
    E terá um resultado como este.
    
    ![App%20bonito,%20ate%CC%81%20nos%20textos%209e2da1efe4be4bb1beb599d13a6fc4c4/Untitled%201.png](App%20bonito,%20ate%CC%81%20nos%20textos%209e2da1efe4be4bb1beb599d13a6fc4c4/Untitled%201.png)
    
    <aside>
    ⚠️ Para mais informações sobre font-variant acesse a [documentação do MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant).
    
    </aside>
    
- **O que é font-stretch?**
    
    É a propriedade que permite o alargamento ou encolhimento da fonte. Basicamente, seu valores são `expanded`, `ultra-expanded`, `extra-expanded`, `condensed`, `ultra-condensed`, `extra-condensed`, `normal` e valores de porcentagens (de `50%` a `200%`).
    
    ```css
    font-stretch: expanded;
    ```
    
    <aside>
    ⚠️ Como em todos os casos está também não funciona em todas as famílias de fontes.
    
    </aside>
    
    <aside>
    ⚠️ Para mais informações sobre font-stretch acesse a [documentação do MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/font-stretch).
    
    </aside>
    
- **O que é letter-spacing?**
    
    É a propriedade que define espaços entre os caracteres.
    
    Está prorpriedade aceita valores length.
    
    ```css
    letter-spacing: 10em;
    ```
    
    <aside>
    ⚠️ Para mais informações sobre letter-spacing acesse a [documentação do MDN](https://developer.mozilla.org/pt-BR/docs/Web/CSS/letter-spacing).
    
    </aside>
    
- **O que é word-spacing?**
    
    É a propriedade que define o espaço entre as palavras.
    
    Está propriedade também aceita valores length.
    
    ```css
    word-spacing: 2em;
    ```
    
    <aside>
    ⚠️ Para mais informações acesse a [documentação do MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/word-spacing).
    
    </aside>
    
- **O que é line-height?**
    
    É a propriedade que define personaliza o espaço entre as linhas.
    
    Seus valores podem ser com ou sem unidades de medidas.
    
    ```css
    line-height: 2.3;
    ```
    
- **O que é text-transform?**
    
    É a propriedade que permite a transformações de um texto, por exemplo, é possível transformar um texto para `uppercase`, `lowercase` ou `captalize`  através desta propriedade.
    
    ```css
    text-transform: lowecase
    ```
    
- **O que é text-decoration?**
    
    É a propriedade que define a aparencia decorativa de um texto. Está aceita três tipos de valores, line, style e color, e também é possível utilizar o shorthand com alguns casos de multivalores.
    
    ```css
    text-decoration: overline underline wavy red ;
    ```
    
- **O que é text-align?**
    
    É a propriedade que define o alinhamento de um texto. Seus valores podem ser `center`, `right`, `left` e `justify`.
    
    ```css
    text-align: center;
    ```
    
- **O que é text-shadow?**
    
    É a propriedade que permite definir sombra para o texto. Seus valor é constituído de posição e cor da sombra.
    
    A posição da sombra segue a sintaxe de eixo x e depois eixo y. O terceiro valor numérico é o blur radius da sombra, ou seja, o grau  de esfumaçamento da sombra.
    
    ```css
    text-shadow: 1em 2em 10px black;
    ```
    
- **Como funciona o Shorthand para fontes?**
    
    Shorthand é o formato de aplicar valores a algumas propriedades.
    
    No caso da `font` pode-se aplicar diversas estilizações condensando todas em uma regra. Por exemplo pode-se aplicar `font-style`, `font-variant`, `font-weight`, `font-stretch`, `font-size`, `line-height` e `font-family` em uma unica linha.
    
    ```css
    font: italic normal bold normal 2em/2 Helvetica, Arial, sans-serif;
    ```
    
    Dessa forma, pode-se obter um resultado semelhante a este.
    
    ![App%20bonito,%20ate%CC%81%20nos%20textos%209e2da1efe4be4bb1beb599d13a6fc4c4/Untitled%202.png](App%20bonito,%20ate%CC%81%20nos%20textos%209e2da1efe4be4bb1beb599d13a6fc4c4/Untitled%202.png)
    
    <aside>
    ⚠️ Um ponto importante para se atentar ao definir um shorthand para a font é que,  os valores de **font-size** e **line-height** são separados por uma `/`.
    
    </aside>
    

<aside>
⚠️ Para mais informações sobre estilização de fonts acesse a [documentação do MDN](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals).

</aside>