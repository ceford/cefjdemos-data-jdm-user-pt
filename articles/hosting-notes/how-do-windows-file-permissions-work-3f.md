<!-- Filename: How_do_Windows_file_permissions_work%3F / Display title: Permissões de Arquivos do Windows -->

## Introdução

Para aqueles de vocês que estão desenvolvendo ou entregando seus sites Joomla!
de um ambiente Windows, às vezes é difícil obter informações relevantes sobre permissões. Infelizmente, é um fato que a maioria dos serviços web são oferecidos em Unix e que o Unix é bastante bem documentado dentro desse ambiente. Esperamos que as informações a seguir ajudem a esclarecer qualquer confusão e forneçam um pouco de orientação também.

### Visão Geral do Servidor Web Windows

Primeiramente, vamos discutir as diferenças entre servidores. Em geral, a maioria das pessoas que usam Windows parecem estar utilizando o Apache (Win32) ou o Microsoft IIS. Esses dois servidores web operam de maneira muito diferente e utilizam modelos de entrega ligeiramente diferentes. Apache (Win32) geralmente é executado no computador host como o Usuário sob o qual foi instalado, enquanto o IIS instala-se sob um usuário específico, mas será executado como um novo usuário instalado *IUSR_*.

### Padrões de Permissão

Por padrão, o Unix tende a dar acesso completo apenas ao usuário *proprietário* de arquivos e diretórios, em oposição a essa abordagem, o Windows por padrão atribuirá ao Grupo *Todos*, permissões completas. A primeira coisa que qualquer bom Administrador Windows deve fazer é remover os direitos do grupo *Todos*, para melhorar a segurança. Para testes em PC local, isso provavelmente não é necessário, mas explica por que, se o *Todos* não for removido e você executar algum tipo de script de verificação de permissões ou a verificação de pré-instalação do Joomla!, no geral você terá permissões completas de *Leitura, Escrita e Execução*, porque você está adquirindo os direitos do Grupo *Todos*.

### Microsoft Internet Information Server (IIS)

O IIS vem em dois sabores principais, PWS (Personal WebServer) e IIS (Internet Information Server). Essencialmente, estes são a mesma aplicação. O PWS é apenas uma versão reduzida do IIS projetada para ambientes desktop, enquanto o IIS é projetado para ambientes de servidor. O PWS o limita a um único site principal, então suas instalações de aplicativos estarão geralmente em subdiretórios do site principal. O IIS, por outro lado, fornece a funcionalidade para que Hosts Virtuais sejam executados a partir desses diretórios, oferecendo capacidade multi-site.

Devido às diferentes limitações de funcionalidade, o PWS não possui o *Assistente de Permissões*, pois acredita-se que não seja necessário. Apenas um usuário usará o servidor PWS. No IIS, muitos usuários usarão o Servidor, exigindo diferentes atribuições de permissão.

Uma vez que a conta *Todos* é removida, o Windows IIS fica com a conta *IUSR_* tendo direitos de nível superior aos diretórios do Servidor Web. Uma verificação de permissões agora deve gerar resultados diferentes. Apenas a conta *IUSR_* tem permissões completas e outros usuários devem adquirir apenas *Leitura* ou nenhum direito. Os direitos são determinados por quais outros usuários foram atribuídos a quais direitos nos diretórios do IIS manualmente.

### Atribuindo Permissões

A atribuição de permissões no Windows é razoavelmente direta, mas pode ser um pouco confusa às vezes. Clique com o botão direito no arquivo ou pasta apropriado. Selecionar *Propriedades* ou *Compartilhamento e Segurança* entrará no painel de Gestão de Segurança do Windows. Selecionar (clique uma vez) qualquer nome de usuário listado exibirá os direitos que esse usuário possui na metade inferior do painel. Alguns direitos podem estar *acinzentados*. Estes estão indisponíveis, seja porque o usuário atual (com o qual você está conectado) não tem permissões suficientes para alterá-los, ou porque eles são herdados do diretório acima e foram configurados para usar as permissões desse diretório de nível superior (isso geralmente é o mecanismo padrão).

Como você pode ver, o Windows utiliza o seguinte esquema de Permissões/Direitos:

| # | Permissões | Direitos |
|:-----:|:----------|:---------|
| 1 | Controle Total | Permite: 1, 2, 3, 4, 5, 6, 7 |
| 2 | Modificar | Permite: 2, 3, 4, 5, 6 |
| 3 | Ler e Executar | Permite: 3, 4 |
| 4 | Listar Conteúdo da Pasta | Permite: 4 (mas não pode executar programas) |
| 5 | Ler | Permite: 5 (Implica: 4) |
| 6 | Escrever | Permite: 6 (Implica: 4) |
| 7 | Permissões Especiais | Permite: Combinações |

### Propriedades de permissões de arquivos do Windows

As permissões de arquivos do Windows podem ser vistas como tendo propriedades **semelhantes** às permissões de arquivo (Modos) do UNIX ou Linux, elas apenas são representadas de maneira diferente. Por exemplo, se você é principalmente um usuário de Unix/Linux, provavelmente está acostumado a ter permissões representadas como 644/666 755/777, em vez de serem descritas nos termos acima. Portanto, quando lhe for dito para usar 644, isso equivale a:

* O proprietário deste arquivo pode ler e escrever nele.
* O grupo do proprietário pode ler o arquivo.
* Todos os outros podem ler o arquivo.

**Nota:** As permissões do Windows e do Unix (Listas de Controle de Acesso) não equivalem exatamente, pois o Windows não usa o mecanismo *Grupos* da mesma maneira. No entanto, para esta discussão e em relação ao ambiente de hospedagem web, eles podem ser sumariamente equiparados. Ah, mas, no Windows ***Grupos*** não são usados e ***Todos*** devem ter sido removidos. É aqui que o Windows e o Unix não se equivalem totalmente, mas o que pode ser feito é *corresponder* ou *correlacionar* significados equivalentes.

Este esboço não realmente fornecerá um guia específico de permissões do Windows ou NTFS, mas mais um entendimento de como as permissões numeradas em estilo UNIX/Linux comumente citadas se correlacionam em uma máquina com um sistema de arquivos NTFS. Os arquivos que são colocados na pasta raiz www ou public_html, ou em qualquer diretório que seu site (www.dominio.com.au ou localhost) aponte no seu disco rígido, devem ser de propriedade de sua conta de usuário, mas apenas se esse usuário não for considerado um usuário privilegiado como *Administrador* no Windows ou *root* no UNIX/Linux. Essas contas permitem acesso demais e nunca devem ser usadas para uso diário.

### Melhores Práticas

As práticas de segurança comumente usadas sugerem que todos os **arquivos** devem ter as seguintes permissões.

* **Proprietário:** Leitura e Escrita
* **Grupo:** Apenas Leitura
* **Outros:** Apenas Leitura

Todos os **diretórios/pastas** devem ter as seguintes permissões:

* **Proprietário:** Leitura, Escrita e Execução
* **Grupo:** Leitura e Execução
* **Outros:** Leitura e Execução

Discutivelmente, isso não é necessariamente *a segurança* ideal, mas um equilíbrio deve ser encontrado entre segurança, funcionalidade e manutenção. O Windows, ao contrário do Unix, não mantém uma única ACL para *Execução*, mas simplesmente fornece *Ler e Executar* combinados, o que não implica *Escrever*. O ACL de *Ler e Executar* implica, no entanto, *Listar Conteúdo do Diretório*. Portanto, se você tiver apenas permissões de *Ler e Escrever* em um diretório, mas não *Executar*, você não poderá ver o conteúdo do diretório e também poderá ter problemas ao tentar executar o arquivo através de um navegador web. Um pequeno entendimento das permissões UNIX/Linux é necessário para correlacioná-las totalmente às permissões do Windows. A tabela a seguir pode ajudar:

| Modo Unix | ACL do Windows | Comentários |
|:-----:|:-----------|:----------|
| 7 | Modificar | Leitura, Escrita e Execução, você deve ser o proprietário deste arquivo |
| 6 | Ler e Escrever |  |
| 5 | Ler e Executar | usado para a maioria dos aplicativos |
| 4 | Apenas Ler | segurança por obscuridade não é uma boa prática |
| 3 | Escrever e Executar | não disponível no Windows, a menos que "Permissões Especiais" sejam usadas, não comumente usado |
| 2 | Apenas Escrita | não disponível no Windows, a menos que "Permissões Especiais" sejam usadas, não comumente usado |
| 1 | Apenas Execução | não disponível no Windows, a menos que "Permissões Especiais" sejam usadas, não comumente usado |

Em comparação com os Modos Unix, quando você vê algo como 644, você dividiria isso em três elementos:

**6** : **4** : **4**

O primeiro número representa as permissões do **Proprietário**, o segundo representa as permissões do **Grupo** e o terceiro, as permissões dos **Outros**. O equivalente do Windows seria:

* **Proprietário** (6): **Ler e Escrever**
* **Grupo** (4): **Apenas Ler**
* **Outros** (4): **Apenas Ler**

Esperamos que este exemplo forneça algumas insights sobre como correlacionar Modos/Permissões Unix em Permissões/ACLs do Windows. Este documento não inclui assuntos mais complexos como permissões *Eficazes*, *Herdadas* ou *Especiais*. Apesar da facilidade de uso do Windows, os mecanismos de Permissões e ACL da Microsoft são, na verdade, razoavelmente complexos e muito extensos, mas isso pode proporcionar um rápido recurso para tentar aliviar um pouco da confusão em torno das traduções de Permissões Unix e Windows.

*Traduzido por openai.com*

