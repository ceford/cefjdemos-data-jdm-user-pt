<!-- Filename: Purging_expired_cache_files / Display title: Limpar Cache Expirado  -->

## Arquivos de Cache

Arquivos de cache são arquivos temporários criados para melhorar o desempenho do seu site. Você precisa garantir que os arquivos de cache que expiraram, e que portanto não são mais necessários, sejam removidos do sistema. Caso contrário, você eventualmente ficará sem espaço em disco.

Arquivos de cache expirados podem ser removidos através da interface do Administrador ou da interface de Linha de Comando (CLI).

## Método de Purgar - Administrador

No *Painel Principal*
* Selecione a opção **Cache** no painel do *Sistema*.
* Na página *Manutenção: Limpar Cache*, selecione o botão **Limpar Cache Expirado** na Barra de Ferramentas.

## Purge - Método da Linha de Comando

Abra uma janela de terminal e navegue até o diretório cli na raiz do seu site.  
Se você não souber quais comandos CLI estão disponíveis, emita o seguinte comando:
```bash
php joomla.php
```
Você verá uma lista de comandos disponíveis. O comando `cache` é:
```bash
php joomla.php cache:clean
```
Deverá haver uma mensagem de confirmação verde ou, possivelmente, uma mensagem de erro marrom.  

## Exclusão Automática de Arquivos de Cache Expirados

Você pode excluir automaticamente arquivos de cache expirados usando um cron job. Serviços de hospedagem facilitam isso, fornecendo um formulário para selecionar a frequência com que um trabalho é executado e o comando a ser usado. Portanto, você pode optar por definir o cron para executar às 05:00 todos os dias com o seguinte comando:
```
 /usr/local/bin/ea-php82 /home/username/public_html/cli/joomla.php cache:clean
 ```
A maioria dos gerenciadores de tarefas *cron* permite que você insira um endereço de e-mail para o qual a saída do cron será enviada. Se você não quiser que uma mensagem seja enviada, adicione ` > /dev/null 2>&1` ao comando.

A versão do PHP usada na linha de comando geralmente é diferente da usada para a entrega de um site. Ela pode ser incompatível com o Joomla. Portanto, use o caminho completo para a versão do PHP que você deseja usar em vez de `php` sozinho.

*Traduzido por openai.com*  

