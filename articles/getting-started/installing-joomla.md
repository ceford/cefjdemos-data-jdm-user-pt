<!-- Filename: J4.x:Installing_Joomla / Display title: Instalando o Joomla -->

## Introdução

Instalar o Joomla! pela primeira vez é muito fácil. Após completar os passos preliminares, configurar um ambiente de hospedagem e criar um banco de dados, o instalador web integrado do Joomla configurará seu novo site em apenas alguns minutos. Os passos anteriores:

### Configuração de Hospedagem

Se você ainda não configurou um ambiente de hospedagem, precisa fazer isso agora, seja em um serviço de hospedagem ou no seu computador local.

Além disso, existem algumas configurações do PHP que precisam ser adequadas para que o Joomla seja instalado. As configurações geralmente estão em um arquivo de configuração *php.ini* ou *user.ini* no servidor. Se você está em hospedagem compartilhada, fale com o seu serviço de hospedagem sobre como alterar essas configurações, se for possível fazê-lo. Se estiver trabalhando em um localhost, por exemplo, com XAMPP, ou um VPS ou host dedicado, você não deve ser restringido por essas configurações e pode ajustá-las você mesmo.

Os valores mínimos para o arquivo *php.ini* estão mostrados abaixo:

- *memory_limit:* 256M
- *upload_max_filesize:* 64M
- *post_max_size:* 64M
- *max_execution_time:* 30

É possível trabalhar com valores menores de upload_max_filesize e post_max_size, mas extensões maiores falharão ao carregar, causando problemas imprevisíveis.

### Configuração do Banco de Dados

Se você ainda não configurou um banco de dados, faça isso agora. Isso é abordado para um serviço de hospedagem cPanel no tutorial [Hospedagem cPanel](jdocmanual?article=user/hosting/cpanel-hosting). Há também um tutorial *Criando um Banco de Dados para Joomla!* que abrange métodos localhost e phpMyAdmin.

Você precisará anotar as informações básicas do banco de dados necessárias quando a instalação real do Joomla for iniciada.

- Localização do banco de dados, geralmente *localhost*, mesmo em um serviço de hospedagem. Pode ser o servidor de um host específico, como *`dbserver1.yourhost.com`*.
- Nome do banco de dados
- Nome do usuário do banco de dados
- Senha do usuário do banco de dados

## Preparar para Instalação

### Baixando e Enviando Arquivos do Pacote Joomla!

Baixe a versão atual do Joomla! a partir do link na
[página de Download do Joomla](https://downloads.joomla.org/)

Mova o arquivo zip do pacote de instalação do Joomla baixado para o servidor.
Para um serviço de hospedagem, você pode usar a função de Upload do Gerenciador de Arquivos do cPanel
ou pode usar um Cliente FTP para transferir o arquivo zip do Joomla
5.x baixado para o seu servidor. Há vários clientes FTP disponíveis.
Aqui está uma [Comparação detalhada de software de clientes FTP](https://en.wikipedia.org/wiki/Comparison_of_FTP_client_software).
Se tiver dúvidas, use o FileZilla.

*Pasta raiz* do Seu Servidor

É melhor mover o pacote zip baixado para o seu servidor e
descompactá-lo lá do que descompactar localmente e depois mover a estrutura de arquivos.
Normalmente, você envia seus arquivos da web para a pasta raiz do seu serviço de hospedagem.
Isso geralmente é chamado de `public_html`, mas outras variações
incluem `htdocs` e isso depende de como seu anfitrião configurou o
servidor. Para propósitos do Joomla, você pode carregar os arquivos diretamente no
*public_html* ou em uma subpasta que você criou dentro dele.

**Aviso:** Se você descompactar os arquivos no seu próprio computador e depois copiá-los para
seu servidor, certifique-se de mover apenas as pastas e arquivos contidos **dentro**
do pacote do Joomla. Se você descompactar as pastas e arquivos em uma pasta,
por exemplo, chamada *`Joomla`* e depois enviar essa pasta, seu site
terá que ser acessado em *`seudominio.com/Joomla`* ao invés de
*`seudominio.com`*. Você pode renomear o subdiretório de Joomla para
algo mais apropriado para o site, como jblog, e pode achar isso
conveniente. **Nota:** os nomes de diretórios devem ser em letras minúsculas, sem
espaços e usando hífens em vez de sublinhados para separar palavras.

Os arquivos do pacote zip podem ser extraídos diretamente no anfitrião usando
várias ferramentas de linha de comando (ex: unzip), que precisam estar instaladas no
servidor. Se o seu serviço de hospedagem usa a ferramenta de administração cPanel, o
botão de Extrair pode ser pressionado no Gerenciador de Arquivos. Além disso,
a ferramenta gratuita de terceiros Akeeba Kickstart
também pode ser usada para esse propósito. Os arquivos e diretórios descompactados
serão colocados na pasta atual. A extração no seu computador local depende
do seu sistema operacional. Tente clicar com o botão direito e veja se há um menu de extração. Neste caso,
seu sistema operacional pode colocar os arquivos em uma pasta com o mesmo nome do arquivo zip.
Após a extração, você pode deletar o arquivo zip e renomear a pasta
extraída para algo curto e adequado para uso em um URL.

## Iniciar Instalação

Com os requisitos acima atendidos, um banco de dados criado e os arquivos necessários do Joomla no lugar, você está pronto para instalar o Joomla. Inicie o instalador web do Joomla abrindo o seu navegador favorito e acessando o nome de domínio do site. Em uma instalação de hospedagem, você usará *`https://www.yoursitename.com`*. Se estiver instalando o Joomla localmente, você usará *`http://localhost/`* e deverá ver a tela de instalação.

![Parte 1 do instalador Joomla, idioma de instalação e nome do site](../../../en/images/getting-started/installing-joomla-installer-1.png)

O Joomla tentará identificar o campo *Selecionar Idioma* automaticamente a partir do idioma do seu navegador. Você pode alterar isso se necessário.

Preencha as seguintes informações.

- **Nome do Site** O nome do seu site — pode ser alterado a qualquer
  momento na página de Configuração Global do Site.

Quando tudo na primeira página estiver completo, clique no botão *Configurar Dados de Login* para continuar.


## Dados de Login

Agora você deve ver a tela de dados de login.

![Instalador Joomla parte 2, dados de login](../../../en/images/getting-started/installing-joomla-installer-2.png)

Preencha as seguintes informações.

- **Nome Real** O nome do Super Usuário. É assim que o Joomla irá
  cumprimentá-lo quando você fizer login.
- **Nome de usuário da conta do Super Usuário** O nome de usuário para o *Super Usuário*.
  Evite usar *admin* como nome do Administrador!
- **Senha de Administrador** Lembre-se de que um Super Usuário tem controle máximo sobre
  as interfaces do Site e do Administrador, por isso use uma senha difícil.
  Use **Meu Perfil** na interface de *Administração* para alterá-la mais tarde.
- **Endereço de Email do Super Usuário** O endereço de email do Super Usuário. Insira um
  email válido caso você esqueça sua senha. Este é o endereço de email
  onde você receberá um link para alterar a senha do Super Usuário.

Quando tudo na segunda página estiver completo, clique no botão *Configurar Conexão ao Banco de Dados*
para prosseguir.

## Configuração do Banco de Dados

Insira as informações do banco de dados anotadas quando você criou o banco de dados
para esta instalação.

![Instalador Joomla parte 3, configuração do banco de dados](../../../en/images/getting-started/installing-joomla-installer-3.png)

Para simplificação, estas instruções são uma referência para instalar
com um banco de dados MySQLi. As instruções na página de instalação são autoexplicativas, mas aqui estão novamente:

- **Tipo de Banco de Dados** MySQLi é o banco de dados comum usado
- **Hostname** Onde seu banco de dados está localizado. Comum é *localhost*,
  mesmo em serviços de hospedagem. No entanto, alguns hosts usam um servidor de banco de dados específico, como *dbserver1.seuhost.com*.
- **Nome de Usuário** O nome de usuário usado para conectar ao banco de dados
- **Senha** A senha para o usuário do banco de dados (não sua
  senha de Administrador)
- **Nome do Banco de Dados** O nome do banco de dados
- **Prefixo das Tabelas** Isso é gerado automaticamente como uma
  característica de segurança. Você pode aceitar o padrão gerado aleatoriamente ou mudá-lo.
  Apenas não se esqueça de colocar o caractere de sublinhado (`_`) no final do
  prefixo.
- **Criptografia de Conexão** especifica como a conexão com o
  banco de dados deve ser criptografada. Se você não sabe - então é melhor
  ficar com o padrão. No entanto, isso permite que empresas que usam autenticação de um ou dois fatores na conexão do banco de dados o forneçam.

Todas essas escolhas e mais podem ser editadas na página de Configuração Global do Site,
sob as *Opções do Servidor* após a conclusão da instalação. Observe,
você quebrará sua instalação se mudar estas configurações após
a instalação, a menos que tenha uma cópia completa do banco de dados atual
sendo usado pela instalação do Joomla. Usos comuns seriam atualizar
o nome de usuário e a senha do banco de dados ou completar a migração de uma
instalação existente para um novo host com parâmetros diferentes.

Depois de clicar no botão *Instalar o Joomla*, você deverá ver a barra de progresso da instalação do Joomla.

![Instalador Joomla parte 4, barra de progresso da instalação](../../../en/images/getting-started/installing-joomla-installer-4.png)

Uma vez que a instalação seja concluída, você deverá ver a página de sucesso.

## Conclusão

### Sucesso e Conclusão da Instalação

Parabéns! Seu site Joomla está pronto.

![Instalador Joomla parte 5, seu site Joomla está pronto](../../../en/images/getting-started/installing-joomla-installer-5.png)

A captura de tela acima mostra uma instalação para desenvolvedores. Uma instalação em produção remove automaticamente a pasta de Instalação.

Se você quiser começar a usar o Joomla imediatamente sem instalar idiomas extras, pode selecionar *Abrir Administrador* para ir ao *Painel de Controle do Administrador* ou selecionar *Abrir Site* para ir à Página Inicial do Site. Você pode ver uma seção com configurações de PHP recomendadas.

- **Configurações Recomendadas** Essas configurações são recomendadas na sua configuração de PHP, mas não impedirão que o Joomla! seja instalado. Você pode se referir às instruções acima sobre como elas podem ser alteradas, se houver necessidade.

### Idiomas Extras

Como parte do processo de instalação do Joomla, você tem a oportunidade de instalar idiomas adicionais antes de concluir a instalação.

Para fazer isso, selecione o botão Instalar Idiomas Adicionais.

Isso o levará a uma página de instalação extra permitindo você selecionar os idiomas que necessita.

#### Instalar Idiomas Adicionais

Uma lista de pacotes de idiomas é exibida.

![Instalador Joomla parte 6, instalar idiomas adicionais](../../../en/images/getting-started/installing-joomla-installer-6.png)

Selecione até 3 idiomas que deseja instalar. (Mais de 3 de uma vez pode causar problemas de tempo de execução; você pode instalar mais posteriormente.)

Lembre-se dos seguintes pontos:

- Os pacotes de idioma incluídos em distribuições personalizadas não serão listados nesta etapa, pois já estão instalados.
- Uma versão dos pacotes propostos corresponderá à versão principal do Joomla (5.0.x, 5.1.x, etc.). A versão secundária do pacote pode não corresponder, por exemplo, você está instalando a versão 5.0.3 e um pacote de idioma 5.0.2 é exibido.
- Os pacotes de idioma não correspondentes no exemplo acima podem conter strings não traduzidas.
- Os pacotes de idioma não correspondentes serão oferecidos como uma atualização quando os pacotes forem atualizados pelas equipes de Tradução registradas. A atualização disponível será mostrada no Painel de Controle, bem como em **Extensões → Atualizar**. Esse comportamento é semelhante a **Extensões → Instalar Línguas**.

*Próximo* e uma barra de progresso serão exibidos enquanto o(s) pacote(s) de idioma estão sendo instalados.

#### Escolha o Idioma Padrão

Quando a instalação dos idiomas estiver completa, você verá uma tela semelhante a *Parabéns! Seu site Joomla está pronto.* A diferença será uma lista dos idiomas instalados permitindo que você selecione o idioma padrão para o Site e a interface do Administrador.

![Instalador Joomla parte 7, escolher idioma padrão](../../../en/images/getting-started/installing-joomla-installer-7.png)

- Selecione o idioma padrão que você deseja usar.
- Quando você tiver selecionado o idioma padrão, clique no botão *Definir idioma padrão* para confirmar.
- Uma mensagem do sistema será exibida confirmando que o Joomla definiu o idioma padrão do ADMINISTRADOR e do SITE. Essa mensagem pode ser fechada.

#### Finalizar

Agora você pode navegar até o *Painel de Controle do Administrador*. Faça login selecionando *Abrir Administrador* ou vá direto para a Página Inicial do seu site selecionando *Abrir Site*.

