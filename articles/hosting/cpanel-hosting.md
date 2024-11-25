<!-- Filename: J4.x:Hosting_Setup / Display title: Hospedagem cPanel -->

## Introdução

## Hospedagem cPanel

Quando você faz login no seu serviço de hospedagem cPanel, é isso que você deve esperar ver:

![painel de controle de hospedagem cpanel](../../../en/images/hosting/cpanel-hosting.png)

### Configuração do Banco de Dados

O painel de Bancos de Dados é usado para criar um banco de dados e um usuário do banco de dados para o Joomla.

Selecione o item MySQL Databases e insira um nome para o banco de dados no formulário. A primeira parte do formulário é predefinida. O restante fica por sua conta. Deve ser curto e talvez não óbvio - *jblog*, por exemplo.

No mesmo formulário, desça até a seção *Adicionar Novo Usuário*. Insira um nome de usuário. Pode ser qualquer coisa que você quiser. Ele será usado no seu arquivo de configuração do Joomla, portanto, não é algo que você precise lembrar. Use o gerador de senhas para criar uma senha impossível de lembrar e copie-a para um editor de texto - você precisará dela durante a instalação do Joomla.

No mesmo formulário, desça até *Adicionar Usuário ao Banco de Dados*. Selecione o usuário que você criou e o banco de dados que você criou na lista suspensa e clique no botão Adicionar. Um formulário para Gerenciar Privilégios será aberto. Marque a caixa de seleção *Todos os Privilégios* e clique no botão *Fazer Alterações*.

É isso - você agora tem um banco de dados pronto para uma instalação do Joomla.

### Carregar Fonte do Joomla

Em algum momento, você terá baixado o arquivo zip do código fonte do Joomla para seu próprio laptop ou computador desktop. Agora você precisa decidir como estruturar seu site. O diretório raiz do documento para seu site é a pasta *public_html*. Você poderia colocar o Joomla lá. No entanto, isso impede que você use outro aplicativo no mesmo site. Por exemplo, você poderia ter duas instalações completamente separadas do Joomla, uma para produção (visualização pública) e outra para teste (visualização privada). Assim, você poderia criar uma pasta dentro de *public_html*, nomeada *j4*, por exemplo, e carregar o Joomla lá. Você poderia ter outra pasta chamada *j4test* e colocar outra cópia do Joomla lá. A ilustração abaixo mostra tal configuração com dois sites Joomla.

![gerenciador de arquivos de hospedagem cpanel](../../../en/images/hosting/cpanel-file-manager.png)

Depois de decidir sua estrutura, selecione a pasta Joomla escolhida no Gerenciador de Arquivos e clique no botão Carregar. No formulário de upload, selecione o arquivo zip da fonte do Joomla no seu computador local para carregá-lo na pasta selecionada. Após o upload, volte ao Gerenciador de Arquivos, selecione o arquivo *zip* e clique no botão Extrair. Após a extração, você pode selecionar e excluir o arquivo *zip*.

É isso! Você está pronto para instalar o Joomla.

*Traduzido por openai.com*

