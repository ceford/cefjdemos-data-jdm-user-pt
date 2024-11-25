<!-- Filename: J4.x:Adding_a_Custom_Administrator_Menu / Display title: Menu Personalizado de Administrador  -->

## Introdução

Suponha que você tenha um usuário a quem deseja permitir executar apenas uma tarefa no seu site. Considere o caso de uma organização que tem filiais espalhadas por todo o mundo e a única tarefa que cada filial tem permissão de realizar é marcar localidades em um mapa para exibição no site. O componente para essa tarefa é o Ffmap, mas isso não será abordado aqui, exceto pelos itens de menu do Administrador envolvidos.

Para realizar essa tarefa, você precisa criar um Grupo de Usuário personalizado, atribuir um usuário a esse grupo e criar um menu personalizado para uso desse usuário.

## Criar um Grupo de Usuários

- Selecione **Usuário → Usuários → Grupos** no menu do Administrador.
- Selecione o botão **Novo** na Barra de Ferramentas.
  - Insira um **Título *para o Grupo,*** *Ramo* neste caso.
  - Selecione **Público** como o grupo pai. Isto é importante - você não quer herdar permissões de outro grupo.
- Selecione **Salvar e Fechar** na Barra de Ferramentas.

## Definir Permissões Globais para o Grupo

- Selecione **Configuração Global** no Painel Inicial.
- Selecione a aba **Permissões**.
- Selecione o item **Filial**.
- Defina **Login de Administrador** como **Permitido**.
- Selecione **Salvar e Fechar** na Barra de Ferramentas.

Neste ponto, qualquer usuário atribuído ao Grupo de Usuários da Filial poderá 
fazer login na interface do Administrador e ver o Painel Inicial. Existem 
alguns módulos do painel visíveis porque seu nível de acesso foi definido 
como Público, por exemplo: Usuários Conectados, Artigos Populares e Artigos 
Recentemente Adicionados. É melhor definir o acesso a esses módulos como 
Especial. Não haverá itens de menu para o usuário ver.

## Definir Permissão de Componente para o Grupo

Escolha uma das opções:

- Selecione o componente **Ffmap** no menu do Administrador.
- Selecione o botão **Opções** do FFmap na Barra de Ferramentas para abrir sua
  tela de Configuração.

Ou:

- Selecione **Configuração Global** no Painel Inicial.
- Selecione Ffmap na lista de componentes.

Em seguida:

- Selecione a aba **Permissões** e depois o item **Ramo**.
- Configure Acesso à Interface de Administração, Criar, Excluir, Editar, Editar Estado,
  Editar Próprio e Editar Valor de Campo Personalizado para **Permitido**.
- Selecione **Salvar e Fechar** na Barra de Ferramentas.

## Criar um novo menu de Administrador

- Selecione **Menu → Gerenciar** no menu do Administrador.
- Selecione **Administrador** na lista suspensa Site/Administrador.
- Selecione o botão **Novo** na Barra de Ferramentas.
- Insira um título para o menu, por exemplo, **Menu Filial**, e um ID único, por exemplo, **menu-filial**.
- Selecione **Salvar e Fechar** na Barra de Ferramentas.

## Criar um Módulo para o menu

Na lista de Menus, selecione o botão **Módulos Vinculados** no registro do Menu da Filial.

- Insira um Título para o módulo, por exemplo, **Menu da Filial**.
- Selecione Menu para Mostrar: **Menu da Filial**.
- Defina Verificar Menu como **Não**, caso contrário, aparecerão mensagens de aviso sobre funções de Administrador ausentes.
- Selecione a posição: **menu**.

## Criar um Contêiner de Menu de Componentes

- Na lista de Menus, selecione o ícone de Itens de Menu para o Menu de Filial. Isso abrirá a lista de itens, vazia neste estágio.
- Selecione o botão **Novo** na Barra de Ferramentas.
- Insira um título para o item de menu: **Componentes de Filial**.
- Selecione o Tipo de Item de Menu **Selecionar Botão**.
  - Na caixa de diálogo modal, role para baixo até o item **Links do Sistema** e expanda o painel.
  - Selecione o tipo de item **Contêiner de Menu de Componentes**.
- De volta ao formulário de configuração do menu, selecione **Mostrar Nenhum** para ocultar todos os itens do menu de Componentes (vermelho).
- Role para baixo até os itens Ffmap e clique nos botões Ocultar para torná-los Mostrar (verde).
- Selecione **Salvar e Fechar** na Barra de Ferramentas.

## Captura de Tela

![seleção de componente de menu de administrador personalizado](../../../en/images/menus/menus-custom-administrator-menu.png)

## Resultado

Crie um usuário no Grupo de Filial para você mesmo testar. Faça login na interface do Administrador como esse usuário para ver o resultado:

![resultado do menu personalizado do administrador](../../../en/images/menus/menus-custom-administrator-menu-result.png)

## Notas

Se você adicionar outro componente mais tarde, ele será adicionado ao Contêiner do Menu de Componentes e ficará visível por padrão. Você precisará voltar ao item de menu Administrador e definir o novo conteúdo para Ocultar.

Se o componente estiver configurado para incluir itens de menu em cada uma das visualizações de lista do Administrador, por meio da inclusão de arquivos default.xml, você poderá adicionar itens de menu diretamente ao menu personalizado e evitar o uso do Contêiner do Menu de Componentes.

O menu Componentes do Ramo permanecerá como parte do menu Administrador - duplicação inevitável!

*Traduzido por openai.com*

