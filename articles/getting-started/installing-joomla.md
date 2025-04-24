<!-- Filename: J4.x:Installing_Joomla / Display title: Instalando o Joomla -->

## Introdução

Instalar o Joomla! pela primeira vez é muito fácil. Após a conclusão dos passos preliminares, configurar um ambiente de hospedagem e criar um banco de dados, o instalador web integrado do Joomla configurará seu novo site em apenas alguns minutos. Os passos anteriores:

### Configuração de Hospedagem

Se você ainda não configurou um ambiente de hospedagem, precisa fazer isso agora, seja em um serviço de hospedagem ou no seu computador local.

Além disso, existem algumas configurações do PHP que precisam ser suficientes para o Joomla ser instalado. As configurações geralmente estão em um arquivo de configuração *php.ini* ou *user.ini* no servidor. Se você estiver em hospedagem compartilhada, fale com o seu serviço de hospedagem sobre como alterar essas configurações, se for possível fazê-lo. Se estiver trabalhando em um localhost, por exemplo com o XAMPP, ou em um VPS ou host dedicado, você não deve ser restringido por essas configurações e pode defini-las você mesmo.

Os valores mínimos para o arquivo *php.ini* são mostrados abaixo:

- *memory_limit:* 256M
- *upload_max_filesize:* 64M
- *post_max_size:* 64M
- *max_execution_time:* 30

É possível trabalhar com valores mais baixos de upload_max_filesize e post_max_size, mas extensões maiores falharão no envio e causarão problemas imprevisíveis.

### Configuração do Banco de Dados

Se você ainda não configurou um banco de dados, faça isso agora. Isso é abordado para um serviço de hospedagem cPanel no tutorial [Hospedagem cPanel](jdocmanual?article=user/hosting/cpanel-hosting). Há também um tutorial *Criando um Banco de Dados para Joomla!* que cobre os métodos localhost e phpMyAdmin.

Você precisará anotar as informações básicas do banco de dados necessárias quando a instalação real do Joomla for iniciada.

- Localização do banco de dados, geralmente *localhost* mesmo em um serviço de hospedagem. Pode ser um servidor específico, como *`dbserver1.yourhost.com`*.
- O nome do banco de dados
- O nome do usuário do banco de dados
- A senha do usuário do banco de dados

## Prepare-se para a Instalação

### Baixando e Enviando Arquivos do Pacote Joomla!

Baixe a versão atual do Joomla! a partir do link na página de [Download Joomla](https://downloads.joomla.org/)

Mova o arquivo zip do pacote de instalação do Joomla baixado para o servidor. Para um serviço de hospedagem, você pode usar a função de Upload do Gerenciador de Arquivos do cPanel ou pode usar um Cliente FTP para transferir o arquivo zip do Joomla 5.x baixado para o seu servidor. Existem vários clientes FTP disponíveis. Aqui está uma [Comparação detalhada de software de cliente FTP](https://en.wikipedia.org/wiki/Comparison_of_FTP_client_software). Em caso de dúvida, use o FileZilla.

É melhor mover o pacote zip baixado para o seu servidor e descompactá-lo lá do que descompactá-lo localmente e depois mover a estrutura de arquivos. Normalmente, você envia seus arquivos da web para a pasta raiz do seu serviço de hospedagem. Esta pasta é tipicamente nomeada como `public_html`, mas outras variações incluem `htdocs` e isso depende de como o seu host configurou o servidor. Para propósitos do Joomla, você pode carregar os arquivos diretamente em *public_html* ou em uma subpasta que você tenha criado dentro dela.

**Aviso:** Se você descompactar os arquivos no seu próprio computador e depois copiá-los para o seu servidor, certifique-se de mover apenas as pastas e arquivos contidos **dentro** do pacote Joomla. Se você descompactar as pastas e arquivos em uma pasta, por exemplo chamada *`Joomla`* e depois enviar essa pasta, seu site precisará ser acessado em *`seusite.com/Joomla`* em vez de *`seusite.com`*. Você pode renomear o subdiretório de Joomla para algo mais adequado ao site, como jblog, e talvez ache isso conveniente. **Nota:** os nomes de diretórios devem estar em minúsculas, sem espaços e usando hífens em vez de sublinhados para separar as palavras.

Os arquivos do pacote zip podem ser extraídos diretamente no host usando várias ferramentas de linha de comando (por exemplo, unzip), que precisam estar instaladas no servidor. Se o seu serviço de hospedagem utiliza a ferramenta de administração cPanel, o botão Extrair pode ser pressionado no Gerenciador de Arquivos. Além disso, a ferramenta gratuita de terceiros Akeeba Kickstart também pode ser usada para esse propósito. Os arquivos e diretórios extraídos serão colocados na pasta atual. A extração no seu computador local depende do seu sistema operacional. Tente clicar com o botão direito e veja se há um menu de extração. Nesse caso, seu sistema operacional pode colocar os arquivos em uma pasta com o mesmo nome do arquivo zip. Após a extração, você pode excluir o arquivo zip e renomear a pasta de extração para algo curto e adequado para uso em uma URL.

## Iniciar Instalação

Com os requisitos acima atendidos, com um banco de dados criado e os arquivos necessários do Joomla no lugar, você está pronto para instalar o Joomla. Inicie o instalador web do Joomla abrindo seu navegador favorito e acessando o nome de domínio do site. Em uma instalação de hospedagem, você usará *`https://www.yoursitename.com`*. Se você estiver instalando o Joomla localmente, você usará *`http://localhost/`* e deverá ver a tela de instalação.

![Joomla installer part 1, installation language and site name](../../../en/images/getting-started/installing-joomla-installer-1.png)

O Joomla tentará identificar o campo *Selecionar Idioma* automaticamente a partir do idioma do seu navegador. Você pode alterar isso se necessário.

Preencha as seguintes informações.

- **Nome do Site** O nome do seu site — isso pode ser alterado a qualquer momento na página de Configuração Global do Site.

Quando tudo na primeira página estiver concluído, selecione o botão *Setup Login Data* para continuar.

## Dados de Login

Agora você deve ver a tela de dados de login.

![Joomla installer part 2, login data](../../../en/images/getting-started/installing-joomla-installer-2.png)

Preencha as seguintes informações.

- **Nome Real** O nome do Super Usuário. É assim que o Joomla irá lhe cumprimentar quando você fizer login.
- **Nome de usuário da conta Super Usuário** O nome de usuário para o *Super Usuário*. Evite usar *admin* como nome do Administrador!
- **Senha de Administrador** Lembre-se de que um Super Usuário tem controle máximo das interfaces do Site e do Administrador, então use uma senha difícil. Use **Meu Perfil** na interface de *Administração* para alterá-la depois.
- **Endereço de Email do Super Usuário** O endereço de email do Super Usuário. Insira um email válido caso você esqueça sua senha. Este é o endereço de email onde você receberá um link para alterar a senha do Super Usuário.

Quando tudo na segunda página estiver concluído, selecione o botão *Setup Database Connection* para continuar.

## Configuração do Banco de Dados

Insira as informações do banco de dados anotadas quando você criou o banco de dados para esta instalação.

![Joomla installer part 3, database configuration](../../../en/images/getting-started/installing-joomla-installer-3.png)

Para simplificação, estas instruções são uma referência para a instalação com um banco de dados MySQLi. As instruções na página de instalação são autoexplicativas, mas aqui estão novamente:

- **Tipo de Banco de Dados** MySQLi é o banco de dados comum utilizado
- **Hostname** Onde o seu banco de dados está localizado. Comum é *localhost*, mesmo em serviços de hospedagem. No entanto, alguns hosts usam um servidor de banco de dados específico, como *dbserver1.yourhost.com*.
- **Nome de Usuário** O nome de usuário utilizado para conectar-se ao banco de dados
- **Senha** A senha para o usuário do banco de dados (não a sua senha de Administrador)
- **Nome do Banco de Dados** O nome do banco de dados
- **Prefixo da Tabela** Isso é gerado automaticamente como uma característica de segurança. Você pode aceitar o padrão gerado aleatoriamente ou alterá-lo. Apenas não se esqueça de colocar o caractere de sublinhado (`_`) no final do prefixo.
- **Criptografia de Conexão** especifica como a conexão com o banco de dados deve ser criptografada. Se você não souber, é melhor ficar com o padrão. No entanto, isso permite que empresas que usam autenticação de um ou dois fatores para a conexão com o banco de dados possam fornecê-la.

Todas essas opções e mais podem ser editadas na página de Configuração Global do Site, em *Opções do Servidor* após a conclusão da instalação. Nota: você quebrará sua instalação se alterar essas configurações após a instalação, a menos que tenha uma cópia completa do banco de dados atual usado pela instalação do Joomla. Usos comuns seriam atualizar o nome de usuário e a senha do banco de dados ou concluir a transferência de uma instalação existente para um novo host com parâmetros diferentes.

Após selecionar o botão *Instalar Joomla*, você deverá ver a barra de progresso de instalação do Joomla.

![Joomla installer part 4, installation progress bar](../../../en/images/getting-started/installing-joomla-installer-4.png)

Depois de concluir a instalação, você deverá ver a página de sucesso.

## Finalizando

### Sucesso e Finalizando a Instalação

Parabéns! Seu site Joomla está pronto.

![Joomla installer part 5, your joomla site is ready](../../../en/images/getting-started/installing-joomla-installer-5.png)

A captura de tela acima mostra uma instalação de desenvolvedor. Uma instalação de produção remove automaticamente a pasta de Instalação.

Se você quiser começar a usar o Joomla imediatamente sem instalar idiomas adicionais, pode selecionar *Abrir Administrador* para ir para o *Painel de Administração* ou selecionar *Abrir Site* para ir para a página inicial do Site. Você pode ver uma seção com configurações de PHP recomendadas.

- **Configurações Recomendadas** Essas configurações são recomendadas na sua configuração do PHP, mas não impedirão a instalação do Joomla!. Você pode se referir às instruções acima sobre como elas podem ser alteradas, caso haja necessidade.

### Idiomas Extras

Como parte do processo de instalação do Joomla, você tem a oportunidade de instalar idiomas adicionais antes de concluir a instalação.

Para fazer isso, selecione o botão Instalar Idiomas Adicionais

Isso levará você a uma página de instalação adicional, permitindo que você selecione os idiomas necessários.

#### Instalar Idiomas Adicionais

Uma lista de pacotes de idiomas é exibida.

![Joomla installer part 6, install additional languages](../../../en/images/getting-started/installing-joomla-installer-6.png)

Selecione até 3 idiomas que você deseja instalar. (Mais de 3 de uma vez pode causar problemas de tempo limite; você pode instalar mais depois.)

Lembre-se do seguinte:

- Pacotes de idiomas incluídos nas distribuições personalizadas não serão listados nesta etapa, pois já estão instalados.
- Uma versão dos pacotes propostos corresponderá à versão Major do Joomla (5.0.x, 5.1.x, etc.). A versão menor do pacote pode não corresponder, por exemplo, você está instalando a versão 5.0.3 e um pacote de idioma 5.0.2 é mostrado.
- Pacotes de idiomas não correspondidos no exemplo acima podem ter cadeias de texto não traduzidas.
- Os pacotes de idiomas não correspondidos serão oferecidos como uma atualização quando os pacotes forem atualizados pelas equipes de Tradução registradas. A atualização disponível será mostrada no Painel de Controle, bem como em **Extensões → Atualização**. Este comportamento é similar a **Extensões → Instalar Idiomas**.

Selecione *Avançar* e uma barra de progresso será exibida enquanto o pacote ou pacotes de idioma são instalados.

#### Escolha o Idioma Padrão

Quando a instalação dos idiomas estiver concluída, você verá uma tela semelhante a *Parabéns! Seu site Joomla está pronto.*. A diferença será uma lista dos idiomas instalados, permitindo que você selecione o idioma padrão para o Site e a interface do Administrador.

![Joomla installer part 7, choose default language](../../../en/images/getting-started/installing-joomla-installer-7.png)

- Selecione o idioma padrão que deseja usar.
- Quando tiver selecionado o idioma padrão, selecione o botão *Definir idioma padrão* 
  para confirmar.
- Uma mensagem do sistema será exibida confirmando que o Joomla definiu o
  idioma padrão do ADMINISTRADOR e do SITE. Essa mensagem pode ser fechada.

#### Finalizar

Você agora pode navegar para o *Painel de Administração*. Faça login selecionando *Abrir Administrador* ou vá diretamente para a página inicial do seu site selecionando *Abrir Site*.

*Traduzido por openai.com*

