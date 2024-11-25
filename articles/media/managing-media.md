<!-- Filename: J4.x:Managing_Media / Display title: Gerenciando Mídia   -->

## Introdução

No Joomla, mídias são imagens e arquivos que aparecem como ilustrações ou links em artigos, módulos, templates, e assim por diante. Uma característica importante das mídias é que elas são entregues diretamente pelo servidor web sem serem processadas pelo código do Joomla. Isso é rápido e eficiente. Também esteja ciente de que as mídias geralmente são armazenadas na pasta **images** do seu site Joomla. Não confunda isso com a pasta **media**, que contém arquivos de javascript e folhas de estilo.

As imagens e arquivos de mídia são gerenciados com o componente de Mídia do Joomla. Ele permite que você organize o conteúdo de mídia em uma estrutura de pastas, faça upload de itens individuais, execute algumas funções elementares de edição de imagem e coloque imagens e links diretamente nos artigos.

## Como Acessar

A partir da interface do Administrador do Joomla, existem várias maneiras de abrir o componente de Mídia:

- Selecione **Conteúdo → Mídia** no menu do Administrador.
- Selecione **Painel do Site → Mídia** no Painel Inicial.
- Selecione **Conteúdo do CMS → Mídia** em uma tela de edição de artigo.

Nos dois primeiros casos, o componente de Mídia aparece em uma tela de componente normal. No último, aparece em uma janela modal.

## Captura de Tela

A imagem a seguir mostra a página de Mídia logo após a instalação do Joomla, mas com a pasta cassiopeia/sampledata selecionada. Uma pasta *files* foi adicionada para armazenar arquivos não-imagens e uma pasta extra chamada *garbage* foi adicionada para ilustrar a exclusão de pastas:

![Página de Mídia mostrando dados de exemplo cassiopeia](../../../en/images/media/media-sample-data-cassiopeia.png)

## Gerenciamento de Pastas

Os nomes das subpastas em sua árvore de pastas de imagens tornam-se parte da URL da imagem, portanto é importante que, por motivos de vinculação e otimização para mecanismos de busca, os nomes sigam uma convenção:

- tudo em minúsculas
- sem espaços ou pontuação
- se necessário, use um sinal de menos para criar palavras legíveis, por exemplo, arvores-deciduas em vez de arvores_deciduas.

Antes de criar muito conteúdo para seu site, pode valer a pena pensar em como você pode categorizar seu conteúdo e talvez criar uma árvore de pastas de imagens que seja semelhante à sua árvore de categorias. Caso contrário, você pode acabar com um número muito grande de imagens e arquivos na raiz da sua árvore de imagens, o que se tornará difícil de gerenciar. Se você decidir mover imagens para uma estrutura melhor mais tarde, terá que encontrar os links para essas imagens em seus artigos e alterá-los. Isso pode ser uma tarefa demorada e assustadora!

### Navegação em Pastas

Use a árvore de pastas na coluna **Local** para selecionar uma pasta. No caso ilustrado acima, a pasta cassiopeia foi selecionada primeiro. Isso revelou a pasta *sampledata*, que foi então selecionada para mostrar seu conteúdo.

A localização atual também é indicada nas migalhas de pão acima das imagens. Neste caso **images → cassiopeia → sampledata**.

Se você selecionar uma pasta diferente, a pasta anterior no mesmo nível será fechada.

### Criando uma pasta

- Selecione a pasta pai sob a qual a nova pasta deve ser criada.
- Selecione o botão **Create New Folder**.
- Na janela popup *Create New Folder*, insira um nome para a pasta no campo **Folder Name**.
- Clique no botão **Create**.
- A nova pasta aparecerá na pasta pai selecionada junto com uma mensagem de sistema de Sucesso verde.

### Excluindo uma pasta

**Aviso: excluir uma pasta também irá excluir todo o conteúdo da pasta!**

- Selecione o pai da pasta a ser excluída usando a árvore de diretórios mostrada sob **Local**. Isso mostrará todas as pastas e arquivos no pai.
- Mova o cursor sobre a pasta a ser excluída na área de mídia. Ela ficará cinza e um botão aparecerá perto do canto superior esquerdo.
- Selecione o botão. Um tique aparecerá para indicar que está selecionado.
- Selecione o botão **Delete** na Barra de Ferramentas.
- Na caixa de diálogo de confirmação **Confirm Delete**, selecione o botão **Delete**. A pasta será excluída junto com seus arquivos, subpastas e seus arquivos.

A pasta selecionada para exclusão é ilustrada abaixo:

![Página de mídia mostrando a pasta lixo](../../../en/images/media/media-sample-data-garbage-select.png)

## Barra de Ferramentas da Área de Mídia

Esta é a barra acima da lista de imagens, arquivos e pastas que possui botões para uma variedade de tarefas.

### Caixa de Seleção

Uma caixa de seleção que permite selecionar todos os itens na pasta exibida na área de mídia. Você pode querer usá-la para excluir todos os itens atuais sem apagar a pasta.

### Trilhas de Navegação

Use os nomes das pastas acima da área de mídia para retroceder na hierarquia de pastas.

Clique duas vezes em um nome de pasta na área de mídia para abrir essa pasta.

### Pesquisa

Se você tiver uma longa lista de imagens e arquivos, poderá procurar por itens que contenham qualquer grupo de caracteres. A pesquisa é progressiva: à medida que você adiciona caracteres ao termo de pesquisa, a lista é reduzida para apenas aqueles que contêm essa sequência de caracteres.

### Ampliar

Use os botões de ampliação para aumentar ou reduzir o tamanho da miniatura. Dependendo do tamanho da tela, você poderá ver 2, 4, 6 ou 8 imagens de miniaturas lado a lado.

### Modos de Exibição: Lista ou Miniaturas

No modo de visualização em miniaturas, selecione o símbolo de lista para alternar para a visualização em lista. No modo de lista, selecione o símbolo de miniaturas para alternar para a visualização em miniaturas. No modo de lista, você verá informações sobre o tamanho e as dimensões da imagem, entre outros dados.

### Ícone de Informação

Selecione o ícone de Informação para abrir um painel lateral mostrando informações sobre o que estiver selecionado.

*Traduzido por openai.com*

