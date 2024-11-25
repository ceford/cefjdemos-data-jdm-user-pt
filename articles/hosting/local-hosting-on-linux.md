<!-- Filename: No_original_yet / Display title: Hospedagem Local no Linux -->

## Introdução

Este artigo aborda a hospedagem do Joomla em um computador pessoal baseado em Linux para fins de teste e desenvolvimento. As versões de Linux cobertas são da família Debian-Ubuntu, especificamente o Linux Mint. Outras distribuições são semelhantes, mas têm sintaxe de comando e locais de arquivos diferentes.

Você precisa instalar um conjunto de pacotes de software frequentemente referido como pilha LAMP. As letras referem-se a Linux, Apache, MySQL e PHP. Você pode instalar o software usando a Interface Gráfica do Usuário (GUI) ou a linha de comando em uma janela de Terminal. São maneiras diferentes de usar o Gerenciador de Pacotes Synaptic.

## Instalar o Apache com a GUI

No Menu do sistema, marcado com o logotipo LM, selecione Administração / Gerenciador de Pacotes Synaptic. Você será solicitado a inserir sua senha. Digite a senha de login para abrir a GUI. No canto superior direito, há um botão `Pesquisar`. Selecione-o e insira **apache**, depois selecione `Pesquisar`. Marque a caixa `apache2` e, no rótulo pop-up, selecione `Marcar para Instalação`. Outro pop-up mostrará uma lista de pacotes adicionais necessários para suportar o apache. Selecione `Marcar`:

![gerenciador de pacotes synaptic](../../../en/images/hosting/synaptic-package-manager-gui.png "GUI do Gerenciador de Pacotes Synaptic")

Selecione o botão `Aplicar` na barra de ferramentas superior e o botão `Aplicar` no diálogo Resumo. O Apache será instalado e configurado, e o processo terminará com um **diálogo de Alterações Aplicadas**. Selecione `Fechar`.

Você pode confirmar que o Apache está instalado e funcionando abrindo seu navegador, Firefox por padrão em uma nova instalação do Linux Mint, e digitando **localhost** na barra de URL. Você deverá ver a Página Padrão do Ubuntu Apache2:

![página padrão do apache](../../../en/images/hosting/apache-default-page.png "Página Padrão do Apache")

A página contém algumas informações úteis sobre as localizações dos arquivos que podem não estar tão facilmente disponíveis mais tarde, então você pode querer imprimir esta página em papel ou em um arquivo pdf.

## Instalar PHP com o CLI

Provavelmente, a melhor maneira de instalar o PHP é usando a linha de comando. Um dos motivos para isso é que, no momento da escrita, o Gerenciador de Pacotes Synaptic só oferece o PHP8.1, embora o PHP8.2 esteja disponível há algum tempo e possa ser instalado a partir de um repositório de terceiros. Existe uma boa descrição do procedimento neste tutorial com seções de Início Rápido e Detalhado.

Primeiro, feche a interface gráfica do Gerenciador de Pacotes Synaptic e, em seguida, abra uma janela do Terminal e digite os seguintes comandos, um de cada vez:

```bash
sudo add-apt-repository ppa:ondrej/php
sudo apt update
sudo apt install php8.2 php8.2-cli php8.2-{bz2,curl,mbstring,intl}
sudo apt install php8.2-fpm
sudo a2enconf php8.2-fpm
sudo systemctl reload apache2
```
No seu navegador, verifique se a página padrão do localhost ainda está funcionando.

## Instalar MySQL ou MariaDB

Você pode procurar na web informações sobre cada um desses pacotes de banco de dados. MySQL é a escolha tradicional, mas foi adquirido pela Oracle e agora é menos popular. MariaDB é uma substituição Open Source de fácil uso com recursos adicionais. Ambos funcionam com Joomla! 5, mas não é fácil mudar de um para o outro. As tabelas precisam ser exportadas e importadas. Joomla! 5 requer versões mínimas específicas que o Linux Mint oferece através do Gerenciador de Pacotes Synaptic.

Abra a interface gráfica do Gerenciador de Pacotes Synaptic e procure por mysql-server ou mariadb-server. Selecione a caixa de seleção para o item que termina em -server. Selecione `Marcar para instalação` e depois `Aplicar` na barra de ferramentas superior. Você pode abrir o painel de Detalhes para ver o que está acontecendo durante a instalação. Selecione `Fechar` quando terminar.

Você pode testar para ver se o seu banco de dados está funcionando digitando `mysql` na linha de comando. Isso é o mesmo tanto para MySQL quanto para MariaDB. Você deve ver uma mensagem de erro `Acesso negado`, o que é aceitável, pois indica que a instalação do seu banco de dados está realmente funcionando.

## Instalar o phpMyAdmin

O phpMyAdmin é uma ferramenta de gerenciamento de banco de dados com interface gráfica que você precisará para criar e gerenciar seus bancos de dados. No Gerenciador de Pacotes Synaptic, procure por **phpmyadmin**. Selecione a caixa de seleção e marque `Marcar para Instalação`. Após o download, haverá um aviso para selecionar o `Servidor Web para reconfigurar automaticamente`. Selecione a caixa de seleção para `apache2` e, em seguida, o botão `Avançar`. Na próxima tela de configuração, deixe a caixa de seleção `Configurar banco de dados...` marcada e selecione `Avançar`.

Selecione uma senha de aplicativo para o usuário phpmyadmin. Teste: no seu navegador, digite localhost/phpmyadmin na barra de URL. Você deverá ver a tela de login do phpMyAdmin. Com o nome de usuário phpmyadmin e a senha que você inseriu durante a instalação, você poderá fazer login. Mas você não poderá criar nenhum banco de dados! Para resolver o problema, você precisa editar o arquivo de configuração como root na janela do Terminal:

```bash
sudo nano /etc/phpmyadmin/config.inc.php
```

Encontre as duas linhas contendo // $cfg['Servers'][$i]['AllowNoPassword'] = TRUE; e remova as barras iniciais para descomentá-las. Ambas!

Em seguida, faça login no mysql a partir da linha de comando e crie um novo usuário, concedendo a esse usuário todos os privilégios:
```bash
sudo mysql
CREATE USER 'admin'@'localhost' IDENTIFIED BY '';
GRANT ALL PRIVILEGES ON *.* TO 'admin'@'localhost' WITH GRANT OPTION;
exit
```

Depois, volte ao phpMyAdmin e tente fazer login com o nome de usuário **admin** e sem senha. Você deverá ver todos os bancos de dados e ser capaz de criar novos bancos de dados.

## Prioridade do Arquivo Índice

A localização padrão para páginas web no Ubuntu/Linux Mint é /var/www/html. 
Se você listar o conteúdo desse diretório, verá que ele contém o arquivo index.html, 
que contém o conteúdo da Página Padrão do Apache2 no Ubuntu. Crie um arquivo 
chamado index.php nesse diretório com o seguinte conteúdo:

```php
<?php echo phpinfo();
```
Recarregue o localhost. Não há mudança! Insira **localhost/index.php** na barra 
de URL e você verá uma página contendo as informações da versão do PHP. Esse 
comportamento é controlado pela configuração padrão do Apache, que pode ser 
alterada ativando o módulo `dir` do Apache e editando sua configuração:

```bash
sudo a2enmod dir
sudo nano /etc/apache2/mods-enabled/dir.conf
```

Mova o index.php para a frente da lista. Em seguida, reinicie o Apache:

```bash
sudo systemctl restart apache2
```

Desta vez, usando apenas **localhost** na barra de URL, você deve ver o 
conteúdo do arquivo index.php, uma página de Informações do PHP.

## Hosts Virtuais

Em uma instalação padrão do Linux, os arquivos do sistema estão na pasta raiz (/) e os arquivos de dados do usuário estão na pasta home (/home/meunomeusuario). Isso é potencialmente problemático porque o usuário padrão do Apache, www-data, pode não ter permissões apropriadas para criar arquivos no espaço de arquivos do usuário. A melhor solução é criar Hosts Virtuais.

Primeiro, é necessário um módulo que permita ao Apache mudar seu usuário e grupo para se adequar a cada usuário:

```bash
sudo apt-get install libapache2-mpm-itk
sudo a2enmod mpm_itk
```

Em seguida, faça uma cópia do arquivo de configuração do site padrão e edite-o:

```bash
cd /etc/apache2/sites-available
sudo cp 000-default.conf meunomeusuario.localhost.conf
sudo nano meunomeusuario.localhost.conf
```

O arquivo de configuração do site padrão contém comentários para explicar seu conteúdo. Eles são omitidos na ilustração abaixo. Descomente a linha ServerName e mude todas as instâncias de `meunomeusuario` para seu próprio nome de usuário.

```xml
<VirtualHost *:80>
        ServerName meunomeusuario.localhost
        ServerAdmin webmaster@localhost
        DocumentRoot /home/meunomeusuario/public_html
        <IfModule mpm_itk_module>
                AssignUserId meunomeusuario meunomeusuario
        </IfModule>
        <Directory /home/meunomeusuario/public_html/ >
                Options Indexes FollowSymLinks
                AllowOverride None
                Require all granted
        </Directory>
        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

Habilite o novo site e reinicie o Apache:

```bash
sudo a2ensite meunomeusuario.localhost
sudo systemctl reload apache
```

Faça uma entrada no arquivo /etc/hosts para adicionar uma entrada para o novo host virtual. Caso contrário, seu navegador procurará por ele na internet.

```bash
sudo nano /etc/hosts
```
Após concluir, ficará algo assim:

```bash
127.0.0.1       localhost
127.0.0.1       meunomeusuario.localhost
127.0.1.1       hostname

# As linhas seguintes são desejáveis para hosts com capacidade IPv6
::1     ip6-localhost ip6-loopback
fe00::0 ip6-localnet
ff00::0 ip6-mcastprefix
ff02::1 ip6-allnodes
ff02::2 ip6-allrouters
```
**Nome do host:** Este é o nome que você deu ao seu computador quando instalou o Linux. Você precisará dele em breve. Você pode alterá-lo se desejar - mas é melhor ler sobre isso primeiro e fazê-lo antes.

Se tudo correr bem, com uma URL do tipo meunomeusuario.localhost, você verá uma listagem de diretório do seu diretório public_html. A exibição pública de listagens de diretórios é considerada uma prática ruim, um risco de segurança, e geralmente é desativada por outra configuração do Apache. No entanto, para um site pessoal em um computador pessoal usado para desenvolvimento e teste, é muito útil. Muitos sites diferentes podem ser configurados em diferentes subdiretórios. Por exemplo, sites Joomla 4 e Joomla 5, fóruns de discussão, wikis e assim por diante. Quando você tem muitos sites de teste, é difícil lembrar de todos os nomes de subdiretórios!

## Acesso à Rede Doméstica

Se você tiver outro computador na sua rede doméstica, provavelmente gostaria de acessar seu site Linux a partir dele também. Para fazer isso funcionar, você precisa de outro host virtual. Copie e edite o que acabou de ser criado:

```bash
cd /etc/apache2/sites-available
sudo cp username.localhost.conf username.conf
sudo nano username.conf
```
Altere o ServerName de username.localhost para username.hostname e então habilite o novo site virtual e reinicie o Apache.

```bash
sudo a2ensite username
sudo apachectl restart
```
Vá para o seu outro computador na rede doméstica e edite o arquivo hosts pessoal dele. Por exemplo, em um Mac edite /private/etc/hosts e adicione a seguinte linha no final:

```bash
192.168.178.20 username.hostname www.username.hostname
```
Onde 192.168.178.20 é o endereço IP do seu computador Linux.

Agora, no seu segundo computador, você deve conseguir acessar o servidor web no seu computador Linux inserindo username.hostname na barra de URL do seu navegador.

## Notas de Partição

O software instalado usando o Gerenciador de Pacotes Synaptic geralmente está no diretório raiz do Linux (/). Os dados do usuário estão localizados no diretório home (/home). Em uma instalação simples, esses diretórios estão na mesma partição física do disco.

Em uma instalação mais complexa, talvez com a opção de inicializar diferentes sistemas operacionais (Windows ou Linux) ou diferentes versões do mesmo sistema operacional, os dados raiz e do usuário costumam estar em partições separadas. Isso permite o acesso aos mesmos dados do usuário a partir de cada sistema operacional.

Há um problema: um site Joomla localizado em um diretório /home/nome_de_usuário precisa de dados de banco de dados que geralmente estão no diretório raiz, especificamente em /var/lib/mysql. Você pode mover o diretório de dados do MySQL/MariaDB para um local disponível para ambos os sistemas operacionais, seja na partição /home ou em uma partição separada. Este tutorial descreve como mudar o Diretório de Dados do MySQL no Ubuntu e Debian Linux. Isso precisa ser feito para cada sistema operacional, mas não é abordado aqui.

*Traduzido por openai.com*

