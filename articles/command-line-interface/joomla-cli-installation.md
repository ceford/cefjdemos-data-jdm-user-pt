<!-- Filename: J4.x:Joomla_CLI_Installation / Display title: Instalação do Joomla CLI  -->

## Introdução

O CMS Joomla geralmente é instalado por meio de uma interface de navegador. No entanto, usuários experientes podem preferir instalar o Joomla usando comandos em uma interface de terminal. Isso permite a implantação rápida de várias instâncias do Joomla.

## Requisitos do Sistema

O Joomla requer PHP, um banco de dados e um servidor web. Para obter as informações mais recentes sobre o software compatível, além das versões mínimas e recomendadas, por favor, visite a página de <a href="https://manual.joomla.org/docs/next/get-started/technical-requirements/" rel="noreferrer noopener">Requisitos Técnicos</a>.

A instalação pode ser realizada de duas maneiras diferentes:

1. Instalação manual
2. Instalação automática orientada por script

## Instalação manual

A instalação manual oferece bom controle durante o processo de instalação. Cada etapa é visível no terminal e pode ser abortada com `Ctrl+C` em caso de entrada incorreta.

### Etapas a serem realizadas

1. Carregue o pacote de instalação em formato zip ou tar para o servidor web.
2. Descompacte o arquivo zip ou tar.
3. Renomeie a pasta descompactada e mova-a para um local apropriado na raiz de documentos do servidor web.
4. Acesse a pasta contendo o código Joomla e execute o seguinte comando:<br>
   `php installation/joomla.php install`
5. Você será solicitado a fornecer os parâmetros necessários para a instalação, conforme o exemplo abaixo:
```bash
php installation/joomla.php install

Instalar Joomla
===============

Verificando requisitos do sistema...OK
Coletando configuração...

 Insira o nome do seu site Joomla:
 > J51
 Insira o nome real do seu Super Usuário:
 > John Doe
 Defina o nome de usuário para a conta do Super Usuário:
 > johndoe
 Defina a senha para a conta do Super Usuário:
 >
 Insira o endereço de e-mail do Super Usuário do site:
 > johndoe@example.com
 Tipo de banco de dados. Suportado: mysql, mysqli, pgsql [mysqli]:
 >
 Host do banco de dados [localhost]:
 >
 Nome de usuário do banco de dados:
 > j4
 Senha do banco de dados:
 >
 Nome do banco de dados [joomla_db]:
 > j51
 Prefixo para as tabelas do banco de dados [u5dke_]:
 >
 Criptografia para a conexão do banco de dados. Valores: 0=Nenhum, 1=Uma via, 2=Dupla via [0]:
 >
 Caminho relativo ou absoluto para a pasta pública []:
 >
OK
Validando conexão com o DB...OK
Criando e populando o banco de dados...OK
Escrevendo configuration.php e configuração adicional...OK
Excluindo pasta /installation...OK
 [OK] Joomla foi instalado
```

Uma vez que o script seja concluído com sucesso, o novo site pode ser acessado através do seu navegador web.

### Notas

* Preste muita atenção à sua entrada. Não é possível voltar no script. Se a entrada estiver incorreta, o script deve ser abortado.
* O nome do seu site Joomla aparece na barra de título do Administrador, então mantenha-o curto e distintivo. Pode ser alterado posteriormente.
* O nome real do seu Super Usuário pode ser alterado mais tarde.
* O nome de usuário para a conta do Super Usuário deve evitar um nome semelhante a *admin*. É potencialmente inseguro, pois pode ser facilmente adivinhado por um hacker.
* A senha do Usuário deve ter 12 caracteres.
* O tipo de Banco de Dados padrão é *mysqli*. Os tipos de banco de dados suportados são MySQL (mysql) e PostgreSQL (pgsql) e tipos compatíveis como MariaDB.
* O host do Banco de Dados é quase sempre `localhost`. Um endereço IP ou um nome de host deve ser inserido aqui apenas se o servidor de banco de dados responsável estiver instalado em outro host. No entanto, o usuário do terminal precisa ter permissões de gravação no host selecionado. Você obterá essa informação do seu provedor de internet (ISP).
* O nome de usuário do Banco de Dados geralmente é diferente do nome do Super Usuário.
* A senha do Banco de Dados para o banco de dados do Joomla é quase sempre diferente da senha do Super Usuário.
* O nome do Banco de Dados padrão é `joomla_db`, mas outros nomes são frequentemente usados.
* O Prefixo para as tabelas do banco de dados é definido para uma seleção aleatória de cinco caracteres. O valor é usado para separar as tabelas do Joomla de outras tabelas contidas no banco de dados, caso ele também seja usado por outras aplicações.
* A configuração de Criptografia para a conexão do banco de dados é raramente usada. A menos que aconselhado de outra forma pelo seu ISP, deixe este valor no padrão [0].

## Instalação automática dirigida por script

A instalação do Joomla é controlada por um arquivo *joomla.php* localizado na subpasta *installation* após descompactar o arquivo de pacote do Joomla. Qualquer linguagem de programação que permita chamar e executar arquivos PHP permite que você crie um script que automatize as preparações necessárias e a instalação real usando variáveis personalizadas. Uma lista de parâmetros pode ser obtida com o seguinte comando:
```bash
php installation/joomla.php help install
```
Aqui está um exemplo de script shell chamado jinstall.sh colocado na pasta raiz do Joomla criado para uma instalação simples do Joomla:
```
#!/bin/bash

php installation/joomla.php install \
--site-name=SITE-NAME \
--admin-user=ADMIN-USER \
--admin-username=ADMIN-USERNAME \
--admin-password=ADMIN-PASSWORD \
--admin-email=johndoe@example.com \
--db-type=mysqli \
--db-host=localhost \
--db-user=j51 \
--db-pass=Garbage1n0ut \
--db-name=j51 \
--db-prefix=xyz12_ \
--db-encryption=0 \
--public-folder=j51
```
Com suas permissões definidas para 700, é uma questão simples chamar o script a partir da linha de comando com `./jinstall.sh` e o Joomla é instalado literalmente num piscar de olhos. O script pode ter sido editado para alterar os valores dos espaços reservados, ou eles podem ser alterados mais tarde após o login do Administrador.

Se você usar essa abordagem, lembre-se de excluir seu script jinstall.sh ou movê-lo para fora de sua árvore de web para usá-lo em outro lugar mais tarde. A pasta de instalação é removida no final do processo de instalação. Portanto, executar o script jinstall.sh uma segunda vez não funcionará.
*Traduzido por openai.com*

