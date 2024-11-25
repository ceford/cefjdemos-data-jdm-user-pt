<!-- Filename: Help4.x:Components_Privacy_Outline / Display title: Esboço de Privacidade  -->

## Conteúdo

O Conjunto de Ferramentas de Privacidade do Joomla consiste nas seguintes partes:

- **Componente Administrador** Gerencia solicitações de privacidade de informações de usuários.
- **Módulo - Painel de Privacidade** Coloca um painel de Privacidade no Painel Principal.
- **Módulo - Solicitações de Privacidade** Coloca um painel de Solicitações de Privacidade
  no Painel de Privacidade.
- **Módulo - Status de Privacidade** Coloca um painel de Status de Privacidade
  no Painel de Privacidade.
- **Item de Menu - Criar Solicitação** Exibe um formulário para mostrar uma Solicitação de Informação. A ser criado.
- **Plugin - Sistema - Consentimento de Privacidade** Adiciona campos de consentimento a formulários de informações pessoais, como Registro. A ser habilitado.
- **Plugin - Usuário - Termos e Condições** Solicita o consentimento do usuário para
  os termos e condições do site. A ser habilitado.
- **Plugin - Conteúdo - Confirmar Consentimento** Adiciona uma caixa de seleção obrigatória a um
  formulário, por exemplo, o formulário de contato principal. A ser habilitado.
- **Plugin - Privacidade - Vários** Mais plugins, habilitados por padrão,
  sem parâmetros significativos para configurar.

Na instalação, o Conjunto de Ferramentas de Privacidade está pronto para uso do Administrador
sem a necessidade de habilitar plugins ou criar um item de menu.

## Fluxo de Trabalho

Esta é uma sequência típica de eventos:

- Um pedido de informação chega. Ele deve incluir um endereço de email válido para um Sujeito de dados. O Sujeito não precisa ser um usuário registrado. Por exemplo, o Sujeito pode ser um contato adicionado por um Administrador.
- Se a mensagem não for enviada pelo Sujeito através de um formulário de Informações Pessoais do site:
  - O Administrador vai para **Usuários → Privacidade → Solicitações → Novo** para criar um novo pedido de informação. Uma mensagem é enviada para o endereço de email fornecido convidando o Sujeito a confirmar que este é um pedido genuíno.
- Se a mensagem for enviada através de um formulário de Informações Pessoais do site, o Sujeito recebe automaticamente uma mensagem de pedido de confirmação.
- O Sujeito seleciona o link na mensagem de email para abrir o formulário de confirmação. Ao enviar, o Sujeito vê uma mensagem de confirmação.
- O Administrador vê que há Mensagens Privadas pendentes na Barra de Título. Também haverá uma mensagem de email do sistema.
- O Administrador vai para **Usuários → Privacidade → Solicitações** e vê que o status do pedido mudou para **Confirmado**.
- Para um pedido de Exportação de dados, há botões adjacentes de Exportação e Email.
  - O Administrador seleciona o botão de Exportação para visualizar os dados a serem exportados. Isso está em formato XML, mas é exibido de forma sensata no Firefox.
  - O Administrador seleciona o botão de Email para enviar os dados exportados ao Sujeito.
- Para um pedido de Remoção de dados, há um botão Excluir adjacente.
  - O Administrador seleciona o botão de excluir para anonimizar os dados do usuário. O usuário não poderá mais fazer login.
- Selecione o endereço de email do Sujeito de dados para abrir o formulário de Revisão de Pedido de Informação.
- Selecione o botão Completo na Barra de Ferramentas.
- A lista de Pedidos de Informação mostra o Status como Completo e os botões de Ação desapareceram.

Note que esta suíte não exibe um formulário de permissões de Cookie.

*Traduzido por openai.com*

