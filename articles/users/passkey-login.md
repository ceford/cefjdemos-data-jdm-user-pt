<!--
{
    "source": "https://docs.joomla.org/WebAuthn_Passwordless_Login",
    "title": "Login com Passkey",
    "description": " ",
    "author": ""
}
-->

## Introdução

O login com passkey, anteriormente conhecido como Autenticação Web ou
WebAuthn, permite que um usuário faça login em um site com segurança sem usar
uma senha, embora ainda seja necessário um nome de usuário. Ele usa criptografia
forte de uma maneira extremamente resistente aos problemas mais comuns das
senhas:

* alguém a adivinhou (ataque de força bruta)
* alguém a interceptou (ataque man-in-the-middle)
* alguém enganou você para que a revelasse (ataque de phishing)
* alguém a descobriu depois de obter uma cópia dos dados do seu banco de dados
(ataques de injeção SQL)
* alguém a roubou.

O login com passkey não é apenas muito seguro; ele também é muito fácil de usar!
Você não precisa mais memorizar senhas longas nem usar um gerenciador de senhas.
Tudo de que precisa é de um *autenticador*, às vezes também chamado de
*passkey*.

Um autenticador pode ter várias formas, físicas ou virtuais. Pode ser uma chave
de hardware separada conectada ao seu dispositivo via USB, Bluetooth ou NFC.
Pode ser o próprio dispositivo, desbloqueando o autenticador integrado com um
PIN, leitor de impressão digital, escaneamento facial ou verificação biométrica
semelhante.

Esse recurso já funciona em dispositivos Android e iOS/iPadOS, e estamos
trabalhando para habilitá-lo também no Windows. Ele pode até ser o seu telefone —
atualmente isso é possível com telefones Android, mas esse recurso também está
chegando aos dispositivos iOS / iPadOS.

O login com passkey só funciona por HTTPS e somente quando o seu site usa um
certificado válido e confiável para isso. Não se preocupe, você não precisa
gastar dinheiro extra; serviços gratuitos como o Let's Encrypt normalmente
são integrados aos painéis de controle de hospedagem web e funcionam
perfeitamente com o login com passkey.

O login com passkey usa criptografia de chave pública, a mesma tecnologia
comprovada que mantém seus sites seguros com HTTPS, suas informações bancárias
protegidas e assim por diante. A chave privada nunca sai do autenticador. Seu
site armazena apenas uma chave pública. Mesmo que você sofra uma violação de
dados, o invasor ficará com uma chave pública praticamente inútil; seriam
necessários milhares a milhões de anos de CPU para quebrá-la, em comparação
com os poucos minutos ou horas necessários para quebrar o hash de uma senha
fixa que você consegue memorizar.

O login com passkey é o futuro da autenticação. Fácil, seguro e sem complicações.
Tudo o que as senhas fixas não são.

A imagem a seguir mostra um dispositivo de hardware inserido na porta USB de
um computador portátil. Ele custou £15 em fevereiro de 2022.

![fotografia de dispositivo de hardware](../../../en/images/users/passkey-login/01-hardware-device.jpg)

O login com passkey usa um plugin do sistema que é habilitado por padrão. Um
botão **Entrar com passkey** estará presente nas telas de login padrão do Joomla
4 e posteriores, conforme ilustrado na tela de login do Administrador:

![formulário de login seguro do administrador](../../../en/images/users/passkey-login/02-login-form.png)

## Configuração do usuário

O usuário deve primeiro se registrar com um Nome de usuário e uma Senha normais.
Depois de fazer login, acesse o formulário do Perfil do usuário. Para um
Administrador:

- Selecione **Menu do usuário → Editar conta → Login com passkey** para ver o formulário,
  inicialmente sem nenhum autenticador registrado.
- Selecione **Adicionar nova passkey**

A apresentação exata da próxima etapa depende do seu navegador. Normalmente,
você verá um alerta, uma mensagem ou uma janela solicitando que selecione um
tipo de autenticador ou, se estiver usando um autenticador de hardware
conectado ao seu dispositivo, lembrando você de pressionar o botão no
autenticador de hardware. Por motivos de segurança e praticidade, há um
intervalo de tempo relativamente curto permitido para ativar o autenticador:
60 segundos.

![solicitação de hardware do login seguro do administrador](../../../en/images/users/passkey-login/03-hardware-prompt.png)

Depois de desbloquear o autenticador — tocando em um botão, escaneando sua
impressão digital / rosto, inserindo um PIN ou uma combinação dos itens acima,
dependendo do seu autenticador — a mensagem desaparece, o autenticador é
registrado e a tela aparece da seguinte forma:

![autenticador registrado no login seguro do administrador](../../../en/images/users/passkey-login/04-registered-authenticator.png)

É muito importante observar que você só pode registrar ou remover
autenticadores da sua própria conta de usuário. Por motivos de segurança, nem
mesmo um Superusuário pode registrar, editar ou adicionar autenticadores em
outras contas de usuário.

### Autenticadores

Você pode usar qualquer autenticador FIDO U2F ou FIDO2. FIDO U2F é um
padrão mais antigo que oferece suporte a uma seleção mais limitada e menos
segura de métodos criptográficos. FIDO2 é o padrão mais recente, que oferece
suporte a métodos criptográficos muito mais seguros, incluindo a Criptografia
de Curvas Elípticas, um método criptográfico que se acredita ser resistente
até mesmo à computação quântica (caso e quando ela se torne uma realidade
prática). Além disso, os autenticadores FIDO2 podem ser configurados para
ter proteções adicionais, como um PIN ou um controle biométrico (por exemplo,
leitura de impressão digital), o que significa que, mesmo que você perca a
posse física do próprio autenticador, quem o encontrar não poderá entrar nos
seus sites.

Se você está procurando comprar um autenticador de hardware, pode procurar
por "FIDO2" no seu marketplace favorito, como a Amazon. Há uma grande
variedade para escolher.

Você também pode usar uma chave FIDO de software, como o Krypton, como seu
autenticador.

Muitos dispositivos têm autenticação integrada compatível com FIDO2:

- O Windows 10 e 11 têm o Windows Hello com um PIN, leitor de impressão digital,
  câmera de reconhecimento facial ou uma combinação de chave de hardware e PIN.
- O macOS tem TouchID em todos os laptops com o chipset T2 ou baseados em
  Apple Silicon que usam o sensor TouchID integrado, bem como em todos os
  desktops baseados em Apple Silicon que usam o novo teclado Apple Aluminium
  com leitor de impressão digital.
- O iOS / iPadOS tem TouchID em todos os dispositivos com leitor de impressão
  digital e FaceID em todos os dispositivos mais recentes com uma câmera
  infravermelha de projeção de pontos FaceID.
- Alguns dispositivos Android têm um leitor de impressão digital ou uma câmera
  de reconhecimento facial. Eles também podem funcionar como autenticadores
  FIDO2, no Android 9 ou posterior, usando pelo menos o Google Chrome.
- Outros dispositivos também podem estar disponíveis. Por exemplo, telefones
  Android que usam
  [caBLE](https://groups.google.com/a/fidoalliance.org/g/fido-dev/c/go6GoFW27Dw/m/9flCLR5pBQAJ?pli=1)

### Navegadores compatíveis com login por chave de acesso

Na prática, se o seu sistema operacional e navegador foram lançados
depois de meados de 2020, você não deverá ter problemas. Apenas alguns
navegadores muito incomuns ainda não oferecem suporte ao login por chave de acesso.

## Autenticação

Para entrar, você deve inserir seu nome de utilizador no campo Nome de utilizador
do formulário de login. Não é necessário inserir sua senha, mas, se o navegador
a inserir por você, basta deixá-la. A senha NÃO é enviada ao servidor quando o
formulário é enviado pelo botão de Autenticação da Web.

Consequentemente, você pode entrar usando seu Nome de utilizador e Senha ou
usando o login com Nome de utilizador e chave de acesso.

## Como desativar o plugin

Se você não deseja permitir o login por chave de acesso, basta acessar a lista de plugins,
localizar o plugin **System - Passkey (Passwordless) Login** no grupo Sistema e
desativá-lo. Não há parâmetros para configurar.

## Requisitos do servidor

Para que o login por chave de acesso funcione, as seguintes condições prévias
devem ser atendidas:

- HTTPS com um certificado válido e assinado. A maioria dos hosts permite usar
  certificados gratuitos emitidos pela Let's Encrypt. Eles funcionam perfeitamente
  com o login por chave de acesso.
- A extensão OpenSSL do PHP deve estar instalada e habilitada.
- A extensão GMP do PHP ou a extensão BCmath do PHP deve estar instalada
  e habilitada (qualquer uma delas é suficiente).
- A biblioteca Sodium deve estar habilitada, idealmente; ela permite o uso da
  Criptografia de Curvas Elípticas em autenticadores FIDO2 compatíveis, que,
  como dissemos, é o método criptográfico mais seguro.

## Perguntas frequentes e solução de problemas

### Não consigo ver o botão *Entrar com chave de acesso*

Você não está acessando seu site por HTTPS. O login por chave de acesso só está disponível
para sites HTTPS com um certificado válido. Essa é uma precaução de segurança
incorporada ao padrão de login por chave de acesso. O plugin verifica efetivamente se o site
é acessado por HTTPS usando a classe Uri do Joomla. Em casos raros em que o servidor informa
incorretamente o protocolo, talvez você não veja o botão, mesmo que seu site (afirme que) use
HTTPS. O mesmo acontece se você tiver editado o arquivo configuration.php e configurado o
parâmetro de configuração opcional \$live_site com um prefixo de protocolo http:// em vez de https://.

Observe também que módulos e componentes de login de terceiros que implementam
seu próprio formulário de login talvez ainda não exibam esses botões. Adicionamos
uma nova infraestrutura para oferecer suporte a eles, semelhante ao que tivemos de fazer no
Joomla! 3.2 para oferecer suporte à Autenticação de dois fatores.

### Ainda preciso fornecer um nome de usuário. O login com Passkey não deveria eliminar os nomes de usuário?

Na verdade, não. A especificação atual do login com Passkey não fornece
gerenciamento de identidades. Os navegadores da Web exigem que enviemos a eles
uma lista de chaves públicas de login com Passkey aceitáveis durante a fase de
login. Isso significa que precisamos do seu nome de usuário para obtê-las.

Dito isso, usar o login com Passkey finalmente deixa claro que nomes de usuário *não devem
ser considerados segredos*. Eles são considerados informações públicas que
podem ser transmitidas livremente a um adversário, assim como as chaves públicas
armazenadas no banco de dados do site. O único segredo é armazenado no
próprio autenticador e nunca sai dele!

### Registrei um autenticador, mas tentar fazer login informa que não registrei nenhum. Isso é um bug?

É um bug, mas não no próprio plugin de login com Passkey.

Um ou mais plugins do seu site geram Notices, Warnings ou Errors do PHP,
corrompendo, assim, a resposta enviada pelo seu servidor. Como resultado, o
JavaScript da página não consegue analisar a resposta do servidor e não sabe ao certo
se algum autenticador foi registrado pelo usuário.

Acesse o painel administrativo do seu site, Sistema, Configuração Global e defina o Relatório de Erros como Nenhum. Na maioria dos casos de plugins problemáticos do núcleo e de terceiros
isso é suficiente. Caso contrário, examine a saída da solicitação usando as
ferramentas de desenvolvedor do seu navegador para descobrir o que está corrompendo a solicitação.

### Não há nenhuma solicitação no Safari para usar meu autenticador

Isso não deveria mais acontecer com o iOS 13, o iPadOS 13 e o macOS
Catalina ou qualquer versão posterior.

Isso é um bug do Safari em versões mais antigas do Safari. As versões mais antigas do
Safari incluíam apenas suporte ao login com Passkey como um recurso experimental e
ainda não totalmente concluído.

### Não consigo usar um sensor biométrico (TouchID, impressão digital, Windows Hello)

Alguns navegadores mais antigos baseados no Chromium (exceto o Google Chrome propriamente dito) não tinham
suporte completo para autenticadores integrados. Eles travavam ou congelavam
quando você tentava usar um. Esses problemas foram corrigidos nesses navegadores
por volta de meados de 2020.

Se estiver usando o Windows, lembre-se de que seu dispositivo DEVE ter um chip
Trusted Platform Module (TPM), que deve estar habilitado no BIOS.
Ter apenas um sensor biométrico compatível com o Windows Hello não será suficiente. Esta é uma precaução de segurança do próprio padrão de login com Passkey:
as informações do autenticador devem ser processadas usando hardware seguro e
resistente a adulterações para impedir a subversão da chave (por exemplo, um malware
em execução no computador não pode roubar a chave usada para autenticação).

Por fim, lembre-se de que o suporte ao Windows Hello ainda está sendo
desenvolvido e será lançado com o Joomla 4.2.

### Se posso usar um autenticador de software, por que deveria me preocupar com um token de hardware?

O ponto central do login com Passkey é o sigilo absoluto da chave privada. Ela
é conhecida apenas pelo autenticador e deve ser impossível
comunicá-la ao mundo exterior.

No caso de um autenticador de hardware, seja um dispositivo de hardware
independente ou um TPM / Secure Enclave integrado ao seu dispositivo, isso é garantido
pela própria natureza desse hardware.

Um autenticador de software gera uma chave secreta e a armazena no
sistema de arquivos. No entanto, ele ainda é um aplicativo de software comum que
é executado dentro do seu sistema operacional comum, seja o do seu
telefone ou o do seu computador. Como resultado, ele é suscetível a várias classes de ataques
que podem ser usadas para roubar informações sub-repticiamente (problemas de segurança
no próprio software, malware que usa vulnerabilidades da classe Spectre em
CPUs modernas etc.).

Portanto, um autenticador de software é muito mais conveniente e seguro do que
uma senha comum, mas um autenticador de hardware oferece a melhor segurança.
Escolha seu autenticador com base no seu orçamento e nas suas necessidades de segurança.

Considerando que o preço de uma chave FIDO (compatível com
o login com Passkey) é inferior a €20 na Amazon, você pode usar um autenticador de hardware na
maioria dos casos práticos de uso.

### Por que as credenciais são criptografadas no banco de dados? Isso não é exagero?

A única coisa armazenada no banco de dados é a chave pública retornada pelo
autenticador quando estamos realizando a cerimônia de atestação (esse é o
nome formal para registrar um autenticador, de acordo com a especificação de
login com Passkey). Por ser uma chave pública, ela não precisa ser protegida
contra leitura. Mesmo que um usuário não autorizado conseguisse ler essas
informações, não seria capaz de se passar pelo autenticador, por exemplo,
clonando-o.

No entanto, se um usuário mal-intencionado tivesse acesso de gravação apenas à
tabela de banco de dados `#__webauthn_credentials`, sem acesso de leitura ao
sistema de arquivos e sem acesso de gravação a qualquer outra tabela, ele
poderia, teoricamente, **adicionar** seu próprio autenticador e, assim,
conseguir se passar pelo usuário visado no sistema. Esse é um ataque bastante
teórico, pois também seria necessário conhecer o identificador do usuário que
está sendo atacado, algo mais difícil de obter sem algum conhecimento interno
do próprio site. Além disso, ter acesso de gravação apenas a essa tabela, e não
ao banco de dados inteiro (caso em que seria possível criar um novo
Superusuário), é extremamente improvável. Ainda assim, criptografamos as
credenciais para tornar impossível até mesmo o sucesso desse ataque
inteiramente teórico.

Temos plena consciência de que, se um usuário tiver acesso de leitura ao
sistema de arquivos do servidor, ele terá acesso à chave de criptografia e às
informações de conexão com o banco de dados, todas armazenadas em
configuration.php. No entanto, nesse caso, você já foi invadido: o invasor
pode ler o configuration.php e, portanto, sabe como se conectar ao seu banco
de dados. Nesse caso, ele pode fazer o que quiser no seu site, inclusive
excluir todos os Superusuários existentes e criar sua própria conta de
Superusuário. Portanto, não há motivo para tentar lidar com essa situação;
você estaria totalmente comprometido (invadido). A única coisa que poderia
salvá-lo seriam backups regulares, testados e armazenados fora do local.

### Configurei a autenticação de dois fatores, mas estou conectado sem fornecer minha chave secreta. Isso não é inseguro?

Não, isso é intencional e faz parte do projeto.

Quando adicionamos a autenticação de dois fatores (TFA) no Joomla! 3.2, você
só conseguia fazer login no seu site usando um nome de usuário e uma senha.
Senhas podem ser roubadas ou adivinhadas. Portanto, a TFA era a única forma de
oferecer um mínimo de segurança em alvos de alto risco e alto valor. Isso foi
em 2013.

O login com Passkey é uma solução de autenticação completamente diferente,
que não apresenta nenhum dos problemas das senhas fixas. Ele usa criptografia
forte e hardware seguro para tornar praticamente impossível subverter as
chaves criptográficas de autenticação. Ele também não é suscetível a
phishing, ou seja, você não pode ser enganado para usá-lo em um site que se
passa por outro, pois a credencial de login com Passkey está vinculada ao nome
de domínio exato para o qual foi emitida (sim, se você usar vários domínios
para o seu site ou transferir o site para outro domínio, será necessário
registrar novamente todos os seus autenticadores de login com Passkey — você
entendeu corretamente!). Como resultado, a autenticação com login por Passkey
é incrivelmente segura e supera os motivos que tornaram a TFA necessária.
Isso significa que, se você se autenticar com sucesso usando o login com
Passkey, a chave secreta da TFA não precisa ser — e, portanto, não é —
verificada.

Em um mundo ideal, você só conseguiria fazer login no seu site usando o login
com Passkey. Esse é um recurso no qual estamos trabalhando, e talvez você não
queira ativá-lo; afinal, se o nome do seu domínio mudar ou se você perder o
acesso a todos os seus autenticadores de login com Passkey, ou redefini-los,
ficará impedido de acessar seu site. Portanto, você ainda deve ativar a TFA na
sua conta de usuário, considerando que o login com senha ainda pode ser usado
como alternativa para acessar seu site e deve ser protegido contra ataques
conhecidos a senhas fixas.

### O TFA não é suficiente? Por que precisamos do login com chave de acesso?

O TFA por si só é suficiente na maioria dos casos, mas apresenta dois problemas.

Primeiro, ele proporciona uma experiência de usuário bastante inconveniente. Você precisa fornecer sua
chave secreta, que muda constantemente, junto com seu nome de usuário e senha. A maioria das pessoas
usa TOTP (o PIN de seis dígitos que muda a cada 30 segundos), o que torna
o login mais lento e tende a frustrar os usuários. Usar uma YubiKey é muito
mais rápido, mas também é mais caro e complicado de provisionar quando
você tem mais do que alguns usuários no site. Uma YubiKey também tem uma
vida útil esperada de cerca de 2 anos de uso diário ao gerar senhas de uso único (ela fica sem a
memória de gravação única usada para controlar as
assinaturas emitidas).

Segundo, se você estiver usando TOTP, ainda estará suscetível a problemas de segurança
como keyloggers, phishing e à possibilidade de que a chave secreta
usada para gerar o TOTP seja roubada. Além disso, com um milhão de
possibilidades e trinta segundos para tentar, é concebível que um
invasor tenha sorte, já que o Joomla não bloqueia sua conta nem
emprega limitação de taxa para tentativas de login malsucedidas. Embora
essas proteções pudessem ser implementadas, a própria implementação
poderia ser abusada para criar uma situação de negação de serviço que
bloqueasse um usuário legítimo do site enquanto o invasor estivesse
ocupado infiltrando-se nele. É um caso em que o remédio é pior que a doença.

O login com chave de acesso melhora muito a experiência do usuário. Os principais navegadores adotaram
o login com chave de acesso e oferecem uma experiência de usuário convincente, orientando os usuários a
usar autenticadores com sucesso. Fazer login com chave de acesso é mais
conveniente até mesmo quando comparado ao uso do preenchimento automático
de um gerenciador de senhas. Com versões recentes dos sistemas operacionais
móveis, até mesmo essa experiência, que antes era um pouco confusa,
está rapidamente se tornando mais fácil do que as senhas e o TFA jamais foram.

Onde o login com chave de acesso realmente se destaca é na segurança. Por usar
hardware seguro e uma validação forte do nome de domínio do site, ele é
praticamente imune a keyloggers, phishing e subversão de chaves. Ele
também possui proteção integrada contra clonagem de chaves. Sim, você ainda pode
perder seu hardware — mas os autenticadores FIDO2, sejam dispositivos
externos ou integrados, podem ser bloqueados com um PIN ou biometria. No geral, usar
o login com chave de acesso com autenticadores FIDO2 é mais resistente a roubo e perda
do que as chaves da sua casa ou do seu carro.

## Observações para desenvolvedores

### Botões de login adicionais

O módulo de plugin e o com_users agora usam o evento onUserLoginButtons,
definido e chamado em
`Joomla\CMS\Helper\AuthenticationHelper::getLoginButtons`, para recuperar as
definições de quaisquer botões adicionais que precisam ser colocados após o
botão de login normal.

Todos os desenvolvedores que implementarem um módulo de login ou, de modo mais geral, um formulário de login
também devem usar o método estático público
`Joomla\CMS\Helper\AuthenticationHelper::getLoginButtons` para recuperar essas definições e renderizar
esses botões, tornando seu software totalmente compatível com o Joomla 4.

Os desenvolvedores que desejarem implementar botões personalizados devem observar como o
plugin de sistema de login com chave de acesso implementa essa funcionalidade. Esses botões podem ser usados
para implementar serviços de logon único de terceiros ou até mesmo
fazer login usando serviços de identidade de terceiros, como os oferecidos
por redes sociais populares (Facebook, Google, Twitter, GitHub etc.).

Essa alteração não afeta negativamente a compatibilidade com versões anteriores. Os
módulos de login e formulários de login de terceiros continuarão funcionando normalmente,
mesmo que não implementem o recurso de botões de login adicionais, com a
notável ausência de integrações proporcionadas por esse recurso, como a própria Autenticação Web. Em outras palavras, eles não deixarão de funcionar (o que
seria uma quebra de compatibilidade), mas não terão todos os recursos.

### Permitindo com_ajax na página de login do backend

A página de login do Administrador inclui com_ajax na lista de permissões em
AdministratorApplication, para que ele possa ser usado para processar solicitações de usuários
convidados.

Essa alteração não causa problemas de compatibilidade com versões anteriores, desde que os
desenvolvedores usem práticas sensatas e não presumam que ser chamado por
com_ajax no backend seja prova de que o usuário está conectado ao
backend. Essa seria uma prática de segurança inadequada. A prática correta é
usar o objeto User do Joomla para detectar se o usuário é um convidado e, caso não seja,
se ele tem a permissão necessária para executar a ação solicitada por meio do
com_ajax. Em outras palavras, se essa alteração tiver quebrado
seu código, então seu código já estava quebrado e precisava ser reestruturado
de qualquer forma.

## Informações adicionais

A documentação inicial desse recurso está na solicitação de pull request em
[PR #28094](https://github.com/joomla/joomla-cms/pull/28094)

*Traduzido por openai.com*