<!-- Filename: J4.x:Multi-factor_Authentication / Display title: Autenticação Multifator  -->

## Introdução

O sistema de autenticação multifator do Joomla! é baseado no Akeeba Loginguard e grande parte desta documentação foi derivada com permissão da Akeeba.

## O que ele faz?

Ele adiciona vários métodos opcionais de Verificação em Duas Etapas para o login no Joomla! Após fazer login apenas com seu nome de usuário e senha, você é solicitado a fornecer sua verificação em segunda etapa, por exemplo, um código gerado pelo Google Authenticator. Até que você forneça uma verificação em segunda etapa correta, não poderá acessar nenhuma página no site. Você será sempre redirecionado para a página de "login cativo". Isso é semelhante ao que o Google faz quando você tenta entrar no GMail.

Isso difere do método original de autenticação de dois fatores do Joomla!, que exigia que o segundo fator de autenticação (por exemplo, o código gerado pelo Google Authenticator) fosse inserido junto com o nome de usuário e a senha.

As vantagens da Verificação em Duas Etapas são:

- É menos confuso para o usuário. Não há mais necessidade do campo "Chave Secreta", que confunde os usuários.
- Pode funcionar com métodos de login sem senha, como login social (por exemplo, Facebook), token de hardware seguro, SSO (single sign-on) etc.
  Esclarecimento: A Verificação em Duas Etapas pode ser configurada para ser solicitada após um usuário fazer login com um método de login sem senha. Ela não implementa métodos de login sem senha.
- Oferece melhor controle de acesso. Você pode definir Opções do Usuário para Exigir ou Desativar a Autenticação Multifator por grupo de usuários.
- Permite métodos de autenticação alternativos em uma única conta. Você pode ter vários métodos de autenticação em sua conta. Por exemplo, você pode configurar um aplicativo Google Authenticator e um YubiKey.
- Suporta métodos que não exigem a introdução de um código. Por exemplo, dongles FIDO2, verificação biométrica, etc. Estes precisam interagir com o navegador e/ou o sistema operacional através de APIs nativas HTML5.
- Suporta métodos que exigem interação do usuário. Por exemplo, enviar um código via mensagem push, SMS ou e-mail. Esses métodos exigem saber qual usuário está sendo autenticado antes de enviar o código de autenticação ao usuário.
- É gratuito. Ao contrário de serviços de terceiros que fornecem autenticação multifator, você não precisa pagar uma taxa inicial de configuração ou uma taxa de manutenção mensal/anual para cada site ou usuário usando a Verificação em Duas Etapas. O software é gratuito.

## Como funciona

Você faz login no seu site normalmente, por exemplo, fornecendo um nome de usuário e senha. É importante notar que você não precisa inserir suas credenciais de autenticação em segundo passo nesta etapa.

O sistema detecta que você está logado, mas não realizou a autenticação de segundo passo. Ele armazena o URL que você deveria ver e imediatamente o redireciona para a página de login captiva. Qualquer tentativa de navegar para uma página diferente resultará no aparecimento da página captiva.

Módulos no seu site podem conter informações privilegiadas. Para garantir a confidencialidade, os módulos são forçosamente desativados no momento da renderização. Isso significa que nenhuma posição de módulo será renderizada na página. Lembre-se disso caso você note que o cabeçalho ou outras áreas de design importantes do seu site estão ausentes na página de login captiva.

Note que plugins, por outro lado, NÃO são desativados. Isso ocorre tanto porque o Joomla torna extremamente difícil remover plugins específicos uma vez que estão carregados, quanto porque a maioria dos plugins realiza funcionalidades críticas no seu site.

Após fornecer sua verificação de segundo passo, uma sinalização é definida na sessão do usuário, indicando que você está totalmente autorizado a usar o site. Além disso, você será redirecionado para o URL que foi armazenado logo após o login inicial.

## Autenticação de Dois Fatores versus Logins WebAuthn

Fazer login com WebAuthn é a opção mais segura. Você só fornece um nome de usuário que deve ser considerado como informação pública e sem privilégios. O site cria um desafio criptográfico que é assinado pelo navegador usando hardware seguro — um token de hardware seguro externo ou o Trusted Platform Module / Secure Enclave do seu dispositivo — e retorna ao servidor. O servidor valida a assinatura. Esta validação usa criptografia de chave pública com o site armazenando apenas a chave pública. Isso torna o login virtualmente inviolável e extremamente seguro. Se você usar essa opção, não precisará de um segundo fator de autenticação — mas, se realmente quiser, pode usar WebAuthn para isso também.

Exceto pelo uso de qualquer método de login federado (como fazer login com sua conta de mídia social, um serviço de Single Sign-On, um servidor LDAP, etc.), um login convencional com nome de usuário + senha não é nem de longe tão seguro quanto um login WebAuthn. Inserir um nome de usuário e uma senha pode ser interceptado, roubado ou adivinhado. Isso torna muito problemático confiar apenas em um nome de usuário e senha.

Para a autenticação multifatorial, você fornece apenas seu nome de usuário e senha. Um ataque de phishing bem-sucedido apenas obteria esse primeiro fator de autenticação, mas não o seu segundo fator de autenticação. Após um login bem-sucedido, você é apresentado a uma página cativa. Você não pode fazer nada no site até fornecer seu segundo fator. Como a entrada do segundo fator é apresentada em sua própria página, ela pode ser interativa (por exemplo, WebAuthn), assíncrona (por exemplo, recebendo um OTP por email, mensagem de texto ou notificação push) ou iniciada pelo usuário (por exemplo, um TOTP ou um Yubikey OTP). Ainda melhor, um usuário pode ter múltiplos métodos de segundo fator habilitados em sua conta para evitar bloqueios acidentais do site. Por exemplo, você pode estar usando WebAuthn com um dongle de hardware seguro externo como seu segundo fator mais seguro e principal. Você também pode configurar um TOTP regular caso perca o dongle ou esqueça de levá-lo com você. Alguns métodos de segundo fator permitem várias instâncias, por exemplo, você pode ter múltiplos autenticadores WebAuthn para poder usar o autenticador embutido em seu computador Windows, seu iPhone e seu tablet Android sem ter que se lembrar de levar um dongle de hardware e adaptadores todas as vezes que sair da sua mesa.

Vamos recapitular. Das opções mais seguras para as menos seguras, temos:

- WebAuthn como seu método de login principal com autenticação multifatorial secundária.
- WebAuthn como seu único método de login.
- Nome de usuário e senha como seu método de login principal com autenticação multifatorial secundária.
- Apenas um nome de usuário e senha como seu único método de login.

## Plugins

Cada um dos fatores na Autenticação Multifatorial é implementado por meio de plugins. Eles podem ser habilitados ou desabilitados conforme necessário. E novos podem ser adicionados quando surgirem novos métodos. Os plugins incluídos no núcleo do Joomla são:

- **Código de Verificação**: códigos de verificação de seis dígitos gerados por um
  aplicativo autenticador (Google Authenticator, Authy, LastPass
  Authenticator, etc.), um gerenciador de senhas (1Password, BitWarden, Keeper,
  KeePassXC, Strongbox, etc.) ou, em alguns casos, pelo navegador.
- **YubiKey**: Permite que os usuários em seu site utilizem a Autenticação Multifatorial usando um token de hardware seguro YubiKey. Os usuários precisam do seu próprio YubiKey, disponível em www.yubico.com.
- **Autenticação Web**: suportado por todos os navegadores modernos. A maioria dos navegadores oferece autenticação específica de dispositivo protegida por uma senha e/ou biometria (sensor de impressão digital, reconhecimento facial, ...).
- **Código de Autenticação por Email**: Use códigos de segurança de seis dígitos com tempo limitado enviados por email. A configuração padrão é de 2 minutos.
- **Código Fixo**: este é destinado para testes e ilustração e está desabilitado por padrão. Não deve ser habilitado em um site de produção.

Observe que há um plugin separado **Sistema - Login Sem Senha WebAuthn** para lidar com o login pelo botão de Autenticação Web no formulário de login.

## Opções de Usuários

O formulário de Opções de Usuários possui um formulário de Autenticação Multifator para configurar como a Autenticação Multifator funciona no Joomla. Selecione o botão Alternar Ajuda Inline para obter informações sobre cada opção.

![formulário de autenticação multifator de opções de usuários](../../../en/images/users/users-configuration-mfa.png)

## Perfil do Usuário

O formulário Administrador / Usuários: Editar Perfil possui abas separadas para Login por WebAuthn e Autenticação Multi-fator, mas esta última é visível apenas para o proprietário da conta. Mesmo Usuários Super não veem esta aba para outros usuários.

O formulário Site / Edite Seu Perfil possui as abas do formulário do backend dispostas uma acima da outra, o que pode ser confuso porque a Autenticação Web aparece duas vezes, primeiro para login sem senha e segundo para Autenticação Multi-fator. A ilustração a seguir mostra a parte de Autenticação Multi-fator do formulário após um método ter sido criado. Isso define automaticamente o recurso como Ativado e mostra a opção de criar Códigos de Backup.

![visão do site sobre o formulário de autenticação multifatorial do usuário](../../../en/images/users/multi-factor-authentication-site-profile.jpg)

Como mencionado acima, você pode testar cada uma delas selecionando o botão + Adicionar ..., mas selecione Cancelar no formulário subsequente se decidir não prosseguir.

