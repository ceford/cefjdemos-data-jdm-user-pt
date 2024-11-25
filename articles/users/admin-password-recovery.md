<!-- Filename: How_do_you_recover_or_reset_your_admin_password%3F / Display title: Recuperação de Senha de Administrador -->

## Introdução

Normalmente, um Superusuário pode adicionar, editar e excluir usuários e senhas da lista de Usuários. Em algumas situações, isso pode não ser possível. Por exemplo, a pessoa que conhecia a senha de um Superusuário não está mais disponível. Ou talvez o Superusuário tenha esquecido a senha que foi utilizada.

Nesses casos, existem dois métodos disponíveis para permitir que um Administrador do site faça login como Superusuário.

## Método 1: Edite o Arquivo configuration.php

Se você tiver acesso ao arquivo `configuration.php` da instalação do Joomla no seu servidor, então você pode redefinir a senha de um Super Usuário ou criar um novo Super Usuário, caso consiga fazer login como Gerente ou Administrador.

Você precisa abrir o arquivo `configuration.php` em um editor de texto. Primeiro, altere as permissões do arquivo para 644. As ferramentas de gerenciamento do seu site, como cPanel ou Plesk (existem outras), normalmente permitem que você faça isso online. Se não, você pode precisar usar FTP para baixar o arquivo, alterá-lo localmente e fazer o upload novamente.

Adicione esta linha no final do arquivo, mas antes da chave de fechamento:
```
    public $root_user='myname';
```
onde **myname** é um nome de usuário com acesso ao grupo *Gerente* ou *Administrador* para o qual você conhece a senha. Um nome de usuário que está nos grupos *Autor*, *Editor* ou *Publicador* não funcionará porque esses grupos não têm acesso ao back-end.

Este usuário agora será um Super Usuário temporário.

Faça login no back-end e altere a senha do Super Usuário para a qual você não tem a senha ou crie uma nova conta de Super Usuário. Se você criar um novo usuário, pode querer bloquear ou deletar o usuário antigo dependendo das suas circunstâncias.

Ao terminar, certifique-se de usar o link *Selecione aqui para tentar fazer isso automaticamente* que aparece na caixa de alerta para remover a linha que foi adicionada ao arquivo configuration.php. Se o uso do link não for bem-sucedido, volte e delete a linha adicionada ao seu arquivo configuration.php usando um editor de texto.

Se você não tiver nenhum usuário que saiba suas senhas, pode ser necessário fazer uma alteração no seu banco de dados.

## Método 2: Editar o Banco de Dados

Se os métodos acima não funcionaram, você tem duas outras opções, ambas
requerem trabalhar diretamente com o banco de dados MySQL.

### Alterar uma Senha no Banco de Dados

A opção mais simples é alterar a senha do Super Usuário no banco de dados para
um valor conhecido. Isso requer que você tenha acesso ao banco de dados MySQL
usando o phpMyAdmin ou outro cliente. Estas instruções mostram como alterar uma
senha para a palavra **secret**.

Este método funcionará apenas se o usuário selecionado estiver nos grupos
*Gerente* ou *Administrador*.

**Certifique-se de alterar a senha do Super Usuário assim que recuperar o acesso!**

1.  Abra o phpMyAdmin e selecione o banco de dados do site Joomla! Isso irá
    mostrar as tabelas do banco de dados no lado esquerdo da tela.
2.  Encontre e selecione a tabela *#__users* onde *#_* é o prefixo da tabela do
    seu site.
3.  Na visualização *Navegar*, encontre o usuário cuja senha você deseja alterar e
    selecione o ícone de Editar para esta linha.
    - Se a lista for longa, selecione o botão SQL na parte superior e use esta consulta:<br>
    `SELECT * FROM `xxxxx_users` WHERE `username` = 'username'`<br>
    onde você usa o prefixo do seu banco de dados para substituir `xxxxx` e o nome de usuário
    que você precisa encontrar no lugar de `username`.
4.  No formulário de edição, altere a senha para<br>
    `d2064d358136996bd22421584a7cb33e:trd7TvKHx6dMeoMmBVxYmg0vuXEA4199`<br>
    e selecione o botão *Ir* na parte inferior do formulário. O phpMyAdmin deve
    exibir a mensagem *Linhas afetadas: 1*. Neste ponto, a senha deve ser **secret**.
5.  Faça login com este usuário e senha e altere a senha deste
    usuário para um valor seguro. Verifique todos os usuários para garantir que eles são
    legítimos. Se você foi hackeado, talvez queira alterar todas as
    senhas do site.

### Adicionar um novo Super Usuário

Se alterar a senha não funcionar, ou você não tem certeza de qual usuário é um
membro do grupo de Super Usuários, você pode usar este método para criar um novo
Super Usuário.
1.  Abra o phpMyAdmin e selecione o banco de dados do site Joomla!
2.  Selecione o botão *SQL* na barra de ferramentas para executar uma consulta SQL no
    banco de dados selecionado. Isso exibirá um campo chamado "Executar consulta/consultas
    SQL no banco de dados xxxxx".
3.  Exclua qualquer texto neste campo e copie e cole a seguinte consulta.
    Lembre-se de substituir `xxxxx` pelo seu próprio prefixo de banco de dados.
    ```
    INSERT INTO `xxxxx_users`
       (`name`, `username`, `password`, `params`, `registerDate`, `lastvisitDate`, `lastResetTime`)
    VALUES ('Administrator2', 'admin2',
        'd2064d358136996bd22421584a7cb33e:trd7TvKHx6dMeoMmBVxYmg0vuXEA4199', '', NOW(), NOW(), NOW());
    INSERT INTO `xxxxx_user_usergroup_map` (`user_id`,`group_id`)
    VALUES (LAST_INSERT_ID(),'8');
    ```
    Selecione o botão *Ir* para executar a consulta e adicionar o novo Super Usuário à
    tabela.

Neste ponto, você deve ser capaz de fazer login na parte administrativa do Joomla!
com o nome de usuário *admin2* e a senha *secret*.

Depois de fazer login, vá para a lista de Usuários e altere a senha para um novo valor seguro
e adicione um endereço de e-mail válido à conta.

Se houver a possibilidade de ter sido *hackeado*, certifique-se de verificar se todos os usuários
são legítimos, especialmente qualquer membro do grupo de Super Usuários.

## Senhas Temporárias Alternativas

**Aviso:** Os valores das senhas mostrados nesta página são de conhecimento público e são apenas para recuperação. Para evitar ser hackeado, certifique-se de mudar uma senha temporária para um valor seguro após fazer login.

    senha = "esta é a senha com hash MD5 e sal"
    ------------------------------------------------------
    admin  = 433903e0a9d6a712e00251e44d29bf87:UJ0b9J5fufL3FKfCc0TLsYJBh2PFULvT
    segredo = d2064d358136996bd22421584a7cb33e:trd7TvKHx6dMeoMmBVxYmg0vuXEA4199
    OU812  = 5e3128b27a2c1f8eb53689f511c4ca9e:J584KAEv9d8VKwRGhb8ve7GdKoG7isMm

*Traduzido por openai.com*

