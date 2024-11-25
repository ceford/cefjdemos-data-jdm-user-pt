<!-- Filename: How_do_you_password_protect_directories_using_htaccess%3F / Display title: Proteger Diretórios com Senha -->

## Introdução

Você pode querer proteger um diretório ou todo um site do acesso público. Uma razão para isso é negar acesso público a um site de desenvolvimento. Somente aqueles que conhecem o nome de usuário e a senha terão acesso concedido. Outra razão é a paranoia - por exemplo, proteção da pasta do administrador para que os usuários tenham que inserir um nome de usuário e senha apenas para obter acesso ao formulário de login do Administrador do Joomla.

O método descrito aqui é para servidores Apache usando um arquivo *.htaccess*.

### Advertência do Apache.org

A autenticação básica não deve ser considerada segura para qualquer definição particularmente rígida de segurança. Embora a senha seja armazenada no servidor em formato criptografado, ela pode ser transmitida do cliente para o servidor em texto simples através da rede. Qualquer pessoa ouvindo com qualquer tipo de sniffer de pacotes poderá ler o nome de usuário e a senha à medida que são transmitidos.

O nome de usuário e a senha são passados com cada solicitação, e não apenas quando o usuário os insere pela primeira vez. Portanto, o sniffer de pacotes não precisa estar escutando em um momento particularmente estratégico, mas apenas por tempo suficiente para ver qualquer solicitação única atravessar a rede.

Além disso, o conteúdo em si também está trafegando pela rede de forma clara, e assim, se o site contiver informações sensíveis, o mesmo sniffer de pacotes teria acesso a essas informações, mesmo se o nome de usuário e a senha não fossem usados para obter acesso direto ao site.

Não use autenticação básica para qualquer coisa que exija segurança real. É um empecilho para a maioria dos usuários, já que muito poucas pessoas se darão ao trabalho, ou têm o software ou equipamento necessário, para descobrir senhas. No entanto, se alguém desejasse entrar, não levaria muito para que ele o fizesse.

A autenticação básica através de uma conexão SSL, contudo, será segura, já que tudo será criptografado, incluindo o nome de usuário e a senha.

## Usando cPanel

Se você está usando um serviço de hospedagem, deve usar o método dele para proteção de diretório. Por exemplo, o cPanel tem uma opção chamada Privacidade do Diretório. Ao selecioná-la, você pode navegar para qualquer diretório e definir um nome para ele. Você então terá a oportunidade de criar um Nome de Usuário e Senha para o diretório nomeado. Simples?

Se você agora olhar no diretório protegido, encontrará um novo arquivo .htaccess contendo algo como o seguinte para proteger a pasta api do Joomla:

```
#----------------------------------------------------------------cp:ppd
# Seção gerenciada pelo cPanel: Diretórios Protegidos por Senha -cp:ppd
# - Não edite esta seção do arquivo htaccess!                   -cp:ppd
#----------------------------------------------------------------cp:ppd
AuthType Basic
AuthName "API"
AuthUserFile "/home/username/.htpasswds/public_html/[jroot]/api/passwd"
Require valid-user
#----------------------------------------------------------------cp:ppd
# Fim da seção gerenciada pelo cPanel: Diretórios Protegidos por Senha -cp:ppd
#----------------------------------------------------------------cp:ppd
```

É importante estar ciente de que a proteção de diretório do cPanel pode usar o mesmo arquivo .htaccess que está sendo utilizado pelo Joomla para outros fins.

Se você olhar no arquivo de senha citado, verá o Nome de Usuário que você forneceu e a versão criptografada da senha.

A proteção pode ser removida repetindo o processo e desmarcando a caixa de seleção `Proteger este diretório com senha.` Isso remove a seção de autenticação do arquivo .htaccess. Não remove o arquivo .htaccess!

## Regras do .htaccess

Você pode realizar todas as etapas necessárias manualmente. Esta ferramenta pode ajudar:

<a href="https://www.htaccessredirect.net/" rel="nofollow noreferrer noopener"><em>gerador de .htaccess</em></a>

Ela cria os arquivos necessários para você. Você precisa especificar o nome de usuário, senha e caminho.

Preencha as duas seções: **Arquivo de Proteção por Senha** e **Gerador de htpasswd** e depois selecione o botão `Gerar Código`. Você receberá o texto para o arquivo .htaccess e o texto para o arquivo .htpasswd em caixas separadas.
Exemplos:
```
//Arquivo de Proteção por Senha
<Files /admin>
AuthName "Prompt"
AuthType Basic
AuthUserFile /home/user/.htpasswd
Require valid-user
</Files>
```

```
John:$apr1$a3dbt6j7$KJQr137CY9QuN6tYl6M4Z1
```

*Traduzido por openai.com*

