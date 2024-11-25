<!-- Filename: J4.x:Privacy_Setup / Display title: Configuração de Privacidade  -->

## Componente de Privacidade

O Componente de Privacidade é usado para gerenciar informações de privacidade, para recolher pedidos de informações ou solicitações para exclusão de informações. Ele se baseia em endereços de e-mail, portanto, aplica-se mais obviamente a usuários registrados que devem fornecer um endereço de e-mail durante o registro. Também se aplica a dados de usuários não registrados cujos endereços de e-mail foram fornecidos através do componente de Contatos. Não implementa a permissão para usar cookies ou rastreamento exigida pelo RGPD.

Quando informações pessoais identificáveis são coletadas, você deve garantir:

- O usuário é informado por que você está solicitando essas informações em linguagem simples e fácil de entender.
- O usuário sabe quais dados você coleta sobre ele.
- O usuário sabe para que você usará os dados.
- O usuário consentiu ativamente com o uso dos dados por você.

Normalmente, essas informações são descritas em um artigo da Política de Privacidade.

## Painel de Privacidade

O painel de privacidade fornece um resumo das **Solicitações de Privacidade** e do **Status de Privacidade** do site. Para acessar:

- Selecione **Usuários → Privacidade** no menu do Administrador.

![painel de privacidade](../../../en/images/privacy/privacy-dashboard.png)

Existem dois módulos exibidos por padrão no Painel de Privacidade:

### Solicitações de Privacidade

Este módulo fornece um resumo das solicitações de informação atuais.

### Status de Privacidade

Este módulo mostra o status das opções que os proprietários do site devem atender:

- **Política de Privacidade Publicada** defina um artigo de Política de Privacidade no plugin
  **Sistema - Consentimento de Privacidade**.
- **Item de Menu de Formulário de Solicitação Publicado** defina um item de menu para permitir
  que usuários autenticados enviem solicitações.
- **Solicitações Urgentes Pendentes** verifique as solicitações confirmadas mais antigas que a idade especificada nos parâmetros do componente (padrão 14 dias) e alerte o proprietário do site sobre quaisquer solicitações que exijam atenção urgente.
- **Envio de E-mail Habilitado** o site deve ser capaz de enviar e-mails para
  processar solicitações de informação.
- **Criptografia de Banco de Dados** isso é relevante quando um banco de dados remoto é usado.

## Plugin: Sistema - Consentimento de Privacidade

Se este plugin estiver desativado, o painel de Status de Privacidade do Dashboard mostrará que a Política de Privacidade está **Indisponível** e fornecerá um link para o formulário de edição do plugin. Quando ativado, o plugin solicita que qualquer novo usuário que se registre em seu site consinta com a Política de Privacidade. Todos os usuários existentes serão redirecionados para seu Perfil de Usuário para que possam dar o consentimento.

Para configurar os consentimentos:

- Selecione **Painel Inicial**→**Plugins** no menu do Administrador.
- Encontre o plugin **Sistema - Consentimento de Privacidade** (não confundir com o plugin Privacidade - Consentimentos).
- Selecione para abrir o formulário de entrada de dados do plugin.

![plugin sistema consentimento de privacidade](../../../en/images/privacy/plugin-system-privacy-consent.png)

- Defina o **Status** como **Ativado**.
- Opcional: Selecione ou crie um artigo para vincular ao formulário de Registro. Ou defina o Tipo de Privacidade como Item de Menu e selecione ou crie um item de menu.
- Selecione a guia **Validade** e **Alternar Ajuda Inline** para uma explicação de cada campo. Habilite e ajuste os parâmetros **se** desejar que os consentimentos expirem após um determinado número de dias.

### Notas sobre Consentimento de Privacidade para sites multilíngues:

**Resumo da Política de Privacidade e Mensagem de Redirecionamento** Se você usar o texto padrão, ele será exibido no idioma do usuário. Não é possível traduzir o texto personalizado. Se desejar personalizar o texto e exibi-lo em vários idiomas, deixe este campo em branco e use o recurso de substituição de idioma do Joomla para personalizar as strings de idioma `PLG_SYSTEM_PRIVACYCONSENT_NOTE_FIELD_DEFAULT` e `PLG_SYSTEM_PRIVACYCONSENT_REDIRECT_MESSAGE_DEFAULT` para cada idioma instalado.

**Artigo de Privacidade** e **Item de Menu de Privacidade** Se você associar este artigo ou item de menu a alternativas em outros idiomas, a política de privacidade será exibida no idioma correto para o usuário.

## Plugin: Usuário - Termos e Condições

Quando habilitado, este plugin solicita que qualquer novo usuário que se registrar em seu site consinta com os Termos e Condições para uso do seu site. Todos os usuários existentes serão redirecionados para seu Perfil de Usuário para que possam consentir.

Este plugin não está habilitado por padrão. Para habilitar:

- Selecione **Painel Inicial → Plugins** no menu do Administrador.
- Encontre o plugin **Usuário - Termos e Condições**.
- Selecione para abrir o formulário de entrada de dados do plugin.
- Defina o **Status** como **Habilitado**.
- Opcional: Selecione ou crie um artigo para vincular no formulário de Registro.

### Notas do Usuário - Termos e Condições para sites multilíngues

**Termos e Condições Curtos** Se você usar o texto padrão, ele será exibido no idioma do usuário. Não é possível traduzir o texto personalizado. Se deseja personalizar o texto e exibí-lo em vários idiomas, deve deixar este campo em branco e usar a facilidade de substituição de idioma do Joomla para personalizar as strings de idioma `PLG_USER_TERMS_NOTE_FIELD_DEFAULT` para cada idioma instalado.

**Artigo de Termos e Condições** Se você associar este artigo a alternativas em outros idiomas, a política de privacidade será exibida no idioma correto para o usuário.

## Visualização de Consentimento de Registro do Usuário

Juntos, os dois plugins aparecem no formulário de Registro do Usuário como na
captura de tela a seguir:

![visualização de consentimentos de privacidade no site](../../../en/images/privacy/privacy-consents-site.png)

## Item do Menu: Solicitação de Informação de Privacidade

Usuários registrados podem solicitar um resumo de informações ou remoção através de um item de menu. Configure da seguinte forma:

- Selecione **Menus** → **Menu Inferior** no menu do Administrador (use o menu que for mais conveniente).
- Insira um **Título** apropriado, exemplo: **Solicitação de Informação de Privacidade**.
- Use o botão **Selecionar** para abrir o diálogo popup de Tipo de Item de Menu.
- Na seção **Privacidade** selecione o item **Criar Solicitação**.
- Defina o campo **Acesso** como **Registrado**.
- **Salvar & Fechar**.

Vá para a visualização do seu site e verifique se o item do menu não é exibido quando você não está logado e se ele é exibido após o login. Use o link e experimente a opção **Exportar**. Você pode experimentar a opção **Remover** mais tarde usando uma conta fictícia. Se houver uma solicitação pendente, você verá uma mensagem de erro:

"Sua solicitação de informação não pôde ser criada. Já existe uma solicitação de informação ativa para este endereço de e-mail e tipo de solicitação. Por favor, contate o proprietário do site para atualizações sobre esta solicitação."

## Item de Menu: Confirmar Solicitação de Privacidade

Para fins de SEF, você pode criar um item de menu oculto para que o usuário confirme a solicitação. Isso estará no link enviado por e-mail.

- Selecione **Menus** → **Menu Oculto** no menu do Administrador (crie um menu oculto sem posição de módulo atribuída, ou veja abaixo).
- Insira um **Título** adequado, exemplo: **Confirmar Solicitação de Privacidade**.
- Use o botão **Selecionar** para abrir o diálogo popup do Tipo de Item de Menu.
- Na seção **Privacidade**, selecione o item **Confirmar Solicitação**.
- Se você não tiver um Menu Oculto, utilize seu menu principal e, na aba Tipo de Link, configure **Exibir no Menu** como **Não**.
- **Salvar & Fechar**.

## Itens do Menu do Administrador

Dê uma olhada nos outros itens do menu do Componente de Privacidade.

### Solicitações de Privacidade do Administrador

Esta tela é o local central para processar e gerenciar solicitações de informações dos usuários. Por favor, veja o artigo relacionado sobre o Fluxo de Trabalho de Privacidade para orientações sobre o processamento de solicitações.

![solicitações de informações de privacidade](../../../en/images/privacy/privacy-information-requests.png)

### Capacidades de Extensão

Esta tela coleta e exibe informações sobre as capacidades relacionadas à privacidade relatadas por extensões individuais. Destina-se a auxiliar na preparação de documentação, como um artigo de política de privacidade ou um artigo de termos de serviço.

![capacidades de extensão de privacidade](../../../en/images/privacy/privacy-extension-capabilities.png)

O conteúdo da página vem de cadeias de caracteres de idioma no núcleo, no componente de privacidade e em plugins que implementam o evento onPrivacyCollectAdminCapabilities. Isso inclui:

- Autenticação
- Captcha
- Instalador
- Privacidade
- Sistema
- Usuário

As informações serão exibidas no idioma selecionado para o login do Administrador.

### Consentimentos

Esta tela exibe uma lista de consentimentos, do mais recente para o mais antigo. Será no idioma utilizado no formulário de consentimento, normalmente durante o registro. Você pode pesquisar por nome de um usuário específico. Note que o consentimento para concordar com os Termos e Condições do site não é registrado aqui. Isso está apenas no Log de Ações do Usuário.

![consentimentos de privacidade](../../../en/images/privacy/privacy-consents.png)

*Traduzido por openai.com*

