<!-- Filename: J4.x:Submenus / Display title: Submenus  -->

## Noções Básicas de Menu

No Joomla, três elementos contribuem para a exibição de um menu para o usuário:

- Um Menu é um contêiner para itens de menu.
- Um Item de Menu é um link para uma página do site ou página externa.
- Um Módulo de Menu fornece um método para alocar o menu a uma posição na página e controlar aspectos da aparência ou comportamento do menu ou da página.

Menus simples consistem em listas de links. Às vezes, os membros de uma lista têm relações de pai-filho exibidas como filhos indentados ou listas suspensas. As relações de pai-filho podem ser aninhadas em qualquer nível. No entanto, aninhar além de dois níveis pode tornar as listas pouco atraentes e difíceis de usar.

Há ocasiões em que você pode desejar mostrar os filhos de um menu pai como um submenu separado. Um caso de uso comum é mostrar um submenu à esquerda de uma página, o conteúdo da página no centro e um índice da página à direita. Este tutorial explica como fazer isso.

### Dados de Exemplo

Suponha que você tenha uma série de artigos sobre animais. Pode ser animais de estimação, uma folha de informações veterinárias ou um zoológico. O seguinte é um exemplo curto de estrutura para fins de demonstração:

    Animais
        Gatos
            Burmese
            Azul Russo
        Cães
            Collies
            Pomeranos

As listas podem ser bastante longas, então você pode desejar exibir apenas uma lista de raças de gatos em páginas sobre gatos e apenas uma lista de raças de cães em páginas sobre cães. A captura de tela a seguir mostra o layout alvo que o usuário gostaria de alcançar:

![objetivos dos submenus animais gatos](../../../en/images/menus/submenus-objectives-animals-cats.png)

Neste exemplo, quando o usuário seleciona o item de menu Animais, a página Animais é carregada e o módulo de menu Gatos desaparece (nenhum módulo de Cães também). Selecionar o item de menu Gatos faz com que o módulo de menu Gatos apareça ao lado da página Gatos. Selecionar o item de menu Burmese faz com que a página Burmese apareça. Selecionar o item de menu Cães substitui o módulo de menu Gatos por um módulo de menu Cães ao lado da página Cães.

Para experimentar este tutorial por conta própria, você precisará criar alguns artigos, um menu com itens de menu e três módulos de menu.

## Criar Artigos

Se você for super eficiente, pode criar um artigo e então criar um item de menu a partir do artigo. Para isso, você precisaria primeiro criar um novo menu e seguir alguns passos extras durante a criação do artigo. Portanto, é melhor manter as coisas simples no início e começar com seus novos artigos:

- Selecione **Conteúdo** → **Artigos** → **+** no menu do Administrador.
  Ou selecione o botão `Novo` na lista de Artigos.
- Preencha o formulário como faria para qualquer artigo.
- Selecione o botão `Salvar & Novo` a partir de `Salvar & Fechar` para prosseguir para o próximo novo artigo.

Os dados de exemplo mostrados acima exigem sete artigos.

## Criar um Novo Menu

No menu do Administrador:

- Selecione **Menus **→** Gerenciar**.
- Na página de lista de Menus, selecione o botão `Novo` para criar um novo menu.
- No formulário Adicionar Menus, dê ao menu um título: Animais e um nome único: animais.
- Em alguns casos, pode ser necessário lembrar-se para que serve este menu. Portanto, preencha o campo de descrição.
- Salvar ou Salvar & Fechar.

![submenus new menu](../../../en/images/menus/submenus-new-menu.png)

## Criar Itens de Menu

Existem sete itens de menu para criar.

### Item de Menu Animais

Os novos itens de menu estarão localizados no menu Animais.

- Selecione **Menus**→**Animais**→**+** no menu do Administrador.
- Preencha o formulário Menu: Editar Item.
  - Título: Animais
  - Tipo de Item de Menu: Artigo Único
  - Selecionar Artigo: Animais - este é o artigo principal usado para
    introduzir a série sobre Animais
  - Menu: Animais
  - Pai: - Sem Pai - este é a raiz do menu
- Selecione **Salvar & Novo** na lista suspensa `Salvar & Fechar`.

### Item de Menu Gatos

Isso é muito parecido com o item de menu Animais. Exceto:

- O título deve ser Gatos.
- O artigo selecionado no campo Selecionar Artigo deve ser `Gatos`.
- O Item Pai deve ser definido como `Animais`.

### Item de Menu Burmese

Repita novamente. Exceto:

- O título deve ser Burmese.
- O artigo selecionado no campo Selecionar Artigo deve ser `Burmese`.
- O Item Pai deve ser definido como `Gatos`.

### Mais Itens de Menu

Continue até ter sete itens de menu, um para cada artigo.

## Lista de Itens do Menu

Quando você tiver criado todos os seus itens de menu, verifique se eles têm as corretas relações de pai-filho e se estão na ordem correta. Você pode ordenar pela coluna de Ordenação (a segunda coluna) e usar os controles de arrasto (elipse vertical) para mover os itens para a ordem correta. Se algum item tiver um pai errado, basta selecionar o título do item e alterar o pai no formulário Menus: Editar Item.

![lista de itens de menu de submenus](../../../en/images/menus/submenus-menu-items-list.png)

## Módulos de Menu

Nesta fase, você tem um menu, mas ele não possui um módulo para ser atribuído a uma posição na página. Você pode usar o menu inteiro como um menu padrão ou um menu suspenso. No entanto, o objetivo deste tutorial é demonstrar como criar submenus. Para isso, você precisará de três módulos diferentes:

- Um módulo de Animais para um submenu com itens de menu sobre Animais, Gatos e Cães.
- Um módulo de Gatos para um submenu com itens de menu sobre raças de gatos.
- Um módulo de Cães para um submenu com itens de menu sobre raças de cães.

## Módulo de Submenu de Animais

No menu do Administrador:

- Selecione **Conteúdo** → **Módulos do Site** → **+** ou selecione `Novo` na
  lista de Módulos (Site).
- Selecione o módulo **Menu**.
- No formulário de edição de Módulos: Menu, insira os seguintes dados:
  - Título: Animais
  - Selecionar Menu: Animais
  - Item Base: Animais (este é o item de menu pai)
  - Nível Inicial: 1
  - Nível Final: 2 (isso limita os itens aos subitens de menu em Gatos e
    Cães)
  - Posição: barra lateral-esquerda (ou onde achar mais adequado)

![submenus animais módulo](../../../en/images/menus/submenus-animals-module.png)

### Atribuição de Menu de Animais

Submenus são normalmente exibidos apenas em páginas onde são relevantes, neste caso, em apenas três páginas. Na aba de Atribuição de Menu:

- Defina o campo de Atribuição de Módulo para `Apenas nas páginas selecionadas`. Isso revela uma lista hierárquica de todos os itens em todos os menus.
- Marque as caixas para Animais, Gatos e Cães.
- Marque as caixas para as raças de gatos e cães. Caso contrário, o submenu Animais irá desaparecer em páginas sobre raças.
- Certifique-se de que nenhuma outra caixa esteja marcada.
- Salvar & Fechar

![atribuição de menu do módulo submenu de animais](../../../en/images/menus/submenus-animals-module-menu-assignment.png)

## Módulo de Submenu de Gatos

Isto é muito parecido:

- Selecione **Conteúdo**→**Módulos do Site**→**+** ou selecione `Novo` na
  lista de Módulos (Site).
- Selecione o módulo **Menu**.
- No formulário de edição de Módulos: Menu insira os seguintes dados:
  - Título: Gatos
  - Selecionar Menu: Animais
  - Item Base: Gatos (este é o item de menu pai)
  - Nível de Início: 3
  - Nível Final: Todos
  - Posição: sidebar-left (ou onde for mais apropriado)

### Atribuição de Menu de Gatos

Na Atribuição de Menu

- Defina o campo Atribuição do Módulo para `Apenas nas páginas selecionadas`. Isso
  revela uma lista hierárquica de todos os itens em todos os menus.
- Marque as caixas contra Gatos, Burmese e Azul Russo. Certifique-se de que
  nenhuma outra caixa esteja marcada.
- Salvar & Fechar

## Módulo de Submenu de Cães

Mais do mesmo...

## Alias do Item de Menu

Até aqui, tudo bem! Mas não há link para a página de Animais a partir do Menu Principal, ou de qualquer um dos outros menus do site. A maneira fácil de corrigir isso é com um Alias do Item de Menu. Para este exemplo, é feita uma entrada no menu na parte superior da página, intitulada Menu Principal Blog. No menu do Administrador:

- Selecione **Menus** → **Menu Principal Blog** (ou qualquer que seja o menu preferido do seu site).
- Selecione o botão `Novo` na Barra de Ferramentas.
- Preencha o formulário Menus: Editar Item
  - Título: Animais
  - Alias: criaturas - já existe um item de menu chamado Animais, então você deve usar um alias diferente.
  - Tipo de Item de Menu: Alias do Item de Menu
  - Item de Menu: Animais - selecionado na lista de itens de menu existentes.

![submenus animals alias](../../../en/images/menus/submenus-animals-alias.png)

- Salvar
- Ordenação - após salvar, a ordem pode ser alterada. Neste exemplo, é colocado primeiro.

## Verifique o Resultado

Visualize as páginas do seu site. Neste exemplo, a maioria das páginas não mostrará os submenus na posição do lado esquerdo. O link Animais no menu superior abrirá a página de animais, a partir da qual é possível navegar para as páginas de Gatos ou Cachorros:

![objetivos submenus animais cães](../../../en/images/menus/submenus-objectives-animals-dogs.png)

*Traduzido por openai.com*

