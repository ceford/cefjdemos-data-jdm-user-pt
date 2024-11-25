<!-- Filename: J4.x:Logging_in_to_Joomla / Display title: Fazendo login no Joomla -->

## Introdução

Uma das grandes vantagens do Joomla! é que ele oferece a flexibilidade de realizar tarefas através do Painel de Administração (frequentemente referido como o backend) e, se habilitado, realizar tarefas diretamente a partir do frontend (a parte voltada para o público) do site.

O acesso ao frontend é uma maneira fácil e eficiente de permitir que redatores de conteúdo adicionem ou editem artigos rapidamente sem precisarem ir até o Painel de Administração.

O login no Joomla é configurado para controlar o que os usuários podem ver e fazer (ou não podem) usando o componente de Usuário do Joomla e os poderosos Níveis de Controle de Acesso (ACL). Isso significa que um site Joomla pode ter usuários que usam apenas o backend, alguns que usam apenas o frontend e outros que usam ambos.

O seguinte aborda o login e logout tanto do backend quanto do frontend de um site Joomla.

**Nota:** Um Administrador Joomla pode ter desativado o acesso ao frontend, exigindo que todas as tarefas sejam realizadas usando o Painel de Administração do backend.

### Login do Administrador

Navegue até a página de Login do Administrador. Este é o endereço web do site acrescido de /administrator, por exemplo, my-joomla-website.com/administrator, que invoca a página de login do Administrador Joomla:

![Formulário de login do administrador](../../../en/images/getting-started/logging-in-to-joomla-administrator-login-form.png)

1.  Adicione seu **Nome de Usuário**
2.  Adicione sua **Senha**

Selecione o botão **Log in** para ser levado ao Painel Inicial do Joomla!.

**Nota:**

1.  O Joomla oferece uma opção para configurar e usar a Autenticação pela Web.  
    Isso não está no escopo deste tutorial.
2.  Se um site tiver vários idiomas instalados, você poderá selecionar um idioma para usar em uma lista suspensa antes de fazer o login.

### Logout do Administrador

Para sair, selecione o **Menu de Usuário** e depois **Log out**.

![Link de logout do administrador](../../../en/images/getting-started/logging-in-to-joomla-logout-link.png)

### Login do Site

Se o acesso ao frontend estiver habilitado, um formulário de login terá sido adicionado ao site. O Joomla permite várias maneiras de fazer isso. Uma instalação padrão inclui um formulário de login na barra lateral do site, mas você pode encontrar um link que foi adicionado ao menu do site ou, talvez, no rodapé. Em alguns casos, um link *Criar Página* pode existir. O design do site ditará onde você acessa o formulário de login.

Este exemplo usa um formulário de login localizado na barra lateral direita.

![Módulo de formulário de login do site](../../../en/images/getting-started/logging-in-to-joomla-site-login-form.png)

No **Formulário de Login**

1.  Adicione seu **Nome de Usuário**
2.  Adicione sua **Senha**

Selecione o botão **Log in**.

Ao fazer login pelo frontend do site, você pode permanecer na mesma página de que fez login ou ser levado à sua página de Perfil. Você notará que o formulário de login também conterá um botão **Log out**.

### Logout do Site

![Módulo de formulário de logout do site](../../../en/images/getting-started/logging-in-to-joomla-site-logout-form.png)

Para sair, vá até o formulário de login e selecione o botão **Log out**.

## Dicas

- Alguns administradores de sites Joomla instalam extensões que escondem ou restringem o acesso ao Painel de Administração do backend. Você pode precisar tomar medidas adicionais ou visitar uma URL de login alternativa.
- Se estiver fazendo edições usando o login no frontend, economize tempo fazendo login na página que deseja editar.

*Traduzido por openai.com*

