<!-- Filename: Smart_Search_configuration_options / Display title: Opções de Busca Inteligente  -->

## Sobre Opções

As opções permitem que você gerencie as configurações globais da Pesquisa Inteligente. As configurações das Opções são herdadas pelas visualizações, mas as configurações em um Item de Menu substituirão as configurações Globais.

O painel de Opções é dividido em duas partes. Quando você terminar de fazer ajustes, selecione o botão Salvar, caso contrário, selecione o botão Cancelar para abandonar quaisquer alterações.

## Opções de Pesquisa

As opções de pesquisa controlam o comportamento dos formulários de busca e dos resultados de pesquisa para a interface do Finder.

- **Descrição do Resultado** - Esta opção controla se os resultados da pesquisa devem ser exibidos com descrições. O padrão é Mostrar.
- **Comprimento da Descrição** - Esta opção controla o comprimento máximo em caracteres das descrições dos resultados da pesquisa. As descrições são truncadas até o comprimento máximo, mas o truncamento é sempre feito no último caractere de espaço para não cortar uma palavra ao meio. Só é eficaz quando a opção Descrição do Resultado está configurada para Mostrar. O padrão é 255 caracteres.
- **URL do Resultado** - Esta opção controla se os resultados da pesquisa devem ser exibidos com URLs abaixo da descrição (se ativado). O padrão é Mostrar.
- **Pesquisa Avançada** - Esta opção controla se as opções de pesquisa avançada devem ser mostradas. O padrão é Mostrar.
- **Expandir Pesquisa Avançada** - As opções de pesquisa avançada estão contidas em um contêiner colapsável. Esta opção controla se o contêiner das opções de pesquisa avançada deve ser expandido por padrão. O padrão é Não.
- **Filtros de Data** - Esta opção controla se os filtros de data devem ser mostrados nas opções de pesquisa avançada. O padrão é Ocultar.
- **Rótulos de Resultado** - Esta opção controla se os resultados da pesquisa devem ser exibidos com Rótulos. Requer que os Rótulos JXtended estejam instalados. O padrão é Mostrar.
- **Destacar Termos de Pesquisa** - Esta opção controla se os termos de pesquisa devem ser destacados nos resultados da pesquisa. O padrão é Sim.

## Opções de Índice

As opções de índice controlam o comportamento do indexador usado para processar e analisar conteúdo para pesquisa. A maioria das configurações, como o multiplicador de peso e as opções de stemmer, não produzirão mudanças imediatas, pois são usadas durante a indexação e os efeitos de alterar essas configurações só serão vistos depois que o índice for esvaziado e executado novamente.

- **Tamanho do Lote do Indexador** - Esta opção controla o tamanho do lote do indexador. O indexador de Pesquisa Inteligente divide o processo total de indexação em vários lotes para reduzir a carga do servidor e evitar os limites de memória e tempo de execução do PHP. Se os itens de conteúdo sendo indexados forem particularmente curtos e/ou o servidor for particularmente rápido, o indexador pode processar mais itens por lote. No entanto, se os itens de conteúdo sendo indexados forem particularmente longos e/ou o servidor for particularmente lento, o indexador terá que processar menos itens por lote. Padrão é 50.
- **Limite da Tabela de Memória** - Esta opção controla o limite da tabela de memória. O indexador de Pesquisa Inteligente usa tabelas de memória MySQL para armazenar temporariamente dados de conteúdo ao invés de armazená-los nos buffers de memória do PHP, pois itens de conteúdo grandes esgotarão rapidamente as configurações padrão de limite de memória do PHP. No entanto, as tabelas de memória MySQL também têm limites de tamanho ajustáveis e reajustá-los não é confiável. Esta configuração é fornecida para lidar com tabelas de memória com limites de tamanho menores do que o usual e só deve ser ajustada ao encontrar erros de "Tabela Cheia" durante a indexação. Padrão é 30.000. Se você encontrar erros de "tabela cheia", tente **reduzir** este parâmetro. O valor ótimo deve resultar em tabelas de memória que são um pouco menores que o parâmetro <a href="http://dev.mysql.com/doc/refman/5.1/en/server-system-variables.html#sysvar_max_heap_table_size" rel="nofollow noreferrer noopener"><em>max_heap_table_size</em></a> no MySQL, que por padrão é de 16 megabytes.
- **Multiplicador de Peso do Texto do Título** - Esta opção controla quanto o texto do título influencia na pontuação de relevância geral de um resultado de pesquisa. Padrão é 1,7.
- **Multiplicador de Peso do Texto do Corpo** - Esta opção controla quanto o texto do corpo influencia na pontuação de relevância geral de um resultado de pesquisa. Padrão é 0,7.
- **Multiplicador de Peso dos Metadados** - Esta opção controla quanto o texto dos metadados influencia na pontuação de relevância geral de um resultado de pesquisa. Padrão é 1,2.
- **Multiplicador de Peso do Texto do Caminho** - Esta opção controla quanto o texto do caminho/URL influencia na pontuação de relevância geral de um resultado de pesquisa. Padrão é 2,0.
- **Multiplicador de Peso de Texto Diverso** - Esta opção controla quanto o texto diversificado influencia na pontuação de relevância geral de um resultado de pesquisa. Padrão é 0,3.
- **Stemmer** - Esta opção controla qual stemmer de idioma deve ser usado durante a indexação. O stemmer Somente em Inglês é uma implementação em PHP puro que não tem dependências. O stemmer Snowball requer a extensão PHP Stem, mas oferece suporte para 14 idiomas, incluindo Dinamarquês, Alemão, Inglês, Espanhol, Finlandês, Francês, Húngaro, Italiano, Norueguês, Holandês, Português, Romeno, Russo e Turco. Padrão é Somente em Inglês.
- **Habilitar Log** - cria um arquivo de log durante o processo de indexação. Padrão é não.

*Traduzido por openai.com*

