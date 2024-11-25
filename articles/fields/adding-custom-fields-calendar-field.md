<!-- Filename: J3.x:Adding_custom_fields/Calendar_Field / Display title: Campo do Calendário -->

## Finalidade

O campo de Calendário oferece uma caixa de texto para a entrada de uma data. Um ícone ao lado da caixa de texto aciona um seletor de calendário pop-up, que pode ser usado para selecionar uma data a partir de um calendário gráfico.

## Criação de Campos

Os parâmetros comuns de campo são descritos em um artigo separado.

* **Título** Você pode ter vários campos de data em um artigo, por isso é necessário cuidado na definição do título para evitar ambiguidades na saída.
* **Rótulo** Isso é o que é exibido na saída. Se deixado em branco, é definido a partir do conteúdo do campo Título, mas pode ser alterado.
* **Mostrar Hora** Se configurado para *Sim*, a hora é adicionada ao campo de data, ao selecionador de data e à data de saída. **Atenção**: Mesmo que você não especifique a hora na data padrão, a hora será exibida quando a opção *Mostrar hora* estiver ativa.
* **Placeholder** Este campo está na aba Opções. Pode ser definido para um formato de data, como *AAAA-MM-DD*, para lembrar os usuários do formato necessário e/ou um lembrete do que a data representa, como *Data de chegada*.

![criação de campo de calendário](../../../en/images/fields/fields-calendar-edit.png)

**Nota:** Neste exemplo, a inclusão do tipo de campo no Título é apenas para fins de demonstração. Deixe-o de fora em seus próprios títulos de campo.

## Entrada de Dados

O uso do campo de Calendário é simples. Você pode digitar a data no formato requerido ou selecionar uma data usando o seletor de datas. É necessário ter cuidado ao digitar as datas. Um erro na data é corrigido ao salvar para uma nova data. Por exemplo, uma data de 2024-14-02 é corrigida para 2025-02-02.

A captura de tela a seguir mostra uma data de Aquisição:

![campo de entrada de dados de calendário](../../../en/images/fields/fields-calendar-data-entry.png)

Os campos só aparecem em um artigo se forem preenchidos no formulário de entrada de dados do artigo.


## Exibição de Dados

A captura de tela do Site a seguir mostra o campo exibido em um artigo. A opção *Exibição automática* é responsável pela posição do campo e o seu modelo é responsável pelo design do campo.

![exibição do campo de calendário no site](../../../en/images/fields/fields-calendar-site.png)

Os formatos de data são localizados usando strings de linguagem. 

*Traduzido por openai.com*

