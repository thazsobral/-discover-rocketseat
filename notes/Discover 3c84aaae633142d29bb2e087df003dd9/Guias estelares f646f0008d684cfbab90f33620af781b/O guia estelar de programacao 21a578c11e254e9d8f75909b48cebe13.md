# O guia estelar de programação

> *Site: [https://app.rocketseat.com.br/node/o-guia-estelar-de-programacao](https://app.rocketseat.com.br/node/o-guia-estelar-de-programacao)*
> 

Este tópico é fundamental para começar na carreira de desenvolvimento.

# Introdução aos fundamentos

- **O que é programar?**
    
    Programar é a atividade realizada através de algoritmos. Essa atividade é construida através de passos, regras e sequência lógica.
    
    Toda a construção de algoritmo geralmente é fundamentada pela resolução de um problema.
    
- **Como o computador pensa/entende?**
    
    O computador se comunica através de instruções. Estas instruções podem ser desde comandos simples até algoritmos complexos. Após a passagem destas intruções, estas são convertidas em linguagem de máquina, ou seja, `0` e/ou `1`. E quando o computador precisa se comunicar com o usuário o cominho de comunição é invertido.
    
    <aside>
    💡 **Comunicação de pessoa para computador**
    pessoa ⇒ conversão de intrução em linguagem de máquina ⇒ computador
    **Comunicação de computador para pessoa**
    computador ⇒ conversão de linguagem de máquina em instrução ⇒ pessoa
    
    </aside>
    
    De forma resumida, o computador apenas recebe instruções, processa e calcula. Estas ordens são passadas através de alguma linguagem de programação.
    
    E por parte do usuário, é necessário saber o mínimo de programação para passar estas intruções.
    
- **Como funciona um algoritmo?**
    
    Funciona semelhante a uma receita, onde é passado ingredientes que por sua vez são aplicadas a uma sequência lógica de passos que possibilite concluir determinada receita.
    
    Os ingredientes são os dados, podendo eles serem booleanos (verdadeiro/falso), numéricos e caracteres.
    
    ## Um exemplo simples de algoritmo
    
    Algoritmo para acender fogão.
    
    1. pegar o fósforo;
    2. ligar o gás do fogão;
    3. acender o fósforo;
    4. posicionar o fósforo próximo da boca ligada do fogão.
    
    <aside>
    ⚠️ No algoritmo acima o fósforo e um fogão podem ser comparados com ingredientes.
    
    </aside>
    
- **Como funciona a web?**
    
    Para entender o funcionamento da web temos basicamente dois caminhos:
    
    - **O caminho simples**
        1. **digitar o endereço do site (url)**
        2. **acessar um site**
    - **O caminho avançado**
        - **acessar site**
            - utiliza uma URL
                - significa Uniform Resource Locator
                - é utilizado para localiza e indentificar um recurso (que neste caso é um site)
            - utiliza protocolo HTTP
                - significa HyperText Transfer Protocol
                - têm a funçao de trocar mensagens entre computadores
                - a mensagem transferida é quebrada em diversas partes (chunks)
        - o pedido é enviado para o servidor DNS
        - **o pedido está percorrendo por diversos proxies**
            - Proxies
                - é qualquer dispositivo (roteador, modem, outros computadores) que está no meio do caminho entre o cliente e o servidor
                - têm a função de encaminhar pacotes
        - **o endereço (URL) é convertido em um endereço (IP) através do DNS**
            - IP
                - significa Internet Protocol
                - têm a função de endereçar computadores
            - DNS
                - significa Domain Name Servers
                - tẽm a função de converter um domínio (url) em um endereço IP
        - o pedido chega até o servidor
        - o servidor análisa o pedido e responde o solicitante
        - **cria linha de comunicação, através do protocolo TCP, entre o seu computador (cliente) e o computador que possui o site (servidor)**
            - o cliente
                - é o computador ou dispositivo que solicitou o serviço (neste caso o browser)
            - o servidor
                - é o computador configurado para receber as solicitações e respondê-las
            - utiliza o protocolo TCP
                - significa Transfer Control Protocol
                - têm a função de garantir que os pacotes cheguem corretamente ao destino
        - a resposta é enviada para o solicitante
        - o browser recebe os "pedaços" do site e o monta
        
        <aside>
        ⚠️ O processo acima é repetido diversas vezes, pois para cada arquivo (.html, .css, .js, .png, etc) é construída uma nova conexão.
        
        </aside>