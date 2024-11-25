<!-- Filename: Smart_Search_on_large_sites / Display title: Pesquisa Inteligente em Grandes Sites -->

## Indexação do Site

A Pesquisa Inteligente funciona criando e mantendo um índice independente de termos de pesquisa em uma série de tabelas do banco de dados. O problema para sites grandes é que o processo de indexação pode ser bastante pesado em termos de uso de CPU, memória e disco. Mesmo após a construção inicial do índice, as atualizações incrementais também podem ser pesadas. A boa notícia é que consultar o índice é uma operação relativamente rápida e leve.

A Pesquisa Inteligente é adequada para a maioria dos sites Joomla. No entanto, a pesquisa apresenta desafios particulares para sites grandes. É importante lembrar que a Pesquisa Inteligente é uma implementação pura em PHP de um mecanismo de busca, e sites particularmente grandes podem se beneficiar mais ao usar um mecanismo de busca independente, como o Solr.

Para usar a Pesquisa Inteligente em um site grande, você provavelmente precisará ajustar algumas das configurações. A seguir, é apresentada uma orientação geral sobre o que observar e o que tentar ajustar. Existem vários problemas pendentes conhecidos em relação à execução da Pesquisa Inteligente em sites grandes, que esperamos sejam resolvidos em versões futuras, e estes também são descritos aqui.

## Sempre Use o Indexador CLI

Como o processo inicial de indexação pode levar bastante tempo, é melhor executar o indexador pela linha de comando para evitar problemas de sessões do navegador expirando. O indexador CLI não expirará, independentemente de quanto tempo leve para completar, e pode ser facilmente interrompido se surgirem problemas. Além disso, mensagens de erro são visíveis com o indexador CLI, enquanto são ocultas quando executado a partir do Administrador.

Para usar o CLI, abra um terminal, mude para a pasta cli na raiz do seu site e digite o seguinte comando:

```
php joomla.php finder:index
```

## Agrupamento

O indexador divide o trabalho de indexação em lotes de itens de conteúdo. Por padrão, o tamanho do lote é definido como 30, o que significa que até 30 itens de conteúdo serão indexados por lote. Aumentar o tamanho do lote pode potencialmente tornar o processo de indexação mais rápido, mas utilizará mais memória e possivelmente mais espaço de armazenamento temporário em disco.

## Problemas de Falta de Memória

Se o indexador estiver ficando sem memória, tente fazer os seguintes ajustes, um de cada vez, até que o problema seja resolvido.

1. Diminua o tamanho do lote. Se você tiver itens de conteúdo particularmente grandes, o indexador pode ficar sem memória mesmo com um único item de conteúdo, então tente reduzir para 5 inicialmente e, se ainda estiver sem memória, reduza para 1.
2. Se você puder alocar mais memória para o indexador, faça isso. Você pode aumentar a memória alocada para o indexador de linha de comando usando um parâmetro extra na linha de comando. Por exemplo, para aumentar o limite de memória para 256Mb, use o comando a seguir, substituindo *256M* pela quantidade de memória que você pode alocar com segurança para um processo no seu sistema.<br>
   *php -d memory_limit=256M finder_indexer.php*
3. Reduza o limite da tabela de memória. O padrão é 30000 termos, o que significa que assim que a tabela temporária na memória *#__finder_tokens* atingir esse número de linhas, o indexador mudará para usar uma tabela de disco em vez de uma tabela de memória. Pode ser que você não tenha memória suficiente para lidar com uma tabela de memória completa ou quase completa, então reduzir o limite fará com que o indexador mude para disco mais cedo e use menos memória. Tente 10000 ou até mesmo números muito menores.
4. Altere o mecanismo de banco de dados usado para as tabelas *__finder_tokens* e *#__finder_tokens_aggregate* de MEMORY para InnoDB. Isso pode impactar seriamente o desempenho, pois mais do processo de indexação usará o disco em vez da memória, mas pode permitir que o indexador termine sem ficar sem memória. Espere que o processo de indexação demore muito mais. No entanto, isso não afetará o desempenho da pesquisa.
5. Tente identificar quais itens de conteúdo estão causando a falta de memória no indexador. Se não for óbvio, você pode tentar desativar todos os plugins de Pesquisa Inteligente, exceto um. Executar o indexador com apenas um plugin ativado por vez deve revelar quais tipos de conteúdo estão causando o problema. Como último recurso, considere dividir alguns itens de conteúdo excepcionalmente grandes em itens separados. Se o problema for com um tipo de conteúdo personalizado, olhe o código do plugin e considere indexar menos do conteúdo disponível por item.

## Problemas de Falta de Espaço em Disco

As tabelas de índice do Smart Search podem crescer rapidamente! As tabelas *__finder_links_termsX* (onde *X* é um único caractere hexadecimal) contêm uma linha por termo/frase por item de conteúdo, e um único artigo do Joomla contendo 1000 palavras normalmente resultará em aproximadamente 3000 linhas sendo adicionadas a essas tabelas. Um segundo artigo de tamanho similar adicionará um número semelhante de linhas, mesmo que ambos os artigos contenham as mesmas palavras. Um site com dezenas de milhares de artigos, alguns dos quais podem conter milhares de palavras, provavelmente acabará com essas tabelas de mapeamento contendo milhões de linhas. Não é incomum que as tabelas de índice ocupem vários gigabytes de espaço em disco em tais circunstâncias.

Com a versão atual do Smart Search, não há muito o que você possa fazer a respeito. No entanto, espera-se que na próxima versão você possa ajustar o número de palavras por frase que são indexadas. Atualmente, isso está fixo em 3, o que significa que cada palavra indexada também é indexada como parte de um par de palavras adjacentes e como parte de um trio de palavras adjacentes. Isso é útil para o recurso de auto-completar e geralmente melhora a qualidade dos resultados de pesquisa. Em sites onde o espaço em disco é um problema, seria bom reduzir isso para 2 ou até mesmo 1, de modo que as tabelas de mapeamento fossem correspondentemente menores.

## Notas

1. Atualmente, não há bloqueio de concorrência para impedir que mais de um processo execute o indexador ao mesmo tempo. Isso quase certamente resultará em um índice corrompido. Até mesmo alguém salvando alterações em um item de conteúdo enquanto um índice completo está sendo realizado poderia potencialmente danificar o índice.

*Traduzido por openai.com*

