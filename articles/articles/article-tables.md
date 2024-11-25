<!-- Filename: J4.x:Article_Tables / Display title: Artigo: Editar - Tabelas  -->

## Sobre Tabelas

Em HTML, tabelas consistem em linhas e colunas de células. Por exemplo, uma tabela simples pode consistir em 4 linhas e 4 colunas, totalizando 16 células. No entanto, as células podem ser combinadas horizontalmente ou verticalmente para criar estruturas de tabelas bastante complexas. As tabelas também possuem características menos óbvias, como cabeçalho, corpo, rodapé e legendas. E mais, tabelas podem ser aninhadas!

Por padrão, as células das tabelas se expandem para acomodar seu conteúdo. A única estilização vem da marcação da tabela: por padrão, células de cabeçalho (`<th>`) possuem texto em negrito e centralizado, enquanto células de dados (`<td>`) têm texto normal e alinhado à esquerda.

O uso de tabelas deve ser reservado para dados estritamente tabulares, como um Horário ou um Calendário, onde é importante manter a estrutura de linhas e colunas. Tabelas não devem ser usadas para layout, como posicionamento de imagens ou texto lado a lado.

Há mais informações nos seguintes artigos:

- [Noções Básicas sobre Tabelas](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Basics)
- [Recursos Avançados e Acessibilidade](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Advanced)
- [Estilizando Tabelas](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Styling_tables)

Tabelas são um dilema! Se você inserir uma tabela usando as ferramentas de tabela do TinyMCE, a tabela ficará boa na tela de edição e no site, mas o layout é alcançado com estilos CSS em linha, que podem ser volumosos e difíceis de editar. Se a tabela for inserida como HTML puro, o resultado não fica bom no editor de texto do TinyMCE, mas pode tirar proveito das classes do Bootstrap e parecer muito melhor no site. Ambos os métodos são abordados abaixo.

## Inserir uma Tabela com Ferramentas do TinyMCE

Para começar com uma tabela:

- Abra o artigo que deseja editar.
- Coloque o cursor em uma linha em branco onde a tabela deve aparecer.
- Selecione o botão *Tabela* na primeira linha de ferramentas do TinyMCE.
- No menu suspenso, selecione Tabela e depois mova o cursor para definir o número de linhas e colunas. As setas do teclado também funcionam para isso.
- Selecione a última célula na matriz 4x4.
- Preencha as células da tabela.

Opções de edição:

- Você pode inserir uma linha acima ou abaixo de uma célula selecionada.
- Você pode inserir uma coluna antes ou depois de uma célula selecionada.
- Você pode excluir uma linha ou coluna.
- Você pode arrastar as bordas das colunas para alterar a largura ou altura das colunas.
- Você pode mesclar células - arraste sobre as células para selecioná-las e depois use Tabela -> Célula -> Mesclar células.
- Você pode selecionar Propriedades da Tabela incluindo largura da borda, estilo e cor e cor de fundo.

Se você usar o botão Alternar Editor, verá que o layout é alcançado com declarações de estilo inline em cada linha e cada célula. Aqui está um pequeno exemplo:

```html
<table style="border-collapse: collapse; width: 100%; height: 96px;" border="1"><colgroup><col style="width: 24.9735%;"><col style="width: 24.9735%;"><col style="width: 24.9735%;"><col style="width: 24.9735%;"></colgroup>
<tbody>
<tr style="height: 24px;">
<td style="height: 24px;">Dia</td>
<td style="height: 24px;">Manhã</td>
<td style="height: 24px;">Tarde</td>
<td style="height: 24px;">Noite</td>
</tr>
<tr style="height: 24px;">
<td style="height: 24px;">Terça-feira</td>
<td style="height: 24px;">Boas-vindas</td>
<td style="height: 24px;">Apresentações</td>
<td style="height: 24px;">Churrasco</td>
</tr>
...
</tbody>
</table>
```

## Inserir uma Tabela como HTML

Se preferir, você pode dispensar os estilos inline e usar as classes do Bootstrap. Você teria que modificar a tabela criada pelas ferramentas de Tabela do TinyMCE ou digitá-la você mesmo. Ficaria assim:

```html
<div class="table-responsive">
<table class="table table-striped table-bordered table-group-divider">
<thead>
<tr>
<th>Dia</th>
<th>Manhã</th>
<th>Tarde</th>
<th>Noite</th>
</tr>
</thead>
<tbody class="table-group-divider">
<tr>
<th>Terça-feira</th>
<td>Boas-vindas</td>
<td>Apresentações</td>
<td>Churrasco</td>
</tr>
...
</tbody>
</table>
</div>
```

Aqui, as classes do Bootstrap têm os seguintes efeitos:

- `table` - aplica vários estilos para dar um layout de tabela padrão agradável.
- `table-striped` - linhas alternadas são escuras e claras.
- `table-bordered` - aplica bordas às células.
- `table-group-divider` - aplica uma linha em negrito acima de um elemento.
- `table-responsive` - permite que uma tabela larga role da direita para a esquerda.

A seguinte captura de tela do site mostra uma tabela para um programa de conferência com os estilos inline padrão do TinyMCE e uma tabela similar com estilos do Bootstrap:

![Exemplo de tabelas](../../../en/images/articles/articles-site-tables.png)

Veja a documentação do Bootstrap sobre [Tabelas](https://getbootstrap.com/docs/5.3/content/tables/) para mais opções.

## Consideração

Você pode colocar o HTML para uma tabela em um módulo personalizado e incluir esse módulo no artigo. No artigo, ele aparece como `{loadmoduleid xx}` onde xx é o ID do módulo.

*Traduzido por openai.com*

