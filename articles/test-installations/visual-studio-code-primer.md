<!-- Filename: Visual_Studio_Code_Primer / Display title: Introdução ao Visual Studio Code  -->

## VS Code - Um IDE Gratuito e Popular

Da Wikipedia:

> Visual Studio Code, também comumente referido como VS Code, é um editor
> de código-fonte criado pela Microsoft para Windows, Linux e macOS.
> As funcionalidades incluem suporte para depuração, realce de sintaxe,
> completude inteligente de código, snippets, refatoração de código e Git
> incorporado. Os usuários podem alterar o tema, atalhos de teclado, preferências,
> e instalar extensões que adicionam funcionalidades adicionais.

## Instalação

A página padrão do site do VS Code tem uma lista suspensa para cada plataforma suportada. É provável que sua plataforma já esteja pré-selecionada. Então, baixe e instale, e você estará pronto para começar.

### Primeiros Passos

A página *Comece* do VS Code tem alguns itens de *Início*, uma lista de itens *Recentes* e uma curta lista de *Percursos*. Se você for completamente novo no VS Code, é recomendável visualizar estes. Eles levam apenas alguns minutos.

A Documentação do VS Code está disponível no menu *Ajuda / Documentação*. Os [Vídeos Introdutórios](https://code.visualstudio.com/docs/getstarted/introvideos) valem muito a pena serem vistos. Cada um dura de 2 a 6 minutos e oferece uma excelente introdução às funcionalidades do VS Code.

A documentação oficial é o lugar a se consultar se você quiser pesquisar informações específicas.

### Extensões do VS Code

O VS Code pode ser usado para qualquer tipo de texto, incluindo uma ampla gama de linguagens de programação. Ele funciona com JavaScript sem a necessidade de adicionar extensões. Outras linguagens são detectadas por contexto, então, se você começar a criar e salvar códigos PHP, provavelmente será solicitado a instalar um pacote de suporte para PHP.

Clique no ícone de *Extensões* na *Barra de Atividades* à esquerda para ver o que você já tem instalado e o que é recomendado. Você precisará da extensão PHP Debug!

### A Disposição da Tela do VS Code

Alguns termos usados em instruções subsequentes:

- **Barra de Atividades**: a barra estreita à esquerda da tela. Selecione qualquer ícone para abrir ou fechar a Barra Lateral Primária.
- **Barra Lateral Primária**: quando aberta, mostra os detalhes da atividade selecionada.
- **Barra de Status**: na parte inferior da tela. Mostra o que está acontecendo.
- **Painel**: uma área abaixo dos editores de texto para exibir outras informações.

Selecione um ícone de layout no canto superior direito para abrir ou fechar qualquer um desses itens.

## Codificando uma Extensão Joomla

Para criar uma extensão, seu objetivo é criar um arquivo zip que você possa instalar em um site Joomla em funcionamento. Então, você precisa de uma pasta para conter seu código. Esta pasta deve estar no seu espaço pessoal de arquivos no seu laptop ou computador de mesa, usado para desenvolvimento local. Ela não deve estar na árvore do seu site. Por exemplo, você poderia usar *~/jextensions* para conter subpastas para diferentes extensões. Eu uso *~/git* porque é curta e fácil de soletrar, embora potencialmente confusa, já que cada subpasta usa um repositório git separado.

### Código de Exemplo

Se você gostaria de algum código de exemplo para trabalhar, há uma extensão disponível no GitHub chamada *mod_debugme*. Como o nome sugere, é um módulo com alguns bugs. Além do código do módulo, há um arquivo *build.xml* para ilustrar uma maneira de automatizar a construção para testes e criação de um arquivo zip.

O módulo é projetado para mostrar os próximos eventos (3 por padrão) de uma lista armazenada em uma tabela de banco de dados. Você pode imaginar isso sendo usado em um site de escritório ou família na expectativa de um bolo.

Pode ser melhor começar usando comandos git na linha de comando. Primeiro, crie uma pasta para seu código e, em seguida, clone o repositório remoto:
```sh
    mkdir ~/git
    cd ~/git
    git clone https://github.com/ceford/j4xdemos-mod-debugme
```
A resposta deve levar apenas alguns segundos:
```sh
    Cloning into 'j4xdemos-mod-debugme'...
    remote: Enumerating objects: 23, done.
    remote: Counting objects: 100% (23/23), done.
    remote: Compressing objects: 100% (16/16), done.
    remote: Total 23 (delta 3), reused 23 (delta 3), pack-reused 0
    Unpacking objects: 100% (23/23), done.
```
Você deve tirar um momento para olhar o conteúdo da pasta:
```sh
    cd j4xdemos-mod-debugme
    ls -al
    total 16
    drwxr-xr-x   6 ceford  staff   192  2 Sep 17:48 .
    drwxr-xr-x   3 ceford  staff    96  2 Sep 17:48 ..
    drwxr-xr-x  12 ceford  staff   384  2 Sep 17:48 .git
    -rw-r--r--   1 ceford  staff  1402  2 Sep 17:48 README.md
    -rw-r--r--   1 ceford  staff   927  2 Sep 17:48 build.xml
    drwxr-xr-x   8 ceford  staff   256  2 Sep 17:48 mod_debugme
```
A pasta *.git* contém informações sobre o repositório. O arquivo *README.md* é um documento markdown que descreve este repositório. O arquivo *build.xml* é um arquivo usado para construir a extensão com uma ferramenta externa, Phing - descrito posteriormente. A pasta *mod_debugme* contém o código da extensão.

### Instalar no Joomla

Comprimir a pasta da extensão para criar um arquivo zip instalável:
```sh
    zip -r mod_debugme.zip mod_debugme
```
Agora você pode instalar o arquivo zip no site Joomla que você usa para testes. Após a instalação, você precisa criar um módulo de Site e atribuí-lo a uma posição de módulo. Como é um módulo com defeito, você poderia atribuí-lo a uma posição em *Todas as páginas* enquanto trabalha nele; ou você poderia atribuí-lo a uma posição em uma única página; ou poderia posicioná-lo em um artigo que tem seu próprio item de menu.

Após a instalação, exclua o arquivo zip.

### Ativar o Modo de Depuração

Na Configuração Global do Joomla, defina *Debug do Sistema* para *Sim* e *Relatório de Erros* para *Máximo*.

Quando você abrir uma página contendo o módulo com bug, verá uma rastreamento de pilha informando onde um erro foi acionado.

![rastreamento de pilha vscode](../../../en/images/test-installations/vscode-primer-stack-trace.png)

Às vezes, o erro de codificação está na primeira linha do rastreamento de pilha. Caso contrário, se o erro for acionado no código da biblioteca, por exemplo, passando dados inválidos para uma função de banco de dados, o erro de codificação pode estar mais abaixo na lista de chamadas de função.

## Abrir Pasta de Extensão no VS Code

No VS Code, use o item de menu Arquivo / Abrir Pasta para localizar e abrir a pasta que contém sua cópia local do código da extensão *mod_debugme*. Você deverá ver algo semelhante ao seguinte:

![visualização de pasta do vscode](../../../en/images/test-installations/vscode-primer-screen.png)

Você pode conseguir diagnosticar o problema apenas lendo o código. No caso do erro *Classe "DebugHelper" não encontrada*, você verá que uma declaração *use* foi comentada algumas linhas antes. Esquecer de inserir uma declaração *use* é um erro comum durante o desenvolvimento inicial!

Corrija esse problema e então compacte e instale o módulo novamente. Essa etapa pode ficar um pouco tediosa quando você tem múltiplos problemas. É aí que as ferramentas de build se tornam úteis.

## Phing

Phing é uma ferramenta de linha de comando, disponível para todas as plataformas, usada para construir pacotes de software usando instruções armazenadas em um arquivo XML, chamado build.xml por padrão. Ao trabalhar com código de extensão, ela pode ser usada para fazer duas coisas:

- copiar arquivos modificados da pasta de origem da sua extensão para os locais corretos na pasta do seu site.
- gerar um novo arquivo zip para novas instalações.

Baixe e instale o Phing. Outras ferramentas de construção estão disponíveis! Você pode instalar o Phing na sua própria pasta bin ou em uma pasta bin do sistema. Você precisa anotar o caminho para o código do Phing. Neste exemplo, ele é *~/bin/phing-latest.phar*. Você pode testá-lo a partir da linha de comando após entrar na pasta contendo o código da sua extensão:
```sh
    cd ~/git/j4xdemos-mod-debugme
    php ~/bin/phing-latest.phar
```
Resposta:
```sh
    Buildfile: /Users/ceford/git/j4xdemos-mod-debugme/build.xml

    mod_debugme > main:
          ... Quaisquer arquivos copiados serão mencionados aqui.
          [zip] Building zip: /Users/ceford/zips/mod_debugme.zip

    BUILD FINISHED

    Total time: 0.0863 seconds
```

## Tarefas do VS Code

Para executar o Phing dentro do VS Code, você precisa criar um arquivo *tasks.json* na pasta *.vscode* na raiz da pasta *j4xdemos-mod-debugme*. Se esta última não existir, primeiro crie-a. Em seguida, crie o arquivo *tasks.json* e insira o seguinte código:
```json
    {
        // Consulte https://go.microsoft.com/fwlink/?LinkId=733558
        // para a documentação sobre o formato do tasks.json
        "version": "2.0.0",
        "tasks": [
          {
            "label": "Build mod_debugme",
            "type": "shell",
            "command": "php ~/bin/phing-latest.phar",
            "windows": {
              "command": "php ~/bin/phing-latest.phar"
            },
            "group": "build",
            "presentation": {
              "reveal": "always",
              "panel": "shared"
            }
          }
        ]
    }
```
Usuários do Windows precisam corrigir o comando específico para o Windows. Agora você pode compilar a extensão usando o menu *Terminal / Executar Tarefa de Construção*. O resultado do comando deve aparecer no Painel de Terminal abaixo da área de Edição.
```sh
      *  Executando tarefa: php ~/bin/phing-latest.phar

    Buildfile: /Users/ceford/git/gitdemo/j4xdemos-mod-debugme/build.xml

    mod_debugme > main:

          [zip] Nada a fazer: /Users/ceford/zips/mod_debugme.zip está atualizado.

    BUILD FINISHED

    Total time: 0.1031 seconds

     *  O terminal será reutilizado por tarefas, pressione qualquer tecla para fechá-lo.
```
Podem surgir mensagens de erro incompreensíveis. A causa mais provável é ter caminhos inválidos para pastas no arquivo *build.xml* ou uma pasta não ter sido criada. Apenas mais um tipo de problema para depurar!  

