<!-- Filename: jdocmanual?manual=user&heading=system&filename=backup.md / Display title: Backup  -->

## Acidentes Acontecem!

Muito tempo, esforço e dinheiro são investidos na criação e manutenção de um
site. É uma pena perder tudo isso por causa de um acidente inesperado. O backup é fácil para sites médios. Sites grandes ou especializados provavelmente precisam de aconselhamento especializado.

## Estratégia de Backup

Os sites Joomla! consistem em duas partes:

* Os **arquivos** localizados na árvore de diretórios raiz do Joomla. Entre as atualizações, os arquivos podem não mudar muito, já que estão principalmente relacionados ao código. Novas imagens e documentos podem ser adicionados e, possivelmente, substituições de templates.
* O **banco de dados** que está localizado em algum lugar no servidor do host. O banco de dados contém a maior parte do conteúdo do site e pode mudar muito à medida que os usuários adicionam ou editam conteúdo.

Todo proprietário de site precisa de uma estratégia para recuperação do site em caso de desastre. O conselho comum nos Fóruns é **restaurar o último backup**. Portanto, decida o que fazer backup e com que frequência fazê-lo.

Os serviços de hospedagem frequentemente fazem **instantâneos** dos sites dos clientes e podem ser capazes de restaurar um site para sua condição de ontem, da semana passada ou do mês passado. Mas isso pode incluir tudo na conta, como e-mails e outros pacotes de software. Não confie nisso para recuperação de sites Joomla.

Este artigo descreve alguns métodos **gratuitos** comuns para fazer backup de sites Joomla. Você pode optar por pagar por ferramentas e/ou serviços de backup, mas isso não está coberto aqui.

## Akeeba Backup

Se você usar o menu do Administrador para navegar até **Sistema / Instalar Extensões / Instalar da Web**, o primeiro item na lista é o *Akeeba Backup*. Ele aparece primeiro na lista porque possui o maior número de avaliações positivas. Não é preciso dizer que tem uma longa história e uma reputação impecável. Existe uma versão gratuita e uma versão paga com alguns recursos extras. Esse é um modelo de negócios comum para desenvolvedores de Extensões. Não tenha receios! A versão gratuita é fácil de usar, não tem distrações e é suficiente para a maioria dos sites. O que ela faz:

* O Akeeba Backup analisa sua instalação para determinar as configurações ideais para criar um arquivo de backup.
* Ele faz um arquivo de backup composto que contém todos os arquivos do site e o conteúdo do banco de dados.
* Armazena backups carimbados com data e hora para gerenciar, baixar ou excluir conforme necessário.
* O download é um arquivo .jpa. Recomenda-se o uso de FTP para realizar o download.
* Existe um aplicativo separado, o Akeeba Kickstart, para descompactar o arquivo .jpa. Tudo isso é descrito na página Gerenciar Backups do Akeeba.
* Após a descompactação, o site é instalado com um instalador do Akeeba em uma sequência semelhante a uma instalação do Joomla.
* O instalador altera a configuração para restaurar em um local diferente e solicita os novos detalhes do banco de dados.

O único problema que pode ocorrer é que o arquivo de backup pode ser muito grande e você pode exceder a sua cota de espaço de arquivo se permitir que os backups se acumulem.

Experimente! Não custa nada e leva minutos em vez de horas.

## Ferramentas de Hospedagem

A maioria dos serviços de hospedagem oferece ferramentas de backup. Exemplo:

### cPanel

Na página de **Ferramentas**, o item *Arquivos* possui um link de *Backup*. A página de **Backup** tem três opções:

* **Backup Completo:** Um backup completo cria um arquivo com todos os arquivos e configurações do seu site. Você pode usar este arquivo para mover sua conta para outro servidor ou manter uma cópia local dos seus arquivos.
* **Backup Parcial**
  - Baixar um Backup do Diretório Home
  - Baixar um Backup de Banco de Dados (com uma lista de bancos de dados)

Há também opções para **Restaurar** cada um desses tipos de backup. Podem estar disponíveis opções para produzir backups automáticos.

Pastas individuais podem ser comprimidas em vários formatos adequados para download usando o Gerenciador de Arquivos do cPanel. Um banco de dados pode ser exportado usando o phpMyAdmin. Nenhum desses métodos é abordado aqui.

## Ferramentas Locais

Há ocasiões em que você pode precisar fazer o backup de um site localmente em um laptop ou computador desktop de escritório. Por exemplo, você pode querer copiar um site para/de um serviço de hospedagem para/de seu computador local. Se você tiver uma instalação local do Joomla, pode usar o Akeeba Backup conforme descrito acima. Caso contrário, você pode fazer backup do banco de dados e dos arquivos do Joomla separadamente.

### mysqldump

Se você estiver usando MySQL, é provável que tenha a ferramenta de linha de comando *mysqldump* disponível. Experimente este comando:

```bash
/usr/local/mysql/bin/mysqldump -u root -p dbname > ~/tmp/dbname-dump.sql
```
onde `root` é um usuário que tem acesso ao banco de dados e `dbname` é o nome do banco de dados que você deseja exportar. Você pode ser solicitado a inserir a senha.

Você também pode enviar o resultado para um comando zip ou gzip:

```bash
/usr/local/mysql/bin/mysqldump -u root -p dbname | gzip > ~/tmp/dbname-dump.sql.gz
```

### phpMyAdmin

Para fazer o mesmo trabalho com sua instalação local do phpMyAdmin, abra-o e selecione o banco de dados que você deseja exportar. Selecione o botão **Exportar** na parte superior da tela. Por padrão, a exportação *Rápida* usa SQL como formato de saída. Selecione o botão **Exportar** para tentar isso. Você será solicitado a indicar um arquivo de saída.

Se você selecionar a opção *Personalizada*, poderá escolher uma opção de Compressão de Saída, seja nenhuma, zipada ou gzipada. Experimente uma exportação comprimida e selecione o botão **Exportar**.

Você precisa **verificar** o banco de dados exportado. Crie um novo banco de dados, talvez `animporttest`, para que ele fique próximo ao topo da sua lista de bancos de dados. Com o novo banco de dados vazio selecionado, use o botão **Importar** na parte superior da tela. No formulário de importação, **Navegue** para encontrar o arquivo que você exportou e, em seguida, selecione o botão **Importar**.

Valeu a pena a **verificação**. A exportação gzip exportou apenas três tabelas. A exportação zip funcionou bem. Isso ficou evidente nos tamanhos dos arquivos exportados. O arquivo zip tinha 4Mb, mas o gzip tinha apenas 75Kb. Deve haver um bug em algum lugar!

### Zip e Gzip

Essas ferramentas de linha de comando são bastante onipresentes e muitas vezes são usadas a partir de interfaces gráficas. Por exemplo, no Finder do Mac, posso selecionar um diretório contendo um site Joomla, clicar com o botão direito e selecionar **Compactar**. Leva alguns segundos para fazer um arquivo zip e não afeta o original.

## Restaurando um Backup

Conselhos comuns dos Fóruns do Joomla:

* Não restaure um backup sobre um site com defeito.
* Esvazie seu banco de dados excluindo todas as tabelas ou crie um novo banco de dados e
atribua um usuário de banco de dados a ele.
* Exclua todos os diretórios e arquivos dentro do diretório raiz do seu Joomla.

## Akeeba Quickstart

Se você usou o Akeeba Backup, então utilize o Akeeba Quickstart para restaurar seu backup.
* Consulte o [Tutorial em Vídeo](http://akee.ba/abrestoreanywhere "").
* Baixe o Akeeba Quickstart (PDF 94Kb) gratuitamente.
* Verifique se o site restaurado está funcionando corretamente!

O Akeeba Quickstart restaura tanto o banco de dados quanto os arquivos do Joomla. Outros métodos restauram o banco de dados e os arquivos do Joomla separadamente.

## Restaurar o Banco de Dados

Se você tiver um backup do banco de dados, é melhor usar ferramentas do sistema para restaurá-lo. O *phpMyAdmin* consegue instalar bancos de dados de tamanho moderado, mas pode não ter tempo ou memória suficiente para bancos de dados grandes.

Se você está usando o cPanel em um serviço de hospedagem, pode importar um banco de dados pela página de *Backup / Restore*. Isso não é descrito aqui.

Se você tiver acesso à linha de comando, seja em um serviço de hospedagem ou no seu laptop ou computador de mesa local, pode usar o comando `mysql` para fazer a importação. Carregue o arquivo do banco de dados para um local temporário fora da sua árvore da web e expanda-o para que você tenha um nome de arquivo terminando em `.sql`. Em seguida, use o seguinte comando:
```
mysql -u dbusername -p -D dbname < db_dump_file.sql
```
Substitua `dbusername`, `dbname` e `db_dump_file.sql` pelos valores reais do seu site. Pode ser solicitado que você forneça uma senha de nome de usuário do banco de dados. Pode demorar um pouco, mas deve ser concluído.

## Restaurar os Arquivos

Trata-se de uma simples questão de expandir o arquivo compactado do seu último backup. Exceto que, às vezes, não é tão simples assim. Dependendo do seu sistema operacional e do método escolhido, os diretórios e arquivos arquivados podem aparecer todos no diretório atual ou em um novo diretório, ou você pode ser solicitado a indicar um diretório de destino. Até que você saiba o que seu sistema faz, pode ser melhor colocar o arquivo compactado em um diretório vazio, expandi-lo lá e depois mover o diretório para onde ele precisa estar.

Alguns usuários preferem usar SFTP para enviar arquivos para um serviço de hospedagem a partir dos arquivos extraídos localmente. Há milhares de arquivos, portanto, isso pode ser bastante demorado.

Na raiz do seu site, há um arquivo chamado `configuration.php`. Ele contém o nome do banco de dados e as credenciais de acesso. Verifique se eles estão corretos para o seu site restaurado. O arquivo tem permissões de acesso definidas para 444. Isso precisa ser alterado para 644 para que você possa salvar qualquer edição necessária.

Com tudo funcionando bem, seu site restaurado deve funcionar e estar no estado em que estava quando o backup foi feito.

## Copiando um Site

Existem várias boas razões para copiar um site inteiro de um servidor para outro. Por exemplo, os especialistas do Fórum muitas vezes recomendam que os usuários criem uma versão local de um site em um laptop ou computador de mesa para fins de teste, como experimentar novas extensões ou designs. Às vezes, uma pessoa decide mudar para um novo serviço de hospedagem por questões de custo ou desempenho.

Qualquer que seja o motivo, o processo é relativamente simples: faça um backup no site original e restaure-o no site de destino. Existem algumas questões a serem observadas:

* Certifique-se de que o host de destino atende aos Requisitos Técnicos Mínimos do Joomla. Isso geralmente significa versões de Servidor, PHP e Banco de Dados.
* Após a instalação, você pode descobrir que alguns módulos essenciais não foram habilitados. A maioria dos serviços de hospedagem resolve esses problemas mediante solicitação.

