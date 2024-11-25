<!-- Filename: J4.x:Module_Display_by_Menu_Item / Display title: Exibição do Módulo por Item de Menu -->

## Introdução

No Joomla, é comum que diferentes módulos apareçam em páginas diferentes. E, às vezes, diferentes módulos são apresentados a diferentes grupos de usuários. O comportamento de exibição do módulo é controlado por uma combinação de Atribuição de Menu e Permissão de Acesso no formulário de edição do módulo. Por padrão, um módulo é exibido em todas as páginas e para todos os grupos de usuários.

## Acesso

Este campo está na aba Módulo do formulário de inserção de dados do módulo. Ele está no painel à direita e não deve ser confundido com a aba Permissões. As opções disponíveis são:

- Público - visível para todos os grupos de usuários.
- Convidado - não visível após o login.
- Registrado - apenas visível após o login.
- Especial - apenas visível após o login para grupos de usuários que não
  sejam Registrados.
- Super Usuário - visível apenas para este grupo de usuários.

## Atribuição de Menu

Existem quatro opções de atribuição de menu:

- Em todas as páginas
- Nenhuma página
- Apenas nas páginas selecionadas
- Em todas as páginas, exceto as selecionadas

Para as duas últimas, um painel de Seleção de Menu é exibido. Inicialmente, os menus que ele contém estão totalmente expandidos, mas podem ser recolhidos com o botão **Expandir as Subárvores do Menu** *Nenhuma*. Em seguida, expanda o menu de interesse.
![atribuição de menu do módulo](../../../en/images/modules/module-display-by-menu.png)

Selecione os Itens de Menu para exibir ou não exibir o módulo conforme desejado.

## Exemplos

### Breadcrumbs Não na Página Inicial

- Abra o módulo de Breadcrumbs.
- Selecione *Em todas as páginas, exceto aquelas selecionadas*
- Selecione *Nenhum* após **Atribuir a Itens de Menu**
- Encontre o item de menu da Página Inicial e marque sua caixa de seleção.
- Salve
- Verifique o site - breadcrumbs devem estar presentes em todas as páginas, exceto na Página Inicial.

*Traduzido por openai.com*

