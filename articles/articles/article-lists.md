<!-- Filename: J4.x:Article_Lists / Display title: Artigo: Editar - Listas -->

## Tipos de Listas

HTML possui três tipos de listas:

- Listas não ordenadas são frequentemente estilizadas com uma indentação e um marcador,
  como esta lista.
- Listas ordenadas são semelhantes, mas marcadas com números.
- Listas de definições consistem em Títulos e Definições.

Os pontos de marcador e os números são aplicados pelo navegador a partir de uma seleção de estilos. O usuário não deve inserir nenhum texto de marcador ou número, pois isso será tratado como parte da lista. O editor TinyMCE possui ícones para aplicar estilos comuns de marcadores e tipos de números. Listas de definições são mais complicadas e precisam ser feitas manualmente.

As listas podem conter outras listas em qualquer nível, embora listas muito indentadas se tornem difíceis de ler, por isso é melhor se limitar a um ou dois níveis.

## Captura de Tela

A captura de tela a seguir mostra uma lista não ordenada com dois níveis de indentação. Ela também exibe o conjunto completo de ferramentas, que é aberto ao selecionar o botão de reticências (...) no final da primeira linha de ícones de ferramentas.

![Listas não ordenadas aninhadas](../../../en/images/articles/articles-edit-lists.png)

Esta captura de tela será usada para explicar como a lista com marcadores foi criada usando as ferramentas *Lista com marcadores* e *Aumentar indentação* ou *Diminuir indentação*:

## Estilos de Lista

### Listas com marcadores

Três estilos estão disponíveis:

- Um círculo preenchido é o padrão.
- Um círculo aberto.
- Um quadrado preenchido.

A seta para baixo à direita do ícone de lista com marcadores abre um pequeno painel
permitindo a seleção do estilo preferido para um item da lista selecionado:

![Ferramentas de manipulação de lista com marcadores](../../../en/images/articles/articles-edit-list-bullets.png)

O ícone de lista funciona como um interruptor. Se o cursor estiver em um parágrafo e um marcador
for selecionado, o parágrafo se torna um item de lista. Se o marcador for selecionado novamente,
o item da lista volta a ser um parágrafo.

Se dois ou mais parágrafos forem selecionados e um ícone de lista for selecionado, cada um dos
parágrafos se torna um item de lista. Para criar uma lista com recuo, selecione a ferramenta
*Aumentar recuo* à direita das ferramentas de Lista. Por padrão, o item da lista com recuo
adotará o próximo estilo de lista.

Então, para explicar como criar as listas com recuo na captura de tela:

- Digite cada um dos termos como parágrafos de uma única palavra.
- Selecione todos os parágrafos para serem transformados em uma lista com marcadores.
- Selecione o ícone de *Lista com marcadores*.
- Selecione o primeiro grupo de termos para serem inseridos.
- Selecione o ícone de *Aumentar recuo*.
- Selecione o segundo grupo de termos para serem inseridos.
- Selecione o ícone de *Aumentar recuo*.

### Listas numeradas

Seis estilos estão disponíveis:

- Números: 1, 2, 3 ...
- Letras: a, b, c ...
- Caracteres gregos: &alpha;, &beta;, &gamma; ...
- Numerais romanos em minúsculas: i, ii, iii ...
- Letras maiúsculas: A, B, C ...
- Numerais romanos em maiúsculas: I, II, III ...

![Ferramentas de manipulação de lista numerada](../../../en/images/articles/articles-edit-list-numbers.png)

As listas numeradas funcionam de maneira um pouco diferente. Quando um item de lista é recuado, ele
assume o primeiro valor numérico e os números do resto da lista sobem para
que a lista esteja sempre em ordem numérica correta.

### Listas mistas

O sistema de numeração pode ser alterado em cada nível. Por exemplo, você pode definir 
o primeiro nível para usar valores numéricos e o segundo nível para usar marcadores, ou
caracteres gregos, ou qualquer outra coisa.

Provavelmente é melhor experimentar com listas para ver como elas podem ser manipuladas.

## Listas de definições

Listas de definições consistem em um *Título de definição* e uma ou mais *Descrições de definição* seguidas pelo próximo *Título de definição* e sua *Descrição*. Elas seriam boas para um *Glossário* ou qualquer tipo de conjunto de pares Chave/Valor. Para criar uma lista de definições:

- Selecione o botão *Alternar Editor* para ver a marcação do artigo em HTML.
- Digite a marcação da Lista de Definições. Aqui está um exemplo:
```html
<dl>
<dt>Anfíbio</dt>
<dd>Vertebrado de sangue frio que põe ovos na água e tem uma fase aquática larval.</dd>
<dt>Réptil</dt>
<dd>Vertebrado de sangue frio que põe ovos em terra.</dd>
</dl>
```
Salve e veja o resultado na Pré-visualização.

*Traduzido por openai.com*

