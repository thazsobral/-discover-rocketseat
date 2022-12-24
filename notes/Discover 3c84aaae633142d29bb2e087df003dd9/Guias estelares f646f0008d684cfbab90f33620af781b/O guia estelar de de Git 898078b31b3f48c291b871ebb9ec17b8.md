# O guia estelar de de Git

> *Site: [https://app.rocketseat.com.br/node/o-guia-estelar-de-git](https://app.rocketseat.com.br/node/o-guia-estelar-de-git)*
> 

Para garantir que seu código está seguro e passível de manunteções futuras este tópico é fundamental.

# Introdução

- **O curso serve para cenários onde:**
    - modificar algo sem perder o que já têm feito
    - Salvar e arquivar o código
    - Risco de perca da estação de trabalho ou perca de arquivo
    - Há a possibilidade de restaurar versões anteriores

# O que é Git

- **O que é um controlador de versão?**
    
    VCS (version Control System) serve para:
    
    - registrar alterações em um ou mais arquivos
    - lembrar de versões anteriores posteriormente
    - reverter alterações de um arquivo ou projeto
    - comparar mudanças ao longo do tempo
    - visualizar autor de alguma modificação
    - recuperar arquivos corrompidos
    - etc
- **Quais os tipos de controles de versão?**
    - **Sitemas locais**
        - permite manipular arquivos entre diretórios
        - tipo comum e simples
        - possibilita erros
        - propenso a erros, onde se torna fácil de sobrescrever código etc.
        
        ![O%20guia%20estelar%20de%20de%20Git%20898078b31b3f48c291b871ebb9ec17b8/Untitled.png](O%20guia%20estelar%20de%20de%20Git%20898078b31b3f48c291b871ebb9ec17b8/Untitled.png)
        
        **Sistems locais com RCS (Revision Control System)**
        
        - semelhante aos Sistemas locais (acima)
        - registra as alterações
        - permite visualizar as diferenças entre versões de um arquivo
        - possui um formato especial no disco
        - permite restaurar versões anteriores de um arquivo
        
        **Algumas desvantagens**
        
        - não é possível compartilhar com outros
        - se der roblema no disco tudo é perdido
    - **Sistemas centralizados** (Ex.:CVS, Subversion e Perforce)
        - os arquvos de controle de versão ficam em um único servidor
        - varias pessoas utilizam os arquivos deste servidor
        
        **Algumas vantagens sobre VCSs locais**
        
        - permite controle sobre atividades dos colaboradores do projeto
        - os administradores tem controle sobre quem pode fazer o que
        - é mais fácil administrar um CVS do que clientes distribuidos
        
        **Algumas desvantagens**
        
        - se o servidor der problema impossibilita os clientes utilizarem
        - se o disco do servidor der problema todos os arquivos são perdidos
    - **Sistemas distribuídos** (Ex.:Git, Mercurial, Bazaar e Darcs)
        - possibilita duplicar ou clonar localmente o repositório
        - não há o risco de perder os arquivos caso algum disco dê problema, pois há diversas cópias dele.
        - cada clone é um backup dos arquivos
        - os cliente utilizam a versão mais recente dos dados
        - quando trabalhado localmente a partir de um repositório descentralizado também é mantido uma cópia local, assim não é necessário estar conectado com o repositório remoto.
- **O que é o git?**
    
    É um sistema de versão distribuido e open-source.
    
    Ele permite gravar pontos na história dos arquivos através de commits, o que possibilita voltar até esses pontos posteriormente.
    
    Ele também permite controlar o fluxo de alterações de um projeto através e branchs. As branchs são ramificações do fluxo de commits, assim pode-se a partir de um ponto gravado gerar mais fluxos de versão do projeto. Para explicar melhor, é como se tivesse criado linhas do tempo alternativas para a hstória do projeto. Isso permite trabalhar com diversos autores ao mesmo tempo e analisar e resolver conflitos entre as versões.
    

# Instalando o Git

Para instar o git basta seguir o tutorial disponível no [site](https://git-scm.com/downloads).

Para verificar se já está instalado basta digitar `git --version`.

- **Como fazer a configuração inicial?**
    
    **Configure sua identidade**
    
    Abra o terminal e digite o seguinte comando para definir o nome do autor que vai utiizar o git no computador.
    
    ```bash
    git config --global user.name "seu_nome"
    ```
    
    Depois defina o e-mail do autor que vai utilizar o git.
    
    ```bash
    git config --global user.emai "seu_email"
    ```
    
    Essas informações vão ser registradas juntamente com os commits realizados.
    
    Caso não o computador não pertença a este usuário ou deseje utilizar o usuário e e-mail para um único projeto basta remover a flag `--global`.
    
    **Configure seu editor**
    
    Esse editor serve para digitar a mensagem do commit entre outras coisas relacionadas ao git.
    
    ```bash
    git config --global core.editor <seu_editor>
    ```
    
    **Visualiar as configurações**
    
    ```bash
    git config --list
    ```
    
    **Configure ainda mais**
    
    Também é possível visualizar e atribuir variáveis de configuração através do `git config`. Essas variáveis podem ser armazenadas em três lugares diferentes:
    
    1. `/etc/gitconfig`: estas configurações ficam disponiveis para todos os usuários do sistema e todos os repositórios. Para definir estas configuração passa a flag `--system`.
    2. `~/.gitconfig` ou `~/.config/git/config`: estas configurações afetam somente o usuário. Para definir estas configurações utilize a flag `--global`.
        
        > *No Windows está pasta fica disponível no diretório `C:/Users/$USER`*
        > 
    3. `.git/config`: estas configurações ficam disponíveis somente para o repositório.
- **O que é git help?**
    
    É um comando que auxilia no uso do git.
    
    Para utilizar ele basta digitar `git help` que será retornado um manual básico de utilização do git. Caso deseje se aprofundar em algum comando específico basta digitar `git help` seguido do comando deseja, como demonstrado no exemplo abaixo.
    
    ```bash
    git help log
    ```
    

# Começando

- **Como iniciar um repositório?**
    
    Para iniciar um repositório temos o método básico que é, cria a pasta do seu projeto e em seguida digite `git init`. Dessa forma, será iniciado o controle de versão dentro deste repositório.
    
    É importante destacar que o controle de versão iniciado rastreia as alterações realizadas dentro do repositório executado o comando, isso inclui as alterações realizadas dentro dos sub diretórios também.
    
- **Onde o git guarda o histórico do projeto?**
    
    Todo o histórico e configuração do repositório está dentro da pasta `.git`, que por sua vez é gerado através do comando `git init`.
    
- **O que é Git log e como usá-lo?**
    
    É onde fica armazenado todo o histórico de eventos relacionados ao repositório, sendo esses eventos os commits.
    
    Para consultar os log em forma extensa digite o comando a seguir.
    
    ```bash
    git log
    ```
    
    Caso queira uma versão mais enxuta.
    
    ```bash
    git lo --oniline
    ```
    
    Se preferir apenas um número especifico de log digite o seguinte comando.
    
    ```bash
    git log -n 5
    ```
    
    Caso queira retornar logs desde um determinado dia.
    
    ```bash
    git log --since=2019-01-01
    ```
    
    Podemos também filtrar os logs por autor.
    
    ```bash
    git log --author=Fulano
    ```
    
    Para utilizar expressões regulares basta utilizar o seguinte.
    
    ```bash
    git log --grep="init"
    ```
    
- **O que é um Git commit e como usá-lo?**
    
    Commit é um ponto marcado na história do repositório, ele serve para registrar alterações dentro do próprio repostório e seus documentos.
    
    Antes de criar um commit, precisamos ter nossas alterações adicionadas. Lembrando que essas alterações podem ser criações, alterações e exclusões de arquivos.
    
    ```bash
    git add file.txt
    ```
    
    Depois podemos criar nosso commit.
    
    ```bash
    git commit -m "minha mensagem"
    ```
    
    <aside>
    ⚠️ Para arquivos que já estão sendo "rastreados" pelo git podemos utilizar o comando `git commit -am "<mensagem_commit>"`. Dessa forma economizamos o comando `git add <nome_arquivo>`. Mas o primeiro comando só funciona se o arquivos já estiver sendo "ratreado", ou seja, já foi adicionado ao repositório alguma vez.
    
    </aside>
    

# Conceitos

- **Quais são os estágios de um arquivo?**
    
    Os arquivos dentro do sistema do git passam por basicamente três estágios para se fluxo:
    
    ![O%20guia%20estelar%20de%20de%20Git%20898078b31b3f48c291b871ebb9ec17b8/Untitled%201.png](O%20guia%20estelar%20de%20de%20Git%20898078b31b3f48c291b871ebb9ec17b8/Untitled%201.png)
    
    Primeiro o repositório é iniciado com o `init`/`clone`, depois ele segue os três estagios:
    
    1. **Modified**: neste estágio o arquivo está dentro do Working Diretory, ou seja, ele ainda está dentro do nosso diretório padrão sendo trabalhado.
    2. **Staged**: neste estágio o arquivo que foi modificado foi adicionado (`add`) ao Stage Area, ou seja, ele está num estágio de "empacotado" (pronto para ser commitado).
    3. **Commited**: neste estágio o arquivo foi commitado (`commit`) para dentro do Local Repository. Neste momento o arquivo e suas alterações foram marcadas na história do repsitório.
    
    Esses três estágios podem passar por uma análogia dependendo do estágio em que estão, onde:
    
    <aside>
    👉 **Working Directory**: *Os arquivos estão sendo trabalhados.* → **Stage Area**: *Os arquivos foram colocados dentro de uma caixa.* → **Local Repository**: *A caixa com os arquivos/modificações foram enviados para o repositório.*
    
    </aside>
    
    Caso queira remover alguma alteração/arquivo no "empacotamento" digite o seguite comando.
    
    ```bash
    git rm --cached <nome_do_arquivo>
    ```
    
- **O que é Git Workflow?**
    
    Git Workflow é o nome dado ao fluxo de trabalho de git. Esse fluxo se compõe dos estágios de arquivos e sua marcação na linha do tempo do repositório.
    
    ![Na imagem acima é mostrado os estágios dos arquivos, os pontos gravados (`A`, `B` e `C`) na história do repositório e a última versão do arquivo (`file.txt(v3)`).](O%20guia%20estelar%20de%20de%20Git%20898078b31b3f48c291b871ebb9ec17b8/Untitled%202.png)
    
    Na imagem acima é mostrado os estágios dos arquivos, os pontos gravados (`A`, `B` e `C`) na história do repositório e a última versão do arquivo (`file.txt(v3)`).
    
    Dessa forma fica resumido o fluxo de trabalho do git.
    
    Para melhorar o gerenciamento do fluxo no momento em que estiver trabalhando, pode-se utilizar o seguinte comando.
    
    ```bash
    git status
    ```
    
- **O que é Hash SHA-1?**
    
    É o nome dado ao código gerado para cada commit realizado. Esse código serve como um identificador único do momento marcado na história do repositório, e é através dele que se torna possível retornar a um determinado estado do repositório.
    
    O Hash SHA-1 é gerado através de uma soma que serve para conferir posteriormente a integridade dos dados gravados naquele determinado momento.
    
    ![Nesta imagem é mostrado que cada commit gera um hash ou código único, pois o código é gerado de acordo com os metadados do commit.](O%20guia%20estelar%20de%20de%20Git%20898078b31b3f48c291b871ebb9ec17b8/Untitled%203.png)
    
    Nesta imagem é mostrado que cada commit gera um hash ou código único, pois o código é gerado de acordo com os metadados do commit.
    
    Uma outra forma de visualizar esses hashs são como fotográfias do estado dos arquivos em determinado momento.
    
    <aside>
    ⚠️ O SHA-1 é formado por 40 caracteres contendo valores hexadecimais.
    
    </aside>
    
- **O que é HEAD?**
    
    HEAD no git simboliza um ponteiro que aponta para qual ponto (`commit`) da história e qual linha do tempo (`branch`) do repositório estamos também.
    
    Para visulizar este ponto podemos executar o seguinte comando.
    
    ```bash
    git log
    ```
    
    Para saber qual o caminho correto que precisa acessar para saber o valor do ponteiro basta digitar o seguinte comando.
    
    ```bash
    cat .git/HEAD
    ```
    
    Sabendo o caminho do arquivo do ponteiro HEAD podemos seguir com o comando abaixo.
    
    ```bash
    cat .git/<caminho_do_arquivo>
    ```
    

# Alterando arquivos

- **O que é GIT ADD?**
    
    É o comando para adicionar arquivos no ratreamento do git ou de forma mais simples, empacotar arquivos para serem commitados.
    
    ```bash
    git add <nome_do_arquivo>
    ```
    
    Caso queira adicionar todos os arquivos juntos basta substituir o `<nome_do_arquivo>` por ponto (`.`).
    
    Pode-se também utilizar outras expresões para adicionar arquivos como, `*.txt` que adiciona todos os arquvos que contêm a extessão .txt. E o mesmo se aplica para outras extessões.
    
    ```bash
    git add *.txt
    ```
    
- **Como editar arquivos?**
    
    Para editar arquivos para a linha do tempo do repositório basta utilizar o `git add` depois da alteração no próprio arquivo. Assim o git marca essa alteração a história do repositório.
    
    Para empacotar as alterações utilizamos para serem enviadas para o controle de versão utilizamos o comando `git commit`.
    
    Um ponto interessante para se citar é que no primeiro commit do repositório podemos utilizar o seguinte comando que agilizar o processo.
    
    ```bash
    git commit -a
    ```
    
    Ou
    
    ```bash
    git commit -am "mensagem do commit"
    ```
    
    neste formato o passamos do estágio do Working Directory direto para o o estágio do Local Repository.
    
- **O que é GIT DIFF?**
    
    Utilizando o `git status` podemos visualizar o resultado das alterações feitas no repositório.
    
    Mas caso seja necessário visualizar com mais detalhes as modificações feitas no repositório utilize o comando `git diff`.
    
    ![O comando `git diff` representa as alterações  através de linhas. As linhas em vermelho contendo o sinal de menos (`-`) representa as linhas removidas e as linhas verdes com sinal de mais (`+`) representam as linhas incluidas.](O%20guia%20estelar%20de%20de%20Git%20898078b31b3f48c291b871ebb9ec17b8/Untitled%204.png)
    
    O comando `git diff` representa as alterações  através de linhas. As linhas em vermelho contendo o sinal de menos (`-`) representa as linhas removidas e as linhas verdes com sinal de mais (`+`) representam as linhas incluidas.
    
    Para arquivos adicionados não são mostrados através do comando `diff` pois eles não estão sendo rastreados pelo git. Ou seja, o comando `git diff` serve para ver alterações nos arquivos rastreados, seja essas alterações as modificações nos arquivos ou remoção dos mesmos.
    
    Por padrão o comando `git diff` visualiza apenas as modificações que estão no Working Directory. Para visualizar os arquivos adicionados no Stage Area utilize o seguinte comando.
    
    ```bash
    git diff --staged
    // ou
    git diff --cached
    ```
    
    Podemos também visualizar as alterações com cores nos documentos. Para isso utilize a flag `--color-words`.
    
    ```bash
    git diff --color-words
    ```
    
    Outro ponto interessante de citar sobre este comando, é que em seu retorno é indicado as linhas que foram realizadas as alterações.
    
    ![Neste caso indica que têm alterações a partir da linha 30.](O%20guia%20estelar%20de%20de%20Git%20898078b31b3f48c291b871ebb9ec17b8/Untitled%205.png)
    
    Neste caso indica que têm alterações a partir da linha 30.
    
- **Como remover arquivos com git?**
    
    Para remover arquivos através do git utilize o seguinte comando.
    
    ```bash
    git rm <nome_do_arquivo>
    ```
    
    Dessa forma é aplicado a remoção do arquivo da pasta e da lixeira, e é adicionado automaticamente a alteração no Stage Area.
    
- **O que é GIT MV?**
    
    O comando `git mv` serve tanto para renomear arquivos quanto para mover arquivos.
    
    Para renomear basta seguite o seguite sintaxe apresentada no comando abaixo.
    
    ```bash
    git mv <nome_atual_do_arquivo> <novo_nome_do_arquivo>
    ```
    
    Dessa forma a alteração adicionada no Stage Area é identificada como renamed.
    
    ![O%20guia%20estelar%20de%20de%20Git%20898078b31b3f48c291b871ebb9ec17b8/Untitled%206.png](O%20guia%20estelar%20de%20de%20Git%20898078b31b3f48c291b871ebb9ec17b8/Untitled%206.png)
    
    Renomear arquivos com o `git mv` segue o mesmo fluxo do `git rm`, onde o arquivo sofre a alteração e já é adicionado ao Stage Area.
    
    Para mover arquivos utilizamos também o comando `git mv`, mas neste caso ao invés de passar um nome novo para o arquivo passamos o caminho para onde queremos movê-lo, como demostrado abaixo.
    
    ```bash
    git mv <nome_do_arquivo> <caminho_do_novo_local_do_arquivo>
    ```
    

# Desfazendo mudanças

- **Como desfazer alterações do repositório?**
    
    Depende do caso da alteração você aplica alguns comandos diferentes.
    
    Para desfazer alterações feitas em algum arquivo e que **não** esteja **adicionado no Stage Area**. Para isso, é realizado uma restauração do arquivo.
    
    ```bash
    git restore <nome_do_arquivo>
    ```
    
    Para desfazer alterações **adicionadas ao Stage Area** utilizamos a flag `--staged`.
    
    ```bash
    git restore --staged <nome_do_arquivo>
    ```
    
    Ou se preferir podemos utilizar o formato antigo do comando.
    
    ```bash
    git reset HEAD <nome_do_arquivo>
    ```
    
- **Como corrigir o último ponto na história (commit)?**
    
    Corrigir o último commit é mais simples do que corrigir commits mais antigos.
    
    O git trabalha com hashs, e esse códigos são gerados utilizando também o hash do commit anterior, e dessa forma o hash de commits anteriores também dependem de commits passados. E é por esse motivo que corrigir o último commit é mais simples, pois ele não impacta em commits posteriores.
    
    Para realizar esta correção utilizamos a flag `--amend` (corrigir) com o seguinte comando.
    
    ```bash
    git commit --amend -m "mensagem do ultimo commit corrigida"
    ```
    
    <aside>
    ⚠️ É importante destacar que até mesmo correções feitas em commits geram uma nova hash, por isso alterar commits mais antigos são mais complexos.
    
    </aside>
    
    Caso queira corrigir outras alterações utilizamos outras flags ou nenhuma, dependendo do que será corrigido.
    
- **Como restaurar um arquivo de outros pontos da história (commit)?**
    
    Para restaurar arquivos de outro qualquer ponto da história podemos utilizar o comando git checkout, como demostrado abaixo.
    
    ```bash
    git checkout <hash_do_commit> -- <nome_do_arquivo>
    ```
    
    Dessa forma o arquivo é restaurado e é incluido automaticamente no Stage Area.
    
- **Como remover arquivos que não estão no Stage Area?**
    
    Podemos fazer isso de uma forma destrutiva é utilizando o comando `git clean`.
    
    ```bash
    git clean -n // para listar os arquivos que seram alterados
    
    // e
    
    git clean -f // para remover todos os arquivos que não estão no Stage Area
    
    ```
    
    <aside>
    ⚠️ Tenha cuidado ao utilizar este comando pois ele não gera nenhuma marcação na história, ou seja, removido os arquivos com este comando não há como recuperá-los.
    
    </aside>
    
- **Como retornar a um ponto na história (commit)?**
    
    fazendo isso retornamos os arquivos existentes no commit escolhido que já não existem mais no estado atual do repositório.
    
    <aside>
    ⚠️ Para fazer isso é importante está com o Working Area limpo, ou seja, sem pendências de alterações no diretório.
    
    </aside>
    
    Esta tarefa utilizamos o comando `git revert`, sendo ele utilizados de duas maneiras.
    
    A primeira é contando quantos commits queremos voltar. Ou seja, conte quantos commits você deseja retornar e adicione o `~` antes, como demonstrado abaixo.
    
    ```bash
    git revert HEAD~1
    ```
    
    Ou podemos utilizamos o próprio hash do commit, como também demonstrado a seguir.
    
    ```bash
    git revert <hash_do_commit>
    ```
    
    <aside>
    ⚠️ Assim como em outros comandos do git, as alterações realizadas com este comando são incluidas automaticamente no Stage Area.
    
    </aside>
    

# Usando Git em um projeto real

- **O que é GIT SHOW?**
    
    Este comando é semelhante ao git diff, mas neste é mostrado todas as linhas alteradas no commit.
    
    ```bash
    git show <hash_do_commit>
    ```
    
- **O que é o arquivo .gitgnore?**
    
    Estte é um arquivo de configuração que ser justamente para ignorar o rastreamento de arquivos e diretórios.
    
    Para utilizá-lo basta criar um arquivo nomeado como `.gitignore` e adiocionar o nome dos arquivos ou diretórios que deseja ignorar, como no exemplo abaixo.
    
    ```bash
    .DS-store // dessa forma estamos ignorando o arquivo .DS-store
    node-modules/ // dessa forma estamos ignorando o diretorio node-modules
    ```