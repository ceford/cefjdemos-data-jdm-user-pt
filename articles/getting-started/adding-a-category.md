<!-- Filename: J4.x:Getting_Started:_Adding_a_Category / Display title: Adicionando uma Categoria -->

## Introdução

Proprietários de sites com mais de alguns artigos devem pensar sobre como melhor apresentar o conteúdo para facilitar a navegação. Por exemplo, se você tem um zoológico, um museu, uma coleção de minerais ou apenas um grande jardim, pode ter talvez 1000 espécimes para descrever. Um artigo para cada espécime, com fotografias, necessita de alguma estrutura organizacional. Se os artigos fossem arquivos, você provavelmente os colocaria em uma hierarquia de arquivos. Em um CMS, os artigos não são arquivos, mas as categorias fornecem uma estrutura semelhante a uma árvore. Exemplo:

| Categoria   | Subcategorias                          |
|-------------|----------------------------------------|
| Mamíferos   | Primatas, Macacos, Ungulados, Cães, Gatos |
| Répteis     | Cobras, Lagartos, Crocodilos, Tartarugas  |
| Anfíbios    | Sapos, Rãs                              |
| Aves        | Raptores, Patos, Gaivotas, Tentilhões, Chapins |
| Artrópodes  | Aranhas, Borboletas, Abelhas, Gafanhotos  |
| Peixes      | Tubarões, Salmão, Bacalhau, Arenque, Cavalas |

Subcategorias também podem ter subcategorias adicionais. Uma profundidade máxima gerenciável parece ser cerca de sete. Para a tabela acima, um museu pode adicionar mais categorias principais:

```text
natureza -> vida -> animais -> mamíferos...
natureza -> vida -> plantas -> árvores...
natureza -> minerais...
história -> egito...
ciência -> astronomia...
ciência -> química...
```

Imagine quantos espécimes um museu nacional ou de uma pequena cidade abriga!

## Tipos de Itens de Menu

Existem vários tipos de itens de menu projetados para funcionar com Categorias:

- **Blog de Categoria** Este é um layout de página que possui um ou dois
  artigos principais, muitas vezes ocupando toda a largura da página, depois vários outros artigos em
  duas ou três colunas, e finalmente um mecanismo de paginação para fazer ligação com
  mais artigos na mesma categoria. O artigo principal é o conteúdo antes
  de uma quebra de página, muitas vezes é o primeiro ou segundo parágrafo. Uma página *Inicial* de um site é
  frequentemente um blog de categoria que inclui *Todas as Categorias*. Um layout de *Artigos em Destaque*
  é semelhante a um blog de categoria e geralmente é usado também como página Inicial.
- **Lista de Categoria** Este é um layout de lista que exibe uma lista de
  artigos em uma categoria. Pode ser exibido com um filtro de Busca para permitir
  a pesquisa de artigos por Título, Autor, Visualizações, Tags ou Mês de publicação.
- **Listar Todas as Categorias em uma Árvore de Categorias de Artigo** Este layout lista uma
  árvore de categorias começando de um pai escolhido. Cada ramificação é colapsável e
  é mais útil para estruturas de árvore de categorias grandes e complexas.

Itens de menu são abordados em um artigo posterior.

## Criar uma Categoria

O exemplo a seguir usa uma categoria de Mamíferos inspirada na lista acima para demonstrar como criar uma nova Categoria:

![Formulário de edição de categoria](../../../en/images/getting-started/article-category-edit.png)

- Selecione o item **Conteúdo** no menu do Administrador para expandi-lo.
- Selecione o ícone **+** ao lado do item de menu *Categorias* para abrir o formulário de edição de Categoria.
- O formulário **Artigos: Nova Categoria** tem apenas um campo obrigatório: o *Título*, neste caso, *Mamíferos*.
- O campo **Descrição** é opcional, mas é melhor preenchê-lo, pois é usado em algumas listas. Sugestão:<br> 
  *Mamíferos são animais de sangue quente que dão à luz filhotes vivos.*
- O campo **Pai** especifica se esta é uma categoria principal (-Sem Pai-) ou uma subcategoria selecionada da lista de categorias.
- **Salvar e Fechar** para retornar à página da lista **Artigos: Categorias**.

Esta categoria agora está disponível para uso com artigos.

*Traduzido por openai.com*

