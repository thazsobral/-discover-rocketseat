# O guia estelar de Github

> *SIte: [https://app.rocketseat.com.br/node/o-guia-estelar-de-git-hub](https://app.rocketseat.com.br/node/o-guia-estelar-de-git-hub)*
> 

Conheça um dos principais repositórios de código do mundo.

<aside>
⚠️ Como pré-requisito para está etapa é o [básico de git](O%20guia%20estelar%20de%20de%20Git%20898078b31b3f48c291b871ebb9ec17b8.md).

</aside>

# Introdução

- **Qual a diferença entre Git e Github?**
    
    Git é um controle de versão de repositório e GIthub é um repositório remoto com a finalidade de complementar este controle de versão.
    

# Primeiros passos

- **Como criar uma conta no Github?**
    
    Basta preencher o cadastro em [Signup](https://github.com/join?ref_cta=Sign+up&ref_loc=header+logged+out&ref_page=%2F&source=header-home).
    
- **Como configuar seu perfil público?**
    
    Após acessar sua conta, basta acessar a página de [configurações](https://github.com/settings/emails) e desmarcar a seguinte opção.
    
    ![O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled.png](O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled.png)
    
    Dessa forma seu e-mail estará público.
    

# Criando repositório

- **Como criar um novo repositório?**
    
    Para criar um repositório basta clicar em **Novo** na página de **Repositórios**.
    
    ![O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%201.png](O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%201.png)
    
    Após isso basta preencher os campos e clicar em **Criar Repositório**.
    
    ![O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%202.png](O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%202.png)
    
    - O **Nome do Repositório** é o nome dado ao repositório. Este nome deve ser único na sua conta.
    - Na **Descrição** você pode conter uma breve descrição do seu repositório.
    - Você pode escolher a visibilidade do repositório, **Público** ou **Privado**.
    - Você também pode inicializar o repositório com alguns arquivos considerados padrões como, **README** (arquivo que contém informações sobre o repositório), **.gitignore** (arquivo que define arquivos e diretórios a serem ignorados pelo controle de versão) e **license** (arquivo de define e descreve a licença do repositório). É vale citar que estes arquivos podem ser criados depois da criação do repositório também.
- **Como clonar um repositório?**
    
    Basta acessar o repositório que deseja e clicar no botão **Code** e depois copiar a url do repositório na área de clone.
    
    ![O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%203.png](O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%203.png)
    
    Em seguida acesse seu diretório local onde deseja trabalhar com o clone e digite o seguinte comando git.
    
    ```bash
    git clone <url_do_repositorio_remoto> // para clonar o repositório
    ```
    
    Dessa forma, você terá um clone do repositório desejado.
    
- **Como visualizar o código puro dos arquivos no Github?**
    
    Para visualizar o código do arquivo basta ou acessar o arquivo através dos links no repositório ou se preferir uma versão mais "pura" utilize o botão **raw**.
    
    ![O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%204.png](O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%204.png)
    
- **Como colaborar com outros repositórios através do Github?**
    
    Para fazer através do Github direto, basta acessar o arquivo que deseja colaborar e clicar no icone de lápis,
    
    ![O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%205.png](O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%205.png)
    
    depois clicar em **Propor Mudança**.
    
    ![O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%206.png](O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%206.png)
    
    Dessa forma será gerada um **Pull Request** para o dono do repositório.
    
    <aside>
    ⚠️ Quando criado um **Pull Request** através do Github é gerado automática um **Fork** em seu repositório.
    
    </aside>
    
- **Como deletar um repositório com Github?**
    
    Clique em **Deletar este repositório**
    
    ![O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%207.png](O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%207.png)
    
    e conforme com o nome do repositorio e a sua senha.
    
- **Como fixar repositórios no perfil do Github?**
    
    Clique em **Customizar seus pins** o seu perfil
    
    ![O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%208.png](O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%208.png)
    
    e selecione os repositórios desejados.
    

# Trabalhando com repositórios

- **O que é um chave SSH?**
    
    É um meio mais seguro de autenticação. Essa é uma chave baseada em criptografias de chave pública, ou seja, existem duas chaves, uma para ser utilizada pelo servidor e outra por qualquer outra pessoa.
    
- **Como criar uma chave SSH para ser utilizada no Github?**
    
    ### Gerar uma chave SSH
    
    Acesse o terminal e digite o seguinte comando.
    
    ```bash
    ssh-keygen -t rsa -b 4096 -C "<seu_email>"
    ```
    
    - `-t rsa`: tipo de encriptação rsa.
    - `-b 4096`: força da encripyação.
    - `-C "<seu_email>"`: é o e-mail utilizado para gerar a chave.
    
    Depois digite o seguinte comando para capturar a chave gerada.
    
    ```bash
    cat ~/.ssh/id_rsa.pub
    ```
    
    Em seguinda acesse as configurações de **SSH** e **GPG keys.**
    
    ![O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%209.png](O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%209.png)
    
    E adicione o resultado gerado pelo comando `cat` e insira uma **Nova chave SSH**.
    
    ### Adicionar chave ao ssh-agent
    
    Inicie o ssh-agent em segundo plano e capture o pid retornado.
    
    ```bash
    eval "$(ssh-agent -s)"
    ```
    
    Dessa forma adicione a chave privada ao ssh-agent.
    
    ```bash
    ssh-add ~/.ssh/id_rsa
    ```
    
    <aside>
    ⚠️ Para mais informações de como fazer esta configuração em outros SOs siga a [documentação](https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent).
    
    </aside>
    
    Agora é possível utilizar o link de repositórios através do SSH disponível no repositório.
    
    ![O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%2010.png](O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%2010.png)
    
    E depois adicionando no remote do seu repositório local através do seguinte comando.
    
    ```bash
    git remote add origin <chave_ssh_repositorio_remoto>
    ```
    
    <aside>
    ⚠️ Para finalizar a adição do link é necessário realizar o comando `git push`. Como por exemplo, `git push origin main`. Dessa forma será pedido para confirmar o link de conexão.
    
    </aside>
    
- **Como visualizar os repositórios remotos com o link SSH?**
    
    Após a adição do link remoto utilizando a chave SSH podemos visualizar os repositórios remotos utilizando com comando.
    
    ```bash
    git remote -v
    ```
    
- **Como alterar o nome da branch do Github?**
    
    Para alterar o nome da branch utilizamos o comando.
    
    ```bash
    git branch -M main
    ```
    
- **Como puxar a alteração feita na nuvem para o repositório local?**
    
    Para sincronizar seu repositório local com o repositório remoto ja linkado utilize o seguinte comando.
    
    ```bash
    git pull
    ```
    
- **O que são históricos no Github?**
    
    Para cada commit realizada nos arquivos de um repositório é gerado um log no histórico para o repositório.
    
    ![O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%2011.png](O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%2011.png)
    
    Podendo ele ser visualizado através do botão H**istory.**
    
    ![O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%2012.png](O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%2012.png)
    
    Dessa forma é possível visualizar todas as alterações feitas no arquivo através dos ids visíveis do lado direto de cada commit.
    
    Outro ponto interessante é que pode-se adicionar comentários as alterações, tanto no commit
    
    ![O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%2013.png](O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%2013.png)
    
    como também nas linhas.
    
    ![O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%2014.png](O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%2014.png)
    
    Caso queira acessar o ponto na história do repositório basta acessar o seguinte botão.
    
    ![O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%2015.png](O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%2015.png)
    
- **Como corrigir conflitos de arquivos de merge?**
    
    Podemos ter diversas situações de CONFLICT de merge. Uma dessas situações é:
    
    - **Conflito de merge de alterações de linhas**: onde temos uma alteração realiazada no repositório remoto e no repositório local não temos a mesma alteração, mas temos outra. Para esta situação aparecerá os maracadores de início (`<<<<<<< HEAD`), de separação das suas alteraões e as da branch (`=======`) e fim (`>>>>>>> BRANCH-NAME`) da alteração, como no exemplo a seguir.
        
        ```jsx
        If you have questions, please
        <<<<<<< HEAD
        open an issue
        =======
        ask your question in IRC.
        >>>>>>> branch-a
        ```
        
        Para isso remova as alterações que deseja remover juntamente com os marcadores e salve o documento.
        
        Dessa forma, já pode ser realizado o comando `commit` seguido do comando `push`.
        
        <aside>
        ⚠️ Para resolução de outros conflitos consulte a [documentação](https://docs.github.com/pt/github/collaborating-with-issues-and-pull-requests/resolving-a-merge-conflict-using-the-command-line#:~:text=Conflitos%20de%20merge%20de%20altera%C3%A7%C3%B5es%20diferentes%20na%20linha,-Para%20resolver%20um&text=Voc%C3%AA%20deve%20resolver%20esse%20conflito,tem%20o%20conflito%20de%20merge.&text=Gere%20uma%20lista%20dos%20arquivos%20afetados%20pelo%20conflito%20de%20merge.).
        
        </aside>
        

# Outras features

- **Como consultar tecnologias, projetos e discussões no Github?**
    
    Digite o assunto de interesse no seguinte campo.
    
    ![O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%2016.png](O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%2016.png)
    
    Caso queira buscar no Github todo clique no botão ao lado (All Github).
    
    ![O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%2017.png](O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%2017.png)
    
    Para pesquisar de forma mais detalhada podemos utilizar a seguinte sintaxe para hacks de pesquisa.
    
    ```jsx
    user:<nome_do_usuario> <palavra_de_busca>
    ```
    
    <aside>
    ⚠️ Para mais informações sobre pesquisa no Github consulte a [documentação](https://docs.github.com/pt/github/searching-for-information-on-github/searching-on-github).
    
    </aside>
    
- **O que é um Fork?**
    
    É uma cópia do repositório desejado paa seu Github. Isso pode ser feito através do botão Fork.
    
    ![O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%2018.png](O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%2018.png)
    
- **O que é uma Star?**
    
    É uma sinalização de que o projeto é relevante. Esta sinalização pode ser comparada com o Like de outras redes sociais.
    
    ![O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%2019.png](O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%2019.png)
    
- **O que é um Watching?**
    
    É a sinalização de o repositório esta sendo observado. Dessa forma, todas as alterações realizadas no respositório vão ser notificadas aos observadores dele.
    
    ![O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%2020.png](O%20guia%20estelar%20de%20Github%20cbce153d580a4ae2b810e231b25ae563/Untitled%2020.png)
    
- **Como clonar um repositório?**
    
    Clonar um repositório pode ser feito através do seguinte comando utilizando o protocolo HTTP.
    
    ```jsx
    git clone <url_repositorio>
    ```
    
- **Qual a diferença entre Fork e Clone?**
    
    O Fork é a cópia de um repositório para seu Github, ou seja, repositório remoto. E o Clone é a cópia de um repositório para a máquina local, ou seja, seu repositório local.