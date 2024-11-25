<!-- Filename: / Display title: Hospedagem Local com XAMPP  -->

## Introdução

O XAMPP é um pacote fácil de instalar que agrupa o servidor web Apache, PHP, XDEBUG e o banco de dados MySQL. Isso permite que você crie o ambiente necessário para executar o Joomla! em sua máquina local. A versão mais recente do XAMPP está disponível no site [Apache Friends](https://www.apachefriends.org/index.html). As versões para download estão disponíveis para Linux, Windows e Mac OS X. Baixe o pacote para a sua plataforma.

*Nota Importante sobre XAMPP e Skype:* O Apache e o Skype ambos usam a porta 80 como uma alternativa para conexões de entrada. Se você usa o Skype, vá para o painel Ferramentas-Opções-Avançado-Conexão e desmarque a opção *Usar 80 e 443 como alternativas para conexões de entrada*. Se o Apache iniciar como um serviço, ele ocupará a porta 80 antes que o Skype inicie, e você não verá um problema. Mas, para estar seguro, desative a opção no Skype.

## Instalação

A instalação em qualquer plataforma é muito simples - use o Instalador. Não há manual ou guia real para o XAMPP. A documentação está na forma de FAQs ligadas a partir da página de Downloads.

### Instalação no Windows

Para o Windows, é recomendado instalar XAMPP em "c:\xampp" (não em "c:\program files"). Se você fizer isso, seu Joomla! (e qualquer outra pasta de sites locais) irá para a pasta "c:\xampp\htdocs". (Por convenção, todo o conteúdo web vai para a pasta "htdocs".)

Se você tiver múltiplos servidores http (como o IIS), pode alterar a porta de escuta do xampp. No \apache\conf\httpd.conf, modifique a linha Listen 80 para Listen \[número da porta\] (ex: "Listen 8080").

<div class="alert alert-info">
<h4>Tutorial da Revista da Comunidade Joomla<h4>
<p>Você pode encontrar um tutorial detalhado sobre como instalar o XAMPP no Windows, juntamente com o Joomla 4 Beta, o Joomla Patch Tester e o Git neste <a
href="https://magazine.joomla.org/all-issues/june-2020/github-installing-git"
rel="noreferrer noopener">artigo da Revista da Comunidade Joomla</a>.</p></div>

Para instalar o XDebug: [XAMPP - Configuração do XDebug para PHP 8](https://odan.github.io/2020/12/03/xampp-xdebug-setup-php8.html)

### Instalação no Linux

#### Instalar XAMPP

A página de downloads baixa um instalador chamado xampp-linux-x64-8.2.12-0-installer.run, onde 8.2.12 é a versão mais recente. Execute o arquivo do instalador para instalar Apache2, MySQL e PHP.

Após a instalação, use os seguintes comandos para iniciar e parar os serviços:
```sh
    sudo /opt/lampp/lampp start
    sudo /opt/lampp/lampp stop
```

#### Teste seu servidor localhost XAMPP

Abra seu navegador e aponte para

    http://localhost

O index.php redirecionará para

    http://localhost/xampp

Lá você encontrará instruções sobre como alterar nomes de usuários/senhas padrão. Em um PC que não serve arquivos para a Internet ou LAN, então mudar os padrões é uma decisão pessoal.

#### Obtenha o Joomla

* Baixe o arquivo zip de instalação mais recente do Joomla
* Extraia para o seu disco rígido
* Conecte-se ao localhost com um cliente FTP padrão
* Crie uma pasta para seu Joomla no servidor localhost
* Transfira os arquivos de instalação do Joomla descompactados para a pasta Joomla recém-criada.

##### Importante:

- A instalação do xampp define a Propriedade correta dos arquivos e permissões.
- Usar o **comando CHOWN** irá **causar problemas de Propriedade com o xampp**.
- **Usar nautilus** para manipular pastas/arquivos no localhost irá **causar problemas de Propriedade com o xampp**.

#### Informações do banco de dados

- Host: localhost
- Nome padrão do Banco de Dados: test
- Usuário padrão do Banco de Dados: root
- Senha padrão: Não há senha padrão.
- Senha de administrador: sua escolha.

Instalar Dados de Exemplo é recomendado para o usuário iniciante.

Após a instalação, delete o diretório de instalação e aponte seu Navegador para: `http://localhost/seunovojoomladiretorio` ou `http://localhost/seunovojoomladiretorio/administrator`.

#### Criando um link no menu do Ubuntu

##### Para criar uma GUI para o xampp conectada ao seu menu do Ubuntu

Abra o Terminal e digite:

    sudo nano /usr/share/applications/xampp-control-panel.desktop

Em seguida, copie o seguinte para o editor nano e salve.

    [Desktop Entry]
    Encoding=UTF-8
    Name=XAMPP Control Panel
    Comment=Iniciar e Parar XAMPP
    Exec=gksudo "python /opt/lampp/share/xampp-control-panel/xampp-control-panel.py"
    Icon=/usr/share/icons/Tango/scalable/devices/network-wired.svg
    Terminal=false
    Type=Application
    Categories=GNOME;Application;Network;
    StartupNotify=true

Se o painel de controle não iniciar, tente executar o comando Exec diretamente no terminal:

    gksudo "python /opt/lampp/share/xampp-control-panel/xampp-control-panel.py"

Se você receber o erro:

    Error importing pygtk2 and pygtk2-libglade

Instale as bibliotecas ausentes:

    sudo apt-get install python-glade2

#### Depurador PHP XDebug

O pacote XAMPP para Linux não inclui o depurador PHP XDebug. Para instalar o XDebug no Debian ou Ubuntu:

- Instale o pacote *build-essential*:

    sudo apt-get update
    sudo apt-get install build-essential
    sudo apt-get install autoconf

- Baixe o [pacote de desenvolvimento](http://www.apachefriends.org/en/xampp-linux.html) para sua versão do XAMPP e extraia sobre sua instalação existente:

    sudo tar xvfz xampp-linux-devel-1.7.7.tar.gz -C /opt

- Construa o XDebug:

    wget http://xdebug.org/files/xdebug-2.1.3.tgz
    tar xzf xdebug-2.1.3.tgz
    cd xdebug-2.1.3/
    /opt/lampp/bin/phpize

Depois disso, você verá a seguinte saída no seu console…

    Configurando para:
    PHP Api Version:         20090626
    Zend Module Api No:      20090626
    Zend Extension Api No:   20090626

    ./configure --with-php-config=/opt/lampp/bin/php-config
    make
    sudo make install

Então a saída será esta... por favor, monitore o diretório especificado.

    Instalando extensões compartilhadas:     /opt/lampp/lib/php/extensions/no-debug-non-zts-20090626/

Crie uma pasta no seu diretório temporário que irá armazenar o arquivo de dados gerado pelo XDebug:

    sudo mkdir /opt/lampp/tmp/xdebug
    sudo chmod a+rwx -R /opt/lampp/tmp/xdebug

Instalações alternativas:

Instale usando a biblioteca de extensões PHP (PECL) incluída no xampp:

    sudo /opt/lampp/bin/pecl install xdebug

No Ubuntu/Debian você pode instalar usando:

    apt-get install php5-xdebug

(aviso: isso também irá instalar Apache e PHP dos repositórios apt).

##### Aviso para usuários de 64 bits

Ao compilar o XDebug ou instalar via apt-get, você receberá um erro ao (re)iniciar o xampp:

    /opt/lampp/lib/php/extensions/no-debug-non-zts-20090626/xdebug.so: wrong ELF class: ELFCLASS64

Isso ocorre porque o xampp executa 32 bits, mas o XDebug é 64 bits. Para superar esse problema, ou você faz o xdebug.so em uma máquina de 32 bits ou faz o download de:

    http://code.activestate.com/komodo/remotedebugging/

Baixe o arquivo: "PHP Remote Debugging Client" para "Linux (x86)" Extraia o conteúdo do arquivo em seu computador, este arquivo compactado contém várias pastas com números de versão ex: 4.4, 5.0, 5.1... 5.3 e assim por diante, entre na pasta com o número de versão mais alto ou naquela que funciona para você, então copie manualmente o arquivo "xdebug.so" para o seguinte local, sobrescreva se necessário.

    /opt/lampp/lib/php/extensions/no-debug-non-zts-20090626/

Lembre-se de que este local pode ser diferente no seu computador

### Instalação no Mac OS X

O Mac OS X na verdade inclui um servidor Apache nativamente, mas a maioria dos desenvolvedores prefere usar as ferramentas integradas e a configurabilidade fornecida pelo XAMPP.

Como na maioria dos programas no Mac, a instalação é muito fácil. Visite o site [Apache Friends](https://www.apachefriends.org/) e baixe o instalador (xampp-osx-8.2.4-0-installer.dmg). Clique duas vezes no instalador baixado para iniciar o processo de instalação.

Para iniciar o servidor, abra "XAMPP Control.app" e pressione o botão de iniciar ao lado do Apache.

#### Um Pouco de Solução de Problemas

Muitos usuários do Mac têm um pouco de dificuldade nesta fase ao tentar configurar outra instância do Apache em sua máquina. Se você não conseguir iniciar o Apache do XAMPP, você tem duas opções: **Você pode mudar a porta de escuta do XAMPP.** Em \Applications\XAMPP\xamppfiles\etc\httpd.conf, modifique a linha que diz "Listen 80" para Listen \[número da porta\]. Exemplo:

    Listen 8080

**Você pode mudar a porta de escuta do servidor Apache pré-instalado.** No finder, vá para "/etc" (CMD+SHIFT+G); a partir daqui, você poderá navegar pelos arquivos Apache normalmente ocultos. Encontre a pasta rotulada Apache2 e edite o arquivo "http.conf". Modifique a linha que diz "Listen 80" para Listen \[número da porta\]. Exemplo:

    Listen 8080

*Nota: Se você optar por alterar a porta do servidor Apache pré-instalado, poderá precisar reiniciar o computador para que as alterações tenham efeito. Você também terá que se autenticar como administrador para mudar esses arquivos.*

### Teste da Instalação do XAMPP

Uma vez que o XAMPP está instalado e você iniciou o serviço Apache com a ferramenta Control Panel do XAMPP, você pode testá-lo abrindo seu navegador e navegando até `http://localhost`. Você deve ver a tela de boas-vindas do XAMPP semelhante à mostrada abaixo.

![A página inicial do xampp](../../../en/images/hosting/local-hosting-xampp.png)

Selecione o link chamado `phpinfo()` no menu superior. Isso exibirá uma longa tela de informações sobre a configuração do PHP, conforme mostrado abaixo.

![A página de informações da versão do xampp php](../../../en/images/hosting/local-hosting-xampp-php.png)

Neste ponto, o XAMPP foi instalado com sucesso. Note o *Arquivo de Configuração Carregado*. Vamos editar este arquivo na próxima seção para configurar o XDebug.

*Traduzido por openai.com*

