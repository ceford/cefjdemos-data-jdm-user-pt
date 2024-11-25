<!-- Filename: J4.x:How_To_Use_Content_Tags_in_Joomla / Display title: Tags de Conteúdo  -->

## Introdução

Tags oferecem uma maneira fácil e eficiente de organizar e exibir conteúdo. O **Componente de Tags** permite que tags sejam usadas em diferentes tipos de conteúdo, incluindo artigos, categorias, contatos e feeds de notícias. Ele também possibilita a criação de tags pai e filho.

Ao contrário das **Categorias** do Joomla, onde apenas uma categoria pode ser atribuída a um item, múltiplas tags podem ser atribuídas a um único item, mas não é obrigatório atribuir tags aos itens.

Uma vez que um item está marcado com uma tag específica, clicar no botão da tag em conteúdos que exibem tags levará você a uma página que exibe uma lista de todos os itens que foram marcados com aquela tag específica. Por essa razão, tags são frequentemente usadas como uma maneira de apresentar listas *filtradas* de conteúdo.

Tags podem ser adicionadas em vários lugares, proporcionando flexibilidade na criação de tags.

## Considerações

Antes de começar, considere o propósito das tags no site, especialmente se outras pessoas irão adicionar conteúdo. A menos que sejam adicionadas e gerenciadas corretamente, as tags podem se tornar contraproducentes. Problemas comuns incluem redatores de conteúdo adicionando novas tags desnecessárias e nomes de tags escritos incorretamente. Alguns Administradores de Site podem optar por alterar as permissões de acesso para que apenas usuários específicos possam adicionar novas tags.

Quando as tags são criadas, elas serão exibidas como links nos itens marcados.  
Os estilos e posições das tags são definidos pelo modelo do site. Elas são frequentemente estilizadas como botões ou etiquetas.

A exibição das tags pode ser desativada! Isso pode parecer ilógico, mas é um recurso útil onde as tags são usadas, por exemplo, para filtrar conteúdo para casos de uso específicos.

## A Lista de Tags

- Selecione **Componentes → Tags** no menu do Administrador.

![a página da lista de tags](../../../en/images/tags/tags-list.png)

Independentemente de como as tags são criadas, elas podem ser encontradas nesta lista.

## Adicionando Tags

### Através da Lista de Tags

Selecione o botão **Novo** na Barra de Ferramentas da lista de Tags.

![nova tag chamada predator](../../../en/images/tags/new-tag-predator.png)

- **Título** Este é o único campo *obrigatório*.
- **Alias** Este é criado a partir do Título ao salvar.
- **Descrição** É sempre melhor adicionar uma Descrição. Ela é exibida nos 
  formulários do Administrador e pode ser útil quando muitas tags estão em uso.
- **Pai** Deixe configurado como *Nenhum* se esta for uma tag raiz. Ou escolha 
  uma tag pai da lista se esta for uma tag filha.
- **Status** Este campo é configurado como *Publicado* por padrão. Pode ser 
  configurado como *Não publicado*, *Arquivado* ou *Lixeira*.
- **Acesso** O nível de Acesso é Público por padrão.
- **Nota** e **Nota de Versão:** Se necessário, você pode adicionar notas.
- **Salvar & Fechar** A nova tag aparecerá na Lista de Tags. Se você estiver 
  criando múltiplas tags, pode optar por clicar em **Salvar & Novo** para 
  criar outra.

Uma vez salva, a tag estará disponível para uso nos diversos tipos de conteúdo
que as utilizam.

### De dentro de um Artigo

É possível adicionar novas tags enquanto cria ou edita um artigo. Na aba
Conteúdo do artigo, no **Campo de Tags**, insira o nome da nova tag e
pressione **Enter** para salvar e atribuir a tag ao artigo.

### De dentro de uma Categoria

Tags podem ser adicionadas ao criar ou editar uma categoria. Na aba **Categoria**,
insira o nome da tag no **Campo de Tags** e pressione **Enter** para criar
e atribuir a nova tag.

### De dentro de um Contato

Tags podem ser adicionadas ao criar ou editar um Contato. Na aba **Novo/Editar Contato**,
insira o nome da tag no **Campo de Tags** e pressione **Enter** para 
criar e atribuir a nova tag. Você também pode adicionar novas tags ao criar 
Categorias de Contatos.

### De dentro de um Feed de Notícias

Tags podem ser adicionadas ao criar ou editar um novo Feed de Notícias. Na 
aba **Novo/Editar Feed de Notícias**, insira o nome da tag no **Campo de Tags** e pressione
**Enter** para criar e atribuir a nova tag. Você também pode adicionar novas tags ao 
criar Categorias de Feeds de Notícias.

## Gerenciando Tags

Sempre que você adicionar novas Tags no Joomla, todas elas aparecerão na lista de Tags. Use a lista de Tags para encontrar, abrir e ajustar as configurações das tags.

### Filtro da Lista de Tags

![filtro da lista de tags por tipo](../../../en/images/tags/tags-list-filter.png)

Você pode manipular a lista de várias maneiras:

- Pesquisar uma tag usando parte ou todo o seu título no campo de Pesquisa.
- Reordenar a lista usando arrastar e soltar para otimizar a ordem de saída.
- Publicar ou Despublicar tags usando o botão na coluna Status.
- Selecionar uma ou mais tags e usar o botão **Ações** para Publicar, Despublicar, 
  Arquivar, Fazer Check-in ou Mover para a Lixeira as tags selecionadas.
- Selecionar uma ou mais tags e usar o botão **Ações → Lote** para definir o
  Idioma ou o Nível de Acesso.

### Configurações de Tag

 - Selecione um **Título** de tag para fazer alterações em suas configurações.

No formulário de Edição da tag:

- As configurações da aba **Detalhes da Tag** foram abordadas acima.
- A aba **Opções**:
  - Altere o layout da página da tag (a página que aparece quando você
    clica no link da tag - por exemplo, mysite.com/tags/minha-tag). Este
    layout normalmente depende da configuração padrão e do template.
  - Adicionar uma Classe CSS para aplicar um estilo diferente (aparência) ao link
    da tag. Isso normalmente seria usado apenas pelo Administrador do Site.
  - Definir imagens para a tag - uma imagem de destaque para a lista de tags e/ou uma
    imagem completa para a página da tag.
- A aba **Publicação**: Defina Metadados para a página da tag para Otimização para Motores de Busca (SEO).

## Como o Joomla Exibe Tags

Uma vez que as tags tenham sido criadas no seu site, elas estão disponíveis para uso não apenas em conteúdo, mas também em alguns módulos úteis, como **Tags Populares** e **Tags Similares**. Os exemplos a seguir mostram como elas aparecem em uma instalação padrão usando o modelo padrão **Cassiopeia**.

![exemplo de uso de tags no site labrador amarelo](../../../en/images/tags/tag-examples-yellow-labrador.png)

Quando você clica em uma das tags, será direcionado para uma página que lista todos os itens atribuídos a essa tag específica:

![exemplo de uso de tags no site labrador preto](../../../en/images/tags/tag-examples-black-labrador.png)

Clicar em uma tag levará você a uma página que exibe uma lista de todos os itens atribuídos a essa tag específica - na prática, é uma lista filtrada do conteúdo marcado do seu site. É fornecida uma caixa de filtro para facilitar a localização dos itens à medida que a lista cresce. Você também pode definir o número de resultados que deseja ver em uma única exibição.

## Configuração de Tags

Marcas individuais herdam configurações das opções do componente Tags. Isso é
abordado em um tutorial separado. [ToDo] Selecione o botão **Opções** na Barra de Ferramentas da página de lista de Tags.

A configuração do Componente de Tags pode ser substituída no nível do item de menu.

## Dicas

- Lembre-se de que as Tags são usadas em vários tipos de conteúdo
- Você pode adicionar mais de uma Tag a um item
- Use o botão de Ajuda quando estiver em dúvida

*Traduzido por openai.com*

