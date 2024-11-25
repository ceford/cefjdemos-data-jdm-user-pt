<!-- Filename: J4.x:Adding_a_New_Article / Display title: Artigo: Editar - Conteúdo -->

## Introdução

*Adicionar um Artigo* foi abordado em um artigo de *Introdução*. Este é o primeiro de uma série de artigos que fornecem mais detalhes sobre o formulário *Artigo: Editar*. Ele cobre a aba *Conteúdo* e alguns aspectos do editor TinyMCE, o editor padrão fornecido com o Joomla.

A captura de tela a seguir mostra o formulário de edição com um artigo que já foi salvo.

![O formulário de edição de conteúdo](../../../en/images/articles/articles-edit-content.png)


## Entrada de Dados

O formulário de edição de artigo possui painéis com abas. Um novo artigo tem a aba **Conteúdo** selecionada por padrão. Caso contrário, a última aba aberta é selecionada.

### O campo Título

O campo **Título** é *Obrigatório* e é utilizado sempre que o título do artigo é exibido. Este é o único campo que deve conter algum texto para que seja possível salvar o formulário de edição.

Os títulos devem ser curtos, mas descritivos do conteúdo do artigo, pois aparecem em listas e itens de menu onde o espaço é limitado.

Os títulos não precisam ser únicos, embora seja melhor se forem. Por exemplo, se você selecionar *Salvar como Cópia* na lista suspensa *Salvar e Fechar*, o processo de salvamento vai salvar o artigo atual e gerar um novo com um número acrescentado ao Título e ao Alias. Você pode remover o número do Título, mas não do Alias, e *Salvar* a cópia, criando assim dois artigos com o mesmo título visível.

### O campo Alias

O campo *Alias* geralmente é deixado em branco. Quando o artigo é salvo, o Alias é gerado a partir do título, tornando-o todo em minúsculas e substituindo caracteres não alfanuméricos por hífens.

Se você alterar o título do artigo, pode deletar o Alias e um novo será gerado. Se o Alias foi usado para se referir ao artigo em links internos e externos, isso quebrará os links. Portanto, é melhor não mudar o Alias de um artigo antigo.

### A Aba Conteúdo - Texto do Artigo

A captura de tela acima mostra o texto do artigo em um editor WYSIWYG que se parece um pouco com um processador de texto. No entanto, você deve estar ciente de que o texto do artigo é armazenado como HTML e o campo de entrada de dados é realmente um campo de área de texto contendo esse HTML. Você pode ver isso por si mesmo selecionando o botão *Alternar Editor* abaixo da área de edição. O Editor é, na verdade, uma aplicação JavaScript que reexibe o HTML para torná-lo fácil de ler e manipular.

#### Tags e Atributos HTML Proibidos

Tanto o Joomla quanto o editor TinyMCE têm configurações que proíbem certas tags e atributos HTML. Por exemplo, a lista padrão de proibições do Joomla inclui *iframe*, então, se você tentar incluir essa tag em um artigo, ela será silenciosamente removida ao salvar. Filtros de texto são definidos em *Configuração Global*. O plugin TinyMCE tem uma opção para *Usar Filtro de Texto do Joomla*. Se configurado como *Desligado*, lista *script, applet, iframe* como *Elementos Proibidos*.

#### Barras de Ferramentas do Editor

Acima da área de texto, há linhas de Barras de Ferramentas. Duas são exibidas por padrão. As outras podem ser alternadas selecionando o símbolo de reticências (...) no final da segunda Barra de Ferramentas. As Barras de Ferramentas podem ser configuradas para mostrar diferentes barras e conteúdos de barra para diferentes grupos de usuários.

São muitas ferramentas para descrever cada uma aqui. Isso criaria um palheiro para você procurar uma agulha. Apenas explore!

No entanto, há alguns recursos que merecem explicação extra.

#### Conteúdo CMS

Este botão revela uma lista suspensa que permite a inclusão de itens em um artigo obtidos de outros locais no CMS.

- **Artigo** Este link revela uma lista popup de artigos. Selecione um artigo para incluir um link para esse artigo no artigo atual.
- **Contato** Inclui um link para um Contato no artigo atual.
- **Campo** Inclui um campo no artigo. É exibido como `{field 1}`.
- **Mídia** Inclui uma imagem ou arquivo de um componente de Mídia popup.
- **Menu** Inclui um link para um item do Menu de uma lista de Menu popup.
- **Quebra de Página** Há uma solicitação para um *Título da Página* e um *Alias do Índice*. Esse recurso é usado para dividir documentos longos em várias páginas.
- **Ler Mais** Um separador *Ler Mais...* é inserido na posição do cursor. Escolha um ponto de quebra entre parágrafos antes de selecionar.

#### Links Externos

O item **Inserir** na primeira Barra de Ferramentas possui opções para inserir um *Link...*, *Imagem...* ou *Mídia...*. Estes são para itens externos, então esteja pronto com a URL do item a ser usado.

### A Aba Conteúdo - Configurações

A aba **Conteúdo** é ocupada principalmente pelo editor TinyMCE.

Junto ao conteúdo, há campos para gerenciar a publicação, como e onde o artigo será exibido e quem pode vê-lo quando publicado. Na maioria dos casos, essas configurações podem ser deixadas em seus valores padrões.

1. **Status** *Publicado*, *Não Publicado*, *Arquivado* ou *Lixeira* - o padrão é *Publicado*.
2. **Categoria** Este é um campo *Obrigatório*, mas o padrão será
   *Sem Categoria*. Você pode selecionar uma categoria da lista ou digitar algumas caracteres do nome de uma categoria para encurtar a lista de categorias para escolher.
3. **Destaque** Alternar entre *Não* e *Sim* para exibir o artigo na página inicial se ela usar um layout de *Artigos em Destaque*.
4. **Acesso** O nível de acesso pode ser alterado para restringir o artigo a Grupos de Usuários atribuídos a *Níveis de Acesso* específicos: *Público*, *Convidado*, *Registrado*, *Especial* ou *Super Usuários*.
5. **Tags** Comece a digitar para encontrar e selecionar tags predefinidas ou você pode adicionar uma nova digitando-a e **pressionando enter**.
6. **Nota** Qualquer comentário sobre este artigo que será visível sob o Título na página da lista de Artigos.
7. **Nota de Versão** Adicione comentários para indicar o que mudou nesta versão. Isso é exibido na caixa de diálogo modal *Versões* e o campo retorna a vazio após salvar.

### Outras Abas

**Você pode não ver todas as abas a seguir** pois um Administrador do Site pode ocultar algumas para ajudar a manter a consistência do layout dos artigos em todo o site. Você também pode ver abas adicionais para *Campos Personalizados* se eles tiverem sido configurados.

1. **Imagens e Links** permite definir uma imagem de introdução e destaque e/ou links para aparecer em posições predefinidas. Isso pode ser usado se o seu artigo for exibido em um blog de categoria.
2. **Opções** permite especificar o layout do artigo e informações associadas como título, categoria, tags, detalhes de publicação etc. Isso é normalmente configurado globalmente, mas pode ser específico do artigo através dessas opções.
3. **Esquema** é um método para adicionar metadados a um artigo. É utilizado por robôs, mas não visto por humanos.
3. **Publicação** permite configurar datas e horários de publicação para agendar a publicação de um artigo. Por padrão, quando um artigo é salvo ele será publicado imediatamente. Você também pode configurar os Metadados para o artigo.
4. **Configurar Tela de Edição** permite mostrar ou ocultar parâmetros para o artigo.
5. **Permissões** mostra as permissões para cada grupo de usuários que controlam o que pode ou não ser feito.

Há artigos separados sobre cada uma dessas abas.


## Salvando o Artigo

Depois de adicionar as informações e o conteúdo necessários, você pode salvar o artigo. Existem várias maneiras de fazer isso, dependendo do que você deseja fazer a seguir no Joomla.

Para salvar o artigo, você pode escolher *Salvar* ou *Salvar & Fechar*. Esta última opção tem opções de menu suspenso para *Salvar & Novo*, *Salvar no Menu* e *Salvar como Cópia*.

- **Salvar** Salve o artigo e mantenha-o aberto para continuar editando.
  É uma boa prática salvar regularmente seu trabalho em artigos mais compridos.
- **Salvar & Fechar** Salve o artigo e vá para a lista de artigos. O botão Salvar & Fechar tem opções adicionais no menu suspenso:
  - **Salvar & Novo** Salve o artigo e então abra uma página **Artigos: Novo**.
    Esta opção economiza tempo ao adicionar vários artigos.
  - **Salvar no Menu** Salve o artigo e abra uma página **Menus: Novo Item**.
  - **Salvar como Cópia** Salve o artigo e, em seguida, abra uma página **Artigos: Editar** 
    com um número entre parênteses anexado ao título, e o mesmo número seguindo um hífen, como -2, por exemplo, no campo de alias. Você pode alterar o título e alterar ou excluir o alias do novo artigo que já foi criado.

Uma mensagem do sistema indicará que o artigo foi salvo com sucesso.

### Erros ao tentar salvar:

- Se você não tiver preenchido os campos obrigatórios, uma mensagem de erro em vermelho aparecerá indicando as informações ausentes que você deve adicionar.
- Você verá uma mensagem de erro se o artigo tiver um alias que já existe. Você pode resolver isso alterando o campo do alias.

## Dicas

- Se você não é o Super Usuário ou Administrador, reserve um tempo para entender como o site está configurado. Só porque você salvou um artigo não significa que ele esteja visível no site. Se estão sendo usadas páginas de Categoria Blog, atribuir a categoria correta exibirá o artigo. Caso contrário, um artigo precisa ser atribuído a um item de menu. Você pode fazer isso no próprio artigo ou através do menu **Menus** do Administrador.
- Tente manter os títulos dos artigos curtos e específicos.
- Embora seja possível, se houver vários usuários adicionando artigos ao site, evite criar novas categorias e tags em artigos. Erros de ortografia e diferenças podem facilmente impedir que artigos sejam exibidos onde deveriam. Criar categorias e tags na respectiva página de lista garante consistência em todo o site.
- Se houver necessidade, faça uso de notas dos artigos. Elas podem ser muito úteis, especialmente quando várias pessoas adicionam artigos.
- Onde quer que você esteja no Joomla, pode adicionar um artigo sem ir até o Painel Inicial - use o Menu do Administrador do Joomla.

*Traduzido por openai.com*

