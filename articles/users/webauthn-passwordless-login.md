<!-- Filename: WebAuthn_Passwordless_Login / Display title: Login WebAuthn  -->

## Login sem Senha com WebAuthn

A Autenticação na Web, ou WebAuthn, permite que um usuário faça login de forma segura em um site sem usar uma senha — embora ainda seja necessário um nome de usuário. Ele utiliza criptografia forte de uma maneira que é extremamente resistente aos problemas mais comuns das senhas:
* alguém a adivinhou (ataque de força bruta)
* alguém a interceptou (ataque man-in-the-middle)
* alguém o enganou para divulgá-la (ataque de phishing)
* alguém a quebrou após obter uma cópia dos dados do seu banco de dados (ataques de injeção SQL)
* alguém a roubou.

O WebAuthn não é apenas muito seguro; ele também é muito amigável ao usuário! Você não precisa mais se lembrar de senhas longas ou usar um gerenciador de senhas. Tudo o que você precisa é de um *autenticador*, às vezes também chamado de *chave de acesso*.

Um autenticador pode ter muitas formas, físicas ou virtuais. Pode ser uma chave de hardware separada conectando-se ao seu dispositivo via USB, Bluetooth ou NFC. Pode ser o próprio dispositivo, desbloqueando o autenticador embutido com um PIN, leitor de impressão digital, escaneamento facial ou verificação biométrica similar.

Esse recurso já funciona em dispositivos Android e iOS/iPadOS e estamos trabalhando para habilitá-lo no Windows também. Pode até ser seu telefone — atualmente isso é possível com telefones Android, mas esse recurso também está chegando a dispositivos iOS/iPadOS.

O WebAuthn só funciona via HTTPS e apenas quando seu site está usando um certificado válido e confiável. Não se preocupe, você não precisa gastar dinheiro extra; serviços gratuitos como o Let's Encrypt são normalmente integrados aos painéis de controle de hospedagem na web e funcionam perfeitamente com o WebAuthn.

O WebAuthn usa criptografia de chave pública, a mesma tecnologia comprovada que mantém seus sites seguros com HTTPS, suas informações bancárias seguras, e assim por diante. A chave privada nunca sai do autenticador. Seu site armazena apenas uma chave pública. Mesmo se você sofrer uma violação de dados, o invasor ficará com uma chave pública praticamente inútil; levaria milhares a milhões de anos de CPU para decifrá-la, em oposição a poucos minutos ou horas necessários para quebrar o hash de uma senha fixa que você consegue lembrar.

O WebAuthn é o futuro da autenticação. Fácil, seguro e sem complicações. Tudo o que senhas fixas não são.

A imagem a seguir mostra um dispositivo de hardware inserido na porta USB de um laptop. Custou £15 em fevereiro de 2022.

![fotografia do Dispositivo de Hardware](../../../en/images/users/passwordless-login-hardware-device.jpg)

O WebAuthn usa um plugin do sistema que é ativado por padrão. Um botão de **Autenticação na Web** estará presente nas telas de login padrão do Joomla 4 e posteriores, conforme ilustrado na tela de login do Administrador:

![formulário seguro de login do administrador](../../../en/images/users/passwordless-login-login-form.jpg)

## Configuração do Usuário

O usuário deve primeiro se registrar com um Nome de Usuário e Senha normais. Após fazer login, vá para o formulário de Perfil do Usuário. Para um Administrador:

- Selecione **Menu do Usuário → Editar Conta → Login de Autenticação
  Web W3C (WebAuthn)** para abrir o formulário, inicialmente sem
  autenticadores registrados.
- Selecione **Adicionar Novo Autenticador**

A apresentação exata do próximo passo depende do seu navegador. Tipicamente, você verá um alerta, mensagem ou janela pedindo para selecionar um tipo de autenticador ou, se você estiver usando um autenticador de hardware conectado ao seu dispositivo, lembrete para pressionar o botão no autenticador de hardware. Por razões de segurança e práticas, existe um intervalo de tempo relativamente curto permitido para ativar o autenticador: 60 segundos.

![prompt seguro de login de administrador para hardware](../../../en/images/users/passwordless-login-hardware-propmpt.png)

Assim que você desbloquear seu autenticador — pressionando um botão, escaneando sua impressão digital ou rosto, digitando um PIN ou uma combinação dos métodos anteriores, dependendo do seu autenticador — a mensagem desaparece, o autenticador é registrado e a tela aparece da seguinte forma:

![autenticador registrado seguro de login de administrador](../../../en/images/users/passwordless-login-registered-authenticator.png)

É muito importante notar que você só pode registrar ou remover autenticadores na sua própria conta de usuário. Por razões de segurança, até mesmo um Super Usuário é impedido de registrar, editar ou adicionar autenticadores em outras contas de usuário.

### Autenticadores

Você pode usar qualquer autenticador FIDO U2F ou FIDO2. O FIDO U2F é um padrão mais antigo que suporta uma seleção de métodos criptográficos mais limitada e menos segura. O FIDO2 é o padrão mais novo que suporta métodos criptográficos muito mais seguros, incluindo Criptografia de Curva Elíptica, um método criptográfico que se acredita ser resistente até mesmo à computação quântica (caso ela se torne uma realidade prática). Além disso, os autenticadores FIDO2 podem ser configurados para ter proteções adicionais, como um PIN ou controle biométrico (por exemplo, escaneamento de impressões digitais), o que significa que mesmo se você perder a posse física do próprio autenticador, quem o encontrar não poderá fazer login nos seus sites.

Se você está procurando comprar um autenticador de hardware, pode procurar por "FIDO2" no seu mercado favorito, como Amazon. Há uma ampla seleção para escolher.

Você também pode usar uma chave FIDO de software, como o Krypton, como seu autenticador.

Muitos dispositivos têm autenticação compatível com FIDO2 embutida:

- O Windows 10 e 11 têm o Windows Hello com um PIN, scanner de impressão digital, câmera de reconhecimento facial ou uma combinação de chave de hardware e PIN. O suporte para o Windows Hello está sendo adicionado ao plugin com a meta de lançamento no Joomla 4.2.0.
- O macOS tem o TouchID em todos os laptops com o chipset T2 ou aqueles baseados em Apple Silicon usando o sensor TouchID embutido, bem como todos os desktops baseados em Apple Silicon usando o novo teclado de alumínio da Apple com scanner de impressões digitais.
- O iOS / iPadOS tem o TouchID em todos os dispositivos com scanner de impressões digitais e o FaceID em todos os dispositivos mais novos com câmera de projeção de ponto infravermelho FaceID.
- Alguns dispositivos Android têm um scanner de impressões digitais ou uma câmera de reconhecimento facial. Estes também podem funcionar como autenticadores FIDO2, em Android 9 ou posterior usando o Google Chrome, no mínimo.
- Outros dispositivos também podem estar disponíveis. Por exemplo, telefones Android usando
  ![caBLE](https://groups.google.com/a/fidoalliance.org/g/fido-dev/c/go6GoFW27Dw/m/9flCLR5pBQAJ?pli=1)

### Navegadores compatíveis com WebAuthn

Navegadores baseados em Chromium e Firefox suportam WebAuthn desde o início de 2019.

Safari e todos os navegadores iOS/iPadOS (que, na verdade, são Safari com uma aparência diferente) suportam totalmente WebAuthn desde que o iOS/iPadOS 13 foi lançado no final de 2019.

Praticamente falando, se o seu sistema operacional e navegador foram lançados após meados de 2020, você não deve ter problemas. Apenas alguns navegadores muito incomuns ainda não têm suporte para WebAuthn.

## Autenticação

Para fazer login, você deve inserir seu nome de usuário no campo Nome de Usuário do formulário de login. Você não precisa digitar sua senha, mas se o seu navegador preencher automaticamente, apenas deixe como está. A senha NÃO é enviada para o servidor quando o formulário é enviado através do botão de Autenticação Web.

Segue-se que você pode fazer login com seu Nome de Usuário e Senha ou com Nome de Usuário e Autenticação Web.

## Como Desativar o Plugin

Se você não deseja permitir o WebAuthn, basta ir à lista de plugins e encontrar Sistema - Login Sem Senha WebAuthn no grupo Sistema e desativá-lo. Não há parâmetros a serem configurados.

## Requisitos do Servidor

Para que o WebAuthn funcione, as seguintes condições prévias devem ser atendidas:

- HTTPS com um certificado válido e assinado. A maioria dos provedores permite
  o uso gratuito de certificados emitidos pelo Let's Encrypt. Estes funcionam
  perfeitamente com o WebAuthn.
- A extensão OpenSSL para PHP deve estar instalada e habilitada.
- A extensão PHP GMP ou a extensão PHP BCmath deve estar instalada e
  habilitada (qualquer uma das duas serve).
- A biblioteca Sodium idealmente deve estar habilitada; ela possibilita o uso da
  Criptografia de Curva Elíptica em autenticadores FIDO2 compatíveis, que, como
  dissemos, é o método criptográfico mais seguro.

## Perguntas Frequentes e Solução de Problemas

### Não consigo ver o botão de login "Autenticação Web"

Você não está acessando seu site através de HTTPS. WebAuthn está disponível apenas para sites HTTPS com um certificado válido. Esta é uma precaução de segurança incorporada no padrão WebAuthn. O plugin na verdade verifica se o site está sendo acessado através de HTTPS usando a classe Uri do Joomla. Em casos raros, onde o servidor mente sobre o protocolo, você pode não ver o botão, mesmo que seu site seja (ou alegue ser) HTTPS. O mesmo ocorre se você editar o arquivo configuration.php e configurar o parâmetro opcional \$live_site com um prefixo de protocolo http:// em vez de https://.

Note também que módulos e componentes de login de terceiros que implementam seu próprio formulário de login podem ainda não exibir esses botões. Adicionamos nova infraestrutura para suportá-los, assim como tivemos que fazer no Joomla! 3.2 para suportar a Autenticação de Dois Fatores.

### Ainda preciso fornecer um nome de usuário. O WebAuthn não deveria eliminar os nomes de usuário?

Na verdade, não. A especificação atual do WebAuthn não fornece gerenciamento de identidade. Os navegadores exigem que enviemos uma lista de chaves públicas WebAuthn aceitáveis durante a fase de login. Isso significa que precisamos do seu nome de usuário para buscá-las.

Dito isso, o uso do WebAuthn finalmente deixa claro que os nomes de usuário *não devem ser considerados segredos*. Eles são considerados informações públicas que podem ser livremente transmitidas a um adversário, assim como as chaves públicas armazenadas no banco de dados do site. O único segredo é armazenado no autenticador e nunca sai dele!

### Registrei um autenticador, mas ao tentar fazer login recebo uma informação que não registrei. Isso é um bug?

É um bug, mas não no plugin do WebAuthn propriamente dito.

Um ou mais plugins em seu site estão gerando Notificações, Avisos ou Erros em PHP, corrompendo assim a resposta enviada de volta pelo seu servidor. Como resultado, o JavaScript na página não consegue analisar a resposta do servidor e não tem certeza se há autenticadores registrados pelo usuário.

Vá para o backend do seu site, Sistema, Configuração Global e defina Relatório de Erros para Nenhum. Na maioria dos casos de plugins principais e de terceiros com mau comportamento, isso é suficiente. Caso contrário, examine a saída da solicitação usando ferramentas de desenvolvedor do seu navegador para ver o que está corrompendo a solicitação.

### Não há aviso no Safari para usar meu autenticador

Isso não deveria mais acontecer com iOS 13, iPadOS 13 e macOS Catalina ou qualquer versão posterior.

Este é um bug do Safari em versões mais antigas. Versões mais antigas do Safari incluíram o suporte para WebAuthn apenas como um recurso experimental e não totalmente finalizado.

### Não consigo usar um sensor biométrico (TouchID, impressão digital, Windows Hello)

Alguns navegadores baseados no Chromium mais antigos (exceto o Google Chrome propriamente) não tinham suporte total para autenticadores integrados. Eles poderiam travar ou parar de responder quando você tentasse usar um. Esses problemas foram corrigidos nesses navegadores por volta de meados de 2020.

Se você estiver usando Windows, lembre-se de que seu dispositivo DEVE ter um chip Trusted Platform Module (TPM) e ele deve estar habilitado no BIOS. Apenas ter um sensor biométrico compatível com o Windows Hello não será suficiente. Esta é uma precaução de segurança no próprio padrão WebAuthn: as informações do autenticador devem ser processadas usando hardware seguro e à prova de adulteração para evitar a subversão da chave (por exemplo, malware em execução no computador não pode roubar a chave usada para autenticação).

Finalmente, lembre-se de que o suporte ao Windows Hello ainda está sendo desenvolvido e será lançado com o Joomla 4.2.

### Se posso usar um autenticador de software, por que me preocupar com um token de hardware?

O ponto central do WebAuthn é o segredo absoluto da chave privada. Ele é conhecido apenas pelo autenticador e deve ser impossível se comunicar com o mundo exterior.

No caso de um autenticador de hardware, seja um dispositivo de hardware discreto ou um TPM / Secure Enclave integrado em seu dispositivo, isso é garantido pela própria natureza desse hardware.

Um autenticador de software gera uma chave secreta e a armazena no sistema de arquivos. No entanto, ainda é um aplicativo de software regular que roda dentro do seu sistema operacional regular, seja no seu telefone ou computador. Como resultado, é suscetível a várias classes de ataques que podem ser usados para roubar informações furtivamente (problemas de segurança no próprio software, malware usando vulnerabilidades da classe Spectre em CPUs modernas etc.).

Portanto, um autenticador de software é muito mais conveniente e seguro do que uma senha regular, mas um autenticador de hardware oferece a melhor segurança. Escolha seu autenticador com base no seu orçamento e necessidades de segurança.

Considerando que o preço de uma chave FIDO - que é compatível com o WebAuthn - está abaixo de €10 na Amazon, você pode usar um autenticador de hardware na maioria dos casos práticos.

### Por que as credenciais são criptografadas no banco de dados? Isso não é exagero?

A única coisa armazenada no banco de dados é a chave pública retornada pelo autenticador quando estamos realizando a cerimônia de atestação (esse é o nome formal do registro de um autenticador de acordo com a especificação WebAuthn). Sendo uma chave pública, não precisa de proteção contra leitura. Mesmo que um usuário não autorizado conseguisse ler essas informações, não poderia imitar o autenticador, por exemplo, clonando-o.

No entanto, se um usuário malicioso tivesse acesso de gravação apenas à tabela de banco de dados `#__webauthn_credentials`, sem acesso de leitura ao sistema de arquivos e sem acesso de gravação a qualquer outra tabela, ele poderia conceber **adicionar** seu próprio autenticador, sendo capaz de se passar pelo usuário alvo no sistema. Este é um ataque muito teórico, pois também precisariam conhecer o identificador de usuário para o usuário que estão atacando, o que é mais difícil de obter sem algum conhecimento interno do próprio site. Além disso, ter acesso de gravação apenas a esta tabela e não ao banco de dados inteiro (caso em que poderiam criar um novo usuário super) é extremamente improvável. Ainda assim, estamos criptografando as credenciais para tornar impossível mesmo este ataque totalmente teórico.

Estamos totalmente cientes de que, se um usuário tiver acesso de leitura ao sistema de arquivos do servidor, ele terá acesso à chave de criptografia e às informações de conexão do banco de dados, todas elas armazenadas no configuration.php. No entanto, neste caso, você já está comprometido: o invasor pode ler o configuration.php, portanto, sabe como conectar-se ao seu banco de dados. Neste caso, ele pode fazer o que quiser com seu site, incluindo excluir todos os super usuários existentes e criar sua própria conta de super usuário. Portanto, não há razão para tentar resolver esta situação; você estaria completamente comprometido (hackeado). A única coisa que poderia salvar você são backups regulares, testados e fora do local.

### Configurei a Autenticação de Dois Fatores, mas estou entrando sem fornecer minha Chave Secreta. Isso não é inseguro?

Não, é intencional e foi projetado assim.

Quando adicionamos a Autenticação de Dois Fatores (TFA) no Joomla! 3.2, só era possível fazer login no seu site usando um nome de usuário e senha. Senhas podem ser roubadas ou adivinhadas. Portanto, a TFA era a única maneira de fornecer uma mediana de segurança em alvos de alto risco e alto valor. Isso foi em 2013.

WebAuthn é uma solução de autenticação totalmente diferente que não tem os problemas de senhas fixas. Ele usa criptografia forte e hardware seguro para tornar praticamente impossível subverter as chaves criptográficas de autenticação. Também é não phishable, ou seja, você não pode ser enganado ao usá-lo em um site falso, pois a credencial WebAuthn está vinculada ao nome de domínio exato para o qual foi emitida (sim, se você usar vários domínios para seu site ou transferir seu site para outro domínio, precisará registrar novamente todos os seus autenticadores WebAuthn - você entendeu corretamente!). Como resultado, a autenticação com WebAuthn é incrivelmente segura e substitui os motivos que tornaram a TFA necessária. Isso significa que, se você se autenticar com sucesso usando WebAuthn, a chave secreta da TFA não precisa ser - e, portanto, não é - verificada.

Em um mundo ideal, você só poderia entrar no seu site usando WebAuthn. Esta é uma funcionalidade em que estamos trabalhando e que você talvez não queira habilitar; afinal, se o nome do seu domínio mudar ou você perder o acesso ou redefinir todos os seus autenticadores WebAuthn, você ficará bloqueado fora do seu site. Portanto, você ainda deve habilitar a TFA na sua conta de usuário com base no fato de que o login por senha ainda pode ser usado como um remendo para entrar no seu site e deve ser protegido de ataques conhecidos contra senhas fixas.

### A TFA não é boa o suficiente? Por que precisamos do WebAuthn?

A TFA sozinha é boa o suficiente na maioria dos casos, mas sofre de dois problemas.

Primeiro, tem uma experiência de usuário bastante incômoda. Você precisa fornecer sua chave secreta em constante mudança com seu nome de usuário e senha. A maioria das pessoas usa TOTP (o PIN de seis dígitos que muda a cada 30 segundos) que desacelera o processo de login e tende a frustrar os usuários. Usar uma YubiKey é muito mais rápido, mas também mais caro e mais complicado de provisionar quando você tem mais de alguns usuários no site. Uma YubiKey também tem uma expectativa de vida de cerca de 2 anos de uso diário ao gerar Senhas de Uso Único (ela esgota a memória de gravação única que usa para controlar as assinaturas que emitiu).

Segundo, se você estiver usando TOTP, ainda está suscetível a problemas de segurança, como keyloggers, phishing e a possibilidade de a chave secreta usada para gerar o TOTP ser roubada. Além disso, com um milhão de possibilidades e trinta segundos para tentar todas, é concebível que um invasor possa ter sorte, uma vez que o Joomla! não bloqueia sua conta ou emprega limitações de taxa para tentativas de login fracassadas. Embora essas proteções pudessem ser implementadas, a implementação em si poderia ser abusada para criar uma situação de negação de serviço que bloqueia um usuário legítimo fora do seu site enquanto o invasor está ocupado tentando invadir. É um caso de o remédio ser pior do que a doença.

WebAuthn melhora significativamente a experiência do usuário. Os principais navegadores abraçaram o WebAuthn e oferecem uma experiência de usuário convincente, orientando os usuários a usar os autenticadores com sucesso. Fazer login com WebAuthn é mais conveniente, mesmo quando comparado ao recurso de preenchimento automático de um gerenciador de senhas. Com as versões recentes dos sistemas operacionais móveis, até mesmo essa experiência, uma vez ligeiramente confusa, está se tornando rapidamente mais fácil do que as senhas e a TFA jamais foram.

Onde o WebAuthn realmente está se destacando é na frente da segurança. Em virtude de usar hardware seguro e validação forte do nome de domínio do site, ele é praticamente imune a keyloggers, phishing e subversão de chave. Ele até tem proteção embutida contra clonagem de chaves. Sim, você ainda pode perder seu hardware — mas os autenticadores FIDO2, sejam dispositivos externos ou integrados, podem ser bloqueados com um PIN ou biometria. No geral, usar o WebAuthn com autenticadores FIDO2 é mais resistente a furtos e perdas do que suas chaves de casa ou do carro.

## Notas para Desenvolvedores

### Botões de login extra

O módulo do plugin e o com_users agora usam o evento onUserLoginButtons, definido e chamado em `Joomla\CMS\Helper\AuthenticationHelper::getLoginButtons`, para recuperar as definições de quaisquer botões adicionais que precisam ser colocados após o botão de login regular.

Todos os desenvolvedores que implementam um módulo de login ou, mais geralmente, um formulário de login também devem usar o método estático público `Joomla\CMS\Helper\AuthenticationHelper::getLoginButtons` para recuperar essas definições e renderizar esses botões para tornar seu software totalmente compatível com o Joomla 4.

Desenvolvedores que desejam implementar botões personalizados devem observar como o plugin do sistema WebAuthn implementa essa funcionalidade. Esses botões podem ser usados para a implementação de serviços de logon único de terceiros ou até mesmo para fazer login usando serviços de identidade de terceiros, como aqueles oferecidos por mídias sociais populares (Facebook, Google, Twitter, GitHub, etc).

Essa mudança não impacta adversamente a compatibilidade retroativa. Módulos de login e formulários de login de terceiros continuarão funcionando normalmente, mesmo que não implementem o recurso de botões de login extra, com a exceção notável das integrações proporcionadas por esse recurso, como a própria Autenticação na Web. Ou seja, eles não deixarão de funcionar (o que seria uma quebra de compatibilidade) mas não estarão completos em termos de funcionalidades.

### Permitindo com_ajax na página de login do backend

A página de login do Administrador lista com_ajax como permitido em AdministratorApplication, para que possa ser usado para lidar com solicitações por usuários convidados.

Essa mudança não causa problemas de compatibilidade retroativa, desde que os desenvolvedores usem práticas sensatas e não assumam que ser chamado por com_ajax no backend é prova de que o usuário está logado no backend. Isso seria uma má prática de segurança. A prática sensata é usar o objeto User do Joomla para detectar se é um usuário convidado e, caso contrário, se o usuário tem permissão necessária para efetuar a ação solicitada por com_ajax. Ou seja, se essa mudança quebrou seu código, então seu código já estava quebrado e precisava ser refeito de qualquer forma.

## Mais Informações

A documentação inicial deste recurso está no pull request em
[PR #28094](https://github.com/joomla/joomla-cms/pull/28094)

*Traduzido por openai.com*

