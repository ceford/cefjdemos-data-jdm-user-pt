<!-- Filename: J4.x:Create_and_Manage_Article_Categories / Display title: Artigos: Categorias  -->

## Introdução

Imagine uma biblioteca sem um sistema de classificação: os livros são colocados nas prateleiras na ordem em que são recebidos. Isso não é muito útil se a biblioteca tem milhões de livros e você está procurando algo sobre História, Jardinagem ou Ciência. O mesmo tipo de argumento se aplica a Artigos. Se você tem dezenas, centenas ou milhares de artigos, realmente precisa de um método para classificá-los, de modo a encontrar facilmente o que precisa. É para isso que servem as Categorias.

Uma categoria do Joomla! pode conter tanto artigos quanto subcategorias em uma estrutura em árvore, aninhada em qualquer profundidade, embora seja improvável que você queira ir além de uma profundidade de três ou quatro. Por exemplo, se seus artigos são sobre Natureza, você pode classificá-los da seguinte forma:

- Animais
  - Aves
    - Falcões
    - Tentilhões
    - Gaivotas
  - Mamíferos
    - Primatas
    - Macacos
    - Roedores
- Plantas
  - Flores
    - Margaridas
    - Rosas
  - Árvores
    - Carvalhos
    - Ulmeiros

Neste exemplo, a categoria *Animais* pode conter artigos sobre animais em geral, bem como subcategorias para artigos sobre diferentes tipos de animais.

O Joomla fornece uma única categoria padrão chamada Não categorizado. Qualquer artigo não atribuído a uma categoria específica que você criou torna-se membro da categoria Não categorizada. Você cria categorias conforme necessário para adequar à natureza de seus artigos.

Um artigo só pode estar em uma categoria. Em algumas circunstâncias, isso não é suficiente. Suponha, por exemplo, que você deseja procurar por livros de todos os tipos escritos em um idioma específico, ou todas as plantas que são venenosas ou todos os animais que são perigosos. É aí que as Tags se tornam úteis. Elas são abordadas em outro lugar.

### Usando Categorias

Na página do administrador *Artigos*, o formulário *Opções de Filtro* possui uma lista suspensa **- Selecione Categoria -** que exibe uma árvore de categorias, permitindo filtrar artigos em uma Categoria selecionada. Você também pode criar tipos de item de menu *Blog de Categoria* e *Lista de Categoria* para exibir artigos de uma categoria selecionada para os visitantes do site.

## Adicionando Categorias e Subcategorias

Existem várias rotas para a página *Artigos: Nova Categoria*:

- Através do **Painel Inicial** Selecione o **símbolo de mais (+)** à direita do 
  link *Categorias de Artigos*. Este último leva à página de lista 
  *Artigos: Categorias*.
- Através do **Menu do Administrador** Selecione o item *Conteúdo* para 
  expandir a lista e, em seguida, selecione o **símbolo de mais (+)** à direita 
  do link *Categorias*.
- Através do **Painel de Conteúdo** Selecione o ícone do Painel à direita do 
  link *Conteúdo* no menu do Administrador e, em seguida, no painel *Conteúdo* do 
  painel, selecione o **símbolo de mais (+)** à direita do link *Categorias*.
- Através de **Artigos: Categorias** Siga qualquer uma das rotas para a página 
  de lista e selecione o botão **Novo** na Barra de Ferramentas.

A captura de tela a seguir mostra o link *Categorias de Artigos* do Painel Inicial
para a lista de categorias e o *Símbolo de Mais* adjacente que leva ao
formulário *Artigos: Nova Categoria*.

![O ícone de adicionar categoria destacado no painel inicial](../../../en/images/articles/category-add-via-home-dashboard.png)

## Os Artigos: Formulário de Nova Categoria

![O formulário de edição de nova categoria de artigos](../../../en/images/getting-started/article-category-edit.png)

A captura de tela acima mostra o formulário preenchido. Há apenas dois campos que precisam de conteúdo. Todo o resto tem valores padrão ou nulos que você pode deixar por agora e preencher mais tarde, conforme necessário.

- **Título** Este é o único campo obrigatório. Deve ser curto, mas descritivo da categoria.

### A guia Categoria

- **Descrição** Embora não seja obrigatório, este campo pode ser exibido nas páginas de lista de categorias do site controladas por itens de menu. Você pode precisar voltar e atualizar a descrição mais tarde.
- **Pai** Se configurado para *- Sem pai -*, este novo item é uma potencial categoria pai para outras categorias. Se outra categoria for selecionada como pai, este novo item é uma subcategoria.
- **Status** Por padrão, uma nova categoria é configurada como *Publicado*. Você pode alterar o status de uma categoria para *Publicado*, *Não publicado*, *Arquivado* ou *Lixo*. [Para Fazer] Explique o que acontece quando uma Categoria não é Publicada...
- **Acesso** Por padrão, o acesso é configurado para *Público*. Outras opções para restringir o acesso são *Convidado*, *Registrado*, *Especial* e *Super Usuários*. [Para Fazer] Explique como o Acesso a uma Categoria pode ser usado...
- **Idioma** Em sites multilíngues, configurar isso para *Todos* tornará a nova categoria independente do Idioma do site. Se configurada para um idioma específico, ela estará disponível apenas em páginas que usam esse idioma.
- **Tags** Se você usá-las, pode adicionar uma ou mais tags à categoria. Configurar tags no nível da categoria é uma boa maneira de manter a consistência. Para este tutorial, uma tag *Natureza* foi criada e usada para filtrar listas para mostrar apenas itens relacionados aos tutoriais.
- **Nota** e **Nota da Versão** Use essas opções para adicionar notas relevantes, se necessário.

### A guia Opções

As configurações nesta guia afetam a aparência desta Categoria nas páginas do site.

- **Layout** Refere-se à colocação do conteúdo na página. Pode haver uma escolha de layouts, dependendo do componente e do modelo em uso. [Para Fazer] Exemplos...
- **Imagem** Você pode desejar usar uma imagem para atuar como um ícone para que esta categoria possa ser instantaneamente reconhecida em uma lista de categorias. Se usado para tal propósito, uma *Descrição da Imagem (texto alternativo)* não é necessária, mas a caixa de seleção *Sem Descrição* deve ser marcada.

### Salvar & Fechar

- **Salvar & Fechar** Para terminar de editar esta categoria. Ou na lista suspensa...
  - **Salvar & Novo** Salve esta categoria e abra um novo formulário de edição para uma nova categoria. Por exemplo, você pode desejar começar a construir uma árvore de categorias adicionando uma categoria *Primatas* com *Mamíferos* como seu pai.
  - **Salvar no Menu como Lista** ...
  - **Salvar no Menu como Blog** ...
  - **Salvar como Cópia** ...

Fechar o formulário de edição leva à página de lista **Artigos: Categorias**.

![Uma lista de categorias filtrada pela tag Natureza](../../../en/images/articles/categories-list.png)

### Salvar no Menu como Lista

A seleção deste item a partir da lista suspensa *Salvar & Fechar* irá salvar e fechar o formulário de edição de categoria e abrir um novo formulário de item de menu com todos os dados necessários para criar uma *Lista de Categorias* para esta categoria. Você pode desejar mudar o *Título*. Por exemplo, poderia ser *Lista de Artigos Mamíferos* para deixar claro que é provável que seja uma lista de artigos.

Na guia *Exibição da Página*, tente definir o campo *Mostrar Cabeçalho da Página* para *Mostrar*. Isso mostra *Lista de Artigos Mamíferos* como um cabeçalho em negrito no topo da página, dando-lhe uma aparência mais completa.

### Salvar no Menu como Blog

A seleção deste item a partir da lista suspensa *Salvar & Fechar* irá salvar e fechar o formulário de edição de categoria e abrir um novo formulário de item de menu com todos os dados necessários para criar um *Blog de Categoria* para esta categoria. Você pode desejar mudar o *Título*. Por exemplo, poderia ser *Blog de Artigos sobre Mamíferos* para que os últimos artigos sobre mamíferos sejam destacados.

Na guia *Exibição da Página*, tente definir o campo *Mostrar Cabeçalho da Página* para *Mostrar*. Isso mostra *Blog de Artigos sobre Mamíferos* como um cabeçalho em negrito no topo da página, dando-lhe uma aparência mais completa.

A captura de tela a seguir mostra a visualização do site de uma página de blog de categoria em desenvolvimento.

![Página de blog da categoria Mamíferos](../../../en/images/articles/article-mammals-articles-blog-site-view.png)

## Dicas

- Você também pode criar categorias de artigos dentro de um artigo.
- Lembre-se de que você só pode atribuir um artigo a uma categoria.
- Como tanto as categorias principais quanto as subcategorias podem ter outras subcategorias, planeje e organize as categorias com cuidado. Uma hierarquia de categorias complicada pode se tornar um desafio para gerenciar.
- Outro método de agrupar conteúdo no Joomla é o uso do Componente de **Tags**, permitindo que você adicione várias tags aos seus artigos. Usar categorias e tags pode ajudar a minimizar o número de subcategorias e oferece uma maneira eficiente de estruturar o conteúdo do site e fornecer aos visitantes mais recursos para navegar pelo conteúdo do site.

*Traduzido por openai.com*

