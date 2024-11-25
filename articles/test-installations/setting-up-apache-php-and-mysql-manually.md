<!-- Filename: Setting_up_Apache,_PHP_and_MySQL_manually / Display title: Configuração manual do Apache, PHP e MySQL -->

## Visão Geral

Aqui está uma breve visão geral dos passos para configurar Apache, PHP e MySQL em um ambiente Windows e também referir-se a várias ferramentas relacionadas para manter e trabalhar com a maioria das tarefas relacionadas ao Joomla!.

Para tornar a instrução clara e sucinta, assumiremos que, sempre que não estivermos afirmando uma instrução explícita, você deixará os caminhos de configuração padrão se aplicarem sem modificação.

### Aviso

Se você já tiver algum dos pacotes pré-instalados de AMP em sua máquina:

- Voltar para o seu pacote AMP será difícil. As várias instalações que faremos abaixo substituirão valores de registro e farão mudanças gerais no ambiente. (Isso se aplica pelo menos ao ambiente PC/Windows.)
- Se você precisar manter qualquer configuração (Apache, MySQL ou PHP) ou dados (seus sites existentes e bancos de dados relacionados), antes de tentar seguir esta instrução, faça backups adequados.

(precisa ser expandido com conselhos específicos sobre como alcançar o acima...)

## Configuração do MySQL

1. Baixe o <a href="https://dev.mysql.com/downloads/mysql/"
    rel="nofollow noreferrer noopener">instalador do MySQL</a> apropriado para a sua plataforma.
2. Inicie a instalação e escolha o caminho de instalação personalizado.
3. Prossiga por todo o processo de instalação e clique em Concluir.
4. Agora será apresentado o *Assistente de Configuração da Instância do MySQL Server*.
    1. Certifique-se de que a *Configuração Padrão* está selecionada e vá para Próximo.
    2. Se você já tiver o MySQL instalado, pode receber a mensagem *Um serviço do Windows com o nome MySQL já existe. Por favor, desinstale esse serviço corretamente ou escolha um nome diferente para o novo serviço.* Se sim, escolha um nome alternativo para o serviço.
    3. Na próxima janela, marque a opção *Incluir Diretório Binário no PATH do Windows*. Ao fazer isso, você poderá acessar várias utilidades do MySQL pela linha de comando.
    4. Na próxima janela, você poderá criar uma senha para seu usuário root do MySQL, o usuário com o maior nível de acesso no seu servidor.
    5. Na janela final, todas as mudanças que você configurou até agora serão salvas quando você pressionar o botão *Executar* e o serviço do Windows para essa instância será iniciado.

### Notas

1. Para tornar a instrução o mais acessível possível, pulamos vários cenários de configuração da sua instância do MySQL, como a capacidade de realocar seus arquivos de banco de dados.
2. O MySQL é instalado por padrão com um modo STRICT, que pode causar alguns erros ao usar extensões ou aplicativos que não consideraram isso.

### Recursos do MySQL

- <a href="https://www.heidisql.com/" class="external text"
   rel="nofollow noreferrer noopener">HeidiSQL</a> Uma
  substituição de cliente completo e fácil de usar e extensível do phpMyAdmin em desenvolvimento constante.
- <a href="https://dev.mysql.com/downloads/workbench/"
  class="external text"
  rel="nofollow noreferrer noopener">MySQL Workbench</a> Várias ferramentas, entre as quais você apreciará o Administrador, que o ajuda a configurar sua instância MySQL. Requer o
  <a href="https://dotnet.microsoft.com/en-us/" class="external text"
   rel="nofollow noreferrer noopener">.Net framework</a>.
- <a href="https://www.phpmyadmin.net/" class="external text"
   rel="nofollow noreferrer noopener">phpMyAdmin</a> Um
  poderoso cliente MySQL baseado na web para administrar qualquer coisa relacionada ao MySQL.
- <a href="https://dev.mysql.com/doc/" class="external text"
   rel="nofollow noreferrer noopener">Documentação do MySQL</a>

## Configuração do Apache

1. <a href="https://httpd.apache.org/download.cgi" class="external text" rel="nofollow noreferrer noopener">Baixe o instalador</a> de sua preferência.
2. Execute o assistente de instalação e avance em cada etapa até chegar à janela de Informações do Servidor. Forneça as opções abaixo, respectivamente, e na ordem dada em cada um dos campos, a menos que você tenha algum requisito específico sobre como seu servidor web deve ser configurado:
    1. localhost,
    2. localhost e
    3. admin@localhost
3. Continue no assistente, que instalará e iniciará o servidor web Apache como um serviço do Windows.
4. Na barra de status do Windows, você verá agora uma pena colorida de rosa com um botão de reprodução verde, indicando que o Apache está funcionando. Aponte seu navegador para <a href="http://localhost/" rel="nofollow noreferrer noopener">http://localhost/</a> e você deverá ver uma página indicando que está funcionando.
5. Vamos agora ao local onde o Apache está instalado, que geralmente fica em *C:\Program Files\Apache Software Foundation\Apache2.2*, e explore os vários diretórios:
    1. *bin* - contém vários arquivos binários, alguns dos quais estão listados abaixo. Para acessar esses aplicativos, na maioria baseados em comando, precisaríamos adicionar o caminho para o diretório *bin* na nossa variável de PATH global. Para fazer isso, clique com o botão direito em Meu Computador \> Propriedades \> Avançado \> Variáveis de Ambiente e, na lista de Variáveis do Sistema, localize e selecione a Variável PATH, clique em Editar e adicione um ponto e vírgula ao final. Se não estiver lá, adicione o caminho absoluto para o seu diretório bin. Saia da caixa de diálogo Propriedades do Sistema aceitando.
        1. *httpd.exe* que é o próprio servidor web Apache, que é dividido em vários processos filhos enquanto atende a muitas solicitações simultâneas de clientes que forem necessárias pela diretiva MaxClients;
        2. *ab.exe* é uma ferramenta de benchmarking que vem com o Apache, permitindo que você veja o quão bem sua aplicação pode desempenhar por unidade de tempo.
    2. *conf* - pasta onde estão localizados vários arquivos de configuração, dos quais os seguintes são de maior interesse para o nosso caso:
        1. *httpd.conf* - a maioria das diretivas do servidor estão localizadas neste arquivo, e para fácil acesso, você deve associar o tipo de arquivo *.conf* a um editor amigável, ou seja, qualquer um que não seja o Bloco de Notas padrão.
        2. *extra\httpd-vhosts.conf* - contém diretivas que permitiriam usar seu servidor local como um host virtual, ou seja, capaz de executar vários servidores no seu PC. Um cenário de uso é que, durante a fase de desenvolvimento, se você quiser mapear o domínio real para o qual está trabalhando na sua cópia local, você poderá fazer isso com pequenas alterações neste arquivo. Vamos discutir isto em mais detalhe abaixo.
    3. *htdocs* - a raiz padrão do servidor web, é onde <a href="http://localhost/" rel="nofollow noreferrer noopener">http://localhost/</a> é mapeado, ou seja, se você não o reconfigurar em *httpd.conf* acima.
    4. *logs* - logs de acesso e de erro, usadas ao tentar resolver vários problemas relacionados ao seu servidor ou até mesmo ao seu aplicativo.

### Recursos do Apache

- A <a href="https://httpd.apache.org/docs/current/" class="external text" rel="nofollow noreferrer noopener">documentação de referência do Apache</a>

## Configuração do PHP

1.  <a href="https://windows.php.net/download/" class="external text"
     rel="nofollow noreferrer noopener">Baixe o PHP</a>
    e escolha comumente VC6 x86 Thread Safe em formato Zip. As várias
    opções têm a ver com a forma como o código base do PHP foi compilado
    para binário e provavelmente nada com que você deva se preocupar
    agora.
2.  Crie uma pasta em C:\Program Files\\ (ou onde quer que esteja
    localizada a sua pasta de programas) chamada PHP.
3.  Localize seu arquivo Zip baixado e mova-o para a pasta recém-criada
    e descompacte-o diretamente na pasta.
4.  Agora, vamos adicionar o caminho do PHP à nossa variável PATH global
    seguindo a instrução acima.

### Configurando o PHP

A configuração consiste em editar o arquivo *php.ini*. Um arquivo de
exemplo para diferentes cenários já está na sua pasta PHP. Vamos renomear
*php.ini-development* para *php.ini* e abri-lo no seu editor de texto
favorito. Os valores comuns a ajustar são os seguintes, e todas essas
variáveis estão bem documentadas no arquivo *php.ini*. (Note que esta é
uma configuração de servidor global que se aplica a todos os seus
projetos):

- *max_execution_time* - sempre que você tiver scripts que executem por
  muito tempo e o servidor retornar vários resultados inesperados que
  você acha que são devidos ao fato de não conseguir completar
  todo o processo
- *memory_limit*
- *error_reporting*
- *display_errors*
- *log_errors* - uma variável que você precisaria levar em conta em
  cenários de produção
- *upload_tmp_dir*
- *upload_max_filesize*
- *extension_dir* - para evitar complicações, vamos indicar
  o diretório onde as seguintes extensões estão localizadas, descomentando
  esta variável e atribuindo a localização absoluta da pasta. A linha
  completa deve ser assim:
    extension_dir = "C:\Program Files\PHP\ext"

- A seção de extensões dinâmicas contém vários módulos adicionais que
  você pode querer carregar, e as comentadas são aquelas que vêm
  pré-empacotadas com o PHP e podem ser encontradas no diretório *ext* na
  sua pasta PHP. Se você quiser ativar alguma, remova o comentário como
  deve fazer com as seguintes extensões:
  - php_curl.dll
  - php_gd2.dll
  - php_mbstring.dll
  - php_mysql.dll
  - php_mysqli.dll
  - php_pdo.dll
  - php_pdo_mysql.dll
  - php_xsl.dll
- session.save_path

### Configurando o Apache para Trabalhar com o PHP

Agora que configuramos o PHP para funcionar como queremos, vamos fazer o
mesmo com o Apache.

- Abra o *httpd.conf* e na seção "Dynamic Shared Object (DSO) Support"
  adicione as seguintes diretivas. (Se você localizou sua pasta PHP de
  forma diferente, altere o php5apache2_2.dll abaixo
  correspondentemente):
    LoadModule php5_module "C:/Program Files/PHP/php5apache2_2.dll"
    AddType application/x-httpd-php .php

- No DirectoryIndex, adicione *index.php* e *index.htm* como arquivos
  possíveis para servir quando o diretório for solicitado, como segue:
    DirectoryIndex index.html index.htm index.php

- No final do arquivo, adicione a seguinte linha, que indicará onde o
  arquivo *php.ini* está localizado:
    PHPIniDir "C:/Program Files/PHP"

### Reinicie e Teste o PHP

Assim que você fizer qualquer alteração no *php.ini*, *httpd.conf* ou
qualquer outro arquivo de configuração, será necessário reiniciar o
Apache para ver o efeito das alterações. Então, vamos reiniciar o Apache
usando a ferramenta Apache Monitor que você pode encontrar na barra de
status do Windows. Esperançosamente, não aparecerão diálogos e o Apache
Monitor continuará a funcionar em verde.

Agora vamos testar se o PHP está funcionando. Vá para a raiz de documentos
do seu servidor web (no caso padrão *C:\Program Files\Apache Software
Foundation\Apache2.2\htdocs*) e adicione um arquivo chamado
*phpinfo.php* com o seguinte conteúdo:

```php
<?php
phpinfo();
?>
```

Isso renderizará uma página contendo informações sobre a configuração do
seu PHP e sobre os vários módulos/extensões que estão atualmente
carregados. Aponte o seu navegador para
<a href="http://localhost/phpinfo.php"
rel="nofollow noreferrer noopener">http://localhost/phpinfo.php</a>.

### Instalando e Configurando *xdebug*

1.  Aponte seu navegador para
    <a href="https://xdebug.org/wizard" class="external text"
     rel="nofollow noreferrer noopener">Assistente de Instalação do
    Xdebug</a>. Esta página o ajudará a encontrar uma versão adequada do
    Xdebug.
2.  Copie toda a página do *phpinfo* que executamos acima e cole na área
    de texto e siga as instruções fornecidas para instalar.

### Recursos do XDebug

- O <a href="https://www.php.net/docs.php" class="external text"
   rel="nofollow noreferrer noopener">Manual do PHP</a>
  possui documentação excelente e atualizada com comentários adicionais
  valiosos dos usuários. Versões para download estão disponíveis.
- A
  <a href="https://xdebug.org/docs/" class="external text"
  rel="nofollow noreferrer noopener">Documentação do Xdebug 3</a>

*Traduzido por openai.com*

