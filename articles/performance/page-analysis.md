<!-- Filename: jdocmanual?manual=user&heading=performance&filename=page-analysis.md / Display title: Análise de Página -->

## Lighthouse

> O Lighthouse é uma ferramenta automatizada e de código aberto para melhorar a qualidade das
páginas da web. Você pode executá-lo em qualquer página da web, pública ou que exija
autenticação. Ele oferece auditorias para desempenho, acessibilidade, aplicativos web progressivos,
SEO e mais.

Está disponível como uma ferramenta complementar para o Google Chrome e Firefox e pode ser
executado a partir da linha de comando. Isso é útil para testes em um ambiente de desenvolvimento
local.

Mais informações no site do Chrome para Desenvolvedores: Lighthouse.

Você pode usar a ferramenta online através do site PageSpeed Insights.

A captura de tela a seguir mostra a primeira parte do relatório do PageSpeed Insights:

![Relatório do PageSpeed Insights](../../../en/images/performance/performance-pagespeed-insights.png "Relatório do PageSpeed Insights")

## Melhorias de Desempenho

A segunda parte do relatório sugere métodos para melhorar o desempenho:

* **Eliminar recursos que bloqueiam a renderização** - Economia potencial de 540 ms.
Sinceramente, isso é muito trabalho para pouca recompensa.
* **Ativar a compressão de texto** Economia potencial de 11 KiB. Na
Configuração Global, painel do Servidor, defina a Compressão GZip da Página para *Sim*. Isso deixa
pequenos arquivos JavaScript e CSS para serem minimizados e comprimidos.
* **Reduzir CSS não utilizado** Economia potencial de 62 KiB. Os culpados são
template.min.css e joomla-fontawesome.min.css, mas isso implica
adaptar o CSS para cada página do site, o que é um trabalho muito propenso a erros para
pouca recompensa.
* **Servir ativos estáticos com uma política de cache eficiente** - 21 recursos encontrados.
Referências fornecidas, incluindo referências específicas do Joomla.

A mensagem geral é que algumas sugestões valem a pena serem corrigidas e outras
não.

## Relatório de Dispositivos Móveis vs Desktop

O relatório de Desktop geralmente difere do relatório de Dispositivos Móveis. Algumas questões adicionais identificadas neste caso:

* **Dimensione as imagens adequadamente** - Potencial de economia de 48 KiB. A tag de imagem está, na verdade, otimizada com imagens em webp de 768 e 1200 pixels de largura. Parece que algo intermediário é necessário.

## Acessibilidade

* **Links não têm um nome discernível** Isso se refere às setas para a esquerda e direita na parte inferior da página que navegam para a frente ou para trás. O texto foi deixado de fora para evitar problemas de tradução. É preciso pensar novamente!
* **Os alvos de toque não têm tamanho ou espaçamento suficiente** Isso se refere ao tamanho dos itens do menu nas colunas esquerda e direita. Eles precisam de mais espaço vertical - é necessário um ajuste de CSS.  

## Melhores Práticas e SEO

Embora ambos tenham pontuado 100 para Mobile e Desktop, eles precisam ser verificados novamente após cada alteração de design.

## Resumo

Todos os problemas neste site foram resolvidos, exceto pela desmontagem dos arquivos CSS e pela minificação dos arquivos Javascript e CSS de pequenos componentes.
*Traduzido por openai.com*

