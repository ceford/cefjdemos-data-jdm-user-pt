<!-- Filename: J4.x:Cassiopeia_Template_Customisation / Display title: Personalização de Cassiopeia  -->

## Introdução

Cassiopeia é o modelo de site fornecido com o Joomla 4. É um modelo de propósitos gerais **acessível** e **responsivo** excelente. Ele pode ser personalizado através das opções do modelo e do arquivo *user.css* por usuários com um pouco de conhecimento em HTML e CSS.

A ilustração a seguir mostra a aparência de um site Joomla 4 com um artigo e alguns itens de menu criados.

![Visualização de um único artigo Cassiopeia](../../../en/images/templates/cassiopeia-customisation-article-view.png)

## Modelos: Editar Estilo

Você pode experimentar a aparência do site abrindo o formulário Editar Estilo. Vá para **Sistema → Modelos → Estilos de Modelo do Site** e selecione o título do modelo na coluna Estilo, Cassiopeia - Padrão. A guia Avançado contém configurações que você pode ajustar:

![Cassiopeia editar estilo guia avançada](../../../en/images/templates/cassiopeia-customisation-edit-style.png)

Para testar as opções, abra uma aba ou janela do navegador com a interface do Administrador e uma segunda aba ou janela com a interface do Site e alterne entre elas após cada alteração salva.

### Marca

- **Sim** é o padrão. A barra de logotipo Cassiopeia contendo um Logotipo ou nome da Marca é exibida com um fundo escuro, azul por padrão.
- **Não** A barra de logotipo não é exibida. As opções para selecionar um Logotipo, Título e Slogan desaparecem.

A imagem de marca padrão é a palavra Cassiopeia como uma imagem em um arquivo SVG. Isso é o que é exibido na primeira ilustração acima.

Você pode definir a Marca para Não se desejar fornecer uma marca em um módulo HTML personalizado.

### Logotipo

- **Nenhum** O logotipo da imagem padrão Cassiopeia será utilizado a menos que um Título seja definido.
- **Imagem do Logotipo** O Logotipo selecionado aparecerá no lugar do logotipo Cassiopeia mesmo se um Título estiver definido.

### Título (alternativa ao logotipo)

- **Meu Nome de Marca** Se presente e você não selecionou uma imagem de Logotipo, as palavras no campo Título aparecerão sublinhadas na barra azul superior.

### Slogan

- **Sempre ao seu serviço** Se presente, as palavras no campo de slogan aparecerão em um tamanho de fonte pequeno abaixo da imagem do logotipo ou nome da Marca.

![Cassiopeia marca com slogan](../../../en/images/templates/cassiopeia-customisation-brand-with-tagline.png)

### Esquema de Fontes

- **Nenhum** o padrão. A família de fontes especificada na folha de estilo do modelo é usada, o que geralmente significa que o site usará as fontes com as quais você está familiarizado em seu próprio computador.
- **Outras** Uma família de fontes localizada na hierarquia da pasta do modelo ou baixada da web será utilizada. Você pode ver a aparência alterada do texto em uma página quando recarrega o site após alterar esta opção.

### Tema de Cor

- **Padrão** Uma cor de fundo azul escuro para a barra da Marca e outros recursos, como o botão de Login.
- **Alternativa** Uma cor de fundo marrom em vez de azul escuro.

![Cassiopeia esquema de cores alternativo](../../../en/images/templates/cassiopeia-customisation-alt-color-scheme.png)

### Layout

- **Estático** o padrão. A largura máxima é definida para 1320px. Em telas mais largas, a margem apenas fica mais larga.
- **Fluido** Não há largura máxima.

A visão em um dispositivo móvel de tela estreita:

![Cassiopeia visão móvel](../../../en/images/templates/cassiopeia-customisation-mobile-view.png)

### Cabeçalho Fixo

- **Não** o padrão. Itens de cabeçalho e conteúdo rolam para cima e saem da área de visão.
- **Sim** Exceto em telas estreitas, os itens de cabeçalho permanecem fixos na parte superior da área de visão enquanto os itens de conteúdo rolam para cima. Isso só é evidente quando o conteúdo da página é mais alto que a área de visão.

### Link de Voltar ao Topo

- **Não** o padrão. Não há link de Voltar ao Topo.
- **Sim** Quando o conteúdo é mais alto que a área de visão, no canto inferior direito da página há um botão marcado com um chevron para cima. Selecione-o para rolar de volta ao topo da página.

![Cassiopeia voltar ao topo](../../../en/images/templates/cassiopeia-customisation-back-to-top.png)


## Posições do Template Cassiopeia

À medida que você constrói um site com o Cassiopeia, torna-se muito útil conhecer as localizações das posições que você pode usar para os módulos. Algumas são descritivas, como *menu* e *bottom-a*, mas não é tão óbvio onde elas estão até que você as use. Esta ilustração pode ajudar:

![Posições do template Cassiopeia](../../../en/images/templates/cassiopeia-template-positions.png)

Experimente o seguinte:

### Mover o Módulo de Menu para a Posição *menu*

Um site Joomla 4 recém-instalado tem um menu na posição *sidebar-right*, como visto na primeira ilustração acima. Para este tutorial, alguns itens de menu foram adicionados, um dos quais é um pai com dois itens filhos. Para mover este menu para a posição de menu, vá para **Conteúdo** → **Módulos do Site** no menu do Administrador. Na lista, há três módulos incluindo o Menu Principal. Selecione-o para abrir o formulário de edição Módulos: Menu.

Na aba Módulo, mude o campo de Posição à direita para Menu \[menu\]. Salve e veja o resultado na exibição do Site. O menu parece bom, mas os itens filhos não estão lá.

No formulário de edição do menu, selecione a aba Avançado e role para baixo até o campo Layout. É uma lista suspensa com quatro opções. --Do Módulo-- / Padrão está selecionado por padrão. Experimente as outras opções e veja o resultado. (Lembre-se de *Salvar* no formulário de edição e recarregar na visualização do Site.) Nenhuma das opções --Do Módulo-- mostra os itens do menu filho, mas ambas as opções --Do Template Cassiopeia-- mostram.

![Posições do menu Cassiopeia](../../../en/images/templates/cassiopeia-customisation-menu-position.png)

Então, qual diferença faz o **Colapsável**?

- Dropdown Colapsável: Em dispositivos móveis com telas estreitas, o menu colapsa para um ícone de Hambúrguer até ser selecionado. Na seleção, ele se expande para mostrar uma lista vertical.
- Dropdown: O menu sempre aparece como uma lista vertical.

### Mover o Módulo de Menu para a Posição *topbar*

No formulário de edição, aba Módulo, defina a Posição para Barra Superior \[topbar\] e veja o resultado. Há um problema - o menu está posicionado mais à esquerda do que quando estava na posição de menu. Isso acontece porque a posição do menu e a localização do logotipo têm uma classe CSS de *grid-child*, mas a barra superior não tem. Isso pode ser corrigido com uma entrada no arquivo *user.css*, conforme abaixo.

## Personalizar Cassiopeia

E se você não gostar da cor de fundo azul escuro do cabeçalho? 
Suponha que você prefira um tema verde escuro. Para resolver isso, você precisa ter algum conhecimento de CSS. Vá para **Sistema**→**Modelos de Site**→**Detalhes e Arquivos do Cassiopeia** para abrir o formulário do Template: Customizar (Cassiopeia).

A ilustração abaixo mostra dois grupos de pastas. O primeiro grupo consiste nas pastas e arquivos do template que você não deve alterar, mas pode adicionar. Em particular, você pode adicionar arquivos HTML de substituição de template à pasta *html*. O segundo grupo contém os arquivos de mídia do template que você não deve alterar. No entanto, você pode adicionar um arquivo *user.css* à pasta *css* e/ou um arquivo *user.js* à pasta *js*. Isso seria feito se você quisesse fazer algumas alterações simples na aparência do site.

![Cassiopeia editar arquivos](../../../en/images/templates/cassiopeia-customisation-edit-files.png)

Note que numa nova instalação do Joomla não existe um ficheiro ***user.css*** na pasta css. Este ficheiro deve ser criado para que possa sobrescrever estilos previamente definidos. Se o ficheiro ***user.css*** já existir, seleccione-o para abrir o formulário de edição. Caso contrário, crie-o agora:

1. Selecione o botão Novo Ficheiro.
2. Na janela Novo Ficheiro, selecione a pasta css; caso contrário, o novo ficheiro aparecerá no local errado.
3. Digite user (em minúsculas e sem . css) no campo Nome do ficheiro e seleccione . css no campo Tipo de ficheiro.
4. Selecione o botão Criar para criar o ficheiro.

### Cabeçalhos

Como um começo simples, troque a cor dos cabeçalhos para verde escuro. Cabeçalhos são tags no intervalo *h1, h2, h3, h4, h5* e *h6*. No arquivo *user.css* insira a definição de estilo:
```css
    h1, h2, h3, h4, h5, h6 {
      color: darkgreen;
    }
```
Salve e recarregue o site para ver o resultado. O título da Página ou Artigo deve estar em verde escuro. Caso contrário, verifique o que você digitou. A linguagem formal para documentação do Joomla é o inglês britânico, então use "colour" em vez de "color" como no inglês americano. Mas em CSS deve ser "color". A pontuação está correta?

Não é tão óbvio que algumas tags além dos cabeçalhos podem ser estilizadas para parecerem cabeçalhos. Portanto, adicione isto:
```css
    .h1, .h2, .h3, .h4, .h5, .h6 {
      color: darkgreen;
    }
```
Note aqui que o ponto (.) inicial é um seletor de classe, por exemplo, Dummy H1 - então há um ponto no arquivo CSS, mas não no nome da classe.

### Fundo do Cabeçalho

Na aba do navegador contendo o Site, abra as Ferramentas de Desenvolvedor do seu navegador, Firefox neste exemplo, e selecione a tag do cabeçalho.

![Cassiopeia ferramentas de desenvolvedor](../../../en/images/templates/cassiopeia-customisation-developer-tools.png)

Isso mostra os estilos usados. O estilo container-header é onde a cor de fundo e a imagem de fundo são definidas. Eles precisam ser sobrescritos no arquivo *user.css*. Tente isso:
```css
    .container-header {
      background-color: darkgreen;
      background-image: none;
    }
```
### Estilo *topbar*

Lembre-se daquele comentário sobre o menu estar muito à esquerda na barra superior? Isso acontece porque não possui uma largura máxima e margens apropriadas definidas. Coloque isto no arquivo *user.css* para corrigir isso:
```css
    .container-topbar {
      max-width: 1320px;
      margin-left: auto;
      margin-right: auto;
    }
```
Este é o tema verde em funcionamento:

![Cassiopeia tema verde](../../../en/images/templates/cassiopeia-customisation-green-theme.png)

### Acessibilidade

Note que deve haver um contraste suficiente entre as cores de fundo e de primeiro plano para atender aos padrões de acessibilidade da web. Você pode verificar seu contraste no WebAIM Contrast Checker. Verde escuro é \#006400.

## Substituições

A aba Criar Substituições no formulário Modelos: Personalizar (Cassiopeia) mostra a lista de extensões para as quais você pode criar uma substituição. Note os diferentes símbolos: selecione um símbolo de pasta para mostrar uma lista de pastas e arquivos que ela contém; selecione um símbolo de multi-arquivo para criar imediatamente uma substituição para essa extensão; o item criado desaparece da lista - selecione a aba Editor e localize a substituição criada na pasta *html*. Pode haver mais de um arquivo criado - os arquivos criados são copiados da extensão original, prontos para você editar. Para isso, é necessário ter alguns conhecimentos de HTML e PHP!

Esta é a aba Criar Substituições:

![Cassiopeia criar substituições](../../../en/images/templates/cassiopeia-customisation-create-overrides.png)

Se você estiver apenas experimentando e realmente não quiser uma substituição, pode *Fechar* o formulário de edição, Selecionar o botão Gerenciar Pastas na Barra de Ferramentas e selecionar o botão Excluir na parte inferior do formulário modal Gerenciar Pastas.

Substituições são realmente sobre personalizar extensões em vez do modelo Cassiopeia, e essa é outra história.

## Templates Filhos

Se você deseja fazer alterações mais substanciais na aparência do site, pode criar um template filho. Isso copia apenas uma pequena seleção de pastas e arquivos para que você possa alterar ou adicionar, mas continua a usar as pastas e arquivos do template pai. Utilizando templates filhos, é possível ter algumas páginas com uma cor de tema e outras páginas com uma segunda cor de tema. Templates filhos são abordados em outro lugar. Esta é uma ilustração da estrutura de arquivos em um filho de Cassiopeia:

![Arquivos do template filho de Cassiopeia](../../../en/images/templates/cassiopeia-customisation-child-template-files.png)

*Traduzido por openai.com*

