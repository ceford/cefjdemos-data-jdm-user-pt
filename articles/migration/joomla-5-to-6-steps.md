<!--
{
    "source": "https://docs.joomla.org/https:",
    "title": "Joomla 5 para 6 passo a passo",
    "description": " ",
    "author": ""
}
-->

<div class="alert alert-warning">
<p class="h3">Aviso</p>

Este guia pressupõe que você está começando com o Joomla 5.4.x. Se estiver em uma versão anterior, certifique-se de migrar ou atualizar para o Joomla 5.4.x antes de atualizar para o Joomla 6.x.
</div>

## Introdução

Boas notícias para a atualização do Joomla 5.4.x para o 6.x: é uma atualização, não uma migração. Por quê? Por dois motivos principais:

- As extensões do Joomla 5 (J5) que removeram todas as obsolescências do código, usam código atualizado do Joomla e não exigem que o plugin Comportamento - Compatibilidade retroativa esteja ativado funcionarão no Joomla 6 (J6)
- A maioria das outras funcionará com o novo plugin Comportamento - Compatibilidade retroativa 6 ativado

Esta documentação reflete o processo mais simples, combinando o planejamento e o passo a passo em um único documento. Ainda assim, você precisará de alguns conhecimentos. Consulte a [[Migration Step by Step Self Assessment|Autoavaliação]] para determinar se deve ou não realizar a atualização por conta própria.

<div class="alert alert-info">
<p class="h3">Documentação para desenvolvedores sobre a atualização da versão 5.4 para a 6.0, destinada a desenvolvedores de extensões de terceiros.</p>

- [Removido e incompatibilidade retroativa](https://manual.joomla.org/60/removed-backward-incompatibility)
- [Novas obsolescências](https://manual.joomla.org/60/new-deprecations)
- [Sobre a documentação de migrações](https://manual.joomla.org/migrations)
- [Novos recursos](https://manual.joomla.org/60/new-features/)
</div>

## Planejamento da versão 5.4.x para a 6.x

### Especificações de hospedagem/técnicas

1. Determine se o seu ambiente de hospedagem atende aos requisitos. Você não 
poderá atualizar para o Joomla 6 se o ambiente do seu servidor não atender aos 
[requisitos técnicos](https://manual.joomla.org/docs/get-started/technical-requirements/) mínimos. 
A opção de atualização não aparecerá no componente de atualização do Joomla.
    - PHP 8.3
    - MySQL 8.0.13
    - MariaDB 10.6.x
    - PostgreSQL 14.0

Você pode verificar as informações do sistema no site Joomla 5 clicando em Sistema -> Informações do sistema. Entre em contato com o seu provedor de hospedagem se o seu servidor não atender aos requisitos.

![Painel do sistema com o link Informações do sistema destacado](../../../en/images/migration/joomla-5-to-6-steps/01-steps-5-to-6-system-dashboard.png)

A seguir, temos um exemplo de um ambiente que atende aos requisitos técnicos. Ele mostra MySQL 8.0.43, PHP 8.3, Joomla 5.4.x e o plugin de compatibilidade retroativa desativado.

![Informações do sistema mostrando a versão do Joomla, a versão do PHP, o tipo do banco de dados, a versão do banco de dados e o plugin de compatibilidade retroativa desativado](../../../en/images/migration/joomla-5-to-6-steps/02-steps-5-to-6-system-information.png)

2. Verifique se todas as suas extensões são compatíveis com o Joomla 6. Há vários cenários envolvendo extensões de terceiros para esta atualização.

    1. A extensão pode ser compatível com o J5 e o J6 SEM o uso do plugin de compatibilidade retroativa.
    2. A extensão pode ser compatível com o J5 e o J6 COM o uso do plugin de compatibilidade retroativa.
    3. A extensão pode parecer funcionar no J6, mas apresentar problemas quando você tentar usá-la.
    4. A extensão pode comprometer todo o site.

Não se preocupe! Não é tão ruim quanto parece! Primeiro, vamos falar sobre os plugins de compatibilidade retroativa.

<div class="alert alert-warning">
<p class="h3">Aviso</p>

Para atualizar do Joomla 5.4.x para o 6.x, o plugin de compatibilidade retroativa do Joomla 5 DEVE estar DESATIVADO.
</div>

### Os plug-ins de compatibilidade com versões anteriores

O plug-in [Comportamento - Compatibilidade com versões anteriores 6](https://manual.joomla.org/60/compat-plugin/) incluído no Joomla 5.4.x tem como objetivo aprimorar a compatibilidade com versões anteriores entre o Joomla 5 e o Joomla 6. O plug-in auxilia extensões de terceiros a usarem classes que não estão mais incluídas no Joomla 6. Ele é implementado como um tipo de plug-in de “Comportamento” para garantir que seja carregado antes de qualquer outro plug-in.

![Página de plug-ins mostrando os plug-ins de compatibilidade com versões anteriores](../../../en/images/migration/joomla-5-to-6-steps/03-steps-5-to-6-bc-plugins.png)

A imagem acima mostra dois plug-ins de compatibilidade com versões anteriores:

1. Comportamento - Compatibilidade com versões anteriores e
2. Comportamento - Compatibilidade com versões anteriores 6

O plug-in Comportamento - Compatibilidade com versões anteriores (sem um número no nome do plug-in) é fornecido com o Joomla 4.4.x para criar uma camada de compatibilidade com versões anteriores para extensões do Joomla 5. **Este plug-in deve ser desativado antes de atualizar para o J6**.

O plug-in Comportamento - Compatibilidade com versões anteriores 6 é fornecido com o Joomla 5.4.x para criar uma camada de compatibilidade com versões anteriores para extensões do Joomla 6.

Ambos não podem estar ativados durante a atualização para o J6.

Antes de atualizar do Joomla 5 para o Joomla 6, o plug-in Comportamento - Compatibilidade com versões anteriores (sem um número no nome do plug-in) deve ser desativado. Você precisa garantir que todas as suas extensões de terceiros possam ser executadas no seu site sem que o plug-in Comportamento - Compatibilidade com versões anteriores esteja ativado antes de poder atualizar para o J6.

Depois de determinar que todas as suas extensões de terceiros são compatíveis e funcionam totalmente no J5 sem o plug-in Comportamento - Compatibilidade com versões anteriores ativado, você pode desativá-lo. Dito isso, recomendamos cautela. Antes de desativar o plug-in de compatibilidade com versões anteriores, sugere-se fazer uma das duas coisas a seguir:

1. Faça isso em um site de desenvolvimento/teste. Dessa forma, se você acidentalmente não identificar uma extensão que torne seu back-end inacessível, isso não derrubará seu site de produção.
2. Certifique-se de ter acesso ao banco de dados. Dessa forma, você poderá ativar o plug-in novamente rapidamente pelo banco de dados, se necessário. Mais informações abaixo.

Ao realizar uma atualização para o J5.4.x, o plug-in Comportamento - Compatibilidade com versões anteriores 6 será ativado automaticamente. Em novas instalações do J6, o plug-in de compatibilidade com versões anteriores estará desativado por padrão.

O plug-in Comportamento - Compatibilidade com versões anteriores 6, que oferece suporte a extensões que funcionam no J5, permanecerá disponível durante todo o J6. No J7, as extensões do J5 não terão compatibilidade com versões anteriores fornecida pelo plug-in. Isso dá aos desenvolvedores de extensões mais dois anos para tornar suas extensões compatíveis com o J6 sem o plug-in de compatibilidade com versões anteriores. A intenção é que, a cada lançamento de ciclo de vida, um plug-in de compatibilidade com versões anteriores ofereça suporte ao ciclo de vida anterior até o ciclo de vida seguinte.

É possível desativar o plug-in Comportamento - Compatibilidade com versões anteriores 6 no J6? Ótima pergunta. Depois de determinar que todas as suas extensões de terceiros são compatíveis e funcionam totalmente sem o plug-in de compatibilidade com versões anteriores ativado, você pode desativar o plug-in Comportamento - Compatibilidade com versões anteriores 6. Dito isso, recomendamos cautela. Antes de desativar o plug-in Comportamento - Compatibilidade com versões anteriores 6, sugere-se fazer uma das duas coisas a seguir:

1. Faça isso em um site de desenvolvimento/teste. Dessa forma, se você acidentalmente não identificar uma extensão que torne seu back-end inacessível, isso não derrubará seu site de produção.
2. Certifique-se de ter acesso ao banco de dados. Dessa forma, você poderá ativar o plug-in novamente rapidamente, se necessário. Mais informações abaixo.

### Verificação pré-atualização ou Gerenciar extensões

Teoricamente, a verificação pré-atualização informaria se suas extensões de terceiros são compatíveis com o J6. No entanto, a verificação pré-atualização só é útil se todos os desenvolvedores de extensões tiverem feito com que suas extensões reflitam a compatibilidade com elas. Em um mundo perfeito, a seção **Extensões** da verificação pré-atualização informaria se uma extensão:

* Pode ser atualizada sem o plugin de compatibilidade com versões anteriores ativado
* Pode ser atualizada com o plugin de compatibilidade com versões anteriores ativado
* Requer uma atualização da extensão antes de atualizar do J5 para o J6
* É completamente incompatível

Os testes mostraram discrepâncias entre extensões que são compatíveis e as que não são compatíveis. Isso não é um problema do componente de verificação pré-atualização. Em vez disso, os desenvolvedores de extensões enviam, por meio de suas extensões, informações que preencheriam corretamente a verificação pré-atualização. Se as extensões deles não estiverem codificadas para informar à verificação pré-atualização os dados corretos, há muito pouco (ou nada) que a verificação pré-atualização ou o Projeto Joomla! possam fazer a respeito. Uma boa fonte de informações seria o site do desenvolvedor da extensão de terceiros, para verificar como a extensão específica deve ser tratada durante a atualização do J5 para o J6.

A imagem mais abaixo nesta seção mostra um exemplo do componente de verificação pré-atualização no Joomla 5.4.x, na seção Extensões.

A seção superior exibirá as extensões que exigem uma atualização. Acesse Sistema -> Atualização -> Extensões e atualize suas extensões.
A seção intermediária mostra as extensões para as quais as informações de atualização não estão disponíveis por parte do desenvolvedor da extensão. Você não saberá se elas são compatíveis ou não sem testá-las ou entrar em contato com o desenvolvedor.

A seção inferior mostra as extensões que não exigem atualização. Isso significa que as extensões estão informando ao Joomla que são compatíveis com o Joomla 6. Não é especificado se elas exigem ou não o plugin de compatibilidade com versões anteriores.

Observe que essas extensões não são recomendadas pelo Projeto Joomla. Elas são mostradas apenas como exemplo. Foram escolhidas aleatoriamente no JED para fins de teste.

![Seção Extensões da verificação pré-atualização](../../../en/images/migration/joomla-5-to-6-steps/04-steps-5-to-6-pre-update-check.png)

Recomenda-se usar a seção **Extensões** do componente de verificação pré-atualização apenas como uma visão geral de nível extremamente alto, e não como a fonte de verdade 100% confiável. Em outras palavras, talvez você não possa confiar no componente de verificação pré-atualização, dependendo das extensões que estiver usando.

*Qual é então a fonte de verdade?* Sistema -> Gerenciar extensões

![Painel do sistema com Gerenciar extensões destacado](../../../en/images/migration/joomla-5-to-6-steps/05-steps-5-to-6-system-dashboard-manage.png)

Na tela Extensões: Gerenciar, você poderá ver todas as extensões de terceiros que está usando no site. Na captura de tela abaixo, você vê a tela principal. Na coluna Autor, é possível ver o nome de um desenvolvedor popular de extensões em várias linhas. Também é possível ver o autor Projeto Joomla em várias linhas.

![Página principal de Gerenciar extensões](../../../en/images/migration/joomla-5-to-6-steps/06-steps-5-to-6-extensions-manage.png)

Verifique suas extensões de terceiros. Em seguida, você precisará determinar se elas são compatíveis com o J6 (com ou sem o plugin de compatibilidade com versões anteriores) ou não. Se não forem, a atualização não será bem-sucedida.

### Três maneiras de verificar a compatibilidade das suas extensões de terceiros com o J6

1. Consulte o site do desenvolvedor.
2. Faça um backup/cópia do seu site J5, restaure-o em um subdomínio, ative o modo de depuração e siga o passo a passo (abaixo) para atualizar para o J6. Verifique se algo apresenta problemas. Se isso acontecer, desative cada extensão que gerar um erro, anotando qual é a extensão. Você precisará entrar em contato com o desenvolvedor, pois ela não é compatível com o J6.
3. Instale um pacote limpo do J6 em um subdomínio, ative o plugin Behaviour - Backward Compatibility, instale todas as extensões que você usa e verifique se elas funcionam.

OBSERVAÇÃO: O Joomla! Extensions Directory JED exibirá selos de compatibilidade com o Joomla 6 para extensões que sejam compatíveis com ou sem o uso do plugin de compatibilidade retroativa.

Você pode fazer uma combinação das opções acima. Comece com uma instalação limpa e teste suas extensões. Quando souber quais funcionam ou não, você poderá trabalhar com os desenvolvedores para verificar em que ponto está o desenvolvimento delas para o J6. ENTÃO, quando todas as suas extensões funcionarem em um site limpo, você saberá que pode **testar** uma atualização completa do J5.4.x para o 6.x.

Talvez você queira determinar se uma extensão funciona sem o plugin de compatibilidade retroativa ativado. Nesse caso, você precisará ter acesso ao banco de dados. Planeje-se para isso. Certifique-se de que tem acesso ao banco de dados.

Após instalar uma instalação nova do J6, o plugin de compatibilidade retroativa estará desativado. Instale cada extensão uma de cada vez. Se ela derrubar seu site, ative o plugin de compatibilidade retroativa pelo banco de dados.

O Plugin de Compatibilidade Retroativa pode ser encontrado no banco de dados, na tabela #__extensions. Ele se chama plg_behaviour_compat6. Defina o campo Enabled como 0 para desativar o plugin. Defina-o como 1 para ativar o plugin. Ao ativar novamente o plugin de compatibilidade retroativa, você poderá recuperar o acesso ao backend do Joomla (desde que a extensão funcione com o plugin de compatibilidade retroativa).

OU

Você pode desativar extensões individuais no banco de dados para continuar testando as outras extensões e verificar se funcionarão sem o plugin de compatibilidade ativado. Essas entradas estarão na tabela #__extensions. Altere o campo Enabled para 0 para desativar a extensão.

Em alguns casos, quando você instala no J6 uma extensão que não é compatível com ou sem o plugin de compatibilidade retroativa ativado, será necessário localizar no banco de dados as entradas dessa extensão (pode haver algumas ou muitas) e desativá-las até recuperar o acesso ao backend. Essas entradas estarão na tabela #__extensions. Você alterará o campo Enabled para 0 para desativar a extensão. Assim que puder acessar novamente o backend do Joomla, poderá desinstalá-la corretamente em System -> Manage -> Extensions. Em seguida, entre em contato com o desenvolvedor.

### Cassiopeia e Weblinks

#### Cassiopeia

Cassiopeia continuará sendo o template do frontend do Joomla 6. Suas personalizações devem continuar funcionando, mas ainda recomendamos testá-las em um site de desenvolvimento para ter certeza.

#### com_weblinks

A extensão Weblinks funciona no J6 sem o plugin de compatibilidade retroativa ativado a partir da versão 5.4.0+:

- [Weblinks Evolved in the JCM](https://magazine.joomla.org/all-issues/september-2025/joomla-weblinks-evolved-insights-from-gsoc-2025). 
- [Weblinks on the JED](https://extensions.joomla.org/extension/weblinks/).

### Teste

Como parte do seu planejamento, recomenda-se testar a atualização em um subdomínio ou localmente para determinar se ela funciona perfeitamente. Certifique-se de acompanhar todas as etapas necessárias para que a atualização ocorra **perfeitamente**.

Depois de testar a atualização em um subdomínio ou localhost, e ela funcionar **perfeitamente**, você poderá fazer um backup do seu site de produção e realizar a atualização nele. As instruções passo a passo estão abaixo.

## Atualização passo a passo

O site que você atualizará deve atender a todos os requisitos técnicos e estar executando o Joomla 5.4.x para poder ser atualizado. Se o seu site ainda não estiver executando o Joomla 5.4.x, atualize-o para a versão 5.4.x antes de atualizar para o J6.

1. Siga todas as instruções da seção Planejamento (acima) antes de atualizar.
2. **Faça backup do seu site.**
3. Atualize todas as extensões que precisarem ser atualizadas.
4. Desative ou desinstale todas as extensões que não sejam compatíveis com o J6.
5. Ative o Debug (Configuração global -> aba Sistema -> defina a opção Sistema de depuração como Sim).
6. **Faça backup do seu site novamente.**
7. **Teste o backup para garantir que ele seja restaurado.** (Sim, faça isso. Você se sentirá melhor.)
8. Acesse Sistema -> Atualização -> Joomla
![Painel do sistema com a opção Atualizar Joomla destacada](../../../en/images/migration/joomla-5-to-6-steps/07-steps-5-to-6-system-dashboard-joomla.png)

9. Clique no botão Opções na barra de ferramentas superior, no lado direito.
![Página de atualização do Joomla com o botão Opções destacado](../../../en/images/migration/joomla-5-to-6-steps/08-steps-5-to-6-joomla-update.png)

10. Altere o Canal de atualização para Joomla Next.
![Opções de atualização do Joomla com o canal de atualização destacado](../../../en/images/migration/joomla-5-to-6-steps/09-steps-5-to-6-joomla-update-options.png)

11. Clique em Salvar e fechar na barra de ferramentas superior.
12. Se o seu servidor atender às especificações técnicas, você verá a tela a seguir, com links na barra lateral esquerda para Configurações obrigatórias, Configurações recomendadas e Extensões.
![Verificação pré-atualização com a barra lateral destacada](../../../en/images/migration/joomla-5-to-6-steps/10-steps-5-to-6-pre-update-check-for-6.png)

13. É muito provável que suas Configurações obrigatórias e Configurações recomendadas estejam corretas, pois esta tela não será exibida se o seu ambiente não atender aos requisitos técnicos. As extensões podem não estar corretas. Consulte a seção Planejamento (acima) sobre a verificação pré-atualização e sobre por que ela pode não exibir uma marca de verificação verde mesmo quando todas as extensões são compatíveis. Você já fez os testes (certo?), portanto já sabe se elas são compatíveis ou não.
14. O plugin Compatibilidade retroativa 6 está habilitado no Joomla 5.4.x. Para atualizar para o J6, o plugin Comportamento - Compatibilidade retroativa precisa ser desabilitado.
15. **Se você não seguiu as instruções da seção Planejamento (acima) para a execução de teste, pare agora, volte à seção Planejamento e siga as instruções. O planejamento é a parte mais importante desta atualização.**
16. Quando tiver certeza de que todas as suas extensões são compatíveis com o J6 e tiver testado a atualização com resultado perfeito, você poderá marcar a opção para Reconhecer os avisos sobre extensões potencialmente incompatíveis e prosseguir com a atualização; clique em OK na caixa pop-up e, em seguida, clique no botão Atualizar.
![Aviso para reconhecer os avisos](../../../en/images/migration/joomla-5-to-6-steps/11-steps-5-to-6-pre-update-warnings.png)

17. Em seguida, seu site solicitará novamente a confirmação de que você fez um backup (o que você fez e testou para garantir que ele fosse restaurado).
![Página de envio e atualização para o Joomla 6](../../../en/images/migration/joomla-5-to-6-steps/12-steps-5-to-6-upload-and-update.png)

18. Seu site realizará a atualização para o J6.
![Página de progresso da atualização](../../../en/images/migration/joomla-5-to-6-steps/13-steps-5-to-6-joomla-update-progress.png)

19. Uma atualização bem-sucedida exibirá uma tela como esta:
![Página de status da atualização mostrando sucesso](../../../en/images/migration/joomla-5-to-6-steps/14-steps-5-to-6-joomla-update-success.png)

20. Você verá, no canto superior direito da tela, que seu site está usando o Joomla 6.
21. Teste o frontend do seu site.
22. Teste o backend do seu site.
23. Desative o Debug em Sistema -> Configuração global -> aba Servidor.
24. Corrija sua nova Pesquisa inteligente, se necessário.
25. Desfrute de uma bebida agradável e maravilhe-se com o quanto você é incrível.

## E se algo der errado?

Se você testou tudo previamente, isso não deveria acontecer. Mas é possível que algo no ambiente tenha mudado ou que algum código de uma extensão tenha sido alterado entre o momento dos testes e a atualização.

Como você ativou o Debug antes de começar, deverá conseguir ver qual extensão está causando o problema e desativá-la (isso talvez precise ser feito no banco de dados caso você não consiga mais acessar o backend para desativá-la). Dessa forma, seu site ficará funcionando enquanto você descobre o que deu errado e corrige o problema.

Na pior das hipóteses, restaure o backup para ter tempo de investigar o que aconteceu em um ambiente de teste.

A Correção do banco de dados pode resolver alguns dos seus problemas. Acesse o Painel do sistema e clique em Banco de dados.

![Painel do sistema com o link Banco de dados destacado](../../../en/images/migration/joomla-5-to-6-steps/15-steps-5-to-6-system-dashboard-database.png)

Na página Manutenção: Banco de dados, serão exibidos todos os problemas na estrutura do banco de dados que seu site possa ter. Marque a caixa de seleção apropriada e clique no botão Atualizar estrutura na barra de ferramentas superior.

![Página de banco de dados da manutenção mostrando um problema](../../../en/images/migration/joomla-5-to-6-steps/16-steps-5-to-6-maintenance-database.png)

## Outros lugares para obter ajuda

- [Fórum do Joomla: Quadro de Migração e Atualização 6.x](https://forum.joomla.org/viewforum.php?f=866&sid=47959551fb677ee3690f8b61eece277b)
- [Comunidade Joomla no Mattermost](https://joomlacommunity.cloud.mattermost.com/main/channels/town-square)

*Traduzido por openai.com*