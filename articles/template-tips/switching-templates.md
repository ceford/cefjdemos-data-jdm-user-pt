<!-- Filename: J4.x:Switching_Templates / Display title: Mudança de Modelos  -->

## Modelos de Site e Administrador

O Joomla 4 vem com um único modelo de Site, Cassiopeia, e um único modelo de Administrador, Atum. Você pode obter modelos adicionais de fornecedores de modelos de terceiros, tanto gratuitos quanto pagos, e pode criar seus próprios modelos, mais facilmente como modelos filhos.

É improvável que você queira usar um modelo de Administrador alternativo, então este artigo só cobre modelos alternativos de Site. Para ilustração, foi criado um modelo filho com um tema verde, conforme descrito no artigo sobre Modelos Filhos. Além disso, o site usado para ilustração tem os Dados de Amostra para Teste instalados.

## Estilo de Template Padrão

Um dos seus templates deve ser marcado como padrão. Ele é usado para todas as
páginas, exceto para quaisquer páginas individuais que especificarem um template alternativo.
Para definir o template padrão:

- Selecione **Sistema → Painel de Templates → Estilos de Templates do Site**
  no menu do Administrador.
- Selecione um dos botões na coluna Padrão.

![lista de estilos de templates do site](../../../en/images/templates/switch-templates-styles-list.png)

Dê uma olhada no seu site para garantir que todas as páginas estão usando o
template padrão.

## Usando um Estilo Alternativo

O Joomla permite que você selecione um estilo para uma página específica a partir da designação de menu. A seleção pode ser feita a partir do formulário de Estilo de Template ou do formulário de Edição do Menu. Os métodos produzem o mesmo resultado. O primeiro método é mais conveniente para a seleção de um grupo de itens de menu pertencentes ao mesmo menu.

### Método de Atribuição de Menu de Template

A partir da lista de Estilos de Templates:

- Selecione um estilo que **não** esteja definido como padrão. A estrela amarela indica o estilo padrão.
- Selecione a aba Atribuição de Menu.
- Selecione itens de menu individuais ou alternar todos os itens em um menu.
- Salvar

![aba de atribuição de menu de edição de estilo de templates](../../../en/images/templates/switch-templates-styles-edit-style-menu-assignment.png)

Neste exemplo, todos os itens de menu no menu `Menu Principal de Teste` foram selecionados. Volte ao seu site e selecione qualquer um dos itens de menu que deve usar o template selecionado.

### Método de Detalhes do Menu

Este método é usado para definir o template para itens de menu individuais.

- Selecione **Menus → \[Nome do Menu\]** no menu do Administrador.
- Selecione um link de item de menu na coluna Título para abrir o formulário de edição.
- No campo **Estilo de Template**, selecione o estilo de template desejado.
- Salvar

![formulário de edição de item de menus de templates mostrando a seleção de estilo](../../../en/images/templates/switch-templates-styles-edit-menu-style.png)

Volte ao seu site e selecione o item de menu alterado para verificar se ele é exibido com o estilo de template selecionado.

*Traduzido por openai.com*

