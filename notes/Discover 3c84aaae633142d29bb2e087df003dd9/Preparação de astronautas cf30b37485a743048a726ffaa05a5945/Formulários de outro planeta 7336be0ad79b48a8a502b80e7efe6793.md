# Formulários de outro planeta

> *Site: [https://app.rocketseat.com.br/node/formularios-de-outro-planeta](https://app.rocketseat.com.br/node/formularios-de-outro-planeta)*
> 

A tag form no HTML é a maneira mais tradicional de interagir com o usuário da aplicação e é incrível o que é possível com esse elemento.

<aside>
⚠️ Como pré-requisito para está etapa é o [básico de html](../Guias%20estelares%20f646f0008d684cfbab90f33620af781b/O%20guia%20estelar%20de%20HTML%201e77fb697fb0422bbb9aa467f9626dee.md).

</aside>

# Introdução

- **O que são formulários?**
    
    Formulários na web servem para acapturar dados de entrada (input).
    
    Os formulários permitem uma melhor interação e controle do sistema.
    
    Nos formulários é possível aplicar estilização, validação, controles customizados e claro, javascript.
    

# Estrutura

- **O que é Form?**
    
    Para o formulário HTML, Form é a tag básica utilizada para a criação de um formulário. A tag `<form>` têm o conceito de container estilo `<section>` ou `<footer>`, sendo seu elementos internos os elementos de um formulário.
    
    Os atributos básicos do `<form>` são:
    
    - `action` é para onde os dados seram submetidos. Caso o valor de `action` seja **vazio**, significa que os dados serão enviados para a mesma página.
    - `method` é o método utilizado para enviar os dados do formulário, sendo os métodos mais comuns o `"GET"` e o `"POST"`.
        
        Através do método `"GET"` os dados são passados através da URL e geralmente são dados para serem aplicados apenas na mesma página ou para pesquisa.
        
        Já com o método `"POST"` os dados são passados através do body, sendo este método o mais comum para passar dados para o servidor.
        
        Caso este atributo esteja **vazio** o browser vai entender que o valor é `"GET"`.
        
- **O que é Fieldset?**
    
    É a tag utilizada para agrupamento de campos que possuem o mesmo propósito, deixando assim o HTML mais semântico e possibilitando uma maior acessibilidade.
    
    Os atributos mais comuns do `<fieldset>` são:
    
    - `disable`, que permite desabilitar todos os campos incluidos dentro da tag, além de não serem enviados para o servidor.
    - `form`, permite que seja linkado os campos internos a algum formulário da página, ou seja, não é necessário os campos estarem dentro do formulário para serem enviados. Para realizar este link basta utilizar o nome do `id` do `<form>` no atributo `form` do `<fieldset>`.
    - `name`, permite nomear/linkar os campos internos a algum grupo.
    
    O `<fieldset>` geralmente é acompanhado do `<legend>`. O `<legend>` é o nome do agrupamento explicitamente e é o primeiro elemento dentro do `<fieldset>`.
    
    ```html
    <form id="contact" action="">
        <button>Send</button>
    </form>
    
    <fieldset form="contact" name="contact-email">
        <legend>Dados de contato</legend>
        <label for="">Nome</label>
        <input type="text" value="text">
    </fieldset>
    ```
    
- **O que é Label?**
    
    É a tag que associa ou identifica uma ou mais tags de entrada de dados. A `<label>` permite maior acessibilidade e direcionamento de foco de entrada através do clique.
    
    Para a `<label>` existe alguns atributos específicos como o `for`, que faz uma conexão entre a `<label>` e a tag de entrada de dados. Essa conexão é feita utilizando o `id` da tag de entrada.
    
    ```html
    <!-- primeiro caso -->
    <label for="name">Nome
    	<input type="text">
    </label>
    <!-- ou -->
    <!-- segundo caso -->
    <label for="name">Nome</label>
    <input id="name" type="text">
    ```
    
    <aside>
    ⚠️ O atributo `for` só funciona com alguns elementos como, `<button>`, `<input>` (not hidden), `<meter>`, `<output>`, `<progress>`, `<select>` e `<textarea>`.
    
    </aside>
    
- **O que é Button?**
    
    É a representação de um botão, que pode ser utilizado para interagir com as informações de um formulário (por exemplo, enviando as informações).
    
    A estilização de um button é realizado por padrão pelo user agent (navegador). O que também pode ser mudado utilizando CSS.
    
    Os atributos comuns de um button são:
    
    - `type`, que defini o tipo do tipo de ação que o botão deve ter. Alguns exemplos de ação são, `submit` (enviar as informações do formulário), `button` (também pode ter o mesmo comportamento que o `submit`, quando aplicado dentro de um formulário) e `reset` (limpa as informações do formulário).
        
        ```html
        <form action="">
        	<input type="text" value="texto padrão">
        	<button type="reset">LIMPAR</button>
        </form>
        ```
        
    - `autofocus`, que defini o focu principal do formulário ou da página. ⚠️ Sendo que o primeiro campo ou botão que terá o foco é o primeiro elemento com o atributo `autofocus`.
    - `disabled`, serve para desabilitar a funcionalidade do elemento.
    - `name`, pode ser utilizado em conjunto com o atributo `value`, sendo que ao enviar o formulário o valor contido em `value` será representado pelo valor do atributo `name`.
        
        ```html
        <form action="">
        	<input type="text" value="texto padrão">
        	<button type="submit" name="valor" value="meu valor para ser enviado">ENVIAR</button>
        </form>
        ```
        
    - `value`, contém um valor para ser enviado jutamente com o formulário.
    - `form`, é utilizado para referenciar o formulário em que o botão têm propriedade, ou seja, se o botão têm a função de enviar, este botão terá a função de enviar as informações do formulário referenciado (mesmo que o botão não esteja localizado dentro do formulário).
        
        ```html
        <form action="" id="meu-formulario">
        	<input type="text" value="texto padrão">
        </form>
        	<button type="submit" form="meu-formulario">ENVIAR</button>
        ```
        
    
    <aside>
    ⚠️ Outra tag que pode ter o mesmo comportamento que um botão é a tag `<input>` contendo o atributo `type` com `"submit"`.
    
    </aside>
    
    ```html
    <form action="" id="meu-formulario">
    	<input type="text" value="texto padrão">
    	<input type="submit" value="ENVIAR">
    </form>
    ```
    
- **O que é Datalist?**
    
    É uma tag estrutural para os formulários. Essa tag contém uma lista de valores como sugestão para a tag `<input>`. Os valores contidos na tag `<datalist>` valores são sugestivos e não obrigatórios, ou seja, o usuário pode escolher alguns dos valores apresentados, ou pode preencher algum valor customizado.
    
    ```html
    <datalist id="fruitsdata">
    	<optional>Apple</optional>
    	<optional>Banana</optional>
    	<optional>Orange</optional>
    	<optional>Cherry</optional>
    </datalist>
    ```
    
    Os tipos de input suportado pela tag <datalist> são:
    
    - text;
    - search;
    - url;
    - tel;
    - email;
    - date;
    - month;
    - week;
    - time;
    - datetime-local;
    - number;
    - range, e;
    - color
    
    <aside>
    ⚠️ É importante citar que se os valores contidos na tag `<datalist>` eles não serão apresentados.
    
    </aside>
    
    ```html
    <input type="text" list="fritsdata" placeholder="Escolha uma fruta">
    
    <datalist id="fruitsdata">
    	<optional>Apple</optional>
    	<optional>Banana</optional>
    	<optional>Orange</optional>
    	<optional>Cherry</optional>
    </datalist>
    ```
    
    Os input não suportados pela tag `<datalist>` são:
    
    - hidden
    - password
    - checkbox
    - radio
    - file
    - ou outros tipos de buttons.
    
    <aside>
    ⚠️ Antes de utilizar está tag `<datalist>`, é importante verificar a compatibilidade com o user agent (browser).
    
    </aside>
    

# Tags de entrada de dados

- **O que é Input?**
    
    A tag `<input>` é uma das mais utilizadas, aceitando um elevado número de tipos de entrada.
    
    Os atríbutos básicos para está tag são:
    
    - `type`, para definir o tipo de entrada;
    - `name`, para definir um nome de referência para a tag, e;
    - `id`, para definir um identificador único para a tag.
    
    Para título de conhecimento pode-se citar alguns tipos:
    
    - `text`, para entradas de texto;
    - `date`, para entradas de datas;
    - `number`, para entradas de valores numéricos;
    - `email`, para entradas de e-mail. Neste caso pode ser preenchido qualquer tipo de texto, sendo sua particularidade a verificação de um e-mail no momento da submição do valor.
    - `file`, para entradas de documentos;
    - `password`, para entradas de senhas. Neste caso é aceito todo tipo de texto, mas por padrão seu valor não é exíbido.
- **Quais são os atributos comuns da tag Input?**
    
    Há alguns atributos para comuns à tag `<input>` além do `type`. São eles:
    
    - `autocomplet`, para acionar a sugestão de autocompletar o preenchimento do input. Para configurar as sugestões aplica-se o tipo de sugestão explicítmente. Dessa forma os valores de sugestão são buscados dentro do histórico de preenchimento do browser.
    Outro ponto legal deste atributo é, quando aplicado no tipo `password` por exemplo, podemos aplicar o valor `"new-password"`, o que resulta numa sugestão de nova senha.
        
        ```html
        <input type="email" autocomplet="email">
        ```
        
    - `autofocus`, como citado anteriormente, possui a função de definir um focu automático assim que a página for iniciada. Como é um atributo do tipo boolean, basta declarar o atributo. É válido relembrar que é aconselhável utilizar apenas um por página, mas caso haja mais de um, o primeiro `autofocus` detectado na página será considerado.
        
        ```html
        <input type="text" autofocus>
        ```
        
    - `disabled`, serve para desabilitar o input. Como também é um atributo do tipo boolean, basta aplicá-lo na tag.
        
        ```html
        <input text="text" disabled>
        ```
        
    - `value`, serve para definir um valor de preenchimento para a tag `<input>`.
    - `readonly`, serve para desabilitar somente a função de edição da tag `<input>`. ⚠️ Sendo este atributo válido em apenas alguns tipo de input.
    - `form`, para linkar a tag `<input>` com um determinado formulário. É importante destacar que para referênciar o valor da tag `<input>` referenciada, deve-se utilizar o atributo name. É através do atributo `name` que pode-se recuperar o valor do input depois. ⚠️ Sendo este atributo válido em apenas alguns tipo de input.
    - `required`, serve para indicar que o input é obrigatório, ou seja, caso ele não seja preenchido e seja tentado submetrer seu valor. ⚠️ Sendo este atributo válido em apenas alguns tipo de input.
    - `minlength`, defini um número mínimo de caraccteres.
    - `maxlength`, defini um número máximo de caraccteres.
    - `placeholder`, serve para . ⚠️ Sendo este atributo válido em apenas alguns tipo de input como, password, search, text, tel e url. ⚠️ Outro ponto importante é, o `placeholder` não substirui a tag `<label>`.
    - `pattern`, serve para validação do campo através de expressões regulares.
    - `inputmode`, serve para indicar que o tipo de entrada. Este atributo é muito útil quando utilizada em dispositivos mobile.
    - `title`, para mostrar uma mensagem de informação para o input.
    - `spellcheck`, serve para habilitar o corretor ortográfico.
    
    <aside>
    ⚠️ Para mais informações sobre input, acesse a parte da [documentação](https://developer.mozilla.org/pt-BR/docs/Web/HTML/Element/input) que fala sobre input.
    
    </aside>
    
- **Como funciona o Input do tipo Password?**
    
    Essa tag indica uma senha, que por padrão já vêm mascárada para esconder o que está sendo digitado. A apresentação desse tipo de input dependende diretamente do user agent (browser).
    
    ```html
    <input type="password" autocomplete="new-password">
    ```
    
- **Como funciona o Input do tipo Email?**
    
    É um tipo de entrada especifico para validação de e-mails, ou seja, quando submetido o campo, é válidado seu valor, e verificado se o valor é compátivel com o formato de e-mail.
    
    Um atributo interessante de utilizar nesta tag `<input>` é o multiple, que permite o preenchimento de mais de um e-mail, sendo eles separados por vírgulas.
    
    ```html
    <input type="email" pattern=".+@rocketseat\.com\.br">
    ```
    
- **Como funciona o Input do tipo Url?**
    
    É utilizado para receber uma url. A particularidade deste tipo é a verificação do valor, se é ou não uma url.
    
    ```html
    <input type="url" placeholder="http://example.com" pattern=".*\.com\.br\/.*">
    ```
    
- **Como funciona o Input do tipo File?**
    
    É utilizado para enviar arquivos. Seu atributos comuns podem ser o `value` (para definir o arquivo a ser enviado), `accept` (para descrever que tipo de arquivos são aceitos) e `multiple` (para submeter multiplos arquivos).
    
    ```html
    <form action="" method="post" enctype="multipart/form-data">
    	<input type="file" accept="images/*">
    </form>
    ```
    
    ```html
    <form action="" method="post" enctype="multipart/form-data">
    	<input type="file" accept=".docx" multiple>
    </form>
    ```
    
- **Como funciona o Input do tipo Color?**
    
    Com este tipo de input é gerado uma de seleção color pick. É interessante adicionar o atributo `value`, pois é através dele que será enviado o valor da cor.
    
- **Como funciona o Input do tipo Checkbox?**
    
    São caixas que podem ser selecionadas, sendo muito utilizado para enviar os valores marcados. Para este tipo de input pode ser utilizado o atributo `checked`, para deixar selecionado o checkbox por padrão. També é possível utilizar multiplos valores da seguinte forma.
    
    ```html
    <fieldset>
    	<legend>Choose your interests</legend>
    	<div>
    		<input type="checkbox" id="coding" name="interest" value="coding" checked>
    		<label>Coding</label>
    	</div>
    	<div>
    		<input type="checkbox" id="music" name="interest" value="music" checked>
    		<label>Music</label>
    	</div>
    </fieldset>
    ```
    
- **Como funciona o Input do tipo Hidden?**
    
    É um input que fica escondido, inclusive para leitores de tela. Seu valor é enviado jutamente com o formulário.
    
    ```html
    <input type="hidden" name="id" value="623">
    ```
    
- **Como funciona o Input do tipo Radio?**
    
    É um input que têm como função selecionar uma única opção dentro de um grupo. 
    
    ```html
    <fieldset>
    	<legend>Bora tomar um chá?</legend>
    	<label for="yep">sim</label>
    	<input type="radio" id="yep" name="coffe" value="yep">
    
    	<label for="nono">não</label>
    	<input type="radio" id="nono" name="coffe" value="nono">
    </fieldset>
    ```
    
- **O que é Textarea?**
    
    É um elemento que permite o preenchimento de textos dentro de um formulário, etc. Este eemento é aplicado à multilinhas, sendo ele muito útil para textos grandes.Quando criado o elemento, todo conteúdo inserido entre as tags é preenchido dentro dele.
    
    ```html
    <textarea>
    Este conteúdo está dentro do textarea.
    <textarea>
    ```
    
- **O que é Select?**
    
    É um elemento de seleção que fornece um menu de opções. Este elemento trabalha diretamente com a tag `<option>` contendo o atributo `value`. Caso seja necessário, pode-se utilizar o atributo `multiple` neste elemento.
    
    ```html
    <label for="carselect">Qual o modelo do carro?</label>
    <select name="carmodel" id=" carselect">
    	<option value="">Selecione um modelo</option>
    	<option value="fiat">Uno</option>
    	<option value="audi">A3</option>
    </select>
    ```
    
- **O que é Optgroup?**
    
    É um elemento utilizado para agrupar opções de seleções. Este elemento é otimo paa criar categorias de opções. O atributo label desta tag é utilizada para definir a categoria que será exibida ao usuário no momento da seleção dos opções.
    
    ```html
    <label>Please choose one or more pets:
    	<select name="pets" multiple size="8">
    		<optgroup label="4-legged pets">
    			<option value="dog">Cachorro</option>
    			<option value="cat">Gato</option>
    			<option value="hamster">Hamster</option>
    		<optgroup label="Flying pets">
    			<option value="parrot">Papagaio</option>
    			<option value="macaw">Arara</option>
    			<option value="albatross">Albatroz</option>
    		<optgroup>
    		<optgroup>
    	</select>
    </label>
    ```
    
- **Como funcionar o Input do tipo Search?**
    
    É uma entrada para busca. É parecido com uma entrada de texto, mas pode ter sua aparência modificado dependendo do browser.
    
    ```html
    <form action="">
    	<input type="search"
    		name="q"
    		placeholder="Digite seu termo de busca"
    		size="30"
    		aria-label="Campo de pesquisa: Digite seu termo de busca"
    	>
    	<button>Pesquisar<button>
    </form>
    ```
    
- **Como funcionar o Input do tipo Number?**
    
    É semelhante ao input do tipo text, mas só é possível preencher valores numéricos nele. Neste input é muito utilizado os atributos de validação de intervalo de valores como, `min` e `max`. Outro atributo utilizado dependendo da situação é o step, que permite pular de valores com um intervalo pré definido.
    
    ```html
    <form action="">
    	<input type="number" min="0" max="100" step="5">
    	<button>Enviar<button>
    </form>
    ```
    
- **Como funcionar o Input do tipo Range?**
    
    É uma entrada de controle para seleção de um valor número. Sua apresentação é do tipo slider ou dial control. Seus atributos são os mesmo utilizados no input number, ou seja, `min`, `max` e `step`.
    
    ```html
    <input type="range" min="0" max="100" step="5">
    ```
    
- **Como funcionar o Input do tipo Data e hora?**
    
    São basicamente dois tipos de inputs. O primeiro é o tipo `date`, que permite a entrada de data, mas por conta de diversos padrões de datas pode haver conflitos com registros de arqmazenamento. Para boas prática é aplicado o padrão americano (ano/mês/dia) no caso de armazenamento dessas informações.
    
    ```html
    <input type="date" value="2021-03-22">
    ```
    
    O segundo tipo é o `datetime-local`, que além de permite entrada de data, também permite hora.
    
    O terceiro tipo é o `month`, que permite a entrada de mês e ano.
    
    E o quarto é o `time`, que permite a entrada de hora.
    
    E o quinto e último é o tipo `week`, que por sua vez permite a entrada de semana de acordo com calendário.
    
    <aside>
    ⚠️ Para mais informações sobre este tipo de input consulte [https://caniuse.com.](https://caniuse.com/)
    
    </aside>
    

# Criando um formulário

- **Como criar um bom formulário?**
    
    Primeiro é sempre importante planejar o formulário antes de fazê-lo. Para isso, pode ajudar desenhar o furmulário com objetivo de gerar um protótipo.
    
    Para criar um bom protótipo é interessante, levantar os requisitos essênciais para o formulário, mantendo ele simples e focado, contendo somente os dados necessário e sempre verificando se o formulário te agrada como usuário. Este último é um ótimo exercício para avaliar seu formulário.
    

```html
<body>
    <form action="" method="POST">
        <fieldset>
            <legend>Fale comigo</legend>

            <label for="name">Qual é o seu <strong>nome</strong>?</label>
            <br>
            <input type="text" name="name" id="name" autofocus autocomplete="given-name">
            <br>
            <br>
            <label for="email">Qual é o seu <strong>e-mail</strong>?</label>
            <br>
            <input type="email" name="email" id="email" autocomplete="email" placeholder="example@email.com">
            <br>
            <br>
            <label for="message">Qual é a sua <strong>mensagem</strong>?</label>
            <br>
            <textarea spellcheck name="message" id="message" cols="30" rows="10"></textarea>
            <br>
            <br>
            <button type="submit">Enviar</button>

        </fieldset>
    </form>
</body>
```

A tag form no HTML é a maneira mais tradicional de interagir com o usuário da aplicação e é incrível o que é possível com esse elemento.