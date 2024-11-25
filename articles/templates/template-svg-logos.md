<!-- Filename: J4.x:Template_SVG_Logos / Display title: Modelos de Logos SVG  -->

## Logo da Cassiopeia

O template padrão do site Joomla 4, Cassiopeia, usa a palavra CASSIOPEIA como um Logotipo de Marca. Ela aparece no topo de cada página, a menos que você defina a Marca como Não no formulário Templates: Editar Estilo, guia Avançado, ou use uma palavra de Título em vez de um gráfico. Essa palavra é, na verdade, um arquivo Gráfico Vetorial Escalonável (SVG). Você pode escolher um gráfico alternativo, mas criar e usar um Logo SVG alternativo é bastante complicado. Este breve conjunto de instruções pode ajudar.

## Inkscape

O Inkscape é um aplicativo de gráficos vetoriais de código aberto e multiplataforma, o que significa que você pode baixá-lo gratuitamente e usá-lo no Linux, Mac ou Windows. Para começar, acesse o site do Inkscape e baixe a versão para o seu laptop ou desktop. Inicie o Inkscape e você estará pronto para criar um logotipo de marca SVG. A captura de tela abaixo mostra o Inkscape no meio da criação de um novo logotipo SVG.

![criação do logotipo no inkscape](../../../en/images/templates/templates-svg-logos-inkscape.png)

## Instruções

Para este artigo, é necessário um logotipo que mostre **GREEN CASSIOPEIA** no mesmo tamanho que **CASSIOPEIA** no logotipo padrão, que tem 32 pixels de altura:

1. Inicie o Inkscape, ajuste a janela a um tamanho confortável, selecione Exibir / Zoom / Zoom na Página
2. Selecione a Ferramenta de Texto, marcada com a letra A na Barra de Ferramentas à esquerda
3. Selecione Arial, Negrito, 40 e px
4. Arraste para definir uma caixa ocupando a maior parte da largura da página
5. Digite no Texto: GREEN CASSIOPEIA
6. Selecione Exibir / Seleção de Zoom
7. Selecione a ferramenta Selecionar, marcada por uma seta - no topo da Barra de Ferramentas à esquerda
8. Trave os valores de tamanho Horizontal e Vertical - o símbolo de cadeado na barra superior
9. Defina a unidade de medida para px
10. Altere a altura para 32 - você verá o logotipo mudar para o novo tamanho
11. Selecione Caminho / Objeto para Caminho - sem mudança visível, mas as palavras não são mais texto
12. Selecione Arquivo / Propriedades do Documento
13. Selecione Redimensionar para Conteúdo
14. Aproxime a visão geral
15. Defina o Preenchimento para branco - clique na caixa branca na paleta de cores inferior
16. Arquivo / Salvar em
    local-site-root/images/headers/green-cassiopeia-optimised.svg
    1. Se você salvar em outro lugar, terá que usar um gerenciador de arquivos ou ftp para enviar os arquivos svg. O componente de Mídia pode usar arquivos SVG, mas no momento ele não os carrega.
17. Selecione SVG Otimizado (.svg) na lista de tipos de arquivo na parte inferior da caixa de diálogo de Salvar.
18. Salve, OK para todas as Padrões no formulário de Saída SVG Otimizado
19. Configure algumas Opções do Administrador do Joomla para permitir o uso de arquivos SVG
20. Vá para Conteúdo / Mídia / Opções
    1. Acrescente às extensões permitidas: ,svg
    2. Acrescente às Extensões de Imagem Legais (Tipos de Arquivo): ,svg
    3. Acrescente aos Tipos MIME Legais: ,image/svg+xml
21. Salve & Feche
22. Vá para Sistema / Modelos de Site / Opções
    1. Acrescente aos Formatos de Imagem Válidos: ,svg
23. Salve & Feche
24. Vá para Sistema / Estilos de Modelo de Site
25. Selecione seu modelo
26. Na aba Avançado, campo de Logotipo, use Selecionar para encontrar seu logotipo recém-criado
27. Salve e recarregue sua página do Site

![resultado da criação do logotipo no inkscape](../../../en/images/templates/templates-svg-logos-inkscape-result.png)

*Traduzido por openai.com*

