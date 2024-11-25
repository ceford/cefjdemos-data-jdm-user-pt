<!-- Filename: Smart_Search_Frequently_Asked_Questions / Display title: Perguntas Frequentes sobre Pesquisa Inteligente  -->

## Por que devo usar a Pesquisa Inteligente?

A tecnologia de busca melhorou consideravelmente ao longo dos anos desde que o Joomla foi lançado pela primeira vez e, no entanto, o componente de busca padrão e básico não mudou muito durante esse tempo. Ele ainda é muito rudimentar e carece do tipo de recursos de busca que os usuários da web passaram a esperar, especialmente considerando a prevalência de motores de busca avançados como o Google. A Pesquisa Inteligente permite que você incorpore alguns desses recursos de busca mais avançados ao seu site.

## Por que Criar um Plugin de Pesquisa Inteligente?

Em geral, se você possui um tipo de conteúdo que não é gerenciado pelos componentes principais do Joomla, e deseja oferecer aos visitantes do seu site a oportunidade de pesquisar esse conteúdo, será necessário escrever um Plugin de Pesquisa Inteligente para suportá-lo. Por exemplo, suponha que você tenha um componente que armazena informações sobre diferentes espécies de animais. O componente mantém uma tabela de banco de dados contendo campos como nome científico, nome vernáculo, classificação e uma descrição. Então, você precisará criar um Plugin que informe ao indexador de Pesquisa Inteligente como indexar os dados naquela tabela. Além de indexar palavras e frases individuais, você também pode fazer com que o Plugin adicione cada registro a um mapa de conteúdo, que pode incluir, neste caso, as <a href="https://en.wikipedia.org/wiki/Taxonomy_(biology)" rel="nofollow noreferrer noopener">classificações biológicas de reino, filo, classe, ordem e família</a>. Mapas de conteúdo podem então ser usados para filtrar os resultados de pesquisa.

## É possível selecionar múltiplos nós nos filtros suspensos?

Sim, isso é totalmente suportado pelo próprio Smart Search. Na verdade, você pode usar qualquer interface de usuário que desejar para os filtros. Basta dar uma olhada no código fornecido no módulo e componente padrão do Frontend e você verá como precisa fazer isso.

## Eu Tenho um Site Grande. Posso Usar a Pesquisa Inteligente?

Sites grandes podem se beneficiar mais de um mecanismo de busca dedicado e independente, como o Solr, em vez da implementação pura em PHP usada na Pesquisa Inteligente. Nesta primeira iteração da pesquisa avançada no Joomla, é provável que questões relacionadas à escalabilidade e desempenho sejam reveladas. Também há o potencial para a ocorrência de condições de corrida ao atualizar o índice com mudanças frequentes de conteúdo. Espera-se que essas questões sejam abordadas de forma mais completa em uma versão futura do Joomla.

## Por que a Pesquisa Inteligente tem Tantas Tabelas?

A Pesquisa Inteligente adiciona várias novas tabelas a uma instalação do Joomla, incluindo 16 "tabelas de mapeamento". Estas tabelas de mapeamento resolvem a relação muitos-para-muitos entre os termos de busca e os itens de conteúdo que os contêm. Em teoria, essas 16 tabelas poderiam ser mescladas em uma única tabela e isso teria um impacto praticamente nulo em sites pequenos. No entanto, em sites maiores, haveria um impacto substancial no desempenho, pois a tabela de mapeamento teria um número muito grande de entradas, e atualizar uma tabela tão grande pode ser demorado.

## Por que a Pesquisa Inteligente Usa Tanto Espaço em Disco?

Manter um índice de termos de pesquisa requer uma quantidade considerável de espaço em disco, que aumenta conforme o número de termos que os itens de conteúdo contêm. Como frases também são indexadas, quanto mais longas as frases, mais espaço em disco é necessário. Para a Pesquisa Inteligente no Joomla 2.5, o comprimento máximo de uma frase foi fixado em 3 termos como um compromisso razoável entre a usabilidade de pesquisa e o uso de espaço em disco. É provável que este seja um parâmetro que possa ser ajustado em uma versão futura da Pesquisa Inteligente.

## Por que as entradas nas tabelas de mapeamento não são distribuídas uniformemente?

Talvez seja surpreendente que o número de entradas em cada uma das tabelas de mapeamento não seja nem mesmo aproximadamente o mesmo. Certamente, o desempenho seria melhor com uma distribuição uniforme? Na verdade, não. Há um equilíbrio entre o desempenho de inserção e o desempenho de busca, sendo que a distribuição uniforme é boa para o primeiro, mas ruim para o segundo. Esta é uma área de pesquisa contínua, com o número de tabelas e o algoritmo de distribuição sujeitos a mudanças à luz da experiência.

## Por que existe um plugin separado para Conteúdo de Pesquisa Inteligente?

Isto é apenas uma conveniência que facilita a ativação ou desativação de todos os Plugins de Pesquisa Inteligente com uma única operação. Isso foi considerado desejável porque a Pesquisa Inteligente não é ativada por padrão no Joomla 2.5.

## Por que os plugins de pesquisa inteligente usam eventos separados como *onFinderContentAfterSave*?

A Pesquisa Inteligente utiliza seus próprios eventos, como onFinderContentAfterSave, em vez do equivalente genérico onContentAfterSave, puramente por conveniência, para facilitar a ativação ou desativação da indexação da Pesquisa Inteligente por meio da ativação/desativação de um único plugin.  

## Por que a Pesquisa Inteligente não está habilitada por padrão no Joomla 2.5 e Joomla 3.x?

Como o Joomla 2.5 é o último da série 1.x/2.x, ele deve manter um alto grau de compatibilidade retroativa com a versão anterior da série. Como a Pesquisa Inteligente é algo totalmente novo e não tem semelhança com o componente de pesquisa regular desta ou de versões anteriores, considerou-se importante que os usuários que atualizam dessas versões anteriores não fossem obrigados a mudar a forma como a pesquisa funciona em seus sites. De fato, a ativação da Pesquisa Inteligente é algo que deve ser feito de maneira cuidadosamente planejada.

## Por que Não Existe uma API de Pesquisa?

O foco da versão atual do Smart Search foi transferir o código do antigo componente JXtended Finder para a versão mais recente do Joomla. Como esse código já era considerado estável e havia apenas uma pequena janela de oportunidade para portar o código, considerou-se que um grande redesenvolvimento do Finder estava fora do escopo para o lançamento do Joomla 2.5. Consequentemente, o código utiliza Plugins para evitar quaisquer alterações ao código central do CMS, em vez de desenvolver uma API de pesquisa apropriada. Estamos planejando criar tal API para uma futura iteração do Joomla.

## A Pesquisa Inteligente Pode Fazer Pesquisa Facetada?

Sim. A pesquisa avançada disponível na página de resultados de pesquisa e o módulo de pesquisa inteligente fornecem um exemplo de como você pode filtrar os resultados de pesquisa para produzir uma pesquisa facetada. Não há nada que impeça você de criar suas próprias variações sobre essas ideias básicas. Por exemplo, você pode alterar os menus suspensos simples para aceitar seleções múltiplas, ou pode substituir os menus suspensos por uma série de caixas de seleção.  

## Por que as Buscas com Curingas Não São Suportadas?

A antiga busca do Joomla usava um método muito primitivo de pesquisa que
dependia da busca FULLTEXT fornecida pelo banco de dados. Isso era muito
ineficiente, mas oferecia um meio simples de lidar com consultas de busca
com curingas. A Busca Inteligente oferece um recurso de autocompletar que é
efetivamente uma busca com curingas dos termos no índice, mas a busca completa
com curingas não é suportada devido ao potencial de sobrecarga do servidor
caso o recurso fosse abusado. Na maioria dos casos, a busca com curingas é
usada para abordar variações em um termo de busca. Por exemplo, buscar por
*malabar\** para encontrar referências a *malabarismo* assim como
*malabarista*. A Busca Inteligente tenta evitar a necessidade de busca com
curingas, oferecendo em vez disso o suporte à radicalização de palavras, onde
palavras que têm o mesmo radical são consideradas equivalentes, de forma que
buscar por *malabarista* também recupere instâncias de *malabarismo* sem a
necessidade de usar curingas.

## O Smart Search pode ser usado em sites multilíngues?

Sim, mas ainda existem alguns problemas a serem resolvidos, especialmente em relação ao suporte para idiomas asiáticos.

- Para ser indexado corretamente, você deve garantir que todo o conteúdo seja válido em UTF-8.
- A funcionalidade *Você quis dizer?* utiliza a função Soundex para encontrar frases de pesquisa foneticamente similares. No entanto, o Soundex não funciona bem para idiomas não ingleses e, em muitos idiomas, não funciona de jeito nenhum. Atualmente, estamos pesquisando métodos alternativos para fornecer essa funcionalidade.

Se você usar o Smart Search em um site multilíngue e encontrar algum problema, por favor, informe-o no rastreador para que possamos entender melhor os problemas que precisam ser resolvidos.

## Os plugins *jXTended* Finder funcionarão com Smart Search?

Não. Você precisará atualizar os plugins Finder para que funcionem com o Smart Search. No entanto, as mudanças não devem ser difíceis de implementar e, na maioria dos casos, resultarão em um código significativamente menor. Se você der uma olhada nos plugins atuais do Smart Search, verá que atualizar um plugin Finder é algo bastante simples.

*Traduzido por openai.com*

