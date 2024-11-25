<!-- Filename: https://magazine.joomla.org/all-issues/april-2021/best-practices-to-secure-your-joomla-website / Display title: Melhores Práticas -->

## Artigos de Segurança

Há um número significativo de artigos disponíveis sobre segurança do Joomla, datando de muitos anos atrás. Infelizmente, muitos deles estão desatualizados e talvez sejam enganosos. Por exemplo, existe uma série de artigos de Lista de Verificação de Segurança, nem todos realmente sobre segurança.

Este artigo é baseado em um artigo da revista Joomla! Community Magazine por Ahmad Moussa na Edição de Abril de 2021.

## Melhores Práticas para Proteger seu Site Joomla

O Sistema de Gestão de Conteúdos (CMS) Joomla é amplamente utilizado na internet devido à sua facilidade de uso e popularidade, sendo o segundo maior CMS, com mais de 110 milhões de downloads. No entanto, mesmo popular, o Joomla e todos os outros sites, aplicativos, sites de e-commerce ou outros CMSs contêm riscos de segurança. Você não pode escapar deles, mas, felizmente, ao tomar as precauções corretas desde o início, pode garantir que seu site esteja protegido.

Compilamos este guia abrangente e passo a passo sobre segurança no Joomla para você. Ele pretende fornecer etapas fáceis de seguir para melhorar a segurança do seu site Joomla. Portanto, se proteger seu site Joomla de todos os futuros ataques está na sua agenda, então dê uma olhada. Todas as dicas mencionadas neste artigo são para garantir que você está implementando as melhores práticas de segurança e manutenção para proteger seus ativos mais importantes online.

## 1. Escolha Nomes de Usuário e Senhas Inteligentes

Seja inteligente ao escolher os nomes de usuário e senhas do administrador do Joomla. Não use "admin" como seu nome de usuário e escolha uma senha complexa. Esta é provavelmente uma das melhores maneiras de fortalecer a segurança do seu Joomla e, ironicamente, é uma das mais fáceis.

Usar uma senha segura é necessário para manter uma boa segurança no Joomla. Certifique-se de que sua senha de login seja suficientemente longa (8-14 caracteres) e inclua letras, números e símbolos. Como as senhas diferenciam maiúsculas de minúsculas, usar letras maiúsculas e minúsculas as torna ainda mais fortes. Além disso, torne um hábito mudar as senhas de administrador pelo menos uma vez por mês.

## 2. Pratique o Princípio do Menor Privilégio

Certifique-se de entender os três grupos de permissões distintos:

1. Gerentes: Têm o menor acesso ao backend do Joomla. Podem criar e editar categorias e artigos. Têm acesso ao gerenciador de mídia e podem fazer upload e remover mídia. Não podem instalar ou remover extensões.
2. Administradores: Têm todos os direitos dos Gerentes, junto com algumas permissões adicionais. Têm acesso ao Gerenciamento de Usuários, Gerenciador de Menus e Gerenciador de Extensões. Não podem acessar o menu de Configuração Global do Joomla.
3. Super Usuários: Têm total acesso ao Backend do Joomla. Têm todos os direitos dos Gerentes e Administradores, além do acesso à Configuração Global. Apenas Super Usuários podem adicionar, editar e remover Super Usuários.

É importante distribuir esses papéis cuidadosamente entre seu grupo de usuários. Qualquer pessoa com a função de Super Usuário pode realizar qualquer ação dentro do sistema Joomla. Se você delegar tarefas a um membro da equipe que requer menos permissões, atribua à conta do membro a descrição de acesso mínimo.

## 3. Use a Autenticação Multifator do Joomla

É altamente recomendável ativar a autenticação multifator do Joomla, que adiciona uma camada extra de segurança ao seu site Joomla. Tradicionalmente, quando você quer fazer login no seu site, precisa fornecer seu nome de usuário e senha para se identificar no sistema. O maior problema com essa abordagem é que seu nome de usuário e senha podem ser roubados ou adivinhados. Portanto, os plugins de autenticação multifator do Joomla podem proteger seu site contra hackers, adicionando uma segunda camada de segurança. Existem cinco métodos diferentes para você escolher após inserir seu nome de usuário.

## 4. Restringir Acesso ao Backend de Administração do Joomla

É sensato limitar o acesso ao backend de administração do Joomla usando filtragem de IP, já que é um recurso sensível. Isso também pode ser feito para outras pastas sensíveis do Joomla seguindo os passos mencionados abaixo:

Passo 1: Primeiro, crie um arquivo .htaccess se ele ainda não estiver presente no diretório que você deseja proteger.

Passo 2: Adicione o seguinte código ao arquivo .htaccess:
```
Order Deny, Allow
Deny from all
Allow from xx.xx.xx.xx
```

Passo 3: Insira o endereço IP dedicado do qual você deseja permitir o acesso no lugar de xx.xx.xx.xx.

Mais informações sobre como restringir o acesso a diretórios por endereço IP usando
htaccess podem ser encontradas neste artigo da Documentação do Joomla!. Você também pode usar extensões de segurança que podem restringir o acesso ao backend de administração do Joomla usando a funcionalidade de filtragem de IP e que incluem muitos outros recursos que fortalecem a segurança do seu site Joomla.

## 5. Use Conexões FTP Seguras

Garanta que as conexões usadas para acessar os arquivos do seu site Joomla sejam seguras. Você deve usar criptografia SFTP se o seu provedor de hospedagem oferecer essa opção, ou SSH. Se você estiver usando um cliente FTP, o porto padrão para SFTP geralmente é o 22.

Alguns clientes FTP armazenam senhas em texto simples ou codificadas no seu computador. Mesmo algumas senhas codificadas podem ser convertidas de volta para a original. Recomendamos fortemente não salvar senhas de FTP no cliente para evitar ser hackeado.

## 6. Faça Backups Regulares

Economize tempo se preparando para o pior cenário caso seu site seja atacado. Portanto, é recomendável criar um backup completo e funcional do seu site Joomla. Um backup funcional pode restaurar seu site em minutos após um ataque cibernético.

Os dois principais componentes de um backup são:

- Núcleo do Joomla e outros arquivos importantes
- O Banco de Dados

Além disso, os métodos de backup podem ser flexíveis. Você pode fazer um backup de duas maneiras – Manual e Automática, conforme descrito abaixo:

### Processo Manual

O backup manual do site Joomla requer dois componentes: arquivos e o banco de dados. Para fazer backup dos seus arquivos e pastas do Joomla, utilize um utilitário FTP ou o gerenciador de arquivos caso você use hospedagem de terceiros.

Clientes FTP podem baixar todos os arquivos um por um para sua máquina local. No entanto, esse processo pode ser lento. Depois que os arquivos forem baixados, comprima a pasta em um único arquivo zip e proteja-o com senha.

O banco de dados pode ser feito backup exportando uma cópia para o seu computador. Faça login no banco de dados que você deseja exportar usando o phpMyAdmin. Clique no nome do banco de dados no lado esquerdo da página. Após clicar no seu banco de dados Joomla, você deve chegar a uma tela que possui uma guia rotulada como "Exportar". Selecione a guia Exportar e clique no botão rotulado "Go". Em seguida, salve em um local seguro.

### Processo Automático

Para backup automático, uma extensão do Joomla como o Akeeba Backup pode ajudar. Instale a extensão Akeeba Backup no seu site Joomla após baixá-la do site oficial do desenvolvedor. Após a conclusão da instalação, acesse o painel da extensão e faça o backup do seu site. Quando o backup estiver completo, você será redirecionado para uma página. Aqui, clique em "Gerenciar Backups". Isso abrirá uma página contendo todos os backups. Você pode baixar o backup daqui e salvá-lo localmente.

## 7. Mantenha o Seu Site Joomla Atualizado

Atualizar seu site Joomla pode proporcionar segurança e estabilidade ao site. Além disso, nem todas as atualizações são de versão completa do site; algumas atualizações podem ser pequenas e simplesmente correções de bugs, enquanto outras são atualizações de versão.

O Joomla possui uma equipe de segurança dedicada, conhecida por lançar patches rapidamente. Não aplicar patches ao seu site Joomla pode torná-lo vulnerável a hacks.

Para verificar seu site para atualizações, você pode fazer o seguinte:

Passo 1: Faça login no seu site Joomla como administrador

Passo 2: Em seguida, navegue até Componentes>Atualização do Joomla

Passo 3: Agora, o Joomla verificará se há alguma nova atualização disponível. Se mostrar uma nova atualização, clique na opção “Instalar a Atualização”.

Antes de atualizar para uma versão mais recente do Joomla, certas coisas devem ser verificadas:

- Atualização de Modelos: Verifique se seus modelos Joomla são compatíveis com a nova versão do Joomla. Caso não sejam, peça ao autor do modelo para atualizá-lo ou use uma alternativa.
- Atualização de Extensões: Inspecione e certifique-se de que todas as extensões do Joomla sejam compatíveis com a nova versão do Joomla. Remova todas as que não forem compatíveis. Para atualizar as extensões, navegue até Extensões>Gerenciar e clique em atualizar.
- Limpar Cache: Após atualizar para uma versão mais recente do Joomla, limpe o cache do seu site Joomla. Isso pode ser feito usando a funcionalidade embutida do Joomla.

## 8. Use Extensões e Templates de Terceiros de Confiança:

É recomendado usar um número mínimo de extensões em seu site para alcançar o nível ideal de segurança no Joomla. Utilizar extensões ou templates de terceiros não confiáveis pode criar vulnerabilidades e afetar o desempenho do seu site Joomla. Nem todas as extensões de terceiros são livres de problemas; se puder evitar uma extensão de terceiros, faça-o! Escolha e use extensões e templates profissionais de empresas reputadas, e mantenha-os atualizados para proteger seu site.

## 9. Atualizar a Versão do PHP do seu site Joomla

Proteja seu site contra uma variedade de ataques de hackers e fortaleça a segurança do seu site Joomla atualizando a versão do PHP do seu site para a última versão estável. Certifique-se de selecionar uma versão do PHP que seja compatível com seus templates e extensões Joomla para evitar problemas no seu site. Há várias maneiras de atualizar a versão do seu PHP. As principais estão abordadas em um artigo na edição de setembro de 2020 da Joomla Community Magazine: Como faço para atualizar minha versão do PHP?.

## 10. Reforçar os Cabeçalhos de Segurança HTTP

É altamente recomendado implementar ou atualizar os cabeçalhos de segurança HTTP, pois eles fornecem uma camada de segurança para o seu site Joomla, ajudando a mitigar ataques e vulnerabilidades de segurança. Geralmente, isso requer apenas uma pequena alteração de configuração no seu servidor web. Esses cabeçalhos informam ao navegador como se comportar ao lidar com o conteúdo do seu site. Abaixo estão seis cabeçalhos de segurança HTTP comuns que devem ser revisados:

- Política de Segurança de Conteúdo (Content-Security Policy)
- Proteção contra XSS (X-XSS-Protection)
- Segurança de Transporte Estrita (Strict-Transport-Security)
- Opções de Moldura (X-Frame-Options)
- Pinos de Chave Pública (Public-Key-Pins)
- Tipo de Conteúdo X (X-Content-Type)

## 11. Use uma Extensão de Segurança para Joomla

É necessário limitar as tentativas de login no backend administrativo do Joomla para evitar ataques de força bruta ao seu site Joomla. Isto pode ser implementado através de várias extensões de segurança do Joomla que protegem o backend do administrador do seu site contra tentativas de hacking. Você pode encontrar tais extensões na categoria de segurança da lista de extensões do Joomla.

## 12. Escolha um Provedor de Hospedagem Seguro

Certifique-se de que o provedor de hospedagem que você escolher implemente medidas de segurança para Joomla. Se você optar por uma hospedagem compartilhada, certifique-se de que a sub-rede seja implementada levando em consideração a segurança do Joomla. Comprar um provedor de hospedagem compartilhada e barata pode não ser o ponto de partida ideal, pois seu site será mais lento, sujeito a spam devido a uma 'vizinhança ruim' de sites com baixa reputação, e pode ser comprometido se outros sites forem hackeados. Além disso, ao escolher um plano de hospedagem, verifique vários parâmetros, como personalização, suporte, avaliações, etc.

## 13. Use SSL para Aumentar a Segurança do Joomla

Recomenda-se fortemente instalar um certificado SSL (Secure Socket Layer) no seu site, pois ele criptografará a comunicação entre seu site Joomla e os navegadores dos visitantes. Obtenha um certificado SSL de uma autoridade certificadora verificada e certifique-se de que todo o seu tráfego HTTP seja redirecionado para HTTPS. Para isso, adicione o seguinte código ao seu arquivo .htaccess:

```
# Redirecionar HTTP para HTTPS
RewriteEngine On RewriteCond %{HTTPS} off
RewriteCond %{HTTP:X-Forwarded-Proto} !https
RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
```

## 14. Auditoria de Segurança Joomla Frequente

É extremamente importante descobrir vulnerabilidades antes que um hacker o faça, a fim de manter seu site Joomla seguro. Isso pode ser feito escolhendo uma ferramenta profissional de auditoria de segurança que pode economizar muito tempo na gestão dos seus sites. Auditorias de segurança meticulosas são uma ótima maneira de melhorar a segurança do seu Joomla. Muitos serviços fazem isso automatizando tarefas como a criação de backups do site, escaneando sinais de intrusão e atualizando em massa as extensões de sua confiança. Também pode escanear seu site para verificar o uso das melhores práticas de segurança e realizar uma varredura profunda para identificar possíveis ameaças à segurança. Esses serviços usam uma combinação otimizada de mecanismos manuais e automatizados para descobrir vulnerabilidades no seu site Joomla.  

## 15. Verificar Mensagens Pós-instalação

É altamente recomendado ler todas as mensagens pós-instalação, pois a equipe do Joomla está fornecendo informações importantes que precisam de sua atenção após a atualização ou após a instalação do Joomla pela primeira vez. Essas mensagens contêm principalmente configurações de segurança do Joomla ou alterações de arquivos que devem ser feitas manualmente e que uma atualização não pode modificar.

## 16. Conheça as Extensões Vulneráveis

Sempre verifique o site da Lista de Extensões Vulneráveis e suas páginas nas redes sociais para conhecer os riscos de segurança mais recentes e possíveis correções. É recomendado desinstalar qualquer extensão listada na Lista de Extensões Vulneráveis para a qual não se saiba da existência de uma correção. Certifique-se de atualizar sua extensão vulnerável sempre que uma correção estiver disponível. Se seu site usa uma versão vulnerável de uma extensão que não possui uma atualização de correção, é recomendável substituí-la.

## Conclusão

Como sempre haverá riscos, a segurança do Joomla permanecerá um processo contínuo, exigindo avaliação frequente dos possíveis vetores de ataque. Os proprietários e administradores de sites devem sempre melhorar a segurança de seus sites para reduzir o risco de comprometimento.

*Traduzido por openai.com*

