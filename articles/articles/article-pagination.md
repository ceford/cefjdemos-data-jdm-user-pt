<!-- Filename: J4.x:Article_Pagination / Display title: Artigo: Editar - Paginação  -->

## Artigos Longos

O único limite para o comprimento de um artigo no Joomla é o tamanho do campo do banco de dados usado para conter o texto do artigo. Isso é muito grande! Artigos longos podem conter muitas imagens e demorar para processar, o que pode ser um inconveniente para o leitor e o site. Portanto, existe um mecanismo simples para dividir artigos longos em páginas separadas com um índice.

## Inserir uma Quebra de Página

Para adicionar quebras de página, primeiro abra um artigo no editor de texto, o TinyMCE é o padrão, e prossiga da seguinte forma:

- Posicione o cursor no local onde deseja que ocorra uma quebra de página.
- Na lista suspensa **Conteúdo CMS**, selecione o item *Quebra de Página*.
- Na caixa de diálogo de Quebra de Página, preencha:
  - *Título da Página* - isso será anexado ao título da página existente. Exemplo: Página 2
  - *Alias do Índice* - isso será usado como texto no Índice. Exemplo: Capítulo 2
- Selecione o botão **Inserir Quebra de Página**.

![Formulário da caixa de diálogo de quebra de página](../../../en/images/articles/articles-edit-pagination.png)

- Repita para cada quebra de página que deseja criar.
- Salve o artigo e veja uma Prévia ou a visualização do Site.

![Visualização do site com paginação do artigo](../../../en/images/articles/articles-site-pagination.png)

## Editar ou Mover uma Quebra de Página

Você pode selecionar uma quebra de página e deletá-la. No entanto, não é possível cortar e colar e você não pode abrir uma quebra de página existente no formulário de Quebra de Página. Portanto, para mover ou alterar uma quebra de página, use o editor de Código-Fonte da seguinte maneira:

- Selecione o item **Ferramentas -> Código fonte+** do editor de texto.
- O editor de código fonte mostra o HTML fonte com destaque de sintaxe.
- Role para baixo até a quebra de página que deseja editar ou mover.
- Para mover uma quebra de página:
  - Selecione e Corte a linha que contém a quebra de página.
  - Posicione o cursor na nova posição e Cole a linha cortada.
- Para editar:
  - Altere o texto do título e/ou o texto alternativo conforme desejar.
- Selecione **Salvar**.
- Salve o artigo e dê uma olhada na visualização de Prévia ou de Site.

O editor de Código-Fonte está localizado em uma janela pop-up:

![Editor de código fonte](../../../en/images/articles/articles-edit-pagination-source-code.png)

