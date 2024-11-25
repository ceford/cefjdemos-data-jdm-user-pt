<!-- Filename: J4.x:Site_Modules / Display title: Módulos do Site  -->

## Introdução

Os módulos são extensões leves e flexíveis usadas para renderizar trechos de informações em **caixas** dispostas ao redor de um componente em uma página. Um exemplo bem conhecido é o módulo de login. Os módulos são atribuídos por item de menu, permitindo que você decida mostrar ou ocultar um módulo dependendo de qual página o usuário está visualizando no momento.

Alguns módulos estão vinculados a componentes. Por exemplo, o módulo de **últimas notícias** está ligado ao componente de conteúdo para exibir links para os artigos mais recentes. Os módulos não precisam estar vinculados a componentes. Eles nem mesmo precisam estar vinculados a nada e podem ser apenas HTML ou texto estático.

Pode haver várias instâncias do mesmo módulo. Por exemplo, você pode usar uma instância do módulo de Imagem Aleatória para algumas páginas e outra instância para outras páginas, cada uma usando uma pasta de imagens diferente para selecionar imagens.

## Posições dos Módulos

Os módulos são atribuídos a uma posição em uma página definida pelo template em uso. A ilustração a seguir mostra um layout esquemático do template Cassiopeia:

![Diagrama de posições do template Cassiopeia](../../../en/images/modules/cassiopeia-template-positions.png)

E a lista a seguir mostra as posições de módulos disponíveis por nome:

```xml
	<positions>
		<position>barra superior</position>
		<position>abaixo do topo</position>
		<position>menu</position>
		<position>pesquisa</position>
		<position>banner</position>
		<position>topo-a</position>
		<position>topo-b</position>
		<position>principal-topo</position>
		<position>principal-base</position>
		<position>caminho de navegação</position>
		<position>barra lateral-esquerda</position>
		<position>barra lateral-direita</position>
		<position>inferior-a</position>
		<position>inferior-b</position>
		<position>rodapé</position>
		<position>debug</position>
	</positions>
```

## Adicionar um Módulo Principal

Os módulos principais são aqueles fornecidos com uma nova instalação do Joomla. Há milhares de módulos adicionais disponíveis de fornecedores terceiros. Suponha que você gostaria de exibir uma imagem aleatória para tornar seu site mais interessante para os visitantes. No menu do Administrador, selecione **Conteúdo → Módulos do Site** para ver a lista de módulos do site já em uso:

![Lista de Módulos do Site](../../../en/images/modules/cassiopeia-modules-list.png)

Selecione o botão Novo para ver uma lista de módulos do site disponíveis para instalar:

![Módulos do Site disponíveis](../../../en/images/modules/cassiopeia-modules-available.png)

Role para baixo e selecione o módulo Imagem Aleatória. Isso abrirá o formulário de edição **Módulos: Imagem Aleatória** pronto para você preencher.

![Módulo de imagem aleatória](../../../en/images/modules/cassiopeia-module-random-image.png)

- **Título** Este campo é obrigatório.
- **Tipo de Imagem** O padrão é jpg.
- **Pasta de Imagem** Insira um caminho para uma pasta que contenha imagens do tipo que você selecionou.
- **Link** Um URL para redirecionar caso a imagem seja selecionada.
- **Largura** Força todas as imagens a serem exibidas com essa largura em pixels.
- **Altura** Deixe em branco para manter a proporção da imagem.
- **Posição** Selecione uma posição de módulo para que ele realmente apareça em uma página. Na ilustração, foi selecionado sidebar-right.
- **Salvar & Fechar** Ou use o botão Ajuda na barra de ferramentas para descobrir o que os outros campos fazem.

## Ordem dos Módulos

Após salvar, você pode precisar alterar a ordem dos módulos na posição escolhida. Proceda da seguinte forma:

- Na lista de Módulos, selecione o ícone de Ordenação de Colunas no cabeçalho da tabela dos módulos, que é um triângulo combinado para cima/para baixo. Isso irá ordenar a tabela e mostrar símbolos de agarrar itens, uma elipse vertical. Selecione novamente para reverter a ordem de classificação! O símbolo de ordenação da coluna muda: triângulo para cima para indicar ordem de classificação normal, triângulo para baixo para indicar ordem de classificação reversa.
- Agarre e arraste a elipse de Imagem Aleatória para movê-la para cima ou para baixo. Solte quando estiver na sua posição preferida.

## Visualizar o Site

![Visualização do módulo de imagem aleatória do site](../../../en/images/modules/cassiopeia-module-random-image-site.png)

Verifique a aparência do Site. Neste caso, pode ser uma boa ideia centralizar a imagem. Isso pode ser feito da seguinte forma:

- Volte para o formulário de edição e selecione a Aba Avançada.
- No campo Classe do Módulo, insira text-center e Salve.
- Veja o resultado recarregando a página do Site.

Tudo feito?

## Lista de Módulos Principais

- **Artigos - Arquivados** Este módulo mostra uma lista dos meses de calendário contendo Artigos Arquivados. Depois que você alterar o status de um Artigo para Arquivado, esta lista será gerada automaticamente.
- **Artigos - Categorias** Este módulo exibe uma lista de categorias de uma categoria pai.
- **Artigos - Categoria** Este módulo exibe uma lista de artigos de uma ou mais categorias.
- **Artigos - Mais Recentes** Este módulo mostra uma lista dos Artigos mais recentemente publicados e atuais.
- **Artigos - Mais Lidos** Este módulo exibe uma lista dos Artigos publicados que têm o maior número de visualizações de página.
- **Artigos - Flash de Notícias** O módulo Flash de Notícias exibirá um número fixo de artigos de uma categoria específica.
- **Artigos - Relacionados** Este módulo exibe outros Artigos que estão relacionados ao que está sendo visualizado. Essas relações são estabelecidas pelas Palavras-chave. Todas as palavras-chave do Artigo atual são pesquisadas contra todas as...
- **Banners** O módulo de Banner exibe os Banners ativos do Componente.
- **Migalhas de Pão** Este módulo exibe as Migalhas de Pão.
- **Personalizado** Este módulo permite que você crie seu próprio Módulo usando um editor WYSIWYG.
- **Exibição de Feed** Este módulo permite a exibição de um feed sindicado.
- **Rodapé** Este módulo mostra as informações de direitos autorais do Joomla!.
- **Troca de Idiomas** Este módulo exibe um trocador de idiomas no seu site dos idiomas de conteúdo disponíveis.
- **Últimos Usuários** Este módulo exibe os últimos usuários registrados.
- **Login** Este módulo exibe um formulário de login com nome de usuário e senha. Também exibe um link para recuperar uma senha esquecida. Se o registro de usuários estiver habilitado (em Usuários → Gerenciar → Opções),...
- **Menu** Este módulo exibe um menu no Frontend.
- **Imagem Aleatória** Este módulo exibe uma imagem aleatória da pasta escolhida.
- **Pesquisa Inteligente** Este é um módulo de pesquisa para o sistema de Pesquisa Inteligente.
- **Estatísticas** O módulo de Estatísticas mostra informações sobre a instalação do seu servidor junto com estatísticas sobre os usuários do site e o número de Artigos em seu banco de dados.
- **Feeds de Sindicação** Módulo de Sindicação Inteligente que cria um Feed Sindicado para a página onde o Módulo é exibido.
- **Tags - Populares** Este módulo exibe tags usadas no site em uma lista ou em um layout de nuvem. As tags podem ser ordenadas por título ou pelo número de itens marcados e limitadas a um período de tempo específico.
- **Tags - Similares** O módulo de Tags Similares exibe links para outros itens com tags similares. A proximidade da correspondência pode ser especificada.
- **Quem Está Online** O módulo Quem Está Online exibe o número de Usuários Anônimos (Visitantes) e Usuários Registrados (usuários logados) que estão acessando o site no momento.
- **Envolver** Este módulo exibe uma janela iframe para um local especificado.

*Traduzido por openai.com*

