<!-- Filename: J4.x:Home_Page_in_Different_Style / Display title: Página Inicial em Estilo Diferente  -->

## Página Inicial do Site

A página inicial de um site pode ser selecionada a partir de qualquer tipo de item de menu, escolhendo um ícone cinza na coluna Home de qualquer lista de itens de menu. Experimente fazer uma alteração! Veja a alteração no seu site em uma aba ou janela de navegador separada. Você pode facilmente mudar de volta novamente. Se você quiser uma página inicial distinta, pode optar por um tipo de item de menu Artigo Único, Blog de Categoria, Artigos em Destaque, ou algo diferente.

Suponha que você gostaria de dar à sua página inicial uma aparência distinta e um pouco diferente de todas as outras páginas do seu site. Existem muitos métodos diferentes disponíveis para personalizar a aparência de uma página inicial:

- Através de módulos atribuídos apenas à página inicial.
- Através de estilos personalizados.
- Através de um Sobrescrito de Modelo ou Layout.
- Através de um modelo separado ou um modelo filho usado apenas para o item de menu da página inicial.
- Mais...?

## Exemplo: Dados de Amostra Cassiopeia

Os dados de amostra Cassiopeia criam uma página inicial usando um tipo de item de menu **Artigos em Destaque**. Ela está disposta com a aparência demonstrada na captura de tela abaixo (algumas pequenas alterações foram feitas em artigos individuais para melhorar a captura de tela aqui).

![página inicial usando cassiopeia e dados de amostra](../../../en/images/templates/templates-home-page-style-cassiopeia-sample-data.png)

É assim que o layout é alcançado:

### Módulo de Imagem

A grande imagem abaixo da barra de menu está em um módulo personalizado chamado Imagem, atribuído à posição do banner no template Cassiopeia.

![módulo personalizado usado no estilo de dados de amostra](../../../en/images/templates/templates-home-page-style-custom-module-image.png)

Na aba Atribuição do Menu, o módulo é atribuído apenas à Página Inicial:

![aba de atribuição de menu do módulo personalizado](../../../en/images/templates/templates-home-page-style-custom-module-menu-assignment.png)

A imagem de fundo é selecionada na aba Opções do formulário de edição de Módulos: Personalizado.

Na aba Avançado / campo Layout, o item `banner` é selecionado. O layout do banner é um layout de template:

### Layout de Template

O layout do módulo padrão em
`siteroot/modules/mod_custom/tmpl/default.php` não exibe o módulo como desejado. Existe um layout alternativo em
`siteroot/templates/cassiopeia/html/mod_custom/banner.php`. Como `banner.php`
não está presente no código do módulo personalizado, ele funciona como um layout que você pode selecionar, em vez de uma sobrescrita que é sempre usada. No módulo de Imagem, você pode selecionar o layout padrão, Salvar e recarregar o site para ver a diferença. Volte para o layout de banner e salve novamente para restaurar o comportamento normal.

Existem artigos separados sobre Sobrescritas e Layouts.

### Módulo Newsflash

Abaixo da grande Imagem, há três pequenos boxes, cada um com uma imagem e texto abaixo. Eles são criados usando um módulo Artigos - Newsflash na posição top-a do template. O módulo está configurado para exibir 3 itens. Sua Atribuição de Menu é apenas para a Página Inicial. A aba Avançado possui o Layout configurado para horizontal e o Estilo do Módulo configurado para noCard.

![módulo newsflash](../../../en/images/templates/templates-home-page-style-newsflash-module-image.png)

Isso conclui a explicação de como a página inicial de dados de amostra Cassiopeia foi criada.

## Mais Opções

Você pode desejar fazer mais. Um esquema de cores diferente para a página inicial, uma marca d'água ou um layout personalizado. Aqui estão algumas ideias:

### Exibição da Página

Nos Menus: no formulário Editar Item para o menu inicial, selecione a aba Exibição da Página. O campo Classe da Página geralmente está vazio. Qualquer coisa inserida aqui se torna uma classe extra no elemento

da página. Por exemplo, inserir `fancyhome` resulta no seguinte na saída da página inicial para aquela página específica:
```html
<body class="site com_content wrapper-static view-featured no-layout no-task itemid-101 fancyhome has-sidebar-right">
```
Você pode então criar um arquivo user.css via **Sistema **→** Modelos do Site **→** Detalhes e Arquivos do Cassiopeia**. Selecione o botão `Novo Arquivo` e crie user.css na pasta css. Em seguida, insira os estilos no formulário de edição de user.css. Exemplo:
```css
    .fancyhome {
      background-color: #f8fff8;
    }
```
Isso dará à página inicial um fundo verde claro. Use \#f8f8ff; para um fundo azul claro ou \#ffffee para amarelo claro. Você pode fazer todo tipo de coisas com seu estilo fancyhome, mas você precisa de um bom conhecimento de css.

### Modelos Alternativos para a Página Inicial

Você pode instalar modelos de site alternativos, obtidos de fornecedores de modelos de terceiros. E você pode criar modelos filhos que se comportam de forma semelhante. Em ambos os casos, você pode escolher qual modelo será o padrão para todas as páginas e qual será usado apenas para a página inicial.

- Selecione **Sistema → Estilos de Modelos de Site** no menu do Administrador.
- Selecione o modelo que você deseja usar para a página inicial. Deve ser um dos que não estão selecionados como o modelo padrão.
- Na aba Atribuição de Menu, selecione apenas o item de menu inicial. Qualquer coisa não selecionada aqui ainda usará seu modelo padrão.
- Você pode selecionar algumas opções na aba Avançado, mas elas variam com cada modelo e não são abordadas aqui.

Existem outros artigos sobre personalização do Cassiopeia.

*Traduzido por openai.com*

