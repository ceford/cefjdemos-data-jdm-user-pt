<!-- Filename: Enabling_the_Login_Form_module / Display title: Formulário de Login -->

## Métodos de Login no Site

Existem duas maneiras de permitir que usuários registrados façam login na interface de um site. Há um item de menu **Formulário de Login** encontrado no grupo de itens de menu Usuários. Ele precisa ter suas permissões de *Acesso* definidas como *Convidado*. Um segundo item de menu *Logout* é necessário, com suas permissões de *Acesso* definidas como *Registrado*.

A alternativa é o módulo **Formulário de Login**. Ele é instalado por padrão na posição *sidebar-right* em uma nova instalação do Joomla. Este módulo pode ser movido para outra posição, despublicado, movido para a lixeira e excluído. Estas ações se aplicam a uma instância do módulo e não ao código do módulo. Assim, você pode criar um novo módulo *Formulário de Login* ou fazer um duplicado, talvez para uso em diferentes templates. O módulo Formulário de Login muda sua exibição após o login para apresentar um botão de *Logout*.

## O Módulo de Formulário de Login

Para publicar um Formulário de Login não publicado:

* Selecione **Conteúdo → Módulos do Site** no menu do Administrador.
* Localize o módulo **Formulário de Login**.
* Se o ícone de **Status** for um tique verde dentro de um círculo, ele já está habilitado. Se o ícone de Status for uma cruz cinza, ele está atualmente desabilitado. Selecione o ícone para habilitar o módulo.
* Se o módulo *Formulário de Login* não estiver presente na lista, configure as Opções de Filtro, - Selecione o campo Status para *Todos* ou *Lixeira* para ver se foi movido para a lixeira. Se for esse o caso, ele pode ser publicado selecionando seu ícone de lixeira.
* Se o módulo de Formulário de Login estiver ausente, crie um novo.

Para criar um novo Formulário de Login ou um segundo Formulário de Login:

* Selecione **Conteúdo → Módulos do Site** no menu do Administrador.
* Selecione o botão **Novo** na Barra de Ferramentas.
* Na lista de Módulos, selecione o item **Login**.
* Preencha o formulário de entrada de dados *Módulos: Login*.
  - Insira um Título único.
  - Selecione uma posição de template ou crie uma posição nomeada para uso em um artigo.
  - Preencha outros campos conforme apropriado.
* **Salvar & Fechar**
* Teste se o módulo aparece corretamente no frontend do site.

## Para atribuir o módulo Formulário de Login a páginas da web selecionadas

Você pode fazer o módulo Formulário de Login aparecer em uma ou mais páginas ao atribuí-lo a Itens de Menu selecionados. Isso é feito usando os campos no grupo Atribuição de Menu na tela de edição do módulo:

- Selecione a aba **Atribuição de Menu**.
- A lista **Atribuição de Módulo** tem quatro opções:
  - **Em todas as páginas**: O módulo Formulário de Login aparecerá em todas as páginas.
  - **Em nenhuma página**: O módulo Formulário de Login não aparecerá em nenhuma página.
  - **Somente nas páginas selecionadas**: Uma lista de todos os menus e itens de menu do seu site aparecerá. O módulo Formulário de Login aparecerá nas páginas selecionadas nesta lista.
  - **Em todas as páginas, exceto as selecionadas:** O Formulário de Login aparecerá em todas as páginas não selecionadas.
- **Seleção de Menu**: Mostra uma lista de todos os Menus e Itens de Menu a partir dos quais um ou mais podem ser selecionados. Este campo é usado apenas se o campo **Menus** estiver configurado como **Selecionar Item(ns) de Menu da Lista**.

  ![atribuição de menu de módulo](../../../en/images/modules/modules-login-menu-assignment.png)

## Para personalizar o módulo de Formulário de Login

Se você deseja mudar a aparência do módulo de Login, pode adicionar estilos,
seja estilos do Bootstrap ou seus próprios estilos definidos no arquivo user.css do seu template. Adicione os estilos na aba **Avançado** do formulário de edição de Módulos: Login.

Se você deseja mudar as informações exibidas no formulário de Login, pode criar
uma substituição de template. Veja a seção sobre
[Sobrescrições de Template](jdocmanual?article=user/templates/template-overrides)
para mais detalhes.

*Traduzido por openai.com*

