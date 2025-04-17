<!-- Filename: J4.x:Hosting_Setup / Display title: Configuração de Hospedagem -->

## Introdução

Esta página fornece algumas orientações para quem é completamente novo em tecnologia de hospedagem. Você pode configurar um site em seu próprio laptop ou computador de mesa. Isso é conhecido como hospedagem local e é uma boa maneira de experimentar novos recursos, sendo completamente gratuito. Para tornar o conteúdo do seu site disponível para o resto do mundo, você precisará de uma conta em um serviço de hospedagem e, para isso, terá que pagar.


## Software de Suporte

Joomla! é uma aplicação que depende de três itens de software de suporte: a linguagem de script PHP, um banco de dados (um dos MySQL, MariaDB ou PostgreSQL) e um servidor web (um dos Apache, Nginx, Microsoft IIS, ou ...). Os números de versão mínima são indicados nas tabelas a seguir:

### Requisitos para Joomla! 5.x

| Software           | Recomendado     | Mínimo      |
|--------------------|-----------------|-------------|
| PHP                | 8.3             | 8.1.0       |
| **Bancos de Dados**|                 |             |
| MySQL              | 8.1             | 8.0.13      |
| MariaDB            | 11.1.0          | 10.4.0      |
| PostgreSQL         | 16.0            | 12.0        |
| **Servidores Web** |                 |             |
| Apache             | 2.4             | 2.4         |
| Nginx              | 1.25            | 1.21        |
| Microsoft IIS      | 10              | 10          |

### Requisitos para Joomla! 4.x

| Software           | Recomendado     | Mínimo      |
|--------------------|-----------------|-------------|
| PHP                | 8.2             | 7.2.5       |
| **Bancos de Dados**|                 |             |
| MySQL              | 8.0             | 5.6         |
| PostgreSQL         | 11.0            | 11.0        |
| **Servidores Web** |                 |             |
| Apache             | 2.4             | 2.4         |
| Nginx              | 1.18            | 1.10        |
| Microsoft IIS      | 10              | 8           |

## Serviços de Hospedagem

Os serviços de hospedagem comercial oferecem tudo o que você precisa para suportar um site. Alguns também fornecem instalação com um clique de aplicativos populares, como Sistemas de Gerenciamento de Conteúdo, Fóruns, Wikis e assim por diante. Mas, por favor, note: os especialistas do Fórum Joomla não recomendam o uso da instalação com um clique para o Joomla.

Cada serviço de hospedagem oferece planos diferentes em diferentes níveis de preço. Quanto mais você paga, mais espaço em disco e largura de banda você obtém, juntamente com mais endereços de e-mail, bancos de dados e assim por diante. Alguns também oferecem um nome de domínio gratuito. Na maioria das vezes, você precisa pagar por um nome de domínio e uma pequena taxa de registro anual.

## Hospedagem Gratuita

Não existe hospedagem realmente gratuita! No entanto, um serviço de hospedagem parceiro do Joomla oferece um site Joomla gratuito no domínio joomla.com. Isso lhe dá a oportunidade de experimentar o seu próprio site Joomla totalmente funcional sem nenhum custo. É semelhante a um plano de hospedagem compartilhada, mas com restrições e frequentes apelos para que você faça um upgrade para um plano pago. Além disso, o plano gratuito precisa ser renovado a cada 30 dias ou será encerrado. O artigo a seguir mostra os passos necessários para configurar um site Joomla gratuito.

* [Hospedagem Gratuita Joomla](jdocmanual?article=user/hosting/free-hosting)

Se você descobrir que gosta do Joomla, pode atualizar para um plano pago ou procurar em outro lugar um serviço de hospedagem que atenda às suas necessidades e orçamento.

## Hospedagem Compartilhada

Você pode obter um plano de hospedagem mínimo por cerca de £/$/e50 por ano. Esse nível de plano é frequentemente referido como hospedagem compartilhada e é adequado para qualquer coisa que não envolva dados confidenciais. As empresas devem buscar aconselhamento especializado sobre planos de hospedagem adequados. Escolher um serviço de hospedagem não está isento de problemas. O mais barato pode ter configurações de *php.ini* excessivamente restritivas que não aparecem em sua publicidade. Alguns podem ter uma reputação ruim para suporte.

Se você optar por um plano de hospedagem compartilhada, verifique o seguinte:

- Suporte para aplicativos PHP como Joomla, WordPress e Mediawiki.
- Espaço em disco: 500Mb é o mínimo absoluto. 1Gb ou mais seria melhor se você planeja usar muitas imagens.
- Número de Bancos de Dados: o Joomla utiliza um, mas logo você perceberá que precisa de 5 ou 10 ou mais. Alguns planos oferecem um número ilimitado dentro da alocação total de espaço em disco.
- Tamanho do banco de dados: com o Smart Search, o banco de dados pode crescer muito rapidamente. Se a hospedagem compartilhada tem uma restrição de tamanho do banco de dados, será importante descobrir qual é. Isso pode levar a um site não funcionando.
- Número de endereços de e-mail: muitos!
- Número de conexões HTTP e DB com o servidor, que alguns hosts compartilhados limitam
- Backups: como são feitos e há um documento de Termos de Serviço (TOS) que estabelece quem é responsável pelos backups.

Também verifique o painel de controle e a plataforma oferecidos. A julgar pelos posts nos Fóruns, a maioria usa cPanel no Linux. O serviço de hospedagem deve fornecer todo o software de suporte básico para o website:

- Servidor web Apache 2.4+ - *índices de diretório* devem estar desativados. Também suportados:
  - Nginx 1.18+ (menos usuários, então menos suporte no Fórum)
  - Microsoft IIS\[6\] (menos usuários, então menos suporte no Fórum)
- Banco de dados MySQLi 8.1+ ou clone MariaDB com suporte InnoDB. Também suportados:
  - PostgreSQL 11.0+ (menos usuários, então menos suporte no Fórum).
- PHP 8+ é recomendado.
- Ferramenta de gerenciamento de banco de dados phpMyAdmin.

Antes de comprar, verifique os seguintes requisitos mínimos de PHP para Joomla:

- *memory_limit* - Mínimo: 256M
- *upload_max_filesize* - Mínimo: 64M
- *post_max_size* - Mínimo: 64M
- *max_execution_time* - Recomendado: 30
- *allow_url_fopen* - true

Muitos desses parâmetros podem ser configurados pelo usuário no cPanel. Pergunte se isso é possível.

Se você comprou um nome de domínio, seu serviço de hospedagem irá configurá-lo para você. Eles também devem fornecer um endereço IP para usar até que o registro do seu domínio se propague para os Servidores de Nome de Domínio (DNS), geralmente em algumas horas.

O artigo a seguir mostra o que esperar se você adquirir um plano de hospedagem que inclui uma interface de usuário cPanel.

* [Hospedagem cPanel](jdocmanual?article=user/hosting/cpanel-hosting)

## Hospedagem VPS

Um plano de hospedagem em Servidor Virtual Privado (VPS) proporciona acesso completo a um servidor que compartilha hardware. Ele se comporta como um computador dedicado. Você pode parar e iniciar o servidor, reiniciá-lo e instalar seu próprio software exatamente como faria em um computador de mesa. Você pode criar contas para usuários individuais, assim como na hospedagem compartilhada. Normalmente, você pode permitir alguns recursos que não são permitidos em contas de hospedagem compartilhada.

Os planos de hospedagem Dedicada e em Nuvem são semelhantes em princípio, mas oferecem recursos dedicados ou recursos adaptados às suas necessidades.

Esses planos avançados não são abordados aqui.


## Hospedagem Local

A maioria das pessoas que desenvolvem sites mantém cópias locais em um laptop ou computador desktop para testar atualizações, novas extensões ou experimentar novos designs. Configurar um site de desenvolvimento local requer algum conhecimento técnico, mas é relativamente fácil seguir instruções simples.

Os artigos a seguir descrevem como configurar a hospedagem local em diferentes tipos de computadores desktop ou laptop:

* [Hospedagem Local no Windows](jdocmanual?article=user/hosting/local-hosting-on-windows) apenas para Windows
* [Hospedagem Local com XAMPP](jdocmanual?article=user/hosting/local-hosting-with-xampp) para Linux, Mac e Windows.
* [Hospedagem Local no Linux](jdocmanual?article=user/hosting/local-hosting-on-linux)

