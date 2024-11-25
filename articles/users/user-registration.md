<!-- Filename: J4.x:User_Registration / Display title: Registro de Usuário  -->

## Política de Registro

Em um site Joomla, usuários registrados podem fazer login para ver ou interagir com conteúdos que usuários não registrados não podem acessar. O login no site e o login de Administrador são tratados separadamente, embora exista uma configuração global que permite combiná-los. Alguns sites têm um pequeno número de usuários criados por um Administrador. Outros sites têm tantos usuários que eles precisam se registrar e ativar suas contas por conta própria. A forma como os usuários se registram no seu site é configurada no formulário *Usuários: Opções*.

## Permitir Registro de Usuário

O auto-registro de usuários é desativado por padrão. Qualquer novo usuário deve ser criado por um Gerente ou Administrador. O auto-registro pode ser permitido com algumas alterações simples no formulário *Usuários: Opções*.

- Selecione **Usuários → Gerenciar** no menu do Administrador.
- Selecione o botão *Opções* na Barra de Ferramentas.
- Defina **Permitir Registro de Usuário** como **Sim**.
- O **Grupo de Registro de Novos Usuários** deve ser **- Registrado -** a menos que haja uma boa razão para ser algo diferente.
- A **Ativação de Conta de Novo Usuário** deve ser **Automática** ou **Administrador**.
  - Automática: O usuário receberá um e-mail com um link de ativação. A conta será ativada quando o usuário clicar no link de ativação.
  - Administrador: O usuário receberá um e-mail com um link de ativação. Quando o usuário clicar neste link, o Administrador do Site será notificado via e-mail. O Administrador do Site então precisará ativar a conta do usuário.

![Opções de configuração de usuário](../../../en/images/users/users-configuration-user-options.png)

- **Salvar & Fechar**
- Adicione um módulo de *Login*. Ou
- Adicione um item de menu *Usuários: Formulário de Login* e um item de menu *Usuários: Logout*.

## Desativar Autoinscrição

- Defina **Permitir Registro de Usuário** como **Não**.

## Adicionando um Novo Usuário

Se o auto-registro não for permitido, qualquer novo usuário deve ser criado por um Administrador. Prossiga da seguinte forma:

- Selecione o ícone **Usuários +** no painel do Site do Painel Inicial. Ou
- Selecione **Usuários **→** Gerenciar +** no menu do Administrador.
- Preencha o formulário **Detalhes do Novo Usuário**. A maioria dos campos tem valores padrão adequados.

![Página de entrada de dados de novo usuário](../../../en/images/users/users-new-user.png)

- Selecione a aba **Grupos de Usuários Atribuídos** e marque a caixa correspondente ao grupo de usuários desejado. Registrado é marcado por padrão.
- **Salvar & Fechar**.
- Na lista de Usuários, verifique se a nova conta de usuário está Habilitada (marca verde na coluna de Habilitado).

## Bloquear um Usuário

O melhor método para lidar com um usuário problemático é desativar a conta do usuário ao invés de excluí-la. Esta medida pode ser usada para suspender o usuário e pode ser revertida caso o usuário prometa se comportar. Excluir uma conta quebraria qualquer vínculo com o conteúdo contribuído pelo usuário, como autoria de artigos, e poderia dar ao usuário a oportunidade de se registrar novamente com o mesmo endereço de e-mail.

Para bloquear um usuário:

- Selecione **Usuários → Gerenciar** no menu do Administrador.
- Encontre o usuário na lista de *Usuários*. Use o filtro de texto, se necessário.
- Selecione o ícone de Habilitado que aparece como um tique verde ao lado do nome do usuário. Um rótulo **Bloquear** aparecerá ao passar o mouse.

![Página de entrada de dados de novo usuário](../../../en/images/users/users-hover-block.png)

- Selecione o ícone de *Habilitado*. A página será recarregada com o ícone de Habilitado aparecendo como um cruz cinza.

## Desbloqueando um Usuário

Simples:

- Alterne o ícone *Ativado* de volta para um tique verde.

*Traduzido por openai.com*

