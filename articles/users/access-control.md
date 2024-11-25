<!-- Filename: J4.x:Access_Control / Display title: Controle de Acesso -->

## Introdução

O Joomla possui um mecanismo sofisticado para controlar quem pode ver e manipular conteúdo em um site Joomla. A parte do **quem** é configurada nas opções do componente Usuários com Grupos de Usuários e Níveis de Acesso. A parte do **manipular** é configurada nas Permissões de Ação, seja nas configurações de Configuração Global, nas configurações de Componentes ou nas configurações de Itens. Por exemplo, valores padrão configurados em Permissões Globais podem ser sobrescritos nas Permissões de Artigos (todos os artigos) e as Permissões de Artigos podem ser sobrescritas nas Permissões de Artigo individual.

## Grupos de Usuários

Os Grupos de Usuários são utilizados para dividir os usuários do site em grupos com diferentes responsabilidades. Por exemplo, membros do grupo de usuários Autor têm permissão para fazer login no site, criar artigos e editar seus próprios artigos. Nada mais! Membros do grupo Super Usuários têm responsabilidade sobre todos os aspectos da gestão e operação do site. O Joomla fornece nove grupos de usuários padrão e você pode criar mais, se necessário.

![Lista de grupos de usuários](../../../en/images/users/access-control-users-groups-list.png)

Os grupos de usuários padrão são configurados com relações de pai e filho para minimizar a duplicação de permissões. Exemplos de herança:

- Um membro do grupo Registrado não tem permissão para Login de Administrador. Nem Editor ou Publicador.
- Um membro do grupo Autor tem permissão para Criar e Editar Próprio. O mesmo acontece com Editor e Publicador, mas eles têm permissões extras.

Você pode criar novos grupos de usuários para finalidades especiais, conforme necessário. Por exemplo, você pode querer criar um grupo que tenha permissão de Login de Administrador, mas com acesso restrito a um único componente. Há um exemplo de tal grupo de usuários personalizado no final deste tutorial.

## Níveis de Acesso

Cada vez que você cria um objeto, como um artigo, um módulo ou um item de menu, você verá um campo de Acesso, geralmente na coluna direita do formulário de entrada de dados. É uma lista suspensa que oferece a escolha entre Público, Visitante, Registrado, Especial e Super Usuários. O padrão é Público. Os níveis de acesso padrão para visualização são mostrados na captura de tela a seguir:

![Níveis de acesso dos usuários](../../../en/images/users/access-control-users-access-levels.png)

Exemplos:

- Se você criar um módulo do site e definir o Acesso como Registrado, ele só será visto por usuários que estiverem logados no site.
- Se você criar um item de menu do site e definir o Acesso como Super Usuários, ele só será visto por Super Usuários que estiverem logados no site.

## Permissões

As Permissões de Configuração Global são o ponto de partida a partir do qual as configurações de permissão nos componentes ou itens individuais podem herdar ou substituir. Captura de tela:

![permissões de configuração global](../../../en/images/users/access-control-global-configuration-permissions.png)

A captura de tela mostra que os membros do grupo Público não têm permissão para realizar quaisquer ações. Se você selecionar cada grupo por vez, verá como as permissões mudam de grupo para grupo. Note que Gerente e Administrador têm permissão para Login de Administrador, mas Autor, Editor e Publicador não têm. Estes últimos são efetivamente papéis de Site em vez de papéis de Administrador.

Todas as permissões de grupo herdam do grupo Público. Ele não tem permissão para nenhuma ação. No entanto, por padrão, itens no grupo Público podem ser visualizados, então atribuir permissão Pública a um item permitirá que seja visto por todos os visitantes do site, estejam eles logados ou não.

### Permissões de Artigos

As ações de Permissões de Artigos diferem das ações de Permissões de Configuração Global. Não estão presentes itens relacionados ao login e estão presentes itens relacionados aos fluxos de trabalho. Este é um padrão bastante típico: um componente terá permissões relevantes para o componente; um item de componente (como um artigo) terá permissões relevantes para esse único item.

![Permissões de conteúdo](../../../en/images/users/access-control-global-content-permissions.png)

### Permissões de Artigo Único

As permissões de artigo único têm apenas três itens: Excluir, Editar e Editar Estado:

![permissões de artigo único](../../../en/images/users/access-control-article-permissions.png)

## Exemplo de Controle de Acesso: Usuário com Finalidade Especial

Suponha que você precise criar um Grupo de Usuários para usuários que têm apenas uma responsabilidade, neste exemplo um Administrador de Artigos. Usuários nesse grupo devem ter permissão de Login de Administrador, mas não devem ver nada além dos itens de Conteúdo. Procedimento:

### Criar um novo Grupo de Usuários

- Selecione **Usuários → Grupos** no menu do Administrador.
- Selecione o botão `Novo` na Barra de Ferramentas.
- Preencha o campo Título do Grupo: Administrador de Artigos
- O Grupo Pai deve ser Público - não tem permissões para nada.

![Novo formulário de grupo de usuários](../../../en/images/users/access-control-new-group.png)

### Atribuir a Especial

- Selecione **Usuários → Níveis de Acesso** no menu do Administrador.
- Selecione o item **Especial**.
- Marque a caixa de seleção do Administrador de Artigos no formulário **Usuários: Editar Nível de Acesso de Visualização**.
- Salvar & Fechar.

![Selecionar acesso para grupo](../../../en/images/users/access-control-select-access-for-group.png)

### Permissões de Configuração Global

- Selecione **Painel Inicial → Configuração Global** no menu do Administrador.
- Selecione a guia **Permissões**.
- Selecione o grupo **Administrador de Artigos**.
- Defina **Login de Administrador** como Permitido.
- Salvar & Fechar

![Selecionar acesso para grupo](../../../en/images/users/access-control-article-administrator-global-permissions.png)

### Permissões de Opções de Artigos

- Selecione **Conteúdo → Artigos** no menu do Administrador.
- Selecione o botão `Opções` na Barra de Ferramentas.
- Selecione a guia **Permissões**.
- Selecione o grupo **Administrador de Artigos**.
- Defina todos os itens, exceto os dois primeiros (Configurar ACL & Opções e Configurar Somente Opções), como Permitido.
- Salvar & Fechar

![Selecionar acesso para grupo](../../../en/images/users/access-control-article-administrator-content-permissions.png)

### Criar ou Editar Usuário

- Crie um novo usuário ou edite um usuário existente que não está atribuído a nenhum grupo.
- Selecione **Administrador de Artigos** na guia **Grupos de Usuário Atribuídos** no formulário de edição do Usuário.
- Salvar & Fechar.
- Faça login como um usuário apenas no Grupo de Administradores de Artigos. O menu deve mostrar apenas itens relacionados a artigos:

![Selecionar acesso para grupo](../../../en/images/users/access-control-article-administrator-home-dashboard.png)

*Traduzido por openai.com*

