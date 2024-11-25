<!-- Filename: Installing_Joomla!_using_BitNami_Joomla!_stack / Display title: Instalação do Bitnami  -->

## Prefácio

**NOTA:** O pacote BitNami Joomla! não existe mais como um instalador autônomo. Em vez disso, ele é oferecido como: 1) Uma instância baseada em nuvem, 2) Em um container, seja Kubernetes ou Docker ou 3) Uma máquina virtual. A máquina virtual será executada em seu sistema operacional em um hipervisor como VirtualBox ou VMware Player. Ele ainda vem com todas as dependências necessárias, como no instalador autônomo.

A Opção 1 abaixo não se aplica mais. Além disso, na Opção 2, o BitNami Lamp Stack, mais abaixo, é oferecido na nuvem ou máquina virtual. Em qualquer caso, o Bitnami torna fácil e completa a instalação local de Joomla!

Você pode baixar a versão mais recente do pacote Bitnami para Joomla! para Windows, Linux e Mac em <a href="http://bitnami.org/stack/joomla" rel="nofollow noreferrer noopener">http://bitnami.org/stack/joomla</a>.

**Revisão Necessária!**

O BitNami Joomla! Stack é um instalador tudo-em-um que facilita a instalação do Joomla no seu computador. É gratuito, fácil de usar e auto-suficiente. Isso significa que ele inclui e configura automaticamente cada peça de software (dependência) necessária para executar o Joomla para fins de desenvolvimento ou produção, incluindo Apache HTTP Server, MySQL e PHP.

## Opção 1: Pilha Joomla! (Recomendado)

Este método assume que você já possui um ambiente (**W**indows/**L**inux/**M**ac)...**AMP** (Servidor HTTP Apache, MySQL, & PHP) instalado.

### Instalando a Pilha Joomla!

Independentemente do sistema operacional que você esteja utilizando (Windows / Linux / Mac), o processo de instalação é o mesmo.

Baixe a versão mais recente da Pilha Joomla! do <a href="http://bitnami.org/stack/joomla" rel="nofollow noreferrer noopener">site da BitNami</a>.

Encontre o instalador que você acabou de baixar (o nome do arquivo será semelhante a bitnami-joomla-VERSAO-linux-installer.run. Clique duas vezes no ícone para iniciar o instalador.

Se você estiver usando Linux, será necessário dar permissões de execução para o arquivo primeiro, utilizando este comando:

chmod +x /path/to/bitnami-joomla-VERSAO-linux-installer.run

<img src="https://docs.joomla.org/images/a/a0/Joomla_welcome2.png" decoding="async" data-file-width="614" data-file-height="538" width="614" height="538" alt="Configuração do Joomla Bitnami lampstack" />

Clique em "Avançar".

<img src="https://docs.joomla.org/images/5/5f/Joomla_components2.png" decoding="async" data-file-width="614" data-file-height="538" width="614" height="538" alt="Componentes do Joomla Bitnami lampstack" />

Selecione os componentes que você deseja instalar. Se você não tiver certeza, deixe os componentes padrão marcados. Clique em "Avançar" quando terminar.

<img src="https://docs.joomla.org/images/0/0a/Joomla_directory2.png" decoding="async" data-file-width="614" data-file-height="538" width="614" height="538" alt="Diretório de instalação do Joomla Bitnami lampstack" />

Agora será perguntado onde você deseja instalar o programa. Informe o local onde deseja instalar a Pilha Joomla! da BitNami e clique em "Avançar" quando terminar.

<img src="https://docs.joomla.org/images/3/3c/Joomla_userdata2.png" decoding="async" data-file-width="614" data-file-height="538" width="614" height="538" alt="Conta de administrador do Joomla Bitnami lampstack" />

O usuário e a senha que você fornecer aqui serão usados para criar a conta de administrador no Joomla! Clique em "Avançar" quando terminar.

<img src="https://docs.joomla.org/images/8/8b/Joomla_sitename2.png" decoding="async" data-file-width="614" data-file-height="538" width="614" height="538" alt="Nome do site do Joomla Bitnami lampstack" />

Digite o nome que deseja usar para o seu site Joomla e clique em "Avançar".

<img src="https://docs.joomla.org/images/d/dd/JoomlaReadytoinstall2.png" decoding="async" data-file-width="614" data-file-height="538" width="614" height="538" alt="Pronto para instalar o Joomla Bitnami lampstack" />

O instalador permite que você configure uma conta de email para que o Joomla! possa enviar notificações por email. Clique em "Avançar".

<img src="https://docs.joomla.org/images/9/9d/JoomlaCopyingfiles2.png" decoding="async" data-file-width="614" data-file-height="538" width="614" height="538" alt="Copiando arquivos do Joomla Bitnami lampstack" />

Aguarde um momento enquanto o instalador copia os arquivos e configura sua instalação do Joomla!

<img src="https://docs.joomla.org/images/e/ea/Joomlafinalscreen2.png" decoding="async" data-file-width="614" data-file-height="538" width="614" height="538" alt="Tela final do Joomla Bitnami lampstack" />

O Joomla! agora está configurado e pronto para ser usado. Clique em "Concluir" para iniciar a aplicação.

<img src="https://docs.joomla.org/images/8/8d/JoomlaManager.png" decoding="async" data-file-width="784" data-file-height="586" width="784" height="586" alt="Gerenciar servidores do Joomla Bitnami lampstack" />

Usar a ferramenta de gerenciamento é fácil para iniciar/parar os servidores Apache e MySQL.

<img src="https://docs.joomla.org/images/7/73/Joomlaapplicationscreen2.png" decoding="async" data-file-width="982" data-file-height="729" width="982" height="729" alt="Tela de aplicação do Joomla" />

Você pode gerenciar o banco de dados do Joomla! com phpMyAdmin facilmente.

<img src="https://docs.joomla.org/images/f/f3/JoomlaphpMyAdmin.png" decoding="async" data-file-width="982" data-file-height="751" width="982" height="751" alt="Tela do phpMyAdmin" />

## Opção 2: BitNami LAMPStack e Joomla!

### O que é BitNami LAMPStack?

BitNami LAMPStack é um pacote gratuito e fácil de instalar que reúne todas as
peças de software (dependências) necessárias para configurar um ambiente LAMP (Apache, MySQL e PHP para Linux) em funcionamento para fins de desenvolvimento ou produção. Ele é autônomo, não faz modificações no seu sistema e pode ser desinstalado facilmente. Você pode baixar a versão mais recente do BitNami LAMPStack para Linux em
<a href="http://bitnami.org/stack/lampstack"
rel="nofollow noreferrer noopener">http://bitnami.org/stack/lampstack</a>.
Uma <a href="http://bitnami.org/stack/wampstack"
rel="nofollow noreferrer noopener">versão para Windows</a>
e uma <a href="http://bitnami.org/stack/mampstack"
rel="nofollow noreferrer noopener">versão para OS X</a> também estão disponíveis.

Independentemente do sistema operacional que você está usando (Windows / Linux / Mac), o processo de instalação é o mesmo.

### Instalando o BitNami LAMPStack

Encontre o instalador que você acabou de baixar do site da BitNami (o nome do arquivo será semelhante a bitnami-lampstack-VERSÃO-linux-installer.run). Dê um duplo clique no ícone para iniciar o instalador.

<img src="https://docs.joomla.org/images/1/14/Lampstack_welcome.png"
decoding="async" data-file-width="516" data-file-height="391"
width="516" height="391" alt="Bem-vindo ao BitNami lampstack" />

Clique em "Avançar".

<img src="https://docs.joomla.org/images/7/78/Lampstack_directory.png"
decoding="async" data-file-width="516" data-file-height="391"
width="516" height="391" alt="Diretório do BitNami lampstack" />

Agora ele perguntará onde você deseja instalar o programa. Selecione o
local na sua máquina e clique em "Avançar" quando terminar.

<img src="https://docs.joomla.org/images/2/22/Lampstack_passwd.png"
decoding="async" data-file-width="516" data-file-height="391"
width="516" height="391" alt="Senha do BitNami lampstack" />

Digite sua senha root do MySQL. Esta será a senha para o usuário "root" do banco de dados.

<img
src="https://docs.joomla.org/images/7/72/LampstackReadytoinstall.png"
decoding="async" data-file-width="516" data-file-height="391"
width="516" height="391" alt="BitNami lampstack Pronto para instalar" />

O instalador agora está pronto para iniciar o processo de instalação. Clique em "Avançar".

<img src="https://docs.joomla.org/images/1/19/LampstackCopyingfiles.png"
decoding="async" data-file-width="516" data-file-height="391"
width="516" height="391" alt="BitNami lampstack Copiando arquivos" />

Aguarde um momento enquanto o instalador copia os arquivos e configura sua instalação do LAMPStack.

<img src="https://docs.joomla.org/images/b/bc/Lampstackfinalscreen.png"
decoding="async" data-file-width="516" data-file-height="391"
width="516" height="391" alt="Tela final do BitNami lampstack" />

O BitNami LAMPStack agora está configurado e pronto para ser usado. Clique em "Concluir" para iniciar o aplicativo.

### Instalando o Joomla! manualmente

Siga as instruções descritas no artigo Instalando Joomla.

*Traduzido por openai.com*

