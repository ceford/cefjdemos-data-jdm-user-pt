<!-- Filename: Unable_to_connect_to_the_database / Display title: Conexão com o Banco de Dados  -->

## Erro de Incapacidade de Conectar

Se você recebeu um erro de "**Incapacidade de conectar ao banco de dados**" durante a **instalação**, verifique se você inseriu corretamente os detalhes do banco de dados MySQL/MariaDB. O script de **instalação** não permitirá que você continue a menos que os detalhes estejam corretos.

Observe que não é esperado que você crie um usuário de banco de dados e senha durante a instalação. Eles devem ser criados antes.

Se a falha ocorrer após mover seu site para outro host, verifique os seguintes itens do seu arquivo *configuration.php*. As configurações normais do banco de dados são as seguintes:

    public $dbtype = 'mysqli';
    public $host = 'localhost';
    public $user = 'yourdbuser';
    public $password = 'yourdbpassword';
    public $db = 'yourdbname';
    public $dbprefix = 't6q6i_';

Se a falha ocorrer em um site que estava funcionando, há vários motivos possíveis, às vezes temporários e às vezes acidentais.

## As Falhas Mais Comuns

1. Às vezes, você verá esta mensagem se o MySQL/MariaDB parou de
   funcionar no seu servidor. O administrador do seu servidor pode
   temporariamente desligar o MySQL/MariaDB para realizar
   manutenção. Nesses casos, é provável que seu site volte
   em breve.
2. O usuário do seu banco de dados foi deletado. Se este for o caso,
   você precisará recriar o usuário do banco de dados com o mesmo
   nome de usuário e senha que existiam quando você instalou o Joomla
   pela primeira vez. Use o painel de controle do seu domínio para
   administrar isso ou entre em contato com o administrador do seu
   servidor.
3. Seu nome de usuário ou senha do banco de dados foram alterados.

*Traduzido por openai.com*

