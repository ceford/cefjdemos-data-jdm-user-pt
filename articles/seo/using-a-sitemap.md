<!-- Filename: Using_A_Sitemap / Display title: Usando um Sitemap  -->

## Usando um Sitemap

Embora os mecanismos de busca geralmente consigam encontrar suas páginas pela forma como estão vinculadas a outros lugares na internet, é uma boa prática criar um Sitemap que forneça aos 'bots' dos mecanismos de busca uma lista das páginas no seu site - pense nisso como um mapa para encontrar todo o conteúdo em seu site. Os Sitemaps não são apenas importantes para os motores de busca, mas também são muito úteis para pessoas com deficiência que possam precisar de uma interface simples para visualizar a estrutura do seu site e navegar sem usar suas estruturas de menu. <a href="https://www.w3.org/TR/WCAG20-TECHS/G63.html" rel="nofollow noreferrer noopener">Nota do Grupo de Trabalho W3C sobre Sitemaps</a>

Um sitemap serve a vários propósitos:

- Fornece uma lista estruturada mostrando uma visão geral de todo o conteúdo no seu site
- Permite que um visitante obtenha rapidamente uma visão geral da estrutura do seu site
- Oferece uma maneira alternativa de navegar no seu site, sem a necessidade de estruturas de menu complexas
- Fornece aos mecanismos de busca um meio de encontrar conteúdo que talvez não esteja disponível através das suas estruturas de menu (por exemplo, páginas de entrada)

### Tipos de Sitemap

É possível fornecer sitemaps para tipos específicos de informações, incluindo:

- Vídeo <a href="https://support.google.com/webmasters/answer/80471" rel="nofollow noreferrer noopener">Ajuda do Google sobre sitemaps de vídeo</a>
- Imagens <a href="https://support.google.com/webmasters/answer/answer.py?answer=178636" rel="nofollow noreferrer noopener">Ajuda do Google sobre sitemaps de imagens</a>
- Notícias <a href="https://support.google.com/news/publisher/answer/75717" rel="nofollow noreferrer noopener">Ajuda do Google sobre sitemaps de Notícias</a>
- Internacional <a href="https://support.google.com/webmasters/answer/2620865?hl=en&amp;ref_topic=2370587" rel="nofollow noreferrer noopener">Ajuda do Google sobre sitemaps Internacionais</a>

Esses sitemaps especializados permitem que você forneça informações relacionadas ao tipo específico de mídia - por exemplo, com um sitemap de vídeo, você pode fornecer informações sobre a duração, categoria e status de conteúdo adequado para a família; com sitemaps de imagens, você pode especificar o assunto da imagem, sua licença de uso e tipo de imagem.

### Criando um sitemap

Em um site estático, criar um sitemap é simplesmente uma questão de criar manualmente um arquivo XML usando os padrões adequados e salvá-lo como um arquivo XML. Em um site dinâmico, onde o conteúdo muda regularmente, esta não é realmente uma opção - você teria que atualizar manualmente o arquivo do sitemap sempre que adicionasse algum novo conteúdo!

Por essa razão, há várias extensões de sitemap disponíveis no Diretório de Extensões do Joomla (<a href="https://extensions.joomla.org/category/structure-a-navigation/site-map" rel="noreferrer noopener">Categoria de Sitemap no Diretório de Extensões do Joomla</a>) que permitem que você construa dinamicamente um sitemap que atenda aos padrões de sitemap esperados pelos mecanismos de busca. <a href="https://www.sitemaps.org/" rel="nofollow noreferrer noopener">Protocolo de Sitemaps</a>

A maioria dessas extensões funciona escolhendo itens de menu que você deseja incluir em um sitemap e especificando com que frequência eles mudam (veja Frequência de Atualização). Também é possível incluir sub-páginas desses itens de menu (por exemplo, um item de menu pode levar a uma página de blog de categoria, mas você quer exibir todos os artigos que são mostrados nessa página como itens individuais - outro exemplo pode ser um item de menu apontando para uma página de categoria de loja, e no sitemap você gostaria de listar a categoria, e então cada produto dentro dela como um link separado).

### Frequência de Atualização

Embora você possa especificar manualmente em seu Sitemap com que frequência os spiders dos mecanismos de busca devem visitar seu site, a maioria dos mecanismos de busca possui sistemas embutidos que ajustam automaticamente a frequência de visitas de retorno com base na frequência com que a página em questão foi alterada.

Assim, por exemplo, se você disser aos bots dos mecanismos de busca para visitar sua página diariamente, mas quando ela for visitada nada mudou por uma semana, a frequência de revisitas pode ser ajustada de acordo e não retornar com a frequência que você especificou. Você pode solicitar, por meio dos vários portais de webmasters, que a taxa de revisita seja alterada, se necessário.

Isso sugere, portanto, que se você tiver conteúdo que muda regularmente, seu site será 'spidered' com mais frequência, levando a um indexamento mais rápido do que sites que não mudam com frequência.

Geralmente é sensato especificar páginas que são estáticas para serem rastreadas com menos frequência do que aquelas que mudam regularmente. Por exemplo, um artigo de texto estático pode estar definido com uma frequência de atualização de uma vez por mês, enquanto sua página de blog ou notícias pode estar definida com uma frequência de atualização de uma vez por dia ou uma vez por semana, dependendo da frequência com que você adiciona novo conteúdo.

### Sitemaps HTML

Um sitemap HTML é, essencialmente, um índice de conteúdo do seu site que você pode disponibilizar para os visitantes. Isso serve a dois propósitos:

1.  Fornece um local onde os visitantes podem ir para acessar facilmente qualquer conteúdo do seu site, mesmo que não seja necessariamente fácil de acessar por outros meios de navegação no site
2.  Fornece um armazenamento centralizado de links para o conteúdo do seu site que pode ser facilmente indexado por mecanismos de busca
3.  Permite que usuários com deficiência naveguem rapidamente em seu site com uma lista simples de links, em vez de menus complexos

Pelo menos, um sitemap deve ligar às seções principais e páginas dentro do seu site, mas quanto mais detalhado você puder torná-lo, melhor.

Há extensões disponíveis mencionadas anteriormente que criam sitemaps automaticamente com base no conteúdo do Joomla.

### Sitemaps XML

Os Sitemaps XML são uma maneira fácil para webmasters informarem os mecanismos de busca sobre páginas novas e existentes em seus sites que estão disponíveis para rastreamento. Na sua forma mais simples, um Sitemap é um arquivo XML que lista URLs de um site juntamente com metadados adicionais sobre cada URL (quando foi atualizado pela última vez, com que frequência geralmente muda e quão importante é em relação a outras URLs no site) para que os motores de busca possam rastrear o site de maneira mais inteligente.

Usar o protocolo Sitemap não garante que as páginas da web sejam incluídas nos mecanismos de busca, mas fornece dicas para os web crawlers fazerem um melhor trabalho de rastreamento do seu site.

1.  Um sitemap XML fornece uma lista de links para o conteúdo do seu site que pode ser facilmente indexado pelos motores de busca
2.  É possível criar sitemaps XML específicos para Notícias, URLs Móveis, Imagens e Vídeo

Existem extensões disponíveis que criam sitemaps XML automaticamente com base no conteúdo do Joomla.

*Traduzido por openai.com*

