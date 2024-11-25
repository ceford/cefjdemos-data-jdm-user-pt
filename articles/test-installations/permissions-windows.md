<!-- Filename: How_do_Windows_file_permissions_work? / Display title: Permissões de Arquivo: Windows -->

## Introdução

Para aqueles que estão desenvolvendo ou entregando seus sites Joomla! a partir de um ambiente Windows, pode ser difícil obter informações relevantes sobre permissões. Infelizmente, é um fato que a maioria dos servidores web funciona sob Unix e que Unix é bastante bem documentado nesse ambiente. Esperamos que as informações a seguir ajudem a esclarecer qualquer confusão e forneçam um pouco de orientação também.

## Visão Geral dos Servidores Web Windows

Primeiro, vamos discutir as diferenças entre servidores. Em geral, a maioria dos usuários de Windows parece usar Apache (Win32) ou Microsoft IIS. Esses dois servidores web operam de maneira muito diferente e utilizam modelos de entrega ligeiramente distintos. O Apache (Win32) geralmente é executado no computador host como o Usuário sob o qual foi instalado, enquanto o IIS é instalado sob um usuário específico, mas será executado sob um novo usuário instalado *IUSR_*.

## Padrões de Permissão

Por padrão, o Unix tende a conceder acesso total apenas ao usuário *proprietário* de arquivos e diretórios. Em contraste, o Windows, por padrão, também atribui permissões totais ao grupo *Todos*. A primeira coisa que qualquer bom administrador de Windows fará é remover os direitos do grupo *Todos* para melhorar a segurança. Para testes em PCs locais, isso provavelmente não é necessário, mas explica por que, se o grupo *Todos* não for removido e você executar algum tipo de script de verificação de permissões ou a verificação pré-instalação do Joomla!, você terá permissões completas de *Leitura, Escrita e Execução*. Você está adquirindo os direitos do grupo *Todos*.

## Microsoft Internet Information Server (IIS)

O IIS vem em duas versões principais, PWS (Personal WebServer) e IIS (Internet Information Server). Essencialmente, são o mesmo aplicativo. O PWS é apenas uma versão reduzida do IIS projetada para ambientes de desktop, enquanto o IIS é projetado para ambientes de servidor. O PWS limita você a um único site principal, portanto, suas instalações de aplicativos geralmente estarão em subdiretórios do site principal. O IIS, por outro lado, oferece a funcionalidade para que Hosts Virtuais sejam executados a partir desses diretórios, proporcionando capacidade de múltiplos sites.

Devido às diferentes limitações funcionais, o PWS não possui o *Assistente de Permissões*, pois se considera que não é necessário. Apenas um usuário usará o servidor PWS. No IIS, muitos usuários utilizarão o servidor, portanto é necessária a atribuição de permissões diferenciadas.

Uma vez que a conta *Todos* é removida, o Windows IIS fica apenas com a conta *IUSR_** tendo direitos de nível superior aos diretórios do Servidor Web. Uma verificação de permissões agora deverá produzir resultados diferentes. Apenas a conta *IUSR_** tem permissões completas e outros usuários devem adquirir apenas *Somente Leitura* ou nenhum direito. Os direitos são determinados por quais outros usuários foram atribuídos manualmente aos direitos dos diretórios do IIS.

### Atribuindo Permissões

Atribuir permissões no Windows é razoavelmente direto, mas às vezes pode ser um pouco confuso. Clique com o botão direito no arquivo ou pasta apropriado. A seleção de *Propriedades* ou *Compartilhamento e Segurança* abrirá o painel de Gerenciamento de Segurança do Windows. Selecionar (clicar uma vez) qualquer nome de usuário listado exibirá os direitos que esse usuário possui na metade inferior do painel. Alguns direitos podem estar *acinzentados*. Estes estão indisponíveis, ou porque o usuário atual (com quem você está logado) não tem permissões altas o suficiente para alterá-los, ou são herdados de um diretório acima e foram definidos para usar as permissões desse diretório de nível superior. (Este é geralmente o mecanismo padrão.)

Como você pode ver, o Windows utiliza o seguinte esquema de Permissões/Direitos:

| # | Controle | Permite #     |
| :---:        |:----   | :--- |
| 1.| Controle Total | Permite: 1, 2, 3, 4, 5, 6, 7 |
| 2.| Modificar | Permite: 2, 3, 4, 5, 6 |- |
| 3.| Ler e Executar | Permite: 3, 4  |- | 
| 4.| Listar Conteúdos da Pasta | Permite: 4 (mas não pode executar programas) |- |
| 5.| Ler | Permite: 5 (Implica: 4) |- |
| 6.| Gravar | Permite: 6 (Implica: 4) |- |
| 7.| Permissões Especiais | Permite: Combinações |

### Propriedades de permissões de arquivo do Windows

As permissões de arquivo do Windows podem ser vistas como tendo propriedades semelhantes às permissões de arquivo (Modos) do UNIX ou Linux. Elas são apenas representadas de forma diferente. Por exemplo, se você é principalmente um usuário de Unix/Linux, provavelmente está acostumado a ter permissões representadas como 644/666 755/777, em vez de serem descritas nos termos acima. Então, quando você usa 644, isso significa:

- O proprietário deste arquivo pode ler e gravar nele.
- O grupo do proprietário pode ler o arquivo.
- Todos os outros podem ler o arquivo.

**Nota:** As permissões (Listas de Controle de Acesso) do Windows e do Unix não são exatamente equivalentes; o Windows não usa o mecanismo de *Grupos* da mesma maneira. Para esta discussão e em relação ao ambiente de hospedagem na web, elas podem ser equiparadas. Ah, mas no Windows, *Grupos* não são usados e *Todos* deveriam ter sido removidos. É aqui que o Windows e o Unix não se equiparam exatamente, mas o que pode ser feito é *corresponder* ou *correlacionar* significados equivalentes.

Este esboço não vai realmente fornecer a você um guia específico de permissões do Windows ou do NTFS, mas mais um entendimento de como as permissões numeradas no estilo UNIX/Linux geralmente citadas se correlacionam em uma máquina com um sistema de arquivos NTFS. Os arquivos que são colocados na pasta raiz `www` ou `public_html`, ou qualquer diretório que seu site (`www.dominio.com` ou `localhost`) aponta no seu disco rígido devem ser de propriedade de sua conta de usuário, mas somente se esse usuário não for o que é considerado como um usuário privilegiado, como *Administrador* no Windows ou *root* no UNIX/Linux. Essas contas permitem acesso excessivo e nunca devem ser usadas para uso diário.

### Melhores Práticas

Práticas de segurança comumente usadas sugerem que todos os **arquivos** devem ter as seguintes permissões.

- **Proprietário** Ler e Gravar
- **Grupo** Somente Leitura
- **Outros** Somente Leitura

Todos os **diretórios/pastas** devem ter as seguintes permissões.

- **Proprietário** Ler, Gravar e Executar
- **Grupo** Ler e Executar
- **Outros** Ler e Executar

Argumentavelmente, isso não é necessariamente a segurança *ótima*, mas um equilíbrio deve ser alcançado entre segurança, funcionalidade e manutenção.

O Windows, ao contrário do Unix, não mantém uma única ACL para *Executar*, mas simplesmente fornece *Ler e Executar* combinados, o que não implica *Gravar*. A ACL *Ler e Executar* implica, contudo, *Listar Conteúdo do Diretório*. Portanto, se você tem apenas permissões de *Ler e Gravar* em um diretório, mas não *Executar*, não poderá ver o conteúdo do diretório e também poderá ter problemas ao tentar executar o arquivo por meio de um navegador da web. Um pequeno entendimento das permissões do UNIX/Linux é necessário para equacioná-las/correlacioná-las completamente com as permissões do Windows. A tabela a seguir deve ajudar:

| Modo Unix | ACL do Windows | Comentários|
|:-----------:| :----   | :--- |
| 7 | Modificar| Ler, Gravar e Executar, você deve ser o proprietário deste arquivo | 
| 6 | Ler e Gravar | | 
| 5 | Ler e Executar| usado para a maioria das aplicações | 
| 4 | Somente Ler | segurança por obscuridade não é uma boa prática | 
| 3 | Gravar e Executar | não disponível no Windows, a menos que Permissões *Especiais* sejam usadas, não comumente usado | 
| 2 | Apenas Gravar | não disponível no Windows, a menos que Permissões *Especiais* sejam usadas, não comumente usado | 
| 1 | Apenas Executar | (não disponível no Windows, a menos que Permissões *Especiais* sejam usadas, não comumente usado) |

Em comparação com os modos Unix, quando você vê algo como 644, divida isso em três elementos:

O primeiro número representa as permissões do Proprietário, o segundo representa as permissões do Grupo e o terceiro, as permissões de Outro. O equivalente no Windows seria:

- **Proprietário** (6) Ler e Gravar
- **Grupo** (4) Somente Ler
- **Outros** (4) Somente Ler

Esperançosamente, este exemplo fornece alguma compreensão sobre como correlacionar Modos/Permissões do Unix com Permissões/ACLs do Windows. Este documento não inclui assuntos mais complexos como permissões *Efetivas*, *Herdadas* ou *Especiais*. Apesar da facilidade de uso do Windows, os mecanismos de Permissões e ACL da Microsoft são de fato razoavelmente complexos e bastante extensos, mas isso pode oferecer uma rápida referência para tentar aliviar um pouco a confusão envolvendo traduções de Permissões entre Unix e Windows.

*Traduzido por openai.com*

