<!-- Filename: jdocmanual?manual=user&heading=news&filename=news-feeds.md / Display title: Feeds de Notícias -->

## Introdução aos Feeds de Notícias

Era uma vez comum que um site exibisse itens de notícias de sites remotos em uma página ou painel. Os navegadores até tinham leitores de notícias integrados para fazer exatamente isso. Os tempos mudam e os principais navegadores não oferecem mais essa opção. E há novos métodos para compartilhar conteúdo de sites, especialmente com sites de mídia social.

O método para compartilhar notícias é o *Really Simple Syndication*, geralmente abreviado para **RSS**, e isso ainda tem um lugar na promoção de sites. A seguinte captura de tela mostra o *NetNewsWire*, um leitor de RSS gratuito e de código aberto para Mac. Outros leitores de RSS estão disponíveis para outras plataformas. A ilustração mostra o feed RSS de **Anúncios do Joomla!** selecionado. Dez anúncios estão listados com Título e breve descrição. O anúncio selecionado é mostrado na íntegra na coluna da direita.

![Feed RSS de Anúncios do Joomla](../../../en/images/news-feeds/news-netnewswire-display.png "Anúncios do Joomla")

Imagine o que um ou mais feeds RSS podem fazer pelo seu site!

## Configurando um Feed de Notícias

Seu site possui Feeds de Notícias configurados por padrão. Um site Joomla 5 recém-instalado possui essas duas linhas perto do topo do código-fonte da página inicial:

```
<link href="/j51/index.php?format=feed&amp;type=rss" rel="alternate" type="application/rss+xml" title="Home">
<link href="/j51/index.php?format=feed&amp;type=atom" rel="alternate" type="application/atom+xml" title="Home">
```
Essas linhas permitem que sistemas automatizados usem Feeds RSS ou Atom. O Atom é uma especificação de sindicação de notícias posterior e ligeiramente diferente. As linhas estarão presentes em todas as páginas **Destaque** e páginas de **Blog de Categoria**, mas não na maioria dos outros tipos de páginas. Você pode desativar a inclusão desses feeds RSS, se desejar.  

## Alternar Link do Feed RSS

A configuração global do Link do Feed RSS está localizada na aba **Integração** da página Artigos: Opções. Defina como *Mostrar* ou *Ocultar* conforme achar apropriado. O padrão é **Mostrar**.

A configuração global pode ser substituída em um item de menu de blog de Categoria. Novamente, selecione a aba *Integração* e defina o *Link do Feed RSS* para *Mostrar* ou *Ocultar*.

O Feed RSS não pode ser ocultado na página inicial de Artigos em Destaque (bug?)!

## O Módulo de Feeds de Sindicação

Há um módulo central que você pode colocar em páginas de Blog de Destaques ou Categoria para fornecer um link de Sindicação. Preencha os campos na aba Módulo. A maioria possui padrões adequados. Se o campo Rótulo for deixado em branco, o rótulo padrão em inglês será *Entradas de Feed*. Na aba *Atribuição de Menu*, selecione **Em todas as páginas**. O módulo aparecerá apenas em páginas de Blog de Destaques e Categoria.

![Entrada de dados de feeds de sindicação](../../../en/images/news-feeds/news-syndication-feeds-form.png "Entrada de dados de feeds de sindicação")

Lembre-se de atribuir o módulo a uma *Posição* e marcá-lo como *Publicado*.

Na visualização da página do site, o módulo exibe um link. Não é destinado para clique a menos que você tenha um Leitor de Notícias local configurado. O link precisa ser copiado para uso em um Leitor de Notícias em outro site ou aplicativo de Leitor de Notícias.

![Exibição de feeds de sindicação](../../../en/images/news-feeds/news-syndication-feeds-display.png "Exibição de feeds de sindicação")

Note que o link é para os itens naquela página. Portanto, se o seu site tiver várias páginas de blog de categoria, você terá vários feeds RSS diferentes.
*Traduzido por openai.com*

