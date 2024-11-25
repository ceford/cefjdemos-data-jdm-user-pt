<!-- Filename: J4.x:CLI_Database_Exporter_Importer / Display title: Exportação e Importação de Banco de Dados via CLI -->

## Introdução

Antes de atualizar o Joomla! ou instalar uma extensão de terceiros, é fortemente recomendado que você faça backup do seu site. A interface de linha de comando (CLI) do Joomla! fornece comandos para exportar (fazer backup) e importar (restaurar) o seu banco de dados do Joomla!. Note que ela não faz backup do seu sistema de arquivos, o que deve ser feito separadamente.

## Requisitos

Para usar esses comandos, você precisa de acesso ao terminal do host no qual o site está instalado. Isso pode ser um problema em hospedagens compartilhadas! Você também precisa de conhecimento básico de comandos do shell do Linux, como ls e cd. Se tudo isso for desconhecido para você, é recomendável usar o Akeeba Backup, a extensão de backup e restauração mais popular, e gratuita para uso básico.

## Local de Armazenamento Temporário de Backup

Tenha cuidado ao escolher um local de armazenamento para um backup. Ele deve estar dentro do seu espaço pessoal de arquivos, mas fora da sua árvore web. O objetivo é criar um arquivo de backup que você possa baixar para o seu computador local ou outro lugar seguro, após o qual você pode excluir o arquivo de backup para economizar espaço. Além disso, tenha cuidado para não usar a pasta /tmp do sistema, que pode ser lida por qualquer usuário. O melhor local é sua pasta tmp pessoal. A disposição da árvore de pastas:
```
|-/home/username/tmp - sua pasta tmp pessoal
|-/home/username/public_html - sua pasta raiz do Joomla
```

## Instruções

Faça login no seu host e acesse a pasta raiz do seu site.
```
cd /home/username/public_html
```

- Liste todos os comandos CLI disponíveis:
```sh
  php cli/joomla.php list
```
- Exporte o banco de dados para a pasta tmp da conta:
```sh
  php cli/joomla.php database:export --folder /home/username/tmp/mydbname
```
- Importe o banco de dados da pasta:
```sh
php cli/joomla.php database:import --folder /home/username/tmp/mydbname
```

Você também pode:

- Exportar o banco de dados como um arquivo .zip:
```sh
php cli/joomla.php database:export --zip --folder /home/username/tmp/mydbname
```
- Exportar uma tabela:
```sh
php cli/joomla.php database:export --table xxxxx_action_log_config --folder /home/username/tmp/mydbname
```
- Exportar uma tabela como um arquivo .zip:
```sh
php cli/joomla.php database:export --table xxxxx_action_log_config --zip --folder /home/username/tmp/mydbname
```
- Importar uma tabela:
```sh
php cli/joomla.php database:import --table xxxxx_action_log_config --folder /home/username/tmp/mydbname
```
- Se você precisar de ajuda:
```sh
php cli/joomla.php database:export --help
php cli/joomla.php database:import --help
```

## Backup

Para fazer um backup completo de pastas, arquivos e do banco de dados, execute estes comandos:

1. Arquive o diretório raiz do Joomla:
```sh
tar --exclude='/home/username/public_html/tmp' -zcvf /home/username/tmp/joomla_bak.tgz /home/username/public_html > /home/username/tmp/joomla_bak.log
```
2. Exporte todo o banco de dados do Joomla a partir da pasta raiz do Joomla:
```sh
php cli/joomla.php database:export --folder /home/username/tmp/db_bak
```

## Restaurar

E para restaurá-lo, primeiro certifique-se de que o banco de dados e o usuário do banco de dados existam. Em seguida, execute estes comandos:

1. Extraia o arquivo:
```sh
tar -xvf /home/username/tmp/joomla_bak.tgz --directory /home/username/public_html
```
2. Certifique-se de estar na raiz do seu site:
```sh
cd /home/username/public_html
```
3. Importe o banco de dados do Joomla:
```sh
php cli/joomla.php database:import --folder /home/username/tmp/db_bak
```

## Notas

Nas opções do comando tar -zcvf e -xvf, o v representa verbose - uma lista de
arquivos processados é exibida rapidamente na tela do terminal. Deixe o v de fora para
não ver a lista.  
*Traduzido por openai.com*  

