<!-- Filename: Managing_404_Errors / Display title: Gerenciando Erros 404  -->

## Por que o 404 Not Found é importante

O problema mais comum com sites que estão lutando para melhorar suas classificações nos mecanismos de busca é o número de erros de 'não encontrado' – comumente chamados de erros *404*, pois esse é o código de status retornado quando a página não pode ser encontrada.

Primeiramente, há razões legítimas para ter erros 404 – se você tem uma página para um evento que já ocorreu ou um serviço que você não oferece mais. Nesses casos, eventualmente a página será removida do índice dos mecanismos de busca e não será mais associada ao seu site.

O problema ocorre se você tem muitos erros 404 – por exemplo, se você despublicar uma categoria que continha centenas de artigos. Da perspectiva do mecanismo de busca, isso não é uma boa experiência para seus visitantes, porque eles acessam seu site e a informação que o mecanismo de busca disse que estava lá, não está. É por isso que não é uma boa ideia ter muitos erros 404 no seu site.

## Central da Pesquisa Google

O primeiro passo é descobrir quantos você tem – o que pode ser feito usando o [Central da Pesquisa](https://developers.google.com/search) do Google. Este é um conjunto de ferramentas gratuito que permite analisar seu site e identificar problemas, erros e questões rapidamente. Recomenda-se que você tenha todos os sites que gerencia registrados no Search Central para garantir que você seja notificado no caso de qualquer problema.

Quando você visita o Search Central, há uma seção que mostra os Erros de URL na lista de busca – isso exibirá uma lista dos erros 404 que o Google encontrou em seu site, e um gráfico que mostra como isso mudou ao longo do tempo. Se o gráfico começar a subir, investigue por que existem páginas que estavam no seu site e agora não podem ser encontradas.

Se houve um problema temporário no seu site, você pode marcar os erros como corrigidos.

![ferramentas para webmasters](../../../en/images/performance/404-discovery.png)

## Corrigindo Problemas

A descoberta é apenas uma parte do processo. Depois de ter descoberto os URLs problemáticos, faça algo a respeito (se precisar corrigir!) redirecionando a página para outra no site, reinstaurando a página original ou investigando o que causou o erro 404.

Se precisar redirecionar uma página, você pode usar o plugin System - Redirect para coletar páginas ausentes e o componente System / Redirects para redirecionar páginas ausentes para páginas existentes.

## Monitoramento de Problemas

Se você deseja monitorar seu tráfego de erro 404, a melhor maneira de fazer isso no Analytics é observar o que acontece quando você tem um erro 404. Na maioria dos casos, o título da página muda para 404 – então podemos criar um segmento personalizado que filtrará o tráfego com um título de 404 e informará qual é a página de destino. Isso deve permitir que você monitore e gerencie proativamente seus erros 404 e garanta que os visitantes do seu site não acabem em links quebrados.

![Alertas de Analytics para tráfego 404](../../../en/images/performance/404-analytics-alerts.png)

![Visão geral do público com alertas de Analytics](../../../en/images/performance/404-analytics-alerts-2.png)

O Google também tem a capacidade, no Analytics, de configurar alertas. Os alertas permitem que você receba um e-mail quando certos eventos ocorrem. Neste caso, podemos configurar um alerta para ser notificado se houver um aumento de mais de 5% no número de erros 404 em um período semanal – o que pode significar que temos um problema no site que precisa ser investigado.

Esta é uma ótima maneira de se manter atualizado, mesmo que você não tenha feito login para verificar o seu painel!

![Email de alertas de Analytics](../../../en/images/performance/404-analytics-alerts-email.png)

## Monitoramento de Erros com um Painel

Existe também um painel que você pode instalar chamado *Painel de Integridade de Dados* que mostra informações sobre erros 404, junto com alguns outros métricos que podem ser de interesse. Basta pesquisar na Galeria do Google Analytics por *Painel de Integridade de Dados* e selecionar em qual perfil instalá-lo.

![Integridade de dados](../../../en/images/performance/404-data-integrity.png)

*Traduzido por openai.com*

