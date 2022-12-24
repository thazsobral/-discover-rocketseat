# HTML que faz sentido, para todos

> *Site: [https://app.rocketseat.com.br/node/html-que-faz-sentido-para-todos](https://app.rocketseat.com.br/node/html-que-faz-sentido-para-todos)*
> 

A web é um espaço para todos e, por isso, precisamos entender sobre semântica dos elementos e acessibilidade do HTML.

<aside>
⚠️ Como pré-requisito para está etapa é o [básico de html](../Guias%20estelares%20f646f0008d684cfbab90f33620af781b/O%20guia%20estelar%20de%20HTML%201e77fb697fb0422bbb9aa467f9626dee.md).

</aside>

- **O que é uma web semântica?**
    
    Significa adicionar significado ao conteúdo HTML. Dessa forma, é possível **controlar** e **organizar** melhor a apresentação do conteúdo. Para isso, existem **padrões** e **convenções** que permitem a identificação do conteúdo de forma intencional ou não. Por exemplo,
    
    ![HTML%20que%20faz%20sentido,%20para%20todos%20471b3d62b51341ba8fcb7769d039a526/Untitled.png](HTML%20que%20faz%20sentido,%20para%20todos%20471b3d62b51341ba8fcb7769d039a526/Untitled.png)
    
    observando a imagem acima é possível identificar seus elementos, sendo que uns só bastá uma olhada rápida, e outros precisa-se de mais atenção sobre seu significado. Mas todos podem ser identificados.
    
    Ao utilizar uma marcação semântica consistente em, **auxíliar o user agent** (browser) na identificação correta dos elementos para a melhor apresentação do conteúdo.
    
    <aside>
    ⚠️ É importante ressaltar que, para se obter um HTML bonito e semântico, **não** necessariamente vai utilizar **apenas o HTML**.
    
    </aside>
    
    Outro ponto de se utilizar um HTML semântico é a **acessibilidade**, por exemplo, para usuários que necessitam de um leitor de página, o HTML semântico é imprescindível.
    
    Além disso, um HTML com boa semântica e organizado auxília também no trabalho dos **motores de busca**, onde eles dão preferência para sites com uma semântica bem estruturada.
    
- **Qual é a importância das tags HTML semânticas?**
    
    Basicamente são através das tags que pode-se criar a semântica do HTML. Há algumas tags que por si só já possuem significado e orientações de onde devem ficar na página, dando assim uma razão para a existência delas.
    
    Alguns exemplos de tags com finalidades semânticas são:
    
    - blockquote, que têm como finalidade apresentar uma citação.
    Em alguns casos podemos visualizar o seguinte trecho.
        
        ```html
        <p>
        Nós (programadores), somo pagos para resolver problemas,
        não memorizar soluções.
        																				-Maik Brito
        </p>
        ```
        
        Mesmo o trecho acima funcionando, o mais indicado semânticamente é o seguinte.
        
        ```html
        <blockquote>
        Nós (programadores), somo pagos para resolver problemas,
        não memorizar soluções.
        																				<cite>-Maik Brito</cite>
        </blockquote>
        ```
        
- **Qual a importância de entender os significados semânticos?**
    
    É responsábilidade do autor da página entender o significado dos elementos contidos nela. Mas muitas vezes está não é uma tarefa fácil, pois o HTML não oferece um leque tão extenso de elementos.
    
    <aside>
    ⚠️ É importante citar que, alguns elementos HTML serão utilizados em todos os elementos criados, mas há alguns que dificilmente serão vistos.
    
    </aside>
    
    Em muitos casos a marcação de conteúdo depende sisplesmente de gosto pessoal. Sendo assim, a marcação HTML pode variar de autor para autor.
    
    Um exemplo é está marcação de chat.
    
    ```html
    <p class="nome-chat">Marcos</p>
    <p class="msg-chat">Oi Ana</p>
    <p class="nome-chat">Ana</p>
    <p class="msg-chat">Oi Marcos, tudo bem?</p>
    ```
    
    Outro autor poderia fazê-la da seguinte forma.
    
    ```html
    <dl class="chat">
    	<dt>Marcos</dt>
    	<dd>Oi Ana</dd>
    	<dt>Ana</dt>
    	<dd>Oi Marcos, tudo bem?</dd>
    </dl>
    ```
    
    Ou poderia ser feito de outra forma como abaixo.
    
    ```html
    <blockquote>
    	<cite>Marcos</cite>
    	<p>Oi Ana</p>
    </blockquote>
    <blockquote>
    	<cite>Ana</cite>
    	<p>Oi Marcos, tudo bem?</p>
    </blockquote>
    ```
    
    Em ambos os casos a marcação vai funcionar. O importânte é conhecer que o HTML5 têm como objetivo melhorar a semântica da marcação.
    
- **Qual a diferença entre o HTML4 e HTML5?**
    
    Como citado anteriormente o HTML5 têm como foco construir páginas semânticas. A diferença entre está versão e sua anterior pode ser melhor visualizada com a imagem abaixo.
    
    ![HTML%20que%20faz%20sentido,%20para%20todos%20471b3d62b51341ba8fcb7769d039a526/Untitled%201.png](HTML%20que%20faz%20sentido,%20para%20todos%20471b3d62b51341ba8fcb7769d039a526/Untitled%201.png)
    
- **Quais são as seções comuns do HTML5?**
    
    As pricipais seções de documentos HTML são:
    
    - `<header>`, é o **cabeçalho** da página. Comumente as resposabilidades deste elemento são, conter a logo da página e disponibilizar o menu.
    - `<nav>`, é a **navegação** da site. Geralmente este elemente disponibiliza os liks para outras seções do site, podendo ser para a mesma página ou para outras.
    - `<main>`, é o **conteúdo principal** da página. Desta forma, este elemento apresenta o conteúdo principal da página.
    - `<aside>`, geralmente é a **barra lateral** da página. Em alguns sites, está barra pode ser fixa para a maioria das páginas do site. Comumente, a barra lateral apresenta anúncios, artigos, conteúdos curtos ou um menu de navegação.
    - `<article>`, é um **artigo** da página. Este elemento é considerado muitas vezes independente da página, ou seja, é um elemento que pode ser reaproveitado em outras pagina. Alguns exemplo de conteúdo que apresenta são, artigos, posts, gadget, widget interativo, ou qualquer outro conteúdo independente.
    - `<section>`, é uma **seção** para a página. Este elemento é genérico assim como o `<arcticle>`. Geralmente, este elemento contém um `<h1>` (título) quando não existir um elemento semântico mais específico para apresentá-lo.
    - `<footer>`, é o **rodapé** da página. Normalmente as responsabilidade desta seção são, apresentar informações de contato do dono do site (telefone, e-mail, endereço, etc) e apresentar links para outras páginas e informações do próprio site (como, data de criação, data de atualização, etc).
    
    ![HTML%20que%20faz%20sentido,%20para%20todos%20471b3d62b51341ba8fcb7769d039a526/Untitled%202.png](HTML%20que%20faz%20sentido,%20para%20todos%20471b3d62b51341ba8fcb7769d039a526/Untitled%202.png)
    
    ```html
    <body>
        <header>
            Logomarca
    
            <nav>
                <ul>
                    <li>link</li>
                </ul>
            </nav>
        </header>
    
        <main>
            Conteúdo principal
            <article>
                Artigo
                <section>
                    Seção
                </section>
            </article>
        </main>
    
        <aside>
            Parte lateral
        </aside>
    
        <footer>
            Rodapé
        </footer>
    </body>
    ```
    
- **Como funciona o Header?**
    
    Este é um elemento estrutural e semântico dentro do HTML. Ele é esrutural porque compõe uma estrutura dentro da marcação e semântico porque ele possui um significado para o autor, para a página e para os motores de busca.
    
    Ele é utilizado geralmente **no ínico da página**, sendo neste caso visto como um **header global** da página. Mas ele também pode ser utilizado **em outros elementos** da página como, no `<article>` e `<section>`, sendo neste caso considerado o `<header>` da seção. Dessa forma pode-se observar que é permitido ter **múltiplos headers** quando necessário.
    
    Locais onde o `<header>` **perde o sentido** são, dentro do próprio `<header>` ou dentro do `<footer>`, ou seja, dentro que qualquer lugar menos estes o `<header>` pode estar contido.
    
    <aside>
    👉 Uma característica interessante do elemento `<header>` é, ele possui o comportamente de ocupar a linha inteira, ou seja, quando adicionado o header, este ocupa toda a linha  independente da sua quantidade, e quando adicionado outro conteúdo, este é jogado para a linha seguinte.
    
    </aside>
    
    ```html
    <body>
    	<header>
    		Logomarca
    	</header>
    
    	<main>
    		<article>
    			<header>
    				Título do artigo
    			</header>
    			<p>
    				Conteúdo do artigo
    			</p>
    		<article>
    	</main>
    </body>
    ```
    
- **Como funciona o Nav?**
    
    Este elemento têm a função de conter links que apontam para outras seções, página ou até mesmo sites. O importante é saber que os **links mais importantes** estão contidos dentro dessa tag.
    
    Ele esta comumente contida dentro da seção `<header>` ou em outras seções.
    
    Outro ponto interessante é que, pode-se ver links no `<footer>`, ⚠️ Neste caso, não é necessário utilizar os links dentro da tag `<nav>`. Mas é válido citar que pode-se ter mais de um `<nav>` dentro da página.
    
    <aside>
    👉 Leitores de tela utilizam este elemento para tomar decisões relacionadas a semântica da página.
    
    </aside>
    
    ```html
    <body>
        <header>
            <nav>
                <ul>
                    <li>link</li>
                </ul>
            </nav>
        </header>
    
        <main>
            <article>
                <header>
                    <nav>
                        <ul>
                            <li>link</li>
                        </ul>
                    </nav>
                </header>
            </article>
        </main>
    
        <aside>
            <nav>
                <ul>
                    <li>link</li>
                </ul>
            </nav>
        </aside>
    
        <footer>
            <ul>
                <li>
                    link                
                </li>
            </ul>
        </footer>
    </body>
    ```
    
- **Como funciona o Main?**
    
    Por convenção este elemento é utilizado apenas uma vez na página. Geralmente o `<main>` é filho direto do `<body>`, contendo assim o conteúdo principal da página. Sendo assim, os outros elementos `<article>` ou `<section>` por convenção são filhos do elemento `<main>`.
    
    ```html
    <body>
        <main>
            <h1>Receitas</h1>
            <p>Está é uma página de receitas.</p>
    
            <article>
                <h2>Bolo de cenoura</h2>
                <p>Receita de bolo de cenoura</p>
            </article>
    
            <article>
                <h2>Pavê de chocolate</h2>
                <p>Receita de pavê de chocolate</p>
            </article>
        </main>
    </body>
    ```
    
- **Como funciona o Article?**
    
    Geralmente este elemente possue outros elementos que pode ser reaproveitado dentro da mesma página ou em outras páginas.
    
    O `<article>` pode estar contido dentro dentro de um elemento `<main>` ou diretamente dentro do `<body>` ou em qualquer outro elemento da página (se necessário). Geralmente, ele está está contido dentro do `<main>` quando há repetições na página, caso não, é comum o article está contido diretamente no `<body>`, podendo assim dispensar o `<main>`.
    
- **Como funciona o Aside?**
    
    Este elemento têm como objetivo apresentar conteúdo curtos relacionados ao conteúdo principal da página ou site.
    
    Algumas informações contidas dentro da tag `<aside>` são descrições curtas, glossários, links extras, biografia do autor ou informações de perfil.
    
    Geralmente este elemento é apresentado como uma barra lateral, mas pode também ser exibido em outros formatos. Mas por convenção, independente da forma que é apresentado o conteúdo contido nele deve sempre a mesma finalidade.
    
    ```html
    <body>
        <header>
            <nav>
                <ul>
                    <li>
                        link
                    </li>
                </ul>
            </nav>
        </header>
        
        <main>
            <article>
                Conteúdo da página
    
                <aside>
                    <h3>Glossário</h3>
                    <dl>
                        <dt>Termo 1 contido no conteúdo</dt>
                        <dd>Descrição do termo</dd>
    
                        <dt>Termo 2 contido no conteúdo</dt>
                        <dd>Descrição do termo</dd>
                    </dl>
                </aside>
            </article>
        </main>
    </body>
    ```
    
- **Como funciona o Footer?**
    
    Este elemento geralmente fica no final da página, contendo informações como, informações do autor, copyright, sitemap, contato e algum link para voltar ao topo da página.
    
    Dependendo da estrutura da página, pode-se ter o elemento `<footer>` dentro de outro elemento como o `<article>`, mas geralmente o elemento `<footer>` está posionado no final do do elemento `<body>`.
    
    ```html
    <body>
        <main>
            <article>
                <h1>Sobre nós</h1>
                <p>Formamos um time de profissionais:</p>
    
                <ol>
                    <li>Capacitados</li>
                    <li>Gentis</li>
                    <li>Honestos</li>
                </ol>
    
                <h2>Quem são:</h2>
                <ul>
                    <li>Harry Potter</li>
                    <li>Fred Gruger</li>
                    <li>Chuck</li>
                    <li>Tom Cruise</li>
                    <li>Maddona</li>
                    <li>Eduardo Mãos de Tesoura</li>
                </ul>
    
                <footer>
                    <p>© 2021 Cabelereira Leila</p>
                </footer>
            </article>
        </main>
    </body>
    ```
    
- **Como funciona o Section?**
    
    Este elemento é utilizado para definir seções, ou seja, partes de um determinado conteúdo. Antes quem era utilizado para este fim era a tag <div>, mas semâticamente o <section> é mais indicado.
    
    Para a construção de uma seção geralmente é utilizado um título e depois o conteúdo.
    
    ```html
    <body>
        <main>
            <article>
                <h2>Receita 1</h2>
                <p>Descrição da receita</p>
    
                <section>
                    <h3>Ingredientes</h3>
                </section>
    
                <section>
                    <h3>Modo de preparo</h3>
                </section>
            </article>
    
            <article>
                <h2>Receita 2</h2>
                <p>Descrição da receita</p>
    
                <section>
                    <h3>Ingredientes</h3>
                </section>
    
                <section>
                    <h3>Modo de preparo</h3>
                </section>
            </article>
        </main>
    </body>
    ```
    
- **Quais os elementos genéricos?**
    
    O elementos genéricos, ou seja, sem significado semântico explícito, são utilizados quando não encontramos elementos semânticos para constituir a estrutura da página.
    
    Os elementos mais comuns são:
    
    - `<span>`, para aplicação em texto, e;
    - `<div>`,  para aplicação de bloco.
    
    Em ambos os casos é utilizado em conjunto os atributos `id` e `class` para entregar maior significado ao código.
    
    No caso do elemeto `<span>` pode-se observar a seguinte situação, há um texto que é necessário aplicar a uma determinado trecho maior destaque de forma específica que o `<strong>` não daria.
    
    ```html
    <p>
    	Este é meu texto e 
    	<span id="destaque">
    		neste trecho que aplicar maior destaque
    	</span>
    </p>
    ```
    
    Já no caso do element `<div>`, pode-se imaginar que temos o caso de um bloco para o carrinho de compras, mas como a `<section>` é específica semânticamente para o contexto da página e não do site (como é o caso do carrinho de compras), pode-se utilizar a tag `<div>`.
    
    ```html
    <div id="cart">
    	<h2>Carrinho de compras</h2>
    </div>
    ```