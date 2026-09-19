<!--
{
    "source": "https://docs.joomla.org/https:",
    "title": "Laragon para Windows",
    "description": " ",
    "author": ""
}
-->

## Configurando um ambiente Joomla local usando o Laragon

O Laragon é uma ferramenta leve para Windows que gerencia o Apache, o MySQL e o
PHP em uma única instalação simples. Sem arquivos de configuração, sem
configuração manual — basta baixar, executar e começar a criar/testar o Joomla.
Veja este artigo na Revista da Comunidade Joomla: [Laragon: The Effortless, High-Performance
AMP Server for Windows](https://magazine.joomla.org/all-issues/october-2025/laragon-the-effortless,-high-performance-amp-server-for-windows).

Este guia leva você do zero a um site Joomla local em funcionamento e
também aborda uma pequena peculiaridade da interface na versão mais recente,
que é fácil de corrigir quando você sabe o que está acontecendo.

### Baixando e instalando o Laragon

Para começar, acesse a [página oficial de download do
Laragon](https://laragon.org/download). Baixe a versão completa do Laragon
(atualmente v8.6.1), pois ela inclui tudo de que você precisa (como Apache,
MySQL e as versões mais recentes do PHP) prontamente disponível.
Como alternativa, você pode baixar o [instalador](https://github.com/leokhoa/laragon/releases/download/8.6.1/laragon-wamp.exe) diretamente.

Depois que o arquivo `.exe` for baixado, clique duas vezes nele para iniciar a
instalação.

**Observação sobre o Windows Defender:** Como o Laragon é uma ferramenta
poderosa para desenvolvedores, o Windows Defender SmartScreen pode impedir que
ele seja iniciado e exibir uma tela azul de aviso. Isso é normal — basta clicar
em **Mais informações** e, em seguida, clicar no botão **Executar assim mesmo**
que aparece na parte inferior.

![aviso de proteção da configuração do laragon](../../../en/images/hosting-local/laragon-setup-windows/01-laragon-setup-windows-protected-warning.png)

Avance pelas etapas do assistente de configuração. As configurações padrão são
perfeitamente adequadas, mas preste atenção a estes dois detalhes importantes:

1.  **Local de destino:** Deixe a pasta de instalação como
    `C:\laragon`. Instalar o Laragon dentro de `Program Files` ou
    `Documents` pode causar problemas de permissão posteriormente.
2.  **Opções de configuração:** Verifique se a caixa de seleção **Auto virtual hosts**
    está marcada. Esse é o recurso que fornece ao seu site Joomla local um
    endereço limpo (como `http://myjoomla.test`) em vez de um endereço IP bruto.

![opções de configuração do laragon](../../../en/images/hosting-local/laragon-setup-windows/02-laragon-setup-options.jpg)

Quando a instalação terminar, reinicie o computador. (o assistente de
instalação solicitará que você faça o mesmo)

### Iniciando o servidor e configurando as permissões do firewall

Abra o Laragon no menu Iniciar e clique no botão **Iniciar tudo**.

Como esta é a primeira vez que você executa um servidor local, o Windows
precisa verificar se ele é seguro. Você verá avisos do Firewall do Windows
Defender solicitando acesso à rede para serviços como **Apache HTTP
Server**, **MySQL** e **Mailpit**.

- Basta clicar em **Permitir acesso** em cada um desses avisos.

Depois que o acesso for permitido, o Laragon iniciará seu ambiente local. Você
saberá que ele está funcionando quando os números das portas do Apache e do
MySQL aparecerem na janela do Laragon.

### A peculiaridade de "Já está em execução" (e como corrigi-la)

Quando terminar de trabalhar, você pode clicar em "Parar tudo" para desligar o
Apache e o MySQL e, em seguida, clicar no "X" no canto superior direito para
fechar a janela do Laragon.

Eis a peculiaridade: clicar no "X" não encerra completamente o Laragon. Ele
continua sendo executado silenciosamente em segundo plano. Se você tentar abrir
o aplicativo Laragon novamente pelo menu Iniciar ou pela área de trabalho, verá
um aviso amarelo no canto inferior direito da tela dizendo:
**"O Laragon já está em execução!"**

![aviso de que o laragon já está em execução](../../../en/images/hosting-local/laragon-setup-windows/03-laragon-setup-already-running-notice.png)

**A armadilha:** Se você clicar no "X" desse pequeno aviso amarelo para
fechá-lo, a janela principal do Laragon também desaparecerá, deixando você
completamente sem acesso ao painel de controle. (Observação: às vezes também
pode aparecer uma janela pop-up de licença que faz a interface congelar de
maneira semelhante).

**A solução:** Se a interface desaparecer ou congelar, basta forçar o
encerramento do processo em segundo plano e começar novamente. É muito simples:

1.  Pressione `Ctrl + Shift + Esc` no teclado para abrir o **Gerenciador de
    Tarefas do Windows**.
2.  Procure por **Laragon** na lista de processos em execução.
3.  Clique nele com o botão direito e selecione **Encerrar tarefa**.

Pronto! Você encerrou com segurança o processo em segundo plano travado. Agora
você pode abrir o Laragon pelo menu Iniciar, e ele será carregado perfeitamente,
permitindo que você clique em "Iniciar tudo" sem erros.

### Lidando com as janelas pop-up da licença (as telas de “insistência”)

O Laragon é gratuito para uso em desenvolvimento e testes não comerciais,
sem a necessidade de comprar uma licença. No entanto, após usar o aplicativo
por algum tempo, provavelmente você encontrará uma solicitação de “Chave de
licença” incentivando você a apoiar o projeto.

Como você está usando a versão gratuita, basta fechar essas telas, mas há
uma sequência específica a esperar:

1.  A janela principal de **Chave de licença** aparecerá sobre a interface do
    Laragon. Clique no texto **Fechar** ou no “X”.<br>
    ![janela de chave de licença da configuração do laragon](../../../en/images/hosting-local/laragon-setup-windows/04-laragon-setup-license-key-window.png)
2.  Imediatamente após fechá-la, uma segunda janela pop-up de **Aviso**
    aparecerá, lembrando que o Laragon está sendo executado sem uma licença.
    Clique em **OK** ou no “X”.<br>
    ![aviso de ausência de licença da configuração do laragon](../../../en/images/hosting-local/laragon-setup-windows/05-laragon-setup-no-license-warning.png)
3.  Depois de fechar esse segundo aviso, o Laragon poderá abrir
    automaticamente o navegador da Web e redirecioná-lo para
    `https://laragon.org/key`. Basta fechar essa aba do navegador.
4.  Ao voltar à interface do Laragon e clicar em **Iniciar tudo** para
    iniciar o servidor novamente, talvez seja necessário clicar nas mesmas
    duas janelas pop-up mais uma vez.

Depois de fechá-las pela segunda vez, as janelas pop-up desaparecerão, e
você estará completamente livre para usar o Laragon!

*(Observação: se em algum momento durante essas janelas pop-up a interface do
Laragon congelar e não responder aos cliques, basta lembrar do atalho
`Ctrl + Shift + Esc` do Gerenciador de Tarefas mencionado na etapa anterior
para encerrar o processo em segundo plano e começar novamente)*

### Criando um banco de dados para o Joomla

Antes de instalar o Joomla, você precisa de um banco de dados vazio para
armazenar os dados dele. O Laragon inclui um gerenciador de banco de dados
integrado chamado HeidiSQL, portanto tudo de que você precisa já está
disponível.

1.  Certifique-se de que os serviços do Laragon estejam em execução (clique em
    **Iniciar tudo**).
2.  Clique no botão **Banco de dados** na interface principal do Laragon.
3.  Uma janela do Gerenciador de sessões será aberta. O Laragon preenche
    automaticamente as credenciais locais padrão para você (Usuário: `root`,
    Senha: *\[deixe em branco\]*).
4.  Clique no botão **Abrir** na parte inferior.<br>    
    **Solução de problemas: erro “Access denied for user 'root'@'localhost'”:
    ** Se você clicar no botão **Abrir** e receber imediatamente um erro de
    falha na conexão, não se preocupe! Isso geralmente significa que você tem
    outro programa MySQL (como o XAMPP ou o MySQL Workbench) em execução em
    segundo plano, bloqueando o acesso do Laragon à porta do banco de dados
    (porta 3306).<br>
    ![solução de problemas de acesso da configuração do laragon](../../../en/images/hosting-local/laragon-setup-windows/06-laragon-setup-troubleshooting.jpg)
    **A solução:**
    1.  Pressione a tecla Windows, digite **Serviços** e pressione Enter.
    2.  Role a lista para baixo até encontrar **MySQL**, **MySQL80** ou
        **MariaDB**.
    3.  Clique com o botão direito do mouse no serviço em execução e selecione
        **Parar**.
    4.  Volte ao Laragon, clique em **Parar tudo**, depois em **Iniciar tudo** e
        tente clicar em **Abrir** no Gerenciador de sessões novamente. A conexão
        deverá ser estabelecida sem nenhum erro.
5.  Depois de se conectar com sucesso e entrar no gerenciador de banco de
    dados HeidiSQL, observe a coluna à esquerda. Clique com o botão direito do
    mouse no nome do servidor (geralmente identificado como `Laragon.MySQL` ou
    `127.0.0.1`).
6.  Passe o cursor sobre **Criar novo** e selecione **Banco de dados**.
7.  Um pequeno prompt aparecerá. Digite um nome simples para o banco de dados
    no campo “Nome” (por exemplo: `joomla_dev`). Você pode deixar a lista
    suspensa “Agrupamento” com a configuração padrão.
8.  Clique em **OK**.

Você verá o novo banco de dados aparecer na lista à esquerda. É isso! Agora
você pode fechar completamente a janela do gerenciador de banco de dados.

### Obtendo seus arquivos do Joomla

Agora que seu servidor e banco de dados estão prontos, é hora de colocar os arquivos do Joomla no lugar. A forma de fazer isso depende inteiramente do que você deseja alcançar com esta configuração local:

**Método 1: Para criar um site padrão** Se você deseja apenas criar um site ou testar extensões, precisa da versão estável padrão.

- Acesse a [página oficial de download do Joomla](https://downloads.joomla.org) 
  e baixe o arquivo `.zip` mais recente do **Pacote completo**.

**Método 2: Para testar PRs da comunidade (teste de patches)** Se o seu objetivo é ajudar a comunidade testando patches e Pull Requests, você precisa de um pacote pré-compilado que contenha o código mais recente disponível.

- **A compilação Nightly:** Baixe o `.zip` mais recente da compilação Nightly em
  [Nightly Builds](https://developer.joomla.org/nightly-builds.html).
  Essas compilações são geradas todas as noites e são perfeitas para uso com o componente Joomla Patch Tester.
- **O pacote pré-compilado da PR:** Como alternativa, se você estiver testando uma PR específica no GitHub, role até o final da página da PR, clique em
  **Show all checks** e procure o link **Download Prebuilt packages**.
  ![laragon setup prebuilt package link](../../../en/images/hosting-local/laragon-setup-windows/07-laragon-setup-prebuilt-package-link.png)

**Método 3: Para contribuir com o código principal** Se você planeja escrever código e enviar suas próprias Pull Requests, precisa do código-fonte bruto e não compilado.

- Clone o [repositório do Joomla CMS no GitHub](https://github.com/joomla/joomla-cms)
  diretamente no seu ambiente Laragon usando o Git.
- *Importante:* Um clone bruto do GitHub não funcionará imediatamente — você precisa
  abrir o Terminal do Laragon e executar `composer install` e `npm ci` dentro da sua pasta para compilar as dependências do PHP e os recursos CSS/JS. (Como você instalou a versão completa do Laragon, o Composer e o NPM já estão instalados no seu sistema).

### **Colocando os arquivos no Laragon:**

Independentemente do método escolhido, fazer os arquivos funcionarem no Laragon é exatamente o mesmo processo:

1.  Abra a interface do Laragon e clique no botão **Root**. Isso abre automaticamente a pasta `C:\laragon\www` no seu computador.
2.  Dentro dessa pasta `www`, crie uma nova pasta para o seu projeto. Mantenha o nome da pasta simples, em letras minúsculas e sem espaços (por exemplo:
    `joomla_dev` ou `joomla_pr_test`).
3.  Coloque os arquivos do Joomla dentro dessa nova pasta. (Se você baixou um
    `.zip` no Método 1 ou 2, extraia todo o conteúdo diretamente nessa
    pasta. Se estiver usando o Git no Método 3, clone o repositório nessa
    pasta).
4.  Como você ativou os "hosts virtuais automáticos" durante a instalação,
    o Laragon usa automaticamente o nome da pasta para criar o endereço web local. Assim, uma pasta chamada `joomla_dev` fica acessível no seu navegador em `http://joomla_dev.test`.
    <br>
    **Dica: mantenha seus ambientes organizados:** é uma boa ideia criar
    pastas diferentes para versões distintas do Joomla ou testes específicos de PR
    (por exemplo, uma pasta chamada `joomla5_stable` e outra chamada
    `joomla4_dev`). O Laragon executará todas elas lado a lado com suas próprias
    URLs `.test` limpas, impedindo que seu código e bancos de dados
    se misturem!
    <br>
    ![laragon setup project folders](../../../en/images/hosting-local/laragon-setup-windows/08-laragon-setup-project-folders.png)

## Executando o instalador do Joomla

Você tem seu banco de dados, e seus arquivos do Joomla estão na nova
pasta (por exemplo, `C:\laragon\www\joomla_dev`). Agora é hora de instalar
o Joomla de fato!

**Etapa crucial: recarregue o Apache!** Se o Laragon já estava em execução quando você criou a nova pasta do projeto, ele ainda não sabe que a pasta existe.

- Abra a interface do Laragon.

- Clique em **"Reload"** no canto superior direito. *(Isso força o Laragon a verificar a pasta
  `www` e gerar o novo endereço `http://joomla_dev.test`).*

**Concluindo a configuração:**

1.  Abra o navegador e digite a URL gerada automaticamente para o seu projeto
    (por exemplo, `http://joomla_dev.test`).
2.  Você deverá ver imediatamente a página do instalador web do Joomla.
3.  Escolha seu idioma e informe um nome para o seu site Joomla.
4.  Configure sua conta de Superusuário (lembre-se desses dados de acesso, pois você precisará deles para acessar o painel de administração do Joomla!).
5.  Na tela **Configuração do banco de dados**, insira as credenciais do banco de dados do Laragon que você criou anteriormente:
    - **Tipo de banco de dados:** `MySQLi` (padrão)
    - **Nome do host:** `localhost`
    - **Nome de usuário:** `root`
    - **Senha:** *\[Deixe este campo completamente em branco\]*
    - **Nome do banco de dados:** o nome exato que você digitou anteriormente no HeidiSQL
      (por exemplo, `joomla_dev`).
    ![laragon setup joomla installer database settings](../../../en/images/hosting-local/laragon-setup-windows/09-laragon-setup-joomla-installer-database.png)
6.  Clique em **Install Joomla.**

Quando a barra de progresso terminar, você verá uma mensagem de sucesso — agora poderá clicar em **Open Site** para visualizar seu site local ativo ou em **Open Administrator** para entrar no painel administrativo do Joomla.

Pronto — seu site Joomla local está ativo e pronto para uso.

*Traduzido por openai.com*