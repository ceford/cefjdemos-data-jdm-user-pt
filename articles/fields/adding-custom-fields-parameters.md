<!-- Filename: J3.x:Adding_custom_fields/Parameters_for_all_Custom_Fields / Display title: Parâmetros de Campo -->

## Formulário de Entrada de Dados de Campo

Há 16 ou mais tipos de campos disponíveis na lista de seleção Tipo no formulário de entrada de dados de campo. A maioria dos campos do formulário é igual para todos os tipos de campo, mas outros mudam de acordo com o tipo selecionado. Este artigo descreve os parâmetros comuns para todos os campos. O formulário de entrada de dados também é o mesmo para campos de **Artigo**, **Contato** e **Usuário** e seus campos de Categoria.

Uma lista de Campos estará inicialmente vazia. Para começar, por exemplo, com campos de Artigo:
* Selecione **Novo** na Barra de Ferramentas na lista de Artigos: Campos.

O formulário consiste em um campo de Título e quatro abas.

![Parâmetros de campo aba geral](../../../en/images/fields/fields-parameters-general-tab.png)


## Título

O título é exibido na página de lista *Artigos: Campos*, onde pode ser selecionado para abrir o campo para edição. O título não é exibido quando você cria um artigo ou no frontend. No entanto, o Rótulo pode ser criado a partir do Título e é exibido no formulário de entrada de dados do Artigo e pode ser exibido na exibição do Artigo.

### Aba Geral

#### No painel esquerdo:

- **Tipo** Selecione um dos 16 tipos de campo na lista suspensa. Quando você salva o campo, esse tipo é permanente. Você não pode alterá-lo depois.
- **Nome** O nome será usado para identificar o campo. Deixe em branco e o Joomla preencherá um valor padrão a partir do título.
- **Rótulo** Use um rótulo descritivo para o campo. Este texto não é traduzível. Se você não inserir nenhum texto para um rótulo, o texto do título será usado como texto do rótulo.
- **Descrição** Texto que será mostrado como uma dica de ferramenta para descrever o propósito do campo durante a entrada de dados. Este texto não é traduzível e não será exibido no frontend.
- **Obrigatório** Defina como *Sim* se este é um campo obrigatório que deve ser preenchido antes de enviar um artigo.
- **Usar Apenas em Subformulário** [Explicação necessária]
- **Valor Padrão** Defina um valor padrão, se apropriado. Este texto não é traduzível.
- **Filtro** Escolha uma das opções disponíveis na lista suspensa. O campo será validado para conformidade com o tipo de dado selecionado.
- **Comprimento Máximo** Defina isso para limitar o comprimento dos dados de texto que podem ser inseridos.

### No painel direito:

- **Status** Defina um estado de publicação selecionado entre *Publicado*, *Não Publicado*, *Arquivado* ou *Lixo*.
  - Publicado: O campo é visível enquanto edita um artigo ou um contato. E é visível no Frontend.
  - Não Publicado: O campo não será visível para usuários enquanto edita um artigo ou um contato.
  - Arquivado: O campo não será mais exibido ao editar um artigo ou um contato. Você pode abri-lo no gerenciador de campos quando definir o filtro para arquivado.
  - Lixo: O campo é excluído, mas ainda está no banco de dados. Ele pode ser permanentemente excluído do banco de dados com a função Esvaziar Lixeira no Gerenciador de Campos.
- **Grupo de Campos** Selecione Nenhum ou um Grupo selecionado de uma lista predefinida. Grupos aparecem como abas separadas no formulário de entrada de dados do Artigo.
- **Categoria** Você pode atribuir um campo a uma ou mais categorias de campos. Note que o padrão *Todos* não inclui artigos *não categorizados*.
- **Acesso** O nível de acesso de visualização para este campo.
- **Idioma** Selecione o idioma para este campo personalizado. Se você não estiver usando o recurso de multi-idioma do Joomla, mantenha o padrão *Todos*.
- **Nota** Um campo opcional para fazer suas notas pessoais para o campo.

### Aba de Opções

![Parâmetros do campo aba geral](../../../en/images/fields/fields-parameters-options-tab.png)

#### Opções de Formulário

- **Placeholder** Um texto de espaço reservado que aparecerá dentro do campo personalizado como uma dica para a entrada. O espaço reservado está ativo no Backend enquanto cria um artigo. Você não vê isso no Frontend.
- **Classe do Campo** Os atributos de classe do campo quando o campo é renderizado. Se classes diferentes forem necessárias, liste-as com espaços.
- **Classe do Rótulo (Formulário)** Os atributos de classe do campo no formulário de edição. Se classes diferentes forem necessárias, liste-as com espaços.
- **Editável em** Em qual parte do site o campo deve ser exibido: Site, Administrador ou Ambos.
- **Atributo Showon** Mostrar ou ocultar condicionalmente o campo dependendo do valor de outros campos. A sintaxe a ser usada aqui, por exemplo:
  - `list-of-items:valor1[OU]list-of-items:valor2` onde
  - list-of-items: O nome de um campo já criado do qual este campo depende.
  - valor1: O valor necessário no campo list-of-items para este campo ser exibido.
  - [OU] Para criar uma escolha entre múltiplos campos. No exemplo, este campo será exibido quando o campo list-of-items tiver um valor de valor1 OU valor2.
  - [E] Para combinar múltiplos campos. Este campo será exibido apenas quando os campos list-of-items tiverem o valor valor1 E valor2.
  - Você também pode usar o valor 'não é igual' como em list-of-items!:valor1. A sintaxe mostrará este campo apenas quando list-of-items não for igual a valor1.
  - Para exibir este campo quando o campo list-of-items tiver sido selecionado e não tiver um valor vazio, use a sintaxe list-of-items!: (sem um valor especificado).
  - Nota: Campos de Subformulário lidam com o nome list-of-items de forma diferente. Se você criar um campo de Subformulário e adicionar este campo condicional para um campo que está criando lá, você precisa usar field[ID] em vez de list-of-items, onde ID é o id do campo list-of-items. Portanto, o atributo showon para este campo condicional que você está criando precisa ser: field36:valor1[OU]field36:valor2 onde 36 é o ID do campo 'Lista de itens'. Isso precisa de esclarecimento!

#### Opções de Exibição

- **Classe de Exibição** A classe do contêiner do campo na saída.
- **Classe de Valor** A classe do valor do campo na saída.
- **Rótulo** Mostrar ou Ocultar o rótulo.
- **Classe do Rótulo (Saída)** A classe de saída do rótulo se o rótulo for exibido.
- **Exibição Automática** O Joomla oferece alguns eventos de conteúdo que são acionados durante o processo de criação de conteúdo. Este é o local para definir como os campos personalizados devem ser integrados no conteúdo. Você pode escolher *Após o Título*, *Antes de Exibir Conteúdo*, *Após Exibir Conteúdo* ou *Não exibir automaticamente*.
- **Prefixo** Texto fixo a ser exibido antes de um campo, por exemplo, £.
- **Sufixo** Texto fixo a ser exibido após um campo, por exemplo, EUR.
- **Layout** Selecione um layout a partir de modelos disponíveis e substituições.
- **Exibir Quando Somente Leitura** Selecione entre *Herdar*, *Sim* ou *Não*. Se o campo for somente leitura (talvez o usuário não tenha o nível de acesso), o campo deve ser exibido ou oculto.

#### Pesquisa Inteligente

- **Índice de Pesquisa** Selecione a partir da lista de opções. Aviso: Quando *Tornar pesquisável* é selecionado, o conteúdo do campo é indexado com as permissões de visualização do item de conteúdo. Isso pode levar a uma divulgação inesperada de informações.

### Aba de Publicação

![Parâmetros do campo aba geral](../../../en/images/fields/fields-parameters-publishing-tab.png)

### Aba de Permissões

![Parâmetros do campo aba geral](../../../en/images/fields/fields-parameters-permissions-tab.png)

*Traduzido por openai.com*

