<!-- Filename: J4.x:Article_Preview / Display title: Artigo: Prévia   -->

## Introdução

Pode ser útil pré-visualizar um artigo antes de publicá-lo. Existe um botão de *Pré-visualização* na Barra de ferramentas do formulário de *Artigo: Editar* no backend para esse fim. No entanto, esse recurso usa o artigo salvo e não o conteúdo do formulário do editor. O recurso de Pré-visualização não está disponível no formulário de edição de artigo do frontend.

Você pode não querer tornar um artigo visível até que esteja concluído. Para esse propósito, são necessárias estratégias diferentes para editores do frontend e do backend.

## Pré-visualização do Frontend

A única maneira de manter um artigo semi-privado no front-end é definir seu Acesso como *Registrado* para que apenas usuários logados possam visualizá-lo.

- Faça login no frontend do site.
- Selecione o link *Editar* para um artigo a ser atualizado. Ou...
- Selecione o botão *Novo Artigo* abaixo dos layouts do blog.
  - Defina o nível de Acesso do artigo como *Registrado* até que esteja pronto para publicação.
  - Você pode adicionar um aviso de *Alerta* indicando que o artigo está em construção: `<div class="alert alert-warning">Em Construção</div>`.
- *Salvar & Fechar* para ver o artigo.

## Pré-visualização do Backend

Após efetuar login na interface de Administrador:

- Selecione um artigo para editar ou crie e salve um novo.
- Para manter um novo artigo privado por enquanto, defina o Status como *Não publicado* ou deixe-o *Publicado* e ajuste a data de *Início da publicação*.
- Faça alterações e *Salve* o artigo.
- Selecione o botão *Pré-visualizar* na Barra de Ferramentas. Uma janela de Pré-visualização deve aparecer.
- Se você receber uma mensagem *A página solicitada não pode ser encontrada*, faça login no Frontend e tente novamente.
- Para fechar a janela de Pré-visualização, selecione o botão *X* no canto superior direito.

![A janela de pré-visualização](../../../en/images/getting-started/article-edit-preview.png)

*Traduzido por openai.com*

