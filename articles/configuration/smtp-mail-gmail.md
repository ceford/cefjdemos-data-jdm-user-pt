<!-- Filename: How_to_debug_SMTP_mail_in_Joomla_4 / Display title: Correio SMTP e Gmail -->

## Introdução

Na página de Configuração Global, no painel do Servidor, há uma opção para selecionar um agente de entrega de correio. A configuração padrão é *PHP Mail*. Se isso não funcionar, pode ser aconselhado utilizar SMTP. Ele usa o mesmo mecanismo que sua aplicação de e-mail. Há várias configurações que você precisa acertar. Resumidamente:

Vá para a **Configuração Global** e selecione a aba **Servidor**. Procure o painel de *Correio* na parte inferior do formulário.

- **Mailer** definido como SMTP. Vários campos adicionais aparecem
- **Host SMTP** Isso é localhost por padrão, mas é improvável que funcione. É necessário configurá-lo para o host que gerencia seu correio de saída, por exemplo, uma conta Gmail.
- **Porta SMTP** O padrão é 25. Verifique se esse é o valor que seu Host SMTP espera.
- **Segurança SMTP** O padrão é *Nenhuma*, mas é provável que você precise de STARTTLS.
- **Autenticação SMTP** Isso pode não ser necessário se você estiver usando uma rede doméstica que espera que os e-mails de saída não exijam autenticação. Caso contrário:
- **Nome de Usuário SMTP** e **Senha SMTP** insira os valores que você usa para acessar sua conta de e-mail pela internet.
- Selecione o botão **Enviar Teste de Correio**.

## Usando o Gmail

Se você tem uma conta Gmail funcional, pode usar o Gmail como seu servidor de e-mail configurando-o nas configurações globais.

Na aba do servidor, configure o seguinte:

- Mailer: SMTP
- Host SMTP: smtp.gmail.com
- Porta SMTP: 465
- Segurança SMTP: SSL/TLS
- Autenticação SMTP: Sim
- Configure as próximas duas linhas com suas informações. Você precisa usar uma senha específica de aplicativo (ASP), descrita abaixo.
- Nome de usuário SMTP: seu nome de usuário do Gmail
- Senha SMTP: a senha específica do aplicativo (ASP) que você gerou, descrita abaixo.

As seguintes combinações também funcionam:

- Porta SMTP: 587
- Segurança SMTP: STARTTLS
- Porta SMTP: 25
- Segurança SMTP: STARTTLS

O módulo SSL não precisa estar habilitado no Apache.

A extensão OpenSSL precisa estar habilitada no PHP. Os detalhes podem ser encontrados na [página de Instalação do php.net](https://www.php.net/manual/en/openssl.installation.php).

Se você estiver usando WAMP no Windows, o módulo openssl não está habilitado por padrão e você precisa habilitá-lo. Para fazer isso:

1. Abra o arquivo php.ini e descomente a linha `extension=php_openssl.dll` removendo o ponto e vírgula (;) do início da linha.
2. Salve o arquivo php.ini e reinicie o serviço Apache.

Note que se você usa a verificação em duas etapas no Gmail, precisará adicionar uma nova senha em Configurações - Contas - Alterar configurações da conta - Outras configurações da Conta Google - Segurança - Verificação em duas etapas - Gerenciar suas senhas específicas de aplicativos.

Quando a nova Senha Específica de Aplicativo (ASP) for apresentada em grupos de quatro caracteres separados por espaços, certifique-se de **NÃO inserir os espaços** na senha SMTP nas configurações do servidor de email no Joomla.

- Senhas Específicas de Aplicativos (ASPs): Veja a página de Suporte do Google intitulada [Entrar com Senhas de Aplicativos](https://support.google.com/accounts/answer/185833).
- Verificação em Duas Etapas: Veja a página de Suporte do Google intitulada [Ativar a Verificação em Duas Etapas](https://support.google.com/accounts/answer/185839).

## Depuração

Se o e-mail não for enviado ou nunca chegar:

- Selecione **Plugins** no **Painel Inicial → Painel do Site**.
- Encontre e ative o plugin **Sistema - Depurar** e configure-o:
- Defina **Grupos Permitidos** como *Super Usuários* para restringir a saída de depuração à sua própria sessão de login, tanto no backend quanto no frontend. Se você não quiser fazer login no frontend como Super Usuário, crie um grupo de usuário exclusivo para suas atividades de teste e selecione esse grupo de usuários na lista de grupos de usuários permitidos.
- **Salvar & Fechar**

- Selecione **Configuração Global** no **Painel Inicial → Painel do Site**.
- Na aba *Sistema*, defina **Sistema de Depuração** para *Sim*.
- Na aba *Servidor*, defina **Relatório de Erros** para *Máximo*.
- Na aba *Registro*, anote o conteúdo de *Caminho para Pasta de Logs*, geralmente *\[alguma_coisa\]/administrator/logs*.
- Defina **Registrar Quase Tudo** para *Sim*.
- No painel de *Registro Personalizado*, defina o campo *Categorias de Log* para *mail* (sem aspas).
- **Salvar** para salvar as configurações de depuração.
- Na aba **Servidor**, selecione o botão *Enviar E-mail de Teste* na parte inferior da página.

Se existirem problemas no código durante o teste, você deverá receber um *Rastreamento de Pilha* que ajudará você ou outros a diagnosticar o problema. Além disso, procure um arquivo na pasta de logs com um nome como *administrator/logs/everything.php* e abra-o com um editor de texto. Isso pode ajudar a ver o que foi registrado quando a mensagem foi enviada.

*Traduzido por openai.com*  

