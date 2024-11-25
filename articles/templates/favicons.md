<!-- Filename: J4.x:Favicons / Display title: Favicons  -->

## Os Favicons do Joomla!

Favicons são os pequenos ícones que aparecem na aba do navegador ao lado do nome do seu site. Perto do início do arquivo template index.php, há três instruções para carregar favicons na página:
```php
    // Navegadores suportam favicons SVG
    $this->addHeadLink(HTMLHelper::_('image', 'joomla-favicon.svg', '', [], true, 1), 'icon', 'rel', ['type' => 'image/svg+xml']);
    $this->addHeadLink(HTMLHelper::_('image', 'favicon.ico', '', [], true, 1), 'alternate icon', 'rel', ['type' => 'image/vnd.microsoft.icon']);
    $this->addHeadLink(HTMLHelper::_('image', 'joomla-favicon-pinned.svg', '', [], true, 1), 'mask-icon', 'rel', ['color' => '#000']);
```
Para o template Cassiopeia, o Joomla procurará os favicons nos seguintes locais:

1.  **media/templates/site/cassiopeia/images** - eles não estão lá, então o Joomla procurará no próximo local.
2.  **media/system/images** - eles estão lá, então o Joomla os usará a partir desse local.

Se você quiser usar seus próprios favicons em vez dos favicons do Joomla, você deve enviar para o primeiro local: **media/templates/site/cassiopeia/images**. Você pode fazer isso usando o formulário de Personalização de Templates. Eles não serão afetados por nenhuma atualização no template Cassiopeia.

Favicons às vezes são usados em tamanhos maiores e em lugares fora da aba do navegador. Por exemplo, esta é uma captura de tela de parte de uma página inicial do Firefox mostrando alguns dos locais favoritos do usuário:

![exemplos de favicon da página inicial do firefox](../../../en/images/templates/favicons-firefox-start-collection.png)

Todos os navegadores modernos suportam ícones SVG, então você deve dar prioridade à criação de um ícone SVG.

## Sobre SVG

SVG é um acrônimo para Gráficos Vetoriais Escaláveis (Scalable Vector Graphics). Um arquivo SVG contém texto em um formato que define as localizações e formas das linhas com cores de linha, cores de preenchimento e assim por diante. A captura de tela a seguir mostra o arquivo *joomla-favicon.svg* aberto em um editor de texto. Os números de linha são criados pelo editor de texto. Eles não estão presentes no arquivo. As linhas longas representam curvas e estão truncadas aqui para fins de exibição.

![conteúdo de texto do favicon do joomla](../../../en/images/templates/favicons-joomla-favicon-svg-text.png)

Para criar um arquivo SVG, você precisa usar um aplicativo apropriado, como o Inkscape. Aplicativos de gráficos rasterizados, como Photoshop ou The GIMP, não são adequados. Se você preferir desenhar um ícone em um aplicativo de gráficos rasterizados, ou se tiver um logotipo gráfico rasterizado existente que pode ser adaptado para um ícone, você pode importar o arquivo PNG resultante no Inkscape e então traçá-lo para produzir um arquivo SVG. A imagem traçada deve ser excluída após o traçado!

A criação real de um favicon SVG está além do escopo deste artigo. A criação de um arquivo padrão *favicon.ico* a partir de um arquivo *joomla-favicon.svg* é muito simples—muitos sites fazem isso online gratuitamente.

## Como Criar Favicons

Se você quiser criar seus próprios favicons, a melhor maneira de fazer isso é criar um favicon SVG e, em seguida, usar uma ferramenta online para gerar todos os outros formatos com isso como entrada. Neste exemplo, um ícone é necessário para adequar um modelo filho chamado Cassiopeia Green. Um ícone precisa ser quadrado e não muito elaborado, já que o tamanho mínimo de exibição é 16x16 pixels. Alguns dispositivos precisam de resoluções mais altas, como 32x32 ou 180x180, e o Google recomenda múltiplos de 48x48 pixels. Se você começar com um SVG, não precisa se preocupar com nada disso - basta criar uma imagem quase quadrada com um design adequado. Neste exemplo, o favicon será as letras *J4* em verde escuro.

### Inkscape

Inkscape é um aplicativo gratuito, open source, multiplataforma, para gráficos vetoriais, usado para trabalhar com arquivos SVG. Funciona no Linux, Mac e Windows. Visite o site do Inkscape (inkscape.org) para baixar uma cópia para sua plataforma. As ilustrações a seguir mostram a tela do Inkscape no meio das instruções a seguir.

![inkscape com favicon em preparação](../../../en/images/templates/favicons-inkscape-favicon.png)

### Criar um SVG

1. Inicie o Inkscape e deixe a janela em um tamanho confortável: selecione Ver / Zoom / Zoom Página
2. Selecione a Ferramenta de Texto, marcada com a letra A na Barra de Ferramentas à esquerda
3. Selecione Arial, Normal, 48 e px
4. Arraste para definir a caixa em qualquer lugar na página
5. Digite no Texto: J4
6. Selecione Ver / Zoom Seleção
7. Selecione Caminho / Objeto para Caminho - sem mudança visível, mas as palavras não são mais texto
8. Selecione Arquivo / Propriedades do Documento
9. Selecione Redimensionar para Conteúdo
10. Diminua o zoom para uma melhor visualização - mas certifique-se de que todas as letras ainda estão selecionadas
11. Defina a caixa de altura para o mesmo valor da caixa de largura. Digite isso!
12. Feche o diálogo de Propriedades do Documento
13. Ver / Zoom Página novamente - os caracteres precisam estar centralizados
14. Editar / Selecionar Tudo
15. Objetos / Alinhar e Distribuir
16. Mover seleção como grupo / Relativo à Página / Centralizar no eixo horizontal - você deve ver o J4 movendo-se para o ponto médio vertical
17. Selecione Preenchimento e Contorno à direita - o painel à direita possui uma lista suspensa marcada com um chevron para baixo
18. No painel de Preenchimento e Contorno, selecione Preenchimento e o primeiro quadrado preenchido
19. No painel RGB insira 006400ff no campo RGBA, perto da parte inferior direita - o código para o estilo CSS *darkgreen*
20. Arquivo / Salvar
21. No diálogo Salvar, insira um nome de arquivo adequado, por exemplo, green-favicon-j4.svg
22. Selecione um local adequado, por exemplo, *~/Documents/joomla-dev/svgs*
23. Selecione SVG Otimizado (*.svg*) na lista suspensa na parte inferior do formulário.
24. Selecione *Salvar*
25. Selecione *OK* para todos os padrões no formulário de Saída de SVG Otimizado
26. Feche o SVG em que você está trabalhando - haverá uma oportunidade de salvar a imagem no formato Inkscape, mas você realmente não precisa fazer isso.

### Editar o SVG com um Editor de Texto

Inicie seu editor de texto favorito para fazer algumas alterações que não foram possíveis no Inkscape.

1. Abra seu arquivo SVG recém-criado - observe que a primeira linha é uma especificação XML
2. Você pode deletar a segunda linha - um comentário contendo Criado com Inkscape
3. Se presente, você pode deletar a linha contendo, pois não há texto
4. Abra o arquivo joomla-favicon.svg original - ele está em *joomla_root/media/system/images*
5. Copie o bloco de estilo e cole-o em seu SVG na linha seguinte à declaração SVG
6. Feche o arquivo *joomla-favicon-svg* original para evitar alterações acidentais nele
7. No bloco de estilo do seu próprio arquivo SVG, mude path {fill: \#000;} para path {fill: \#006400;}, o valor na linha
8. Remova *fill="#006400"* da linha
9. Salve
10. Abra a imagem no seu navegador. Para Firefox isso é Arquivo / Abrir Arquivo...

Você deve ver a imagem no seu navegador. O exemplo mostra J4 com 47 pixels quadrados. A próxima etapa é criar os outros tipos de ícones que você precisa usando seu SVG recém-criado como mestre.

### Processamento Online

Acesse o site Real Favicon Generator. Outros sites estão disponíveis, mas este parece ser particularmente abrangente.

1. Selecione o botão rotulado *Selecione sua imagem de Favicon*
2. O site mostrará a imagem mestre. Ele também diz *Sua imagem não é quadrada (688x512). Podemos corrigir isso adicionando margens transparentes*
3. Selecione o botão *Continuar com esta imagem* abaixo da Imagem Mestre.
4. Há subformulários com fundos azul claro para vários tipos de ícone - preencha cada um verificando se a pré-visualização é adequada para você.
5. É melhor seguir com os padrões das Opções do Gerador de Favicon, a menos que você saiba mais. Exceto:
6. Caminho, selecione a opção Eu não posso... e insira: *media/templates/site/cassiopeia-green/images*
7. Selecione o botão *Gere seus Favicons e Código HTML*
8. Após um curto atraso, há um novo formulário, selecione o botão Download do seu pacote: botão *Pacote Favicon*
9. Salve o download ...
10. Selecione e copie o bloco de links para salvar em algum lugar.
11. Feche o site de processamento online

O download é um arquivo *zip* contendo 10 itens: *favicon.ico*, *safari-pinned-tab.svg*, seis arquivos PNG, *browserconfig.xml* e *site.webmanifest*.

### Implantação

Para usar o conjunto padrão de favicons do Joomla, você precisa renomear e mover os ícones para *joomla_root/media/templates/site/yourtemplate/images*:

- Sua imagem SVG mestre, *green-favicon-j4.svg*, deve ser renomeada para *joomla-favicon.svg*
- O arquivo *safari-pinned-tab.svg* baixado precisa ser renomeado para *joomla-favicon-pinned.svg*
- O arquivo *favicon.ico* baixado só precisa ser movido

### O Bloco de Links

O bloco de links copiado anteriormente contém:

```html
<link rel="apple-touch-icon" sizes="180x180" href="media/templates/site/cassiopeia-green/images/apple-touch-icon.png">
<link rel="icon" type="image/png" sizes="32x32" href="media/templates/site/cassiopeia-green/images/favicon-32x32.png">
<link rel="icon" type="image/png" sizes="16x16" href="media/templates/site/cassiopeia-green/images/favicon-16x16.png">
<link rel="manifest" href="media/templates/site/cassiopeia-green/images/site.webmanifest">
<link rel="mask-icon" href="media/templates/site/cassiopeia-green/images/safari-pinned-tab.svg" color="#5bbad5">
<link rel="shortcut icon" href="media/templates/site/cassiopeia-green/images/favicon.ico">
<meta name="msapplication-TileColor" content="#ffc40d">
<meta name="msapplication-config" content="media/templates/site/cassiopeia-green/images/browserconfig.xml">
<meta name="theme-color" content="#ffffff">
```

Provavelmente você não precisa usá-lo!

*Traduzido por openai.com*

