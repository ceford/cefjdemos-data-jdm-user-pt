<!-- Filename: J4.x:Fields_and_Field_Groups / Display title: Campos e Grupos de Campos   -->

## Introdução

Campos são usados para exibir atributos adicionais de Artigos, Contatos ou Usuários. Os dados são inseridos em um formulário de Edição do Administrador e exibidos no Site. Um exemplo:

Suponha que você escreva artigos sobre aspectos da natureza, às vezes Flores, às vezes Animais. Um campo que você pode querer registrar e exibir para ambos é o Nome Científico, que requer um campo de texto. Outro pode ser o Habitat: Floresta, Lagoa, Prado e assim por diante, que requer uma lista suspensa. Para flores, você pode querer registrar a Temporada de Floração usando 4 caixas de seleção, uma para cada estação, ou 12 caixas de seleção, uma para cada mês.

Campos vazios no formulário de entrada não são exibidos na saída do Site, então você pode manter todos os campos em uma lista longa. No entanto, geralmente é melhor usar categorias para seus Artigos, digamos Flores e Animais. Campos podem ser atribuídos a mais de uma Categoria. Assim, campos como Nome Científico e Habitat seriam atribuídos a ambas, mas Temporada de Floração seria atribuído apenas à categoria de Flores.

Se um campo não for atribuído a um grupo, ele aparecerá no formulário de Edição em uma aba de Campos. Se um campo for atribuído a um grupo, ele aparecerá em uma aba com esse nome. Assim, para o grupo de Flores, parece apropriado criar um grupo de campos chamado Dados de Flores (ou apenas Flores, embora usar o mesmo nome para coisas diferentes seja confuso). E para os outros campos comuns, você poderia usar um grupo chamado Natureza.

## Um Exemplo Trabalhado - Notas sobre a Natureza

Para artigos sobre a Natureza, a categoria do artigo e as subcategorias para cada ramo do mundo vivo podem aparecer conforme o exemplo a seguir:

![Categorias de artigos sobre natureza](../../../en/images/fields/fields-articles-categories-list.png)

Algumas características óbvias da Natureza a serem observadas:

- A categoria Natureza é para artigos que tratam da natureza em geral, em vez de tipos específicos de plantas ou animais.
- As subcategorias são para artigos mais específicos e podem precisar de suas próprias subcategorias.
- Todos os seres vivos têm nomes comuns e nomes latinos.
- Flores e Árvores têm uma Estação de Florescimento, Altura e Largura, mas Pássaros e Mamíferos não.
- Pássaros têm envergadura das asas e comprimento, enquanto Mamíferos têm altura e comprimento.
- A cor pode ser constante ou variada.

O ponto aqui é que pode ser necessário configurar Campos ou Grupos de Campos para características comuns, como Nome Latino, e Grupos de Campos separados para cada categoria de natureza.

## Grupos de Campos

Criar Grupos de Campos para Artigos é muito simples:

- Selecione **Conteúdo → Grupos de Campos** no menu do Administrador.
- Selecione o botão **Novo** na barra de ferramentas.
- Insira um **Título** apropriado.
- Insira uma **Descrição**. Esta aparecerá abaixo do campo no formulário de edição do artigo quando *Alternar Ajuda Inline* estiver selecionado.
- Selecione **Salvar & Fechar** na barra de ferramentas.

![Lista de grupos de campos de conteúdo](../../../en/images/fields/fields-field-groups-list.png)

### Ordenação

Na entrada de dados do artigo, os grupos de campos aparecerão na ordem vista nesta lista. Arraste e solte os itens para alterar a ordem.

## Campos

Para criar um novo Campo de Artigo, selecione **Conteúdo → Campos** no menu do Administrador e preencha o formulário. Alguns exemplos estão ilustrados abaixo.

### Texto - Nome em Latim

Note que na captura de tela abaixo, este campo foi atribuído ao Grupo de Campos Natureza e à categoria Natureza. Isso garante que ele sempre apareça em artigos na categoria Natureza e em qualquer subcategoria.

![Campo de texto - nome em latim no grupo natureza](../../../en/images/fields/fields-latin-name.png)

### Caixas de Seleção - Estação de Floração

As caixas de seleção aparecem no formulário de edição do artigo para você marcar a estação de floração. Na exibição do artigo, apenas aquelas marcadas serão listadas. Por exemplo, se você marcar Primavera e Verão, a saída mostrará Estação de Floração: Primavera, Verão.

Note que nesta captura de tela o Campo foi atribuído ao grupo Flores e à Categoria Flores. Isso deve garantir que o campo esteja presente apenas em artigos sobre flores.

![Campo de caixa de seleção - estação de floração](../../../en/images/fields/fields-flowering-season.png)

### Cor - Color

Para causar confusão, o nome do tipo de campo é Color (ortografia americana), mas o rótulo na documentação é Colour (ortografia britânica).

![Campo de cor](../../../en/images/fields/fields-colour.png)

O campo Cor é atribuído ao grupo de campos Natureza e à categoria Natureza, pois não é exclusivo para flores.

### Inteiro - Resistência

A resistência de uma planta pode ser representada como um inteiro de 1 a 7. Não há campo para um número real, então o comprimento e a largura podem ser inteiros com uma escala (cm ou m ou ft) incluída no rótulo. Há configurações de *Prefixo* e *Sufixo* na guia *Opções*. Se não houver limite superior óbvio, deixe o campo *Último:* vazio.

![Campo de resistência](../../../en/images/fields/fields-hardiness.png)

A resistência RHS é uma propriedade geralmente aplicada a flores!

Há um problema com o campo de inteiro. Ele sempre tem um valor e por isso sempre aparece na saída. Você pode contornar esse problema com uma substituição de template para *Plugins / Inteiro*. Por exemplo, você poderia usar um valor acima ou abaixo dos limites esperados para omitir o campo da saída.

## Formulário de Edição de Artigo

Quando um formulário de Novo Artigo é aberto, a Categoria padrão é "Sem categoria" e as abas do formulário não incluem Campos e Flores. Selecione a categoria "Flores" e o formulário será recarregado com essas abas presentes.

### Aba Natureza

![Aba de natureza do artigo Bluebell](../../../en/images/fields/field-article-bluebell-nature-tab.png)

- **Nome Latim** Este é um campo de entrada de texto, então basta digitar o nome latino de qualquer forma de vida que o artigo aborda. No entanto, a categoria Natureza abrange a vida em geral, bem como animais ou plantas específicas. Portanto, este campo não é *obrigatório*.
- **Cor** O campo de seleção de cor pode aceitar a entrada de teclado de um valor de cor hexadecimal ou uma cor selecionada na ferramenta de escolha de cores. O número hexadecimal é xrrggbb onde rr são valores de vermelho, gg são valores de verde e bb são valores de azul. Na saída, o site exibe o valor hexadecimal, o que não é muito útil!

### Aba Flores

![Aba de natureza do artigo Bluebell](../../../en/images/fields/field-article-bluebell-flowers-tab.png)

- **Estação de Floração** O campo de caixa de seleção - os bluebells são flores bem conhecidas da primavera, então a seleção de uma caixa de seleção é apropriada.
- **Resistência** O campo de número inteiro. Há um problema aqui - não há método disponível para deixar este campo vazio. Assim, ele sempre está presente na saída, mesmo para artigos mais gerais sobre flores, onde não é apropriado. Existe uma solução alternativa que envolve uma sobreposição de modelo.

## Resultado do Site

Dê uma olhada no resultado visto em seu site. Neste exemplo, foi criado um item de menu para um único artigo:

![Visualização do artigo Bluebell no site](../../../en/images/fields/field-article-bluebell-site.png)

### A Cor em Hexadecimal

A exibição padrão dos dados é o valor da cor em hexadecimal, que não é muito útil. A solução fácil é criar uma substituição de modelo para o plugin de campos / cor, que é o que está mostrado na captura de tela acima.

Basta substituir esta linha:
```
echo htmlentities($value);
```
por estas linhas:
```
if (is_array($value)) {
  $list = [];
  foreach ($value as $v) {
    $x = htmlentities($v);
    $list[] = '<span class="ps-5 pe-5" style="background-color: ' . $x . ';">&nbsp</span> ' . $x;
    echo implode(', ', $list);
  }
} else {
    $x = htmlentities($value);
    echo '<span class="ps-5 pe-5" style="background-color: ' . $x . ';">&nbsp</span> ' . $x;
}
```
E o valor hexadecimal será precedido por uma amostra com a cor de fundo do valor.

*Traduzido por openai.com*

