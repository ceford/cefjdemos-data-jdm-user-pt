<!-- Filename: jdocmanual?manual=user&heading=performance&filename=accessibility-checker.md / Display title: Verificador de Acessibilidade  -->

## Sistema - Verificador de Acessibilidade do Joomla

Este é um plugin principal que pode ser usado para verificar a acessibilidade durante a criação de conteúdo de artigos. A captura de tela a seguir mostra algumas configurações do plugin:

![Configurações do formulário do plugin](../../../en/images/performance/performance-jooa11y-plugin-form.png "Configurações do Plugin")

Com a opção **Mostrar Sempre** definida como *Ligado*, o ícone de relatório aparece em cada página do site. Isso é útil para o desenvolvimento, mas nunca deve ser deixado ativado para um site ao vivo. Defina como **Desligado**!

Com a opção *Mostrar Sempre* definida como *Ligado*, cada página do site tem um ícone no canto inferior direito com uma contagem do número de problemas. A captura de tela a seguir mostra o ícone selecionado para exibir um painel de informações. Inclui um Contorno da Página, comentários de Legibilidade e Avisos, que podem ser selecionados um por um. O primeiro problema foi selecionado.

![Verificação de acessibilidade do site](../../../en/images/performance/performance-jooa11y-site-display.png "Verificação de acessibilidade do site")

O formulário *Artigos: Editar* tem um botão **Verificação de Acessibilidade** na Barra de Ferramentas. Ele mostra a verificação de um artigo individual em uma janela pop-up:

![Verificação de acessibilidade do editor](../../../en/images/performance/performance-jooa11y-admin-display.png "Verificação de acessibilidade do editor")

## Corrigindo Problemas

O Verificador de Acessibilidade é uma ferramenta para identificar problemas. Ele não corrige problemas. Isso depende de você. O verificador possui algumas configurações que você pode ativar ou desativar conforme necessário. Elas incluem Contraste, Rótulos de Formulários, Links (Avançado) AAA, Legibilidade AAA, Modo Escuro e Filtro de Cores com simulação de quatro tipos de visão de cores defeituosas.

Para mais informações, consulte a Visão Geral do Sa11y.

Por exemplo, sobre Legibilidade, ele diz:

> O Sa11y pode estimar a pontuação de legibilidade de todos os parágrafos e conteúdos de listas. Uma boa pontuação de legibilidade é uma indicação de que seu texto é compreensível e fácil de assimilar. É baseada na média de comprimento das frases e palavras na sua página, usando uma fórmula conhecida como teste de facilidade de leitura de Flesch (Wikipedia). Uma pontuação de leitura "boa" está entre 60 e 100. Às vezes, pode ser difícil alcançar uma boa pontuação de legibilidade. A maioria de suas páginas pode indicar "difícil". Lembre-se de que este recurso é usado apenas para estimar a legibilidade do seu conteúdo. Deve ser usado apenas como referência, e não como indicação de conformidade. O Sa11y calcula a pontuação de legibilidade com base em todos os conteúdos de parágrafos (tags `<p>`) e listas (tags `<li>`). Uma pontuação baixa não afeta o estado de aprovação ou reprovação do Sa11y.

*Traduzido por openai.com*

