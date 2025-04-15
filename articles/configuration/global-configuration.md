<!-- Filename: J4.x:Global_Configuration / Display title: Configuração Global  -->

## Visão Geral

Durante a instalação, um site Joomla cria um arquivo chamado **configuration.php** na raiz do site. Este arquivo contém os valores das variáveis de configuração que se aplicam ao site como um todo. Exemplos incluem o nome do site e as credenciais do banco de dados que foram inseridas durante o processo de instalação. Existem muitas outras variáveis que são fornecidas com valores iniciais adequados.

O formulário de Configuração Global permite que um Super Usuário altere as variáveis de configuração para atender às necessidades do site. Além das variáveis armazenadas em configuration.php, o formulário acompanha informações de Registro, Filtragem e Controle de Acesso, algumas das quais são armazenadas no banco de dados.

## Captura de Tela

O formulário de Configuração Global possui seis abas, algumas das quais têm longas listas de parâmetros. Use o botão *Alternar Ajuda Inline* na Barra de Ferramentas para ver mais ou menos informações sobre cada parâmetro.

![Aba de configuração global do site](../../../en/images/configuration/global-configuration-site-tab.png)

Alguns parâmetros mostram ou ocultam outros parâmetros quando selecionados. Por exemplo, o botão **Site Offline** mostra mais campos quando configurado como *Sim* do que quando configurado como *Não*. Com a ajuda inline expandida, a maioria dos campos está suficientemente bem documentada para não necessitar de mais explicações aqui, exceto algumas notas adicionais do usuário em cada aba.  

## Aba do Site

### Painel do Site

- **Nome do Site** Este é o nome do site que aparece no formulário de login do Administrador e no link do Site na barra de título. Altere conforme necessário.
- **Site Offline** Há um [tutorial](jdocmanual?article=user/configuration/site-offline) separado sobre este item.
- **Limite Padrão da Lista** define o número máximo padrão de itens por página em vistas de lista. Por padrão, este parâmetro é definido como 20, mas as vistas de lista geralmente incluem uma lista suspensa para selecionar outros valores que variam de 5 a 100. Valores menores são mais rápidos de processar e envolvem menos rolagem pelo usuário.

### Painel de Metadados

- **Descrição Padrão dos Metadados do Site** Esta é a descrição padrão dos metadados usada se tal descrição não for especificada em um campo Descrição Meta de um artigo ou em um campo Descrição Meta de um menu. Se todos os três estiverem vazios, a descrição dos metadados é omitida na saída da página. Os mecanismos de busca frequentemente usam isso para fornecer texto descritivo para uma página. Se estiver ausente, os motores de busca podem usar o texto do conteúdo da página, o que pode ser inadequado. Recomenda-se uma descrição do propósito do site de cerca de 20 palavras.
- **Direitos do Conteúdo** define a entrada de metadados *direitos*. Se apropriado, descreva aqui quais direitos outros têm para usar este conteúdo. Esta entrada de metadados é omitida das páginas da web se esta entrada estiver em branco. Exemplo: Licença Creative Commons Attribution 4.0 International (veja o [Escolhedor de Licença Creative Commons](https://creativecommons.org/choose/)).

### Painel de SEO

SEO é um acrônimo para *Otimização para Motores de Busca*. As configurações neste grupo alteram o formato das URLs para páginas no site e isso pode ter um efeito significativo nas classificações de busca de páginas individuais e do site como um todo. URLs de SEO são mais legíveis por humanos.

**Dica** Após fazer qualquer alteração nas configurações deste grupo, atualize qualquer página do site já aberta no seu navegador (geralmente Ctrl+R ou Cmd+R faz isso). Falha em atualizar pode significar que o formato dos links web internos do site não correspondem mais ao que o Joomla espera, dando assim a aparência de links quebrados.

**Dica** Se possível, evite alterar as Configurações de SEO uma vez que um site esteja estabelecido. Fazer isso pode resultar em links quebrados de outros sites e talvez uma queda temporária nas classificações dos motores de busca.

- **Aliases Unicode** Alterar este parâmetro não altera retroativamente os aliases, apenas muda o comportamento da geração automática de aliases para a edição e criação de conteúdo futuro. *Transliteração* (Não) é a configuração padrão.

### Painel de Cookies

- **Domínio de Cookie** Substitui o domínio padrão de cookies do site com o domínio adicionado aqui. A situação mais provável em que isso seria necessário é quando o site Joomla está "conectado" com outros sites (por exemplo, fórum ou e-commerce) em subdomínios do site Joomla. O domínio padrão de cookies pode ser algo como `www.exemplo.com`, mas usar `.exemplo.com` (note o ponto inicial) aqui entregará cookies válidos para qualquer subdomínio de exemplo.com.
- **Caminho do Cookie** Substitui o caminho padrão do site para o qual o cookie é válido com o caminho adicionado aqui. Isso pode ser necessário se você tiver várias instalações do Joomla em pastas irmãs.

## Aba do Sistema

![Aba do sistema de configuração global](../../../en/images/configuration/global-configuration-system-tab.png)

### Painel de Depuração

Os itens deste painel são bem explicados pela ajuda inline. No entanto, se você encontrar um problema que desabilite o acesso normal à interface do Administrador, talvez precise definir o Sistema de Depuração editando configuration.php com um editor de texto. Na maioria dos sistemas de hospedagem baseados em Linux, as permissões do arquivo estão configuradas para 444, o que impede salvar a partir de um editor de texto. Altere a permissão para 644 antes de editar. Em seguida, defina \$debug = `true`; e defina \$error_reporting = `'maximum'`; e salve. Isso deve fornecer um rastreamento de pilha identificando exatamente onde o problema ocorre. Você pode usar isso para buscar ajuda nos Fóruns. A maioria dos problemas surge de extensões de terceiros incompatíveis ou de problemas com o ambiente de hospedagem.

## Guia do Servidor

![Guia do servidor de configuração global](../../../en/images/configuration/global-configuration-server-tab.png)

### Painel de e-mail

Um site Joomla deve ser capaz de enviar e-mails de saída. Entre outras coisas, ele enviará mensagens automáticas para o proprietário do site quando houver atualizações disponíveis. No entanto, alguns serviços de hospedagem restringem os métodos pelos quais os e-mails de saída podem ser enviados.

#### Enviar e-mail de teste

Antes do Joomla 5.3, o botão **Enviar e-mail de teste** enviava uma mensagem para o endereço configurado no campo **E-mail do remetente**. Desde a versão 5.3, o e-mail de teste é enviado diretamente para o endereço de e-mail do administrador conectado.

- Primeiro, tente o PHP Mail e selecione o botão *Enviar Email de Teste*. Se o email chegar, você está pronto para prosseguir. Caso contrário:
- Tente a opção Sendmail. Se isso não funcionar:
- Tente a opção SMTP. Isso precisa ser configurado para um servidor de correio específico. Pode ser um fornecido pelo seu serviço de hospedagem. Pode ser uma conta do Gmail.
- **Host SMTP** O nome do host do servidor SMTP (por exemplo, *smtp.example.com*).
  - **Porta SMTP** A porta a ser usada ao conectar-se ao servidor SMTP. Geralmente será *25* quando a Segurança SMTP estiver configurada como *Nenhuma*, ou *465* ou *587* quando a Segurança SMTP estiver configurada como `SSL/TLS` ou `STARTTLS`. Pergunte ao seu provedor de serviços SMTP qual porta usar.
  - **Segurança SMTP** A forma de segurança exigida pelo servidor SMTP: *Nenhuma*, *SSL/TLS* ou *STARTTLS*. O padrão é *Nenhuma*.
  - **Autenticação SMTP** Indica se o servidor SMTP externo requer ou não autenticação antes de aceitar e-mails de saída. O padrão é *Não*.
  - **Nome de Usuário SMTP** O nome de usuário a ser usado ao conectar-se ao servidor SMTP no modo SSL ou TLS. Pode ser deixado em branco se não houver autenticação SMTP.
  - **Senha SMTP** A senha a ser usada ao conectar-se ao servidor SMTP no modo SSL ou TLS. Pode ser deixada em branco se não houver autenticação SMTP.

### Usando o Gmail como Servidor de E-mail

Se você tem uma conta Gmail ativa, pode usá-la como seu servidor de e-mail configurando-a na configuração global. Na guia do servidor, defina o seguinte:

- Mailer: SMTP
- Host SMTP: smtp.gmail.com
- Porta SMTP: 465
- Segurança SMTP: SSL/TLS
- Autenticação SMTP: Sim
- Configure as duas linhas seguintes com suas informações. Você precisará usar uma senha específica de aplicativo (ASP), descrita abaixo.
- Nome de Usuário SMTP: seu nome de usuário do Gmail
- Senha SMTP: a senha específica de aplicativo (ASP) gerada, descrita abaixo.

As seguintes combinações também funcionam:

- Porta SMTP: 587
- Segurança SMTP: STARTTLS
- Porta SMTP: 25
- Segurança SMTP: STARTTLS

#### Notas

- O módulo SSL não precisa estar ativado no Apache.
- A extensão OpenSSL precisa estar ativada no PHP. Os detalhes podem ser encontrados na [página de instalação do php.net](https://www.php.net/manual/en/openssl.installation.php).
- Se você estiver usando WAMP no Windows, o módulo openssl não está ativado por padrão e você precisará ativá-lo. Para fazer isso:
  - Abra o arquivo php.ini e descomente a linha `extension=php_openssl.dll` removendo o ponto e vírgula `;` do início da linha.
  - Salve o arquivo php.ini e reinicie o serviço Apache.
- Se você usa verificação em 2 etapas no Gmail, você precisará adicionar uma nova senha em Configurações - Contas - Alterar configurações de conta - Outras configurações de Conta Google - Segurança - Verificação em 2 etapas - Gerenciar suas senhas específicas para aplicativos.
- Quando a nova Senha Específica de Aplicativo (ASP) for apresentada em grupos de quatro caracteres separados por espaços, certifique-se de **NÃO inserir os espaços** na senha SMTP nas configurações do servidor de email no Joomla.
- Senhas Específicas de Aplicativos (ASPs): Veja a página de suporte do Google sobre como [Fazer login com Senhas de Aplicativos](https://support.google.com/accounts/answer/185833).
- Verificação em 2 etapas: Veja a página de suporte do Google sobre como [Ativar a Verificação em 2 etapas](https://support.google.com/accounts/answer/185839).

## Aba de Log

![Aba do site de configuração global](../../../en/images/configuration/global-configuration-logging-tab.png)

Em operação normal, um site Joomla deve ter o registro desativado. Se houver problemas, você pode ativar o registro configurando o campo **Registrar Quase Tudo** para `Sim`. A opção **Registrar API Obsoleta** é realmente apenas para desenvolvedores. O campo **Caminho para a Pasta de Logs** mostra onde procurar os logs, caso você tenha configurado o registro para ajudar na depuração. Os logs de erro que você encontrar lá são apenas aqueles capturados pelo Joomla. Pode haver outros erros que só aparecerão nos logs de erro do seu servidor.

## A aba Filtros de Texto

![Aba de configuração global do site](../../../en/images/configuration/global-configuration-filters-tab.png)

As configurações de filtro de texto serão aplicadas a todos os campos do editor de texto enviados por usuários nos grupos selecionados. Essas opções de filtragem oferecem mais controle sobre o HTML que seus provedores de conteúdo enviam. Você pode ser tão rigoroso ou liberal quanto necessário para atender às necessidades do seu site. A filtragem é opcional, e as configurações padrão oferecem boa proteção contra marcações comumente associadas a ataques em sites.

## Aba de Permissões

![Guia do site de configuração global](../../../en/images/configuration/global-configuration-permissions-tab.png)

As permissões controlam o que os usuários em cada Grupo de Usuários podem ver e fazer. As entradas na aba de Permissões definem as permissões padrão para o site.

Existem descrições abrangentes sobre o uso das configurações nesta aba e os princípios gerais de operação e configuração de permissões em um [Tutorial de Lista de Controle de Acesso](jdocmanual?article=user/users/access-control).

*Traduzido por openai.com*

