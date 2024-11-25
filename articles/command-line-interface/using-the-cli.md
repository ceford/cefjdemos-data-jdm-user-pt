<!-- Filename: J4.x:Using_the_CLI / Display title: Usando a CLI -->

## A Interface de Linha de Comando (CLI)

Se você tiver acesso ao terminal do servidor que executa o seu site, poderá usar a CLI do Joomla para realizar tarefas rotineiras sem a necessidade de usar credenciais de login do Joomla. Mesmo sem acesso ao terminal, como em algumas contas de hospedagem compartilhada, é possível executar comandos CLI usando tarefas cron. Os comandos CLI costumam ser mais rápidos ou mais convenientes do que os equivalentes realizados através da interface do Administrador do Joomla (ou cPanel). Backup do site e alteração do estado do site entre offline/online são exemplos em que você poderia preferir usar a CLI.

O núcleo do Joomla possui cerca de 30 comandos úteis e você pode adicionar mais com extensões adicionais. Por exemplo, você poderia buscar dados externos, como Geolocalização ou dados de Taxa de Câmbio, para um componente personalizado.

## Usando a CLI

A CLI é utilizada invocando o executável do comando php na linha de comando. Isso é frequentemente diferente do que é usado por um servidor web, como o Apache. Se você estiver utilizando um cron job, pode ser necessário fornecer o caminho completo para o executável php, assim:

```bash
/usr/local/bin/php /home/username/public_html/[subpasta opcional]/cli/joomla.php
```

Caso contrário, ao usar a linha de comando do terminal, mude para o diretório cli do Joomla e comece a executar o comando sem parâmetros:

```bash
cd /home/username/public_html/[subpasta opcional]/cli
php joomla.php
```

![Lista de comandos](../../../en/images/command-line-interface/cli-command-list.png)

E experimente alguns comandos de ajuda para se familiarizar com o que esperar:

```bash
php joomla.php help
php joomla.php list
php joomla.php help cache:clean
php joomla.php help config:get
```

Cada uma das descrições de Ajuda e strings de uso estão hard-coded nos arquivos da biblioteca Console ou em plugins de terceiros.

Experimente alguns comandos de ação simples:

```bash
php joomla.php config:get debug
php joomla.php cache:clean
php joomla.php site:down
php joomla.php site:up
```

## Opções

Se você estiver chamando comandos a partir de um cron, talvez não deseje ver nenhuma saída:

    php joomla.php -q cache:clean

Note que as opções podem usar um espaço ou sinal de =, mas as variáveis devem usar um sinal de =:

    php joomla.php session:gc --application administrator
    php joomla.php session:gc --application=administrator

    php joomla.php config:set debug=true

## Comandos

Uma breve explicação de cada comando principal.

### Cache

Limpar entradas expiradas do cache do sistema:

    php joomla.php cache:clean --help
    php joomla.php cache:clean

![Resultado da limpeza do cache](../../../en/images/command-line-interface/cli-cache-clean.png)

    php joomla.php cache:clean expired

![Resultado da limpeza do cache expirado](../../../en/images/command-line-interface/cli-cache-clean-expired.png)

### Config

Obter ou definir uma variável de configuração, uma das variáveis em
configuration.php ou um grupo de variáveis. Grupos válidos são db, session,
mail,

    php joomla.php config:get debug --help
    php joomla.php config:get debug

![Resultado de config get debug](../../../en/images/command-line-interface/cli-get-debug.png)

    php joomla.php config:set debug=true

![Resultado de config set debug](../../../en/images/command-line-interface/cli-set-debug.png)

    php joomla.php config:get --group session

![Resultado de config get group session](../../../en/images/command-line-interface/cli-config-get-group-session.png)

### Core

Verifique atualizações ou atualize o Joomla.

    php joomla.php core:check-updates --help
    php joomla.php core:check-updates

![Resultado de core check updates](../../../en/images/command-line-interface/cli-check-updates.png)

    php joomla.php core:update --help
    php joomla.php core:update

![Resultado da atualização do core](../../../en/images/command-line-interface/cli-core-update.png)

### Banco de Dados

Exportar ou importar o banco de dados. Você pode exportar ou importar todas as tabelas ou uma
tabela selecionada. Não use este recurso para importar todas as tabelas de um
site multilíngue. Há um problema que pode impedir o funcionamento completo da Busca Inteligente.

    php joomla.php database:export --help
    php joomla.php database:export --table f4rc2_banners --folder /home/username/tmp/mydb (uma tabela)
    php joomla.php database:export --folder /home/username/tmp/mydb (todas as tabelas)

    php joomla.php database:import --help
    php joomla.php database:import --table /home/username/tmp/mydb/f4rc2_banners (uma tabela)
    [ERROR] O arquivo /home/username/tmp/mydb/f4rc2_banners.xml não existe.
    php joomla.php database:import --folder /home/username/tmp/mydb (todas as tabelas nesta pasta)

### Extensão

Listar, Descobrir, Instalar ou Remover extensões.

    php joomla.php extension:list --help
    php joomla.php extension:list
    php joomla.php extension:list --type component
    php joomla.php extension:list --type file
    php joomla.php extension:list --type language
    php joomla.php extension:list --type library
    php joomla.php extension:list --type module
    php joomla.php extension:list --type package
    php joomla.php extension:list --type plugin
    php joomla.php extension:list --type template

    php joomla.php extension:discover --help
    php joomla.php extension:discover
    php joomla.php extension:discover:list
    php joomla.php extension:discover:install --eid=

    php joomla.php extension:install --help
    php joomla.php extension:install --path=
    php joomla.php extension:install --url=

    php joomla.php extension:remove --help
    php joomla.php extension:remove

### Finder

Apaga e reconstrói o índice (os filtros de pesquisa são preservados).

    php joomla.php finder:index --help
    php joomla.php finder:index
    php joomla.php finder:index purge

![Resultado de purgação do índice finder](../../../en/images/command-line-interface/cli-finder-index-purge.png)

### Agendador

Listar, alterar estado ou executar tarefas agendadas.

    php joomla.php scheduler:list --help
    php joomla.php scheduler:list

    php joomla.php scheduler:state --help
    php joomla.php scheduler:state (prompt interativo para ID da tarefa)

    php joomla.php scheduler:run --help
    php joomla.php scheduler:run --id ID
    php joomla.php scheduler:run --all

### Sessão

Realizar coleta de lixo da sessão.

    php joomla.php session:gc --help
    php joomla.php session:gc
    php joomla.php session:gc --application administrator

    php joomla.php session:metadata:gc --help
    php joomla.php session:metadata:gc

### Site

Coloca o site offline ou online.

    php joomla.php site:down --help
    php joomla.php site:down

    php joomla.php site:up --help
    php joomla.php site:up

### Atualizar

Verifica atualizações de extensões pendentes. Remove arquivos antigos que deveriam
ter sido deletados durante uma atualização do Joomla

    php joomla.php update:extensions:check --help
    php joomla.php update:extensions:check

    php joomla.php update:joomla:remove-old-files --help
    php joomla.php update:joomla:remove-old-files

![Resultado da remoção de arquivos antigos do Joomla](../../../en/images/command-line-interface/cli-update-remove-old-files.png)

### Usuário

Listar e gerenciar usuários.

    php joomla.php user:list --help
    php joomla.php user:list

    php joomla.php user:add --help
    php joomla.php user:add --username cinderella --name Cinderella --email cinders@localhost --usergroup Manager (prompt para senha)
    php joomla.php user:add (prompts para dados)

![Resultado de adicionar usuário com prompts](../../../en/images/command-line-interface/cli-add-user.png)

    php joomla.php user:addtogroup --help
    php joomla.php user:addtogroup (prompts para dados)
    php joomla.php user:addtogroup --usernam=cinderella --group=Manager

    php joomla.php user:removefromgroup --help
    php joomla.php user:removefromgroup (prompts para dados)
    php joomla.php user:removefromgroup --usernam=cinderella --group=Manager

    php joomla.php user:reset-password --help
    php joomla.php user:reset-password (prompts para dados)
    php joomla.php user:reset-password --username=cinderella (prompts para senha)

    php joomla.php user:delete --help
    php joomla.php user:delete (prompts para nome de usuário)
    php joomla.php user:delete --username=cinderella (prompts para confirmação - y para confirmar)

*Traduzido por openai.com*

