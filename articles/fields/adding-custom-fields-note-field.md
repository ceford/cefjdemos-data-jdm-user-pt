<!--
{
    "source": "https://docs.joomla.org/localhost",
    "title": "Campo de Nota",
    "description": " ",
    "author": ""
}
-->

## Finalidade

O tipo de campo de formulário de nota possibilita criar títulos, textos, descrições e até caixas de alerta. Ele também permite organizar as configurações das extensões, separando-as com títulos úteis. Ou adicionar descrições para determinadas configurações (sem precisar depender das dicas de ferramentas). Ou adicionar qualquer outro texto desejado.

## Criação do Campo

### Aba Geral

![Criação do campo de nota](../../../en/images/fields/adding-custom-fields-note-field/01-fields-note-edit.png)

- **Tipo** Número, que não pode ser alterado após a seleção.
- **Nome** O nome exclusivo do campo.
- **Rótulo** Um rótulo traduzível para o campo.
- **Descrição** Uma descrição de campo traduzível opcional.
- **Usar somente em subformulário** *Sim* ou *Não*.
- **Título da Nota** Isso será exibido no formulário de entrada de dados.
- **Conteúdo da Nota** O texto da nota.
- **Classe da Nota** Quaisquer classes existentes ou novas. O padrão *alert alert-info* produz uma caixa de alerta do Boostrap.
- **Tag do Título** Selecione na lista de níveis de título.
- **Mostrar botão Fechar**  Este campo controla a exibição de um "x" para fechar a nota. Ele recebe o valor 'true' (para alertas) ou o valor de data-dismiss do ícone de fechamento do Bootstrap.

### Aba Opções

- **Exibição automática** Se e onde o campo deve ser exibido:
    - **Após o título**
    - **Antes do conteúdo de exibição**
    - **Após o conteúdo de exibição**
    - **Não exibir automaticamente**
- **Layout** uma lista de layouts disponíveis.
- **Exibir no frontend** *Sim* ou *Não*.

## Entrada de Dados

No formulário de entrada de dados, o campo de nota aparece entre os outros campos como texto estilizado de acordo com as opções de estilo definidas no campo. Ele pode conter instruções ou informações.

![Entrada de dados do campo Número](../../../en/images/fields/adding-custom-fields-note-field/02-fields-note-data-entry.png)

**Dica:** Use o mecanismo de ordenação de campos para ordenar a posição da Nota entre os outros campos. Você pode ter vários campos de Nota diferentes para fornecer estrutura e informações aos seus campos.

## Exibição de Dados

Se *Exibir no frontend* estiver definido como *Sim*, o campo de Nota aparecerá entre os outros campos no frontend. Ele pode conter algumas informações gerais comuns a um grupo de artigos.

*Traduzido por openai.com*