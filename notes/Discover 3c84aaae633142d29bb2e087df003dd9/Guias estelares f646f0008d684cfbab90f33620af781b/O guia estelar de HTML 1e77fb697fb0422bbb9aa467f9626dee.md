# O guia estelar de HTML

> *Site: [https://app.rocketseat.com.br/node/o-guia-estelar-de-html](https://app.rocketseat.com.br/node/o-guia-estelar-de-html)*
> 

Todo o conceito do HTML e suas principais tags são apresentadas aqui.

### Conceito

- **O que é HTML?**
    
    HTML (Hypertext Markup Language) é uma linguagem (por causa do seu modo de escrita) de marcação.
    
- **O que é um comentário?**
    
    É um código ou escrita que têm como única finalidade comentar algo dentro do documento, sendo esse código exclusivo para que têm acesso ao arquivo fonte, ou seja, onde foi escrito. Esse código/escrita não é mostrada para o usuário final e é especificado por `<!---` e `--->`.
    
    ```html
    <!-- 
    	Isso é um comentário
    -->
    ```
    
- **Como funcionam as tags?**
    
    As tags são marcações que podem ser representadas de forma gráfica. As tags geralemnte possuem algumas características:
    
    - A **estrutura**, onde elas podem ser divididas em duas estruturas denominadas elementos:
        - **Elemento**: é a estrutura que possui uma tag de abertura e tag de fechamento como
            
            ```html
            <br> conteúdo </br>
            ```
            
        - **Elemento Vázio**: é a estrutura que só possui uma tag única como
            
            ```html
            <img src="" alt="">
            ```
            
    - O **conteúdo**, é onde é inserido os dados que queremos influênciar com a marcação, podendo ele ser, um texto e até outras tags.
    
    > *Podemos dizer também que a combinação de estrutura e conteúdo (como é o caso do elemento com tag de abertura e fechamento) formam um elemento*.
    > 
- **Como funcionam os elementos?**
    
    Os elementos possuem atributos, que por sua vez manipulam características específicas desses elementos. Esses atributos podem ser vistos como configurações ou informações extras dos elementos. Essa configuração segue a seguinte estrutura:
    
    ```html
    <img src="conteudo" alt="">
    // src= (nome do atríbuto seguido do sinal de igual)
    // "conteudo" (valor atribuido)
    ```
    
    Outro ponto interessante é que também podemos utilizar atributos booleanos, ou seja, atributo que só recebe os valores verdadeiro ou falso, como é o caso abaixo.
    
    ```html
    <input type="text" disable>
    ```
    
- **O que são atributos globais?**
    
    São aqueles atributos que podem ser aplicados a todas as tags, como `class` e `id` que são atributos para identificação de elementos, e temos também o `contentediable` que permite alterar o conteúdo de elementos com tags de abertura e fechamento, como é o caso do elemento `<p>conteúdo</p>` que possui texto como conteúdo.
    
    Um atributo global interessante é o `tabindex` que permite configurar a ordem de navegação entre os elementos, como pode ser visto no uso da tecla *Tab* na hora de navegar em um site.
    
    Outros atributos globais podem ser observados no [MDN Web Docs](https://developer.mozilla.org/pt-BR/docs/Web/HTML/Global_attributes).
    
- **O que é aninhamento de tags?**
    
    É quando colocamos uma tag dentro da outra, como
    
    ```html
    <div>
    	<p>
    		Este é um <b>texto de demonstração</b>
    	</p>
    	<p>
    		Este é um outro <b>texto de demonstração</b>
    	</p>
    </div>
    ```
    
    Todo aninhamento segue um hierarquia, o que pode fazer com que a configuração feita na tag mais "acima" influência as mais "abaixo" (ou seja, as aninhadas).
    
    O fluxo das tags aninhadas garante que elas sejam apresentadas no navegar na mesma ordem que são escritas no código, onde no código acima a primeira tag `<p>` aparece antes da segunda sempre que a linguagem é renderizada.
    
    Outro ponto interessante é que algumas tags definem seus posicionamentos, ou seja, a tag `<p>` padrão garante um novo espaço em bloco diferente da tag `<a>` que mantém o posionamento.
    
- **O que são caracteres reservados?**
    
    São caracteres que pertecem a sintaxe da linguagem como `<`.
    
    Caso seja necessário adicionar algum caractere reservado como conteúdo é preciso adicionar o cactere especial equivalente, que no caso do `<` é o `&lt;`.
    
    Outros exemplos de caracateres espeiciais são:
    
    - `&gt;` que é igual a `>`
    - `&amp;` que é igual a `&`
    - `&quot;` que é igual a `"`
    - `&apos;` que é igual a `'`
- **Qual a "anatomia" do HTML?**
    
    A anatomia é a estrutura de uma página html, onde temos tags básicas e necessárias. As tags pertencentes a anatomia são:
    
    - `<!DOCTYPE html>` identifica que o documento está escrito em HTML5
    - `<html></html>` é o elemento "pai" ou *root*, ou seja, um dos principais elementos, sendo que ele contém os elementos `<head>` e `<body>`. Esse elemento pode conter parâmentros como, `lang` que permite definir uma linguagem para o documento, como o exemplo abaixo
        
        ```html
        <html lang="en">
        ...
        </html>
        ```
        
        que define a linguagem do conteúdo em inglês.
        
    - `<head></head>` é o elemento que contém informações importantes para a página, mas que não são apresentadas no corpo da página para o usuário. Essas informações são definidas pela tag <meta> que basicamente define meta dados para o documento como o exemplo abaixo. Dentro dessa tag podemos incluir o pacote de leitura de caracteres como demostrado a baixo
        
        ```html
        <meta charset="utf-8">
        ```
        
        que por sua vez é um dos pacotes de caracteres mais amplos que temos, ou definir compatibilidade com outros dispositos.
        
        ```html
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        ```
        
        Esse elemento pode definir muitas outras meta informações como *links* de documentos e pacotes, e até mesmo o título da página.
        
    - `<body></body>` é o elemento que contém as informações que sera apresentadas no corpo da página para o usuário. Essa informações estão contidas nas tags `<p>` por exemplo.
- **Como criar um projeto HTML?**
    - acesse o pasta que deseja armazenar o documento .html;
    - crie um arquivo .html;
    - abra o documento em um editor de texto e comece a escrever seu código.

### Trabalhando com elementos

- **O que é a semântica no HTML?**
    
    HTML por si só têm como objetivo apresentar um conteúdo da melhor forma possível, utilizando da estrutura do documento e elementos, esse conjunto gera um significado semântico para sua página. Alguns dos benefícios de se ter um HTML com uma boa semântica é a boa recomendação que da página nas ferramentas de busca, compatibilidade com um maior número de extensões e ferramentas (como é o caso do leitor de acessibilidade), entre muitas coisas.
    
    Para se construir uma boa semântica no seu HTML é viável se guiar através de peguntas como
    
    - Qual são os melhores elementos para apresentar a minha ideia?
    - Vou utilizar qual layout para isso?
    - Meu conteúdo é dinâmico ou estático?
    
    etc.
    
    > *Fazer perguntas para si mesmo te ajuda a responde-lâs.*
    > 
- **O que são títulos e parágrafos?**
    
    Título (e subtítulos) é uma marcação indicando o objetivo do parágrafo, sendo que na maioria das vezes é utilizado apenas um título por página, e caso necessário abordar outros objetivos ou temas utilizamos os subtítulos.
    
    - `<h1></h1>` tag de título principal da página
    - `<h2></h2>` tag de subtítulo
    - `<h3></h3>` tag de subtítulo do subtítulo `<h2>` (os próximo Hs seguem a mesma lógica)
    - `<p></p>` tag de parágrafo
    
    > *É indicado ter no máximo 3 Hs por página. Se houver mmais Hs talvez seja necessário adicionar outra página (ref. psicológica).*
    > 
- **O que são listas no HTML?**
    
    São itens contidos na tag `<li></li>`, onde esses itens podem ser ordenados (`<ol></ol>`) ou não ordendos (`<ul></ul>`), como a representação da aplicação da lista abaixo
    
    ```html
    <ol>
    	<li>primeiro item</li>
    	<li>segundo item</li>
    	<li>terceiro item</li>
    </ol>
    ```
    
    É importante envolver a tag `<li>` com uma das tags de ordenação (`<ol>` ou `<ul>`) para manter o valor semântica do seu documento.
    
- **O que são citações no HTML?**
    
    É um elemento de referência para informações de outros autores. As tags utilizadas para citação são:
    
    - `<blockquote></blockquote>` para destacar uma "fala" de um autor, onde pode ser incluida o link da referência através do atributo *cite*. Um exemplo de implentação desta tag é
        
        ```html
        <blockquote 
        	cite="https://developer.mozilla.org/en-US/docs/web/HTML/Element/blockquote">
        	<p>O 
        		<strong>Elemento blockquote no HTML
        			<code>&lt;blockquote&gt;</code>
        			ou
        			<em>HTML Block Quotation Element</em>
        		</strong> onde é indicado que um texto externo foi citado.
        	</p>
        </blockquote>
        ```
        
    - `<cite></cite>` estiliza o trecho envolvido pela tag de forma a identificar um citação simples. Para exemplificar sua aplicação dessa tag
        
        ```html
        <p>Ded acordo com 
        	<a href="https://developer.mozilla.org/en-US/docs/web/HTML/Element/blockquote">
        		<cite>página MSN blockquote</cite>
        	</a>
        </p>
        ```
        
    - `<q></q>` também possui um atributo *cite* para referênciar a font, além de acrescentar aspas no trecho envolvido. como exemplificado abaixo
        
        ```html
        <p>O elemento quote utilizando o <code>&lt;q&gt;</code> é
        	<q cite="https://developer.mozilla.org/en-US/docs/web/HTML/Element/p">
        		usado para citações curtas que não precisam de parágrafos ou quebras de linha.ga
        	</q>
        </p>
        ```
        
- **Como é utilizado abreviações no HTML?**
    
    É utilizado a tag `<abbr>` para indicar que determinada palavra é uma abreviação, onde seu significado é adicionado ao atributo *title*, como exemplificado abaixo
    
    ```html
    <p>Usamos
    	<abbr title="Hypertext Markup Language">HTML</abbr>
    	para estruturar nossos documentos da web.
    </p>
    ```
    
- **Como é aplicado detalhes de contato no HTML?**
    
    Através da tag `<address>` é possível especificar os detalhes de contato do autor da página, como demonstrado abaixo
    
    ```html
    <address>
    	<p>Fulano de Tal<br>
    		<strong>Algum lugr desse mundão, MD</strong>
    	</p>
    </address>
    ```
    
- **O que são listas de descrição?**
    
    É um exemplo de agrupamento de dados em formato de lista, onde podemos atribuir descrições a um conjunto de itens. Para aplicar a lista de descrição utilizamos a tag `<dl>` que envolve as tags de termo de descrição `<dt>` e a própria descrição `<dd>`. Podemos observar a aplicação dessa lista no exemplo abaixo
    
    ```html
    <h2>Glossário</h2>
    <dl>
    	<dt>Hypertext</dt>
    	<dd>É um hiper texto ...</dd>
    
    	<dt>Markup</dt>
    	<dd>É a marcação de texto ...</dd>
    
    	<dt>Language</dt>
    	<dd>É a linguagem com semântica, sintaxe, e ...</dd>
    </dl>
    ```
    
- **Como representar códigos no HTML?**
    
    Para realizar a representaçãod de códigos utilizamos basicamente duas tags, a tag `<code>` é utilizada para partes genéricas e simples de código.
    
    ```html
    <p> O seguinte código é um exemplo de código dentro do texto
    	<code>
    		document
    			.querySelector("body")
    	</code>
    </p>
    ```
    
    Já a tag `<pre>` é utilizada para criar blocos de código matendo os recuos e espaços em branco que aplicarmos ao código em questão.
    
    ```html
    <p> O seguinte código é um exemplo de código que pode quebrar o texto
    	<pre>
    		<code>
    			document
    				.querySelector("body")
    		</code>
    	</pre>
    	, pois sua implementação cria um bloco de código
    </p>
    ```
    
- **O que são elementos genéricos?**
    
    Elementos genéricos dão um significado mais amplo para outras tags.
    
    - A tag `<div>` é uma tag genérica que permite o agrupamento de elementos no conceito de agrupamento em bloco, ou seja, é criado um bloco em torno dos elementos envolvidos.
        
        ```html
        <div>
        	<h2>Elemento de agrupamento</h2>
        	<p>Sendo que todas cofigurações aplicadas a tag &lt;div&gt;
        		se aplica a todos os elementos que a tag envolve.
        	</p>
        </div>
        ```
        
    - A tag `<span>` é utilizada para agrupar textos no conceito de agrupamento em linha, ou seja, não é criado um bloco em torno dos textos envolvidos, sendo essa tag ideal para formatação de textos com CSS.
        
        ```html
        <p>Um novo texto <span>agrupado pela tag &lt;p&gt;</span></p>
        ```
        

### Links

- **O que é uma tag âncora e como ela funciona?**
    
    Também conhecido como link, é representado pela tag `<a>` que têm como função ligar um conteúdo a outro.
    
    Essa tag possui um atributo *href* que referência o conteúdo que está em outra página, sendo que essa referência é aplicada ao elemento que a tag envolve, como exemplificado abaixo
    
    ```jsx
    <a href="https://google.com">Acesse o Google</a>
    ```
    
    Os valores que podem ser atribuídos ao *href* são
    
    - **url completa** como `"https://google.com"` que direciona para um site
    - **fragmento** como `"#fragmento"` que direciona para outra parte dentro da prórpria página como exemplificado abaixo
        
        ```html
        <h1>Saiba mais</h1>
        <ul>
        	<li><a href="#about">Sobre mim</a></li>
        	<li><a href="#history">História</a></li>
        	<li><a href="#works">Trabalhos</a></li>
        </ul>
        
        <h2 id="about">Sobre mim</h2>
        <p>............</p>
        
        <h2 id="history">História</h2>
        <p>............</p>
        
        <h2 id="works">Trabalhos</h2>
        <p>............</p>
        ```
        
    - **e-mail** como `"mailto:fulano@gmail.com"` que direciona para o gerenciador de e-mail contido no sistema operacional e também prepara o envio de um e-mail para o endereço referênciado
    - telefone como `"tel:+551999988776655"` que direciona para uma chamada para o número referênciado
    - **outros**.
    
    Outros atributos são
    
    - O atributo *download* que faz o download da referência (seja ela página ou conteúdo) ao invés de ir para a página.
    - E o atributo *target* que define como vai ser feito a abertura do link, sendo os valores `"self"` (que é o padrão, onde a referência é aberto na mesma página que contém o link) e `"_blank"` (que abre o link em uma nova página).
    - Além de **atributos globais** que também podem ser utilizados, como *class*, *id* e *title*.
    
    É importante citar também que o conteúdo do tag `<a>` pode qualquer coisa envolvida na tag, até mesmo imagens como demostrado abaixo
    
    ```html
    <a href="https://unsplash.com/collections">
    	<img src="https://source.unsplash.com/random">
    </a>
    ```
    
- **Qual a diferença de URLs e caminho de arquivos?**
    
    URL (Uniform Resource Locator) é uma sequência de texto que defino onde algo está localizado na web, como *https://pt.wikipedia.org/wiki/Programa_Olá_Mundo* e caminho de um arquivo é a localização de um arquivo existente dentro do seu projeto. Essa segunda referência pode ser feita através utilizando o caminho de pastas e finalizando com o nome do arquivo, como *arquivos/imagens/logo.png.*
    
- **Como navegar nos caminhos de arquivos?**
    
    Podemos referênciar arquivos de várias forma como explicado abaixo
    
    - **dentro do mesmo diretório** utilizando somente o nome do arquivo, como *logo.png* ou se quiser podemos utilizar o carácter ".", por exemplo *./logo.png*
    - **entrando em diretórios** citando o caminho a ser seguido para encontrar o arquivo, como *imagens/logo.png*
    - **saindo de diretórios** indicando a saída diretório com "..", por exemplo *../arquivos/imagens/logo.png*
    - **através do diretório raíz** citando todo o caminho desde a raíz do diretório até o arquivo desejado, como *projeto/arquivos/imagens/logo.png*
- **Qual a diferença entre URLs absolutas e URLs relativas?**
    
    URLs absolutas são aquelas que inclui protocolo e nome de domínio, sempre apontando para o mesmo local na web. Por exemplo *https://google.com*
    
    URLs relativas são aquelas relativas a página que contém o link e pode pontar para lugares diferentes dependendo da página que está o link. Por exemplo *google.com*
    

### Tabelas

- **O que são e como funciona as tabelas no HTML?**
    
    Tabelas são estruturas que servem para organizar conteúdos em linhas e colunas. As tags utilizadas para montar a estrutura de uma tabela são
    
    - `<table></table>` para definir uma tabela, sendo que essa tag envolve as colunas e linhas
    - `<tr></tr>` para definir uma linha
    - `<th></th>` para definir um cabeçalho da coluna, sendo importante utilizar essa tag apenas para definir cabeçalhos (na primeira linha) ou melhor, dentro da tag `<thead>`
    - `<td></td>` para definir uma célula da linha, sendo melhor aplicar essa tag dentro da tag `<tbody>`
    - `<thead></thead>` para denifir a linha de cabeçalho das colunas da tabela, ou seja, onde fica a tag `<tr>` envolvendo as tags `<th>`
    - `<tbody></tbody>` para definir a área de linhas para o corpo da tabela, ou seja, onde fica as tags `<tr>` envolvendo as tags `<td>`
    
    Para melhor visualizar a implementação dessas tags observe o exemplo a seguir
    
    ```html
    <table>
    	<thead>
    		<tr>
    			<th>Nome</th>
    			<th>Idade</th>
    			<th>Salário</th>
    		</tr>
    	</thead>
    	<tbody>
    		<tr>
    			<td>João</td>
    			<td>21</td>
    			<td>2000.00</td>
    		</tr>
    		<tr>
    			<td>Adriana</td>
    			<td>25</td>
    			<td>3500.00</td>
    		</tr>
    	</tbody>
    </table>
    ```
    
    Outra tag interessante de se utilizar na implementação de uma tabela é a `<caption>`, que descreve a função da tabela, como demonstrado a seguir.
    
    ```html
    <table>
    	<caption>A função dessa tabela é ..</caption>
    	....
    </table>
    ```
    
    As tabelas são boas para visualização de dados via linhas e colunas e oferece uma boa acessibilidade para leitura de dados, mas são pouco flexíveis e precisam de estilização para melhorar sua representação. Outro erro muito comum é a utilização de tabelas para definir layout da página, então **NÃO** utilize tabelas para criar layouts.
    
- **O que são tabelas complexas?**
    
    São tabelas com layout complexo, onde podemos ter por exemplo uma linha contida na estrutura dividida em duas ou mais linhas, causando assim um efeito de mesclagem de células, como demonstrado a seguir.
    
    ![O%20guia%20estelar%20de%20HTML%201e77fb697fb0422bbb9aa467f9626dee/Untitled.png](O%20guia%20estelar%20de%20HTML%201e77fb697fb0422bbb9aa467f9626dee/Untitled.png)
    
    Também podemos ter outras formações.
    
    Para estruturar essas configurações é comumente utilizado os atributos *rowspan* (onde é passado o valor de linhas que a célula ocupará), *colspan* (onde é passado o valor de colunas que a célula ocupará) além da tag `<colgroup>`, que por sua vez têm a função de definir configurações para grupos de colunas.
    
    Outro ponto importante para melhor a semântica de uma tabela é a acessibilidade. Essa característica utiliza dos atributos *scope*, onde podemos informar qual o escopo da célula.
    
    Um exemplo de estruturação de uma tabela complexo está representada a seguir
    
    ```html
    <table>
        <caption>Produzidos x Vendidos por Loja</caption>
        <colgroup>
          <col>
          <col span="2" style="background-color: blue;">
          <col span="2" style="background-color: red;">
        </colgroup>
    
        <thead>
          <tr>
            <th rowspan="2"></th>
            <th colspan="2" scope="colgroup">Primeira Loja</th>
            <th colspan="2" scope="colgroup">Segunda Loja</th>
          </tr>
          <tr>
            <th scope="col">Produzidos</th>
            <th scope="col">Vendidos</th>
            <th scope="col">Produzidos</th>
            <th scope="col">Vendidos</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <th scope="row">Vassoura</th>
            <td>50</td>
            <td>30</td>
            <td>20</td>
            <td>20</td>
          </tr>
          <tr>
            <th scope="row">Balde</th>
            <td>10</td>
            <td>10</td>
            <td>30</td>
            <td>25</td>
          </tr>
        </tbody>
      </table>
    ```
    

### Cabeçalho

- **O que é a tag de cabeçalho?**
    
    A tag `<head>` contém as configurações da página, ou seja, as informções que não serão apresentadas no corpo da página.
    
    Podemos dar como exemplo de tags que são contidas dentro do `<head>` a tag `<meta>`, `<link>`, `<title>`, `<style>` entre outras.
    
- **O que é a tag META?**
    
    É a tag onde definimos metadados da nossa página, sendo esses configurados através de atributos como
    
    - *charset* onde definimos padrões de codificação para characteres especiais, como demonstrado abaixo
        
        ```html
        <meta charset="UTF-8">
        ```
        
    - name que específica o tipo de matadado que será utilizado e content que específica o conteúdo/valor do metadado. Esses dois atributos são comumente usados juntos, onde o name define o tipo e o content defini as configurações. O exemplo a seguir demonstra melhor isso
        
        ```html
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        ```
        
- **O que é Favicon?**
    
    É uma relação entre a página e fontes de icones, sendo esse nome Favicon uma abreviação para Favorite Icons. Essa relação pode ser feita de duas formas, uma básica como demonstrada a seguir 
    
    ```html
    <link rel="icon" href="https://http2.mlstatic.com/frontend-assets/ui-navigation/5.12.1/mercadolibre/favicon.svg">
    ```
    
    e outra mais avançada onde podemos definir outros atributos como por exemplo o tamanho do icone, como o exemplo a seguir
    
    ```html
    <link href="https://http2.mlstatic.com/frontend-assets/ui-navigation/5.12.1/mercadolibre/180x180.png" rel="apple-touch-icon" size="100x100">
    ```
    
    Esses icones podem ser .png, .svg, etc.
    
    > *Também podemos temos diversas ferramentas que podem auxíliar nesse processo de definir um ícone para nossa página, como é o caso do site [logaster](https://www.logaster.com.br/favicon/).*
    > 
- **Qual a importância das metas no SEO?**
    
    Antes precisamos citar o que é SEO (Search Engine Otimization) são técnicas ou diretrizes que servem para melhorar o posicionamento da sua página em motores de busca como o Google, ou seja, melhor recomendar sua página.
    
    As tags metas que auxiliam no SEO da sua página são
    
    - *charset* que auxília na codificação do site no navegador
        
        ```html
        <meta charset="UTF-8">
        ```
        
    - *viewport* que define portabilidade da página com dispositivos móveis
        
        ```html
        <meta name="viewport" content="width=device-width; initial-scale=1.0">
        ```
        
    - *author* que define um autor para a página
        
        ```html
        <meta name="author" content="Fulano">
        ```
        
    - *description* que defini a descrição para a página, sendo esta que irá aparecer nos motores de busca
        
        ```html
        <meta name="description" content="A descrição desta página é ...">
        ```
        
    - robots que defini instruções para os robôs de busca
        
        ```html
        <meta name="robots" content="noindex, nofollow">
        ```
        
- **O que são metas sociais?**
    
    São metadados personalizados por empresas de redes sociais (como o facebook). Por exemplo temos o [Open Graph do Facebook](https://developers.facebook.com/docs/sharing/webmasters?locale=pt_BR), que é um meta que indica a utilização de um conteúdo personalizado (como uma prévia, texto ou imagem) quando for compartilhado o link da página no site do Faccebook.
    
    O atributo que indica a utilização de um meta social é o *property*, que especifica o proprietário do recurso, como exemplificado abaixo.
    
    ```html
    <meta property="og:image" content="http://static01.nyt.com/images/2015/02/19/arts/international/19iht-btnumbers19A/19iht-btnumbers19A-facebookJumbo-v2.jpg">
    ```
    
    Outro exemplo que temos é o [Twitter](https://developer.twitter.com/en/docs/twitter-for-websites/cards/overview/summary-card-with-large-image)
    
    ```html
    <meta name="twitter:title" content="Um título para minha página">
    ```