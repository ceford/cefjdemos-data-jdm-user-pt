<!-- Filename: Setting_up_automatic_Smart_Search_indexing / Display title: Indexação de Pesquisa Inteligente  -->

## Indexação Automática

Embora o índice de Pesquisa Inteligente seja automaticamente mantido atualizado sempre que itens de conteúdo são alterados, há algumas circunstâncias em que é necessário executar novamente o indexador. Você pode fazer isso manualmente usando o botão de ferramenta Indexar na página Pesquisa Inteligente: Conteúdo Indexado. No entanto, se você precisar reindexar o conteúdo automaticamente, também é possível executar o indexador a partir da linha de comando. Isso torna particularmente conveniente executar o indexador a partir de um trabalho *cron*.

No diretório cli, o comando é:

```
php joomla.php finder:index
```

A saída típica do indexador de linha de comando é assim:

    INDEXADOR DE PESQUISA INTELIGENTE
    ============================

    Iniciando o Indexador
    Configurando plugins Finder
    Configurou 154 itens em 0,094 segundos.
     * Lote 1 processado em 0,213 segundos.
     * Lote 2 processado em 0,182 segundos.
     * Lote 3 processado em 0,177 segundos.
     * Lote 4 processado em 0,009 segundos.
    Tempo total de processamento: 0,676 segundos.

## Expurgando Antes da Indexação

Normalmente, executar o indexador fará uma atualização incremental do índice. Ou seja, ele atualizará apenas o índice para os itens de conteúdo que foram alterados desde a última atualização do índice. No entanto, se você precisar limpar completamente todas as entradas de índice existentes antes de reconstruir totalmente o índice, então você precisa realizar uma operação de "expurgo e depois indexação". Para fazer isso, você pode adicionar o argumento `--purge` à linha de comando, assim:

    php joomla.php finder:index --purge

Observe que isso tentará preservar quaisquer filtros estáticos que você possa ter configurado, enquanto clicar no botão "Purgar" na barra de ferramentas do Administrador **não** preservará seus filtros estáticos.

## Configurando um Trabalho *cron*

Embora os detalhes específicos estejam fora do escopo deste artigo, de modo geral, você apenas precisará inserir o comando acima no gerenciador de trabalhos *cron* e especificar a hora ou as horas em que o trabalho deverá ser executado. Provavelmente, você precisará incluir o caminho completo para o indexador. Por exemplo, assim:

```bash
php /var/www/myjoomla/cli/joomla.php finder:index -- purge
```

E possivelmente o caminho completo para o arquivo php, como `/usr/local/opt/php@8.2/bin/php`.

## Problemas de Falta de Memória

Se o seu site tiver requisitos de indexação particularmente complexos, é possível que a alocação de memória padrão não seja suficiente para que o indexador termine a execução. Você pode aumentar a memória alocada para o indexador de linha de comando usando um parâmetro extra na linha de comando, assim:

    php -d memory_limit=256M joomla.php finder:index

Substitua `256M` pelo valor apropriado para suas circunstâncias.

O indexador de linha de comando usa os mesmos parâmetros que o indexador na página de Pesquisa Inteligente: Conteúdo Indexado. Você pode alterar os parâmetros usando o botão da barra de ferramentas Opções nessa página. Note que tanto os campos **Tamanho do Lote do Indexador** quanto **Limite da Tabela de Memória** afetam a quantidade de memória usada pelo indexador.

*Traduzido por openai.com*

