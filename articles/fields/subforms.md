<!-- Filename: jdocmanual?manual=user&heading=fields&filename=subform.md / Display title: Campo do Subformulário -->

## Finalidade

O Campo de Subformulário permite que uma seleção de campos seja agrupada em uma lista repetível.

## Criação de Campos

Primeiro, crie os campos necessários no subformulário. No exemplo descrito aqui, há um campo de Calendário (Data de Aquisição), um campo de Texto (Preço) e um campo de Cor (Cor da Flor) para serem usados em uma lista de vários espécimes.

**Erro:** Há um bug no código do campo de Calendário que leva a um erro fatal ao salvar um artigo pela segunda vez. Para evitar esse problema, defina o valor *Mostrar Hora* do campo Calendário como *Sim*.

Opções especiais para este campo:

- **Título** e **Rótulo** Neste exemplo, estes estão definidos como *Espécimes*.
- **Campos** Adicione os campos necessários no subformulário um por um. Cada linha possui uma lista suspensa de campos disponíveis e uma alternância Sim/Não para Renderizar Valores. A ordem dos itens pode ser alterada com o ícone de arrastar.

![Criação de subformulário](../../../en/images/fields/fields-subform-edit.png)

**Nota:** Neste exemplo, a inclusão do tipo de campo no Título é apenas para fins de demonstração. Deixe-o de fora nos títulos dos seus próprios campos.  

## Entrada de Dados

No formulário de entrada de dados, você precisa adicionar linhas para cada amostra. Cada linha contém um campo de Calendário, um campo de Texto e um campo de Cor.

![Subformulário de entrada de dados](../../../en/images/fields/fields-subform-data-entry.png)

## Exibição de Dados

No Artigo, o subformulário intitulado Especímenes tem uma linha para cada espécime. Procure o item **Especímenes** nesta captura de tela:

![exibição do subformulário no site](../../../en/images/fields/fields-subform-site.png)

*Traduzido por openai.com*

