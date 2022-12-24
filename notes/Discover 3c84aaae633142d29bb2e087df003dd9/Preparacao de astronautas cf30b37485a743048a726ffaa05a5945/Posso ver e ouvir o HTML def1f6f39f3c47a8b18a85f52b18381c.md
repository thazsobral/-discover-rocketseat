# Posso ver e ouvir o HTML

> *Site: [https://app.rocketseat.com.br/node/posso-ver-e-ouvir-o-html](https://app.rocketseat.com.br/node/posso-ver-e-ouvir-o-html)*
> 

Existem muitos elementos de media no HTML incluindo áudio e vídeo e chegou o momento de vermos todas possibilidades deles.

# Audio e Video

- **Como funciona a tag Video?**
    
    Basicamente, existem alguns casos para se analisar antes de acrescentar um vídeo na página.
    
    O primeiro é quando o vídeo está local. Para este caso devemos aplicar a tag vídeo o atributo `src` (source) o que direciona a busca pelo conteúdo da tag diremente ao vídeo, e deve-se também aplicar o atributo `controls`.
    
    ```html
    <video src="./aquivo.mp4" controls></video>
    ```
    
    Caso não funcione dessa forma, pode-se adicionar a tag vídeo a tag `<source>` que também permite buscar múltiplos vídeos. No caso de buscar múltiplos vídeos carrega o vídeo seguinte, caso o vídeo atual não seja encontrado, e caso o novo atual também não carrega e próximo, e assim por diante até finalizar as opções.
    
    ```html
    <video controls>
    	<source src="./aquivo.mp4" type="video/mp4">
    	<source src="./aquivo2.mp4" type="video/mp4">
    </video>
    ```
    
    Alguns atributos básicos da tag vídeo são:
    
    - `width`, utilizado para definir a largura do vídeo;
    - `height`, utilizado para definir a altura do vídeo;
    - `autoplay`, utilizado para definir que, assim qeue a página for carregada o vídeo iniciará automaticamente ;
    - `preload`, utilizado para definir algum tipo de carregamento do vídeo. Os tipos de carregamento básicos são o `auto` (para carregar o vídeo mesmo antes de clicar em play), o `metadata` (para carregar informações básicas sobre o vídeo como o tempo do vídeo) e o `none` (para não carregar nada);
    - `loop`, utilizado para definir que quando finalizado o vídeo e iniciará novamente;
    - `muted`, utilizado para definir que o vídeo deve começar mutado, e;
    - `poster`, para definir uma imagem de fundo antes de clicado para iniciar o vídeo.
    
    O segundo caso é quando aplicamos vídeos de terceiros na página, ou seja, vídeos que não estão no mesmo computador que a página, como é o caso de vídeos do youtube.
    
    Geralmente para este casos os servidores desses vídeos disponibilizam o recurso de embed para compartilhamente desses vídeos .
    
- **Como funciona a tag Audio?**
    
    Essa tag funciona basicamente como a tag `<video>`, mas sem os atributos `width`, `height` e `poster`.
    
    E também pode-se utilizar serviço de terceiros, como o recurso disponível pelo soundcloud.
    
    ```html
    <audio controls>
    	<source src="./aquivo.mp3" type="audio/mp3">
    	<source src="./aquivo2.mp3" type="audio/mp3">
    </audio>
    ```
    
- **Como funciona a tag Iframe?**
    
    Essa é uma tag muito aplicada para utilizar recursos de mídias de terceiros. A tag <iframe> pode ser utilizada também para utilizar outros conteúdos externos como um outro site por exemplo.
    
    ```html
    <iframe src="https://mangalivre.net/" frameborder="0"></iframe>
    ```
    
    ```html
    <iframe
    	width="560"
    	height="315"
    	src="https://www.youtube.com/embed/CVClHLwv-4I"
    	title="YouTube video player"
    	frameborder="0"
    	allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
    	allowfullscreen>
    </iframe>
    ```
    
    ```html
    <iframe
    	src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3699.6974560308267!2d-47.413087685542074!3d-21.984571711138887!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x94c800e1ec7848a9%3A0x22700c6c987e70dd!2sR.%20Manoel%20Leme%20Franco%2C%201145-1043%20-%20Vila%20Santa%20Terezinha%2C%20Pirassununga%20-%20SP%2C%2013636-085!5e0!3m2!1spt-BR!2sbr!4v1619987717361!5m2!1spt-BR!2sbr"
    	width="600"
    	height="450"
    	style="border:0;"
    	allowfullscreen
    	loading="lazy">
    </iframe>
    ```
    
    <aside>
    ⚠️ Para mais informações sobre está tag consulte o [guia no MDN](https://developer.mozilla.org/pt-BR/docs/Web/HTML/Element/iframe).
    
    </aside>
    

# Images

- **Como funciona a tag Image?**
    
    Está é uma das primeiras tags a surgir dentro do mundo web.
    
    Nos primórdios da web só havia texto nos sites, até que um dia a tag image chegou e deu cor aos sites.
    
    ```html
    <img
      src="https://source.unsplash.com/random"
      alt="unsplash"
      title="Imagem de unsplash"
      height="600">
    ```
    
    Os atributos básicos da tag `<image>` são:
    
    - `src`, que específica o caminho da imagem;
    - `alt`, que permite definir um texto alternativo caso a imagem não possa ser carregada;
    - `title`, que permite definir um título na image. Este título será exibido quando o ponteiro do mouse ficar sobre a imagem;
    - `width`, para definir uma largura a imagem, e;
    - `heigth`, para definir uma altura a imagem.
    
    Caso queira colocar um link na imagem, basta envolver a tag `<image>` com a tag `<a>`.
    
    ```html
    <a href="https://source.unsplash.com">
    	<img
    	  src="https://source.unsplash.com/random"
    	  alt="unsplash"
    	  title="Imagem de unsplash"
    	  height="600">
    </a>
    ```
    
    Outro exemplo para observar é
    
    ```html
    <body>
        <a href="https://rocketseat.com.br/">
            <img src="https://rocketseat.com.br/icons/icon-48x48.png"
                alt="icone rocketseat"
                title="icone rocketseat"
                height="50px">
        </a>
    </body>
    ```
    
- **Como adicionar uma imagem de background?**
    
    Um meio de adicionar uma imagem de fundo é através do CSS com a propriedade style.
    
    ```html
    <body
        style="background-image: url(https://source.unsplash.com/random);">
    </body>
    ```
    
    Esse método não dá significado semântico ao elemento, ou seja, é somente para apresentação e estilização.
    
- **Como criar títulos visíveis para imagens de forma semântica?**
    
    Podemos fazer isto utilizando duas tags:
    
    - `<figure>`, que permite envolver a imagem em um elemento de bloco, e;
    - `<figcaption>`, que permite definir um título para a imagem.
    
    ```html
    <body>
        <a href="https://source.unsplash.com/">
            <figure></figure>
                <img src="https://source.unsplash.com/random" alt="imagem unsplash" height="600">
                <figcaption>Imagem unsplash</figcaption>
            </figure>
        </a>
    </body>
    ```
    
- **Como funciona a tag SVG?**
    
    É uma tag de marcação HTML destinada a fazer imagens e possui elementos para gerar formas.
    
    ```html
    <svg width="100" heigth="100">
        <circle
    			cx="50"
    			cy="50"
    			r="40"
    			stroke="green"
    			stroke-width="4"
    			fill="yellow" />
    </svg>
    ```
    
    Dado o grau de complexidade de trabalhar com a construção de SVG, pode-se utilizar softwares específicos para criação desses elementos, um exemplo famoso é o [Figma](https://www.figma.com/), que é um prototipador de interfaces e permite criar SVG e depois exportar seu código.
    
    Basicamente, a tag `<svg>` é utilizada para gerar canvas para a imagem vetorizada, e envolvida por está tag pode-se utilizar outros elementos para gerar as suas formas como:
    
    - `<circle>`, para gerar circulos;
    - `<rect>`, para gerar retângulos;
    - `<polygon>`, para gerar polígonos;
    - entre muitos outros.
    
    As propriedades básicas para utilizar na tag `<svg>` são `width` e `heigth`, para definir largura e altura respectivamente. Já as propriedades básicas das formas vai depender de cada forma.
    
    Na prática, quando for aplicar um SVG no site através da tag `<img>`, é necessário fazer algumas configurações antes como adicionar a versão, o baseProfile e o protocolo xmlns a ser utilizado, como demonstrado abaixo.
    
    ```html
    <svg
      version="1.1"
      baseProfile="full"
      width="100"
      heigth="100"
      xmlns="http://www.w3.org/2000/svg">
        <circle cx="50" cy="50" r="40" stroke="green" stroke-width="4" fill="yellow">
    </svg>
    ```
    
    Dessa forma, pode-se ter uma imagem em arquivo .svg e aplicado a um tag `<img>` no site. Mas desse jeito, não é mais possível manipular a imagem, como era possível antes.
    
    <aside>
    ⚠️ Para mais informações sobre como utilizar este elemento acesse o [documento do MDN](https://developer.mozilla.org/pt-BR/docs/Web/SVG/Element).
    
    </aside>
    
- **Qual a diferença entre imagem rasterizadas e imagem vetorizada?**
    
    Há algumas diferenças entre estes dois tipos de imagens:
    
    - **Imagem rasterizada**: geralmente é uma imagem que está pixelada, ou seja, é uma imagem construída via pixels. Dessa forma, quando ampliadas (escaladas) essas imagens, elas perdem a nitidez. Alguns exemplos são as extensões .png, .jpeg, .jpg, etc.
    - **Imagem vetorizada**: está imagem por sua vez, é construída via algoritmo. Então imagens podem ser redimensionadas em qualquer tamanho que sua nitidez não é perdida.
    
    Dessa forma pode ser destacadas algumas vantagens e desvantagens de se utilizar imagens vetorizadas.
    
    **Vantagens**
    
    - é mais **leve** (pois é feita em texto);
    - é mais **detalhada**;
    - possui maior **acessibilidade** de SEO, e;
    - pode ser **editada via CSS ou atributos**, ou seja, pode ser editada em tempo real.
    
    **Desvantagens**
    
    - pode ser mais **complicada** de trabalhar;
    - quanto mais complexa a imagem, mais **exige do browser**, e;
    - **browsers antigos não possuem suporte** a tag <svg>.
    
    <aside>
    ⚠️ Para utilização de **fotografias**, prefira utilizar **imagens rasterizadas**.
    
    </aside>