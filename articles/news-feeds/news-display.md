<!-- Filename: jdocmanual?manual=user&heading=news&filename=news-display.md / Display title: Exibição de Notícias -->

## O Módulo de Exibição de Feeds

Há um módulo principal de *Exibição de Feeds* disponível para mostrar notícias de outros sites. A captura de tela a seguir mostra o formulário de entrada de dados com a URL do feed de notícias dos Anúncios do Joomla. Observe que a Contagem de Palavras está definida para 100. Caso contrário, o comprimento de um anúncio pode ser excessivo para um módulo de barra lateral.

![Entrada de dados do módulo de exibição de feeds](../../../en/images/news-feeds/news-joomla-news-form.png)

O resultado pode ser ruim, mas pode ser melhorado com alguns estilos personalizados no user.css:

![Entrada de dados do módulo de exibição de feeds](../../../en/images/news-feeds/news-joomla-news-display.png)

## Páginas de Exibição de Feeds

Como alternativa à exibição de notícias em um módulo, você pode criar um item de menu para exibir um feed de notícias em uma página web. No menu do Administrador:

* Selecione **Componentes / NewsFeeds / Feeds**. Você pode primeiro criar uma Categoria para notícias.
* Selecione o botão **Novo** na *Barra de Ferramentas*.
* Preencha o formulário **Feeds de Notícias: Editar**:
    - O **Link** é o link RSS copiado de uma fonte remota.
    - A **Descrição** é opcional.
    - A guia **Opções** possui itens para controlar a *Exibição* do feed.
* **Salvar & Fechar**

![Entrada de dados do componente NewsFeed](../../../en/images/news-feeds/news-feed-data-entry.png)

Crie um item de menu começando pelo menu do Administrador:

* Selecione **Menus / Menu Principal** ou qualquer outro menu para este item.
* Selecione **Novo** na Barra de Ferramentas *Menus: Itens*.
* No **Tipo de Item de Menu** use o botão **Selecionar** para encontrar e selecionar *Feeds de Notícias / Feed Único de Notícias*.
* Preencha o restante do formulário conforme apropriado.
* **Salvar & Fechar**

![Entrada de dados do item de menu NewsFeed](../../../en/images/news-feeds/news-feed-data-entry.png)

Teste-o: vá ao menu do Site e selecione o item de menu do Feed.

![Exibição de NewsFeed](../../../en/images/news-feeds/news-feed-display.png)

Cada item no feed é um `<li>` dentro de uma etiqueta `<ul>`, então, por padrão, aparece marcado por um marcador. Isso não é tão óbvio se os itens forem longos. Você pode aplicar seus próprios estilos em *user.css*. O seguinte colocará cada item em uma caixa distinta:

```
ul.com-newsfeeds-newsfeed__items {
  list-style-type: none;
  padding-left: 0;
}

ul.com-newsfeeds-newsfeed__items > li {
  padding: 1rem;
  margin-bottom: 1rem;
  border: 2px solid navy;
}
```
Que aparece assim:

![Exibição personalizada de NewsFeed](../../../en/images/news-feeds/news-feed-custom-display.png)

## Listar Feeds de Notícias em uma Categoria

A página *Joomla! RSS Feeds de Notícias* lista oito feeds de notícias diferentes. Você pode criar um feed para alguns ou todos eles e atribuí-los a uma Categoria, por exemplo, *Notícias Joomla*. Depois, você pode criar um item de menu com o *Tipo de Item de Menu* definido como *Listar Feeds de Notícias em uma Categoria* e a Categoria definida como *Notícias Joomla*.

![Formulário de menu de feed de notícias por categoria](../../../en/images/news-feeds/news-feed-menu-category-form.png)

Experimente para ver o resultado!
*Traduzido por openai.com*

