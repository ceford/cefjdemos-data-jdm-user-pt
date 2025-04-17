<!-- Filename: Smart_Search_quickstart_guide / Display title: Início Rápido da Pesquisa Inteligente   -->

## Contexto

A busca tem sido uma funcionalidade do Joomla! desde seus primeiros dias. Ela permitia que os usuários pesquisassem no banco de dados por palavras ou frases e retornassem resultados na ordem em que foram encontrados. Esse formato de busca foi removido e substituído pela Busca Inteligente, que pré-indexa palavras significativas e usa algoritmos de pontuação e filtragem para ajudar a retornar os melhores resultados. A Busca Inteligente é habilitada por padrão no Joomla 4 e 5.

### Esteja ciente

Se você tiver itens de conteúdo que não estão disponíveis para visualização pública, a funcionalidade de autocompletar ainda exibirá os termos contidos nesses itens de conteúdo. Os próprios itens de conteúdo não podem ser visualizados e não serão listados nos resultados de busca, mas se a revelação da presença de uma palavra ou frase em um item de conteúdo restrito for uma preocupação, você deve desabilitar o autocompletar. Para desabilitar o autocompletar, use o seguinte procedimento:

1. Faça login no Administrador.
2. Selecione **Componentes → Busca Inteligente**.
3. Selecione o botão **Opções** na barra de ferramentas.
4. Altere *Sugestões de Pesquisa* de **Mostrar** para **Ocultar**.
5. Selecione **Salvar & Fechar**.

## Preparando plugins de Pesquisa Inteligente

Para que o conteúdo seja exibido nos resultados de busca, ele deve primeiro ser indexado por um dos plugins de Pesquisa Inteligente. Antes de iniciar o indexador, é recomendável que você revise os plugins disponíveis e desative quaisquer que não serão necessários para o seu site. Para revisar os plugins de Pesquisa Inteligente disponíveis, use o seguinte procedimento:

1. Faça login no Administrador.
2. Selecione **Plugins** no *Painel Principal*.
3. Filtre os plugins usando o item **finder** na lista **- Selecionar Tipo -**.
4. Revise a lista de plugins e desative qualquer um que não seja necessário para o seu site selecionando o ícone de tique verde na coluna Status do plugin. Isso deve mudar para um ícone de cruz/círculo cinza para indicar que o plugin está desativado.

## Executando o Indexador

Após revisar os plug-ins de busca, é hora de iniciar o indexador do Smart Search. Isso irá escanear o conteúdo do seu site e construir um índice que permitirá buscas rápidas e inteligentes para os visitantes do seu site. Existem duas maneiras de executar o indexador:

* Pelo menu **Administrador / Smart Search / Índice**. Isso é adequado para sites menores.
* Pela Linha de Comando. Isso é adequado para sites maiores e não deve causar erros de tempo limite. No entanto, sites muito grandes podem realmente precisar de um serviço de busca externo.

### Indexar a partir da interface do Administrador

1. Faça login no Administrador.
2. Selecione os itens de menu **Componentes → Smart Search → Índice**.
3. Selecione o botão **Índice** na barra de ferramentas para iniciar o indexador. Isso fará com que uma janela modal seja carregada com algumas informações de status do indexador e uma barra de progresso.

Dependendo do tamanho do seu site, a indexação pode levar de alguns minutos a algumas horas para ser concluída. O indexador usa requisições AJAX para completar o processo geral em pequenos pedaços para evitar problemas de tempo limite e memória. A indexação será concluída quando a barra de progresso desaparecer e a janela modal se fechar.

### Indexar a partir da CLI

1. Abra uma janela de terminal.
2. Navegue até a pasta cli na raiz do seu site.
3. Use o seguinte comando:<br>
   php joomla.php finder:index
4. Quando o indexador terminar, vá para a página de Conteúdo Indexado no Administrador do Smart Search.

## Conteúdo Indexado

A página de Conteúdo Indexado lista todo o conteúdo indexado. Se você preferir que itens específicos não sejam exibidos nos resultados de busca, pode despublicá-los do banco de dados do Smart Search selecionando a caixa de seleção ao lado do título do item e, em seguida, pressionando o botão Despublicar.

**NOTA IMPORTANTE**: Se o seu site tiver uma grande quantidade de conteúdo, itens de conteúdo particularmente grandes ou espaço em disco restrito, você deve ler sobre [Busca Inteligente em sites grandes](jdocmanual?article=user/smart-search/smart-search-on-large-sites).

## Expondo a Pesquisa Inteligente para Usuários do Site

Agora que o índice de Pesquisa Inteligente está preparado e pronto, você precisa expor a Pesquisa Inteligente para os usuários do seu site. A Pesquisa Inteligente oferece duas maneiras de fazer isso:

### A Interface do Módulo

A Pesquisa Inteligente inclui um módulo que pode ser ativado para exibir um formulário de pesquisa simples em qualquer página, praticamente em qualquer posição. Para ativar o módulo de Pesquisa Inteligente, use o seguinte procedimento:

1. Faça login no Administrador.
2. Selecione o item de menu Extensões → Gerenciador de Módulos.
3. Clique no botão Novo na barra de ferramentas do Gerenciador de Módulos.
4. Selecione "Módulo de Pesquisa Inteligente" na lista de tipos de módulos exibida.
5. Configure o módulo, pelo menos, inserindo um título, selecionando a posição do módulo e ajustando as páginas em que ele será exibido, se desejado. Opções adicionais de configuração do módulo são descritas na tela de ajuda do módulo de Pesquisa Inteligente.
6. Selecione o botão Salvar na barra de ferramentas para publicar o módulo.

### A Interface do Item de Menu

A Pesquisa Inteligente também pode ser vinculada através de um item de menu Joomla, permitindo que os usuários naveguem diretamente para o formulário de pesquisa principal. Para criar um item de menu que vincule à Pesquisa Inteligente, use o seguinte procedimento:

1. Faça login no Administrador.
2. Selecione o item de menu Extensões → Gerenciador de Módulos.
3. Pressione o botão Novo na barra de ferramentas do Gerenciador de Menus.
4. Clique no botão Selecionar ao lado do campo Tipo de Item de Menu.
5. Selecione "Pesquisa" na entrada "Pesquisa Inteligente" na lista de tipos de itens de menu exibida.
6. Configure o item de menu, pelo menos, inserindo um Título de Menu e ajustando o item pai, se desejado.
7. Selecione o botão Salvar na barra de ferramentas para publicar o item de menu.

## Testando, Testando, Testando

Para testar a Pesquisa Inteligente, navegue até um dos itens de menu que você criou e insira uma consulta no formulário de busca ou insira uma consulta em uma das instâncias do módulo de Pesquisa Inteligente. Você deverá ver uma lista de resultados de busca se algum resultado puder ser encontrado para a palavra ou frase que você inseriu. Se nenhum resultado for encontrado, uma mensagem será exibida indicando que nenhum resultado foi encontrado. Se nenhum resultado for encontrado e o sistema tiver uma sugestão de busca com base no seu termo, a frase de busca sugerida será exibida acima da mensagem indicando que nenhum resultado foi encontrado.

*Traduzido por openai.com*

