# Terminal sua segunda casa

> *Site: [https://app.rocketseat.com.br/node/terminal](https://app.rocketseat.com.br/node/terminal)*
> 

O terminal é a ferramenta mais poderosa na sua mão, é incrível tudo que podemos fazer com ele e hoje vamos descobrir essas possibilidades.

# Abertura

- **O que é uma interface?**
    
    É a forma de se comunicar com algo. Um exemplo simples é, uma interface para chamar alguém que mora um em uma casa pode ser a campainha.
    
    Dessa forma, fica simples saber que a interface permite a comunicação de alguma coisa para outra coisa.
    
- **O que é command line?**
    
    Existem dois tipos de interface quando o assunto é o básico computadores, temos o **GUI** (Graphical User Interface) e o **CLI** (Command Line Interface).
    
    **GUI** é a interface focada em **recursos visuais**, ou seja, possui recursos visuais que permite a interação com o computador via janelas, botões, menus, mouse. Estas interfaces são comuns para navegar na internet (browser), edição de vídeos, jogos, etc. 
    
    O **CLI** é a interface que permite interação via **linha de comando**, como é o caso do terminal.
    
    No CLI (em ambientes UNIX por exemplo) o **usuário** envia **comandos** para o shell (ou interpretador) via **terminal**, e o **shell** é responsável por executar estes comandos conversando diretamente com o **kernel**, que por sua vez é responsável por conversar diretamente com o **hardware**.
    
    <aside>
    💡 No ambientes baseados em **Linux** por exemplo, o shell padrão é o **Bash** (Bourne-again shell).
    
    </aside>
    
- **Como funciona a sintaxe do Shell?**
    
    Basicamente, o shell utiliza a seguinte sintaxe ou sequência:
    
    1. **Command** (obrigatório), é o programa que será executado.
    2. **Option**(s), é para mudar (ou definir) o comportamento do command, ou seja, explica ao command como ele deve funcionar. 
        
        Geralmente o optional começa com `-` (traço) e utiliza uma letra apenas (mas às vezes também pode-se aplicar mais de uma letra). A maioria dos comandos oferem muitas opções.
        
        <aside>
        💡 Para visualizar as opções do comando na maioria dos programas, utilize a opção `--help`.
        
        </aside>
        
    3. **Argument**(s), é para especificar onde o programa vai operar (arquivos ou diretórios). Mas dependendo do programa o argumento pode ser utilizado para passar informações obrigatórias ou não para o programa. Nestes casos consulte a documentação do programa no site ou (em alguns casos) através da opção `--help`.

# Preparação e dicas

- **O que tab completion?**
    
    É a função de tecla **TAB** para autocomplete de commands e arguments do terminal.
    
    ![https://elias.praciano.com/wp-content/uploads/2016/08/teclado-tecla-tab.jpg](https://elias.praciano.com/wp-content/uploads/2016/08/teclado-tecla-tab.jpg)
    
    <aside>
    ⚠️ Pode ser que alguns terminais não tenham está função.
    
    </aside>
    
- **Quais os atalhos mais úteis para utilizar no terminal?**
    
    São muitos atalhos que podem servir para melhor manuseio do terminal, mas as principais são:
    
    - **up** (seta pra cima) / **down** (seta pra baixo): ambas as teclas servem para navegar no histórico de comandos executados no terminal, ou seja, clicando na seta para cima é obter o comando executado anteriormente, e se continuar clicando é possível obter outros comandos excutados antes. Caso clicado para baixo é possível avançar para comandos executados depois.
    - **ctrl + a** e **home**: posiciona o curso no início da linha.
    - **ctrl + e** e **end**: posiciona o curso no final da linha.
    - **ctrl + u**: limpa toda a linha digitada.
    - **ctrl + k**: remove tudo, a partir do cursor até o final da linha.
    - **ctrl + l**: equivalente ao comando **clear**.
- **O que é Hyper?**
    
    É um terminal desenvolvido em Electron (HTML, CSS e JS) muito famoso entre os desenvolvedores.
    
    Para instalar ele basta acesse o [site oficial do Hyper](https://hyper.is/) e seguir a documentação. Caso queira customizar mais seu terminal siga o [guia do ZSH](https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH).
    
- **Como conseguir ajuda com os comandos do terminal?**
    
    A maior do CLI seguem o mesmo padrão para buscar ajuda sobre comandos.
    
    A **primeira opção** é digitar o comando `man` antes do comando que deseja consultar.
    
    ```bash
    man ls
    ```
    
    Para navegar no manual do comando utilize `z` para ir para a **próxima** página e `w` para **voltar** uma página. Se preferir pode utilizar a tecla `h` para **ajuda** dentro do manual. Utilize a tecla `q` para **sair** do manual.
    
    A **segunda opção** é utilizar o comando `apropos` antes do pedaço do comando que deseja buscar. Este comando retorna todos os comandos que contém em algum pedaço a sequência de caracteres digitado.
    
    ```bash
    apropos ch
    ```
    

# Arquivos e diretórios

- **Quais são os comandos mais úteis utilizados no terminal?**
    - `pwd` (Present Working Directory): retorna o caminho do **diretório atual**.
    - `cd` (Change Directory): **acessa o caminho** para um diretório. O caminho `.` acessa o **diretório atual**, já o `..` acesse o **diretório inferior** na árvore de diretório. Se quiser voltar para o **último diretório** que esteve utilize o caminho `-`. Caso necessário o caminho `/` acessa o **diretório raiz** do seu sistema.
    - `ls` (List): **lista** todos os **caminhos** (arquivos e diretórios) possíveis no diretório.
    - `file`: retorna **informações sobre o arquivo** como, tipo do arquivo e outras informações sobre o arquivo.
    - `stat`: retorna informações sobre o arquivo, dono do arquivo, modificações, tamanho, restrições, e outras **informações mais técnicas**.
    - `mkdir` (Make Directory): **cria um novo diretório**. É possível criar mais diretórios internos de um novo também utilizando a option `-p`.
    - `touch`: **altera a data e hora de modificação** (para a data e hora atual) de arquivos e diretórios, e também **cria novos arquivos**.
    - `cp` (Copy): **copia arquivos e diretórios**. Onde o primeiro argument é o que quer copiar e o segundo argument é para onde quer copiar. Se for necessário copiar um diretório, é preciso utilizar a opção `-r` para copiar também os arquivos internos do diretório.
    - `mv` (Move): **move arquivos e diretórios**, e também renomeia arquivos e diretórios. O que difere um do outro é a forma que é utilizado. Se for mover arquivos e diretórios, o primeiro agument é um nome existente e o segundo argument também. Já para renomear, o primeiro argument existe e o segundo não, e também não pode ser passado como um caminho (senão será movido o arquivo com o novo nome).
    - `rm` (Remove): **remove arquivos e diretórios**. Para remover diretórios, é necessário utilizar o option `-r` para remover os arquivos internos do diretório também. Dependendo das restrições do arquivo, pode ser necessário utilizar o option `-f` para forçar a remoção.
    - `find`: **retorna arquivos ou diretórios encontrados** de acordo com o argument passado. Para utilizar este comando, é necessário passar o local que deseja procurar e o nome do arquivo ou diretório qu está buscando. Pode-se refinar mais o comando passando a option `-type` para definir se é um arquivo ou um diretório, e o option `-name` para definir o nome do arquivo ou diretório.
    - `cat` (Concatenate): **retonar, cancatena e grava o conteúdo de um** determinado **arquivo**.
    - `less`: **abre o conteúdo do arquivo** no modo manual, ou seja, de forma páginada (diferente do `cat`).
    
    <aside>
    ⚠️ Para aprender mais arquivos ou entender mais dos comandos apresentados acima acesse o comando man seguido do comando que deseja aprender, ou acesse o option `--help` do command, para ver um resumo do manual do command, ou acesse o site do [Guia Linux BR](https://guialinux.uniriotec.br/).
    
    </aside>
    
    <aside>
    ⚠️ Se quiser aprender mais sobre Linux baixe os pdfs no [site do Guia Foca](https://www.guiafoca.org/).
    
    </aside>
    
- **O que são Wildcards?**
    
    É o conceito de caracteres curingas, ou seja, utilizando wildcards é possível agilizar o processo de alteração em diretórios como, mover diretórios e arquivos, remover arquivos, etc.
    
    Os principais wildcards são:
    
    - `*`: **substitui um ou mais caracteres** a partir daquele ponto (para trás ou para frente). Por exemplo, se for necessário remover todos os arquivos que começam com os carateres `"db-"` basta utilizar o wildcard `*` no final sequência, que o shell vai compreender que a partir deste wildcard pode haver um ou mais caracteres.
        
        ```bash
        rm -rf db-*
        ```
        
        Agora se for necessário remover todos os arquivos que possuam a extenção `".mp4"`, pode-se utilizar `*` para substituir o que vem antes.
        
        ```bash
        rm -rf *.mp4
        ```
        
    - `?`: substitui apenas um caracter. Por exemplo, se for necessário copiar apenas os arquivos que possua o nome `"file"` e um outro caracter depois para a pasta files, basta utilizar o wildcard `?`, que este será considerado qualquer caracter possível.
        
        ```bash
        cp file? files
        ```
        
- **Como utilizar o editor nano?**
    
    Pode começar digitando o comando `nano` seguido do nome de um arquivo existente (para editá-lo) ou o nome de um arquivo não existente (para criá-lo).
    
    Para salvar o arquivo e suas alterações utilize a combinação `ctrl + o`, ou se preferir pode sair (caso tenha feito alguma alteração no arquivo será questionado se deseja salva-la) `ctrl + x`.
    
- **Como utilizar o editor vim?**
    
    Pode abrir ou criar um arquivo utilize o comando `vim` seguido do nome de um arquivo existente (para editá-lo) ou o nome de um arquivo não existente (para criá-lo).
    
    O vim é diferente de outros editores, seu maior foco é na agilidade de edição de arquivos. Por este motivo é necessário conhecer o básico de atalhos de teclado, como:
    
    - `i`: para iniciar o modo de inserção de texto;
    - a: para iniciar o modo de inserção de texto, mas pulando o cursor para o próximo caractere;
    - `o`: para iniciar o mode de inserção de texto, mas já pulando o cursor para a próxima linha;
    - `ESC`: para sair do modo de inserção (ou outro) e voltar para o modo de visualização;
    - `k` ou `up` (seta para cima): para mover para a cima no modo de visualização;
    - `l` ou `rigth` (seta para a direita): para mover para a direita no modo de visualização;
    - `j` ou `down` (seta para baixo): para mover para a baixo no modo de visualização;
    - `h` ou `left` (seta para esquerda): para mover para a esquerda no modo de visualização;
    - `:q`: para sair do vim, e.
    - `:w`: para salvar alterações no arquivo.
    
    <aside>
    ⚠️ Para aprender um pouco mais sobre vim acesse a [documentação oficial](http://vimdoc.sourceforge.net/htmldoc/usr_toc.html) e pratique de forma desco´ntraída no [Vim Adventures](https://vim-adventures.com/).
    
    </aside>