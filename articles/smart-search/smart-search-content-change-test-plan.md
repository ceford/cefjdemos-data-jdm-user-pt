<!-- Filename: Smart_Search_content_change_test_plan / Display title: Plano de Teste de Pesquisa Inteligente -->

O que se segue é um plano de teste preliminar que cobre (principalmente) a atualização do índice de Pesquisa Inteligente quando ocorrem vários tipos de atualizações de conteúdo.

A Pesquisa Inteligente precisa ser testada para cada um dos tipos de conteúdo principal suportados. Estes são:

- Artigos
- Categorias
- Contatos
- Feeds de notícias
- Links da web

Para cada um dos tipos de conteúdo acima, precisamos testar o seguinte:

## Alterações de texto

Alterar vários campos de texto dentro de um item de conteúdo deve mudar os termos de busca no índice (com uma exceção notável descrita abaixo). Não há necessidade de testar todos os campos de texto para um determinado tipo de conteúdo, já que se funcionar para um deles, funcionará para todos, então basta escolher um para cada tipo de conteúdo. Os seguintes campos de texto são indexados para os componentes principais:

- Artigos
  - Título
  - Apelido
  - Texto do artigo
  - Descrição dos metadados
  - Palavras-chave dos metadados
  - Autor dos metadados
  - Autor
  - Criado por apelido
- Categorias
  - Título
  - Apelido
  - Descrição
  - Link ??? (não tenho certeza se existe tal campo)
  - Descrição dos metadados
  - Palavras-chave dos metadados
  - Autor dos metadados
  - Autor
- Contatos
  - Nome
  - Apelido
  - Nome do usuário vinculado
  - Outras informações
  - Posição (se habilitado nas Opções)
  - Endereço (se habilitado nas Opções)
  - Cidade (se habilitado nas Opções)
  - Região (se habilitado nas Opções)
  - País (se habilitado nas Opções)
  - CEP (se habilitado nas Opções)
  - Telefone (se habilitado nas Opções)
  - Fax (se habilitado nas Opções)
  - Email (se habilitado nas Opções)
  - Celular (se habilitado nas Opções)
  - Página da web (se habilitado nas Opções)
- Fontes de notícias
  - Título
  - Apelido
  - Link
  - Descrição dos metadados
  - Palavras-chave dos metadados
  - Autor dos metadados
  - Autor
  - Criado por apelido
- Links da web
  - Título
  - Apelido
  - URL
  - Descrição
  - Descrição dos metadados
  - Palavras-chave dos metadados
  - Autor dos metadados
  - Autor
  - Criado por apelido

Para testar, basta adicionar algum texto aleatório, como "xyz", dentro de um conjunto de texto regular e próximo ao topo, depois tente buscar por esse termo na interface do usuário.

- sua string aleatória deve aparecer na lista de preenchimento automático conforme você a digita.
- sua string aleatória deve aparecer 3 vezes na lista de preenchimento automático.
  - sozinha
  - junto com a próxima palavra que a segue
  - junto com as próximas 2 palavras que a seguem
- o item de conteúdo contendo sua string aleatória deve aparecer na lista de resultados de busca.
- sua string aleatória deve ser destacada nos resultados da busca, desde que você a tenha inserido próximo ao topo do texto (porque o texto nos resultados da busca é truncado).

Remova sua string aleatória do texto: Isso deve remover os 3 termos/frases de busca do índice. Procurar por qualquer um dos 3 termos/frases de busca não deve produzir resultados de busca.

Exclua o item de conteúdo: Isso removerá todos os termos/frases de busca usados no item de conteúdo do índice, exceto onde esses termos/frases de busca ainda são usados em outros itens de conteúdo.<sup>[\[1\]](#cite_note-1)</sup>

O item de conteúdo excluído não deve aparecer em nenhuma lista de resultados de busca.

## Alterações de estado do item de conteúdo

Encontre um item de conteúdo do tipo necessário usando a Pesquisa Inteligente. Em seguida, execute esses testes:

- Mova o item para a lixeira e repita a pesquisa. O item não deve mais aparecer
  nos resultados da pesquisa.
- Publique novamente o item e repita a pesquisa. O item deve aparecer
  nos resultados da pesquisa novamente.
- Despublique o item e repita a pesquisa. O item não deve mais
  aparecer nos resultados da pesquisa.
- Arquive o item e repita a pesquisa. O item deve aparecer
  nos resultados da pesquisa novamente.

## Alterações no mapa de conteúdo (taxonomia)

Embora as alterações na categoria sejam um caso especial de mudanças no mapa de conteúdo, também precisamos testar alterações nas ramas do mapa de conteúdo que não são de categoria, pois as mudanças de categoria exercitam alguns códigos diferentes. Estes são os campos que não pertencem à categoria e que estão sujeitos aos mapas de conteúdo nos componentes principais:

- Artigos
  - Autor
  - Categoria
  - Idioma
- Contatos
  - Categoria
  - País
  - Idioma
  - Região
- Feeds de notícias
  - Categoria
  - Idioma
- Links da web
  - Categoria
  - Idioma

Então, escolha um (se um funcionar, todos funcionarão para aquele tipo de conteúdo) dos acima que seja apropriado para o tipo de conteúdo e verifique se:

- a alteração do campo resulta no item aparecendo em uma busca usando o menu suspenso relevante (na busca avançada) para o campo que você alterou. <sup>[\[2\]](#cite_note-2)</sup>
- o item de conteúdo não aparece em uma busca usando o valor antigo do campo.

Exclua o item de conteúdo e verifique se ele não aparece mais nos resultados de busca usando o filtro suspenso relevante. Note que **não** é esperado que um nó não utilizado seja removido do menu suspenso de filtro relevante. <sup>[\[3\]](#cite_note-3)</sup>

## Alterações de estado de categoria

Alterar o estado da categoria à qual pertence um item deve atualizar o índice desse item. Além disso, alterar o estado de uma categoria pai da categoria à qual um item pertence também deve atualizar o índice desse item. Para testar, encontre ou crie um item com a seguinte estrutura:

    Categoria A contendo Categoria A.1 contendo item de conteúdo

Altere o estado da Categoria A.1 e teste da seguinte forma:

- Enviar para a lixeira a Categoria A.1 e repetir a pesquisa. O item não deve mais
  aparecer nos resultados de pesquisa.
- Publicar a Categoria A.1 novamente e repetir a pesquisa. O item deve
  aparecer nos resultados de pesquisa novamente.
- Despublicar a Categoria A.1 e repetir a pesquisa. O item não deve
  mais aparecer nos resultados de pesquisa.
- Arquivar a Categoria A.1 e repetir a pesquisa. O item deve aparecer
  nos resultados de pesquisa novamente.

Restaurar a Categoria A.1, em seguida, alterar o estado da Categoria A e testar da
seguinte forma:

- Enviar para a lixeira a Categoria A e repetir a pesquisa. O item não deve
  mais aparecer nos resultados de pesquisa.
- Publicar a Categoria A novamente e repetir a pesquisa. O item deve
  aparecer nos resultados de pesquisa novamente.
- Despublicar a Categoria A e repetir a pesquisa. O item não deve mais
  aparecer nos resultados de pesquisa.
- Arquivar a Categoria A e repetir a pesquisa. O item deve aparecer
  nos resultados de pesquisa novamente.

## Alterações no nível de acesso de itens de conteúdo

Altere o nível de acesso de um item de conteúdo para algo que um usuário frontal não deveria poder ver.

- verifique se o item de conteúdo não aparece nas listas de resultados de pesquisa.

Altere o nível de acesso de volta para algo que um usuário frontal deveria poder ver.

- verifique se o item de conteúdo agora aparece nas listas de resultados de pesquisa.

Observe que os termos de pesquisa dentro do item de conteúdo ainda aparecerão na lista de autocompletar, mesmo que o usuário não tenha acesso ao próprio item de conteúdo. Este é o comportamento esperado, embora seja algo que possamos querer investigar. <sup>[\[4\]](#cite_note-4)</sup>

## Alterações no nível de acesso da categoria

Alterar o nível de acesso da categoria à qual um item pertence deve atualizar o índice para esse item. Além disso, alterar o nível de acesso de uma categoria pai da categoria à qual um item pertence também deve atualizar o índice para esse item. Para testar, encontre ou crie um item com a seguinte estrutura:

    Categoria A contendo Categoria A.1 contendo item de conteúdo

Realize os seguintes testes:

- Altere o nível de acesso da Categoria A.1 para algo que um usuário de front-end não deve conseguir ver.
  Verifique se o item de conteúdo não aparece nas listas de resultados de pesquisa.
- Altere o nível de acesso da Categoria A.1 de volta para algo que um usuário de front-end deve conseguir ver.
  Verifique se o item de conteúdo agora aparece nas listas de resultados de pesquisa.
- Altere o nível de acesso da Categoria A para algo que um usuário de front-end não deve conseguir ver.
  Verifique se o item de conteúdo não aparece nas listas de resultados de pesquisa.
- Altere o nível de acesso da Categoria A de volta para algo que um usuário de front-end deve conseguir ver.
  Verifique se o item de conteúdo agora aparece nas listas de resultados de pesquisa.  

## Alterações de estado do Smart Search

Na tela Administrador → Componentes → Smart Search → Mapas de Conteúdo é possível alterar o estado de publicação/não publicação dos ramos e nós do mapa de conteúdo. Os seguintes testes devem ser realizados:

- Não publicar um ramo do mapa de conteúdo (por exemplo, Autor).  
  Verifique se o menu suspenso de filtro para esse ramo não está mais visível na pesquisa avançada.
- Não publicar um nó do mapa de conteúdo (dentro de um ramo publicado). Por exemplo, "Animais" dentro do ramo "Categoria".  
  Verifique se o nó não está listado no menu suspenso de filtro para o ramo na pesquisa avançada.

Na tela Administrador → Componentes → Smart Search → Conteúdo Indexado, realize o seguinte teste:

- Não publicar um item de conteúdo.  
  Verifique se o item de conteúdo não aparece mais nos resultados de pesquisa.

Na tela Administrador → Extensões → Gerenciador de Plug-ins, realize o seguinte teste:

- Defina o filtro "Selecionar tipo" para "localizador" ou "pesquisa inteligente".
- Escolha um dos plug-ins de tipo de conteúdo e não publique-o.  
  Todos os dados para esse tipo de conteúdo devem ser removidos do índice.

Nota: Se você publicar o plug-in novamente, ele não adicionará os dados de volta ao índice. Este é o comportamento esperado. Você precisará executar o indexador novamente para obter os dados de volta.

*Traduzido por openai.com*

