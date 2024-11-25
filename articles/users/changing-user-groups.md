<!-- Filename: Changing_user_groups / Display title: Alteração de Grupos de Usuários -->

## Herança de Grupos

As listas de grupos usam um padrão de herança. Por exemplo, um usuário no grupo Autor herda todos os privilégios do grupo Registrado e ganha alguns privilégios extras. Da mesma forma, um usuário no grupo Editor herda todos os privilégios do grupo Autor e ganha mais alguns privilégios extras. Os grupos de backend herdam o nível mais alto de privilégio no frontend.

Por essa razão, você só precisa selecionar um grupo para um usuário individual - o grupo com mais privilégios.

## Passos

Você pode alterar o grupo de um usuário seguindo estes passos. É necessário fazer login como Administrador ou Super Usuário para poder alterar os grupos de um usuário. Além disso, um Administrador não pode tornar a si próprio ou outros em Super Usuários.

1. No *Painel Inicial*, selecione o item **Usuários**. Ou...
2. No item de menu *Usuário*, selecione **Usuários** e depois **Gerenciar**.
3. Encontre o usuário desejado na lista de usuários. Você pode pesquisar pelo nome, nome de usuário, email ou id: prefixo.
4. Selecione o nome do usuário para editar.
5. Selecione a guia *Grupos de Usuários Atribuídos*.
6. Selecione o grupo ao qual o usuário precisa pertencer.
7. Selecione *Salvar*.  

## Lista de Controle de Acesso (ACL) para Joomla

A seguir, encontra-se a Lista de Controle de Acesso (ACL) para Joomla. O grupo de usuários está listado, e os marcadores abaixo descrevem as permissões associadas a esse grupo.

### Grupos do Frontend

#### Convidado

- Visualizar site público e artigos públicos

#### Registrado

- Privilégios do Grupo Convidado
- Visualizar artigos registrados
- Sem acesso a itens restritos ao Grupo Convidado

#### Autor

- Privilégios do Grupo Registrado
- Criar novos artigos
- Editar artigos que possuem
- Visualizar conteúdo especial

#### Editor

- Privilégios do Grupo Autor
- Editar todos os artigos, incluindo os não publicados

#### Publicador

- Privilégios do Grupo Editor
- Publicar artigos

### Grupos do Backend

Esses grupos permitem que você faça login no Administrador através da URL */administrator*.

#### Gerente

- Privilégios do Grupo Publicador
- Acesso ao Backend do Administrador

#### Administrador

- Privilégios do Grupo Gerente
- Criar novos usuários
- Instalar extensões

#### Super Usuário

- Privilégios do Administrador
- Alterar modelo do site
- Alterar configuração global

*Traduzido por openai.com*

