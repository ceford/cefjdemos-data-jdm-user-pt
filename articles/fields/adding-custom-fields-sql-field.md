<!-- Filename: J3.x:Adding_custom_fields/Sql_Field / Display title: Campo SQL -->

## Finalidade

O campo SQL fornece uma lista suspensa de entradas obtidas a partir de uma consulta ao banco de dados. Para usar este campo, é necessário saber como construir uma consulta e testá-la no phpMyAdmin.

## Criação de Campo

As opções especiais neste campo são:

- **Múltiplo** Permitir que múltiplos valores sejam selecionados. Se configurado como *Sim*, a lista exibirá 4 itens. Caso contrário, exibirá 1 item. Em ambos os casos, há uma lista longa para rolar ao fazer seleções - se ativada.
- **Consulta** A consulta SQL que fornecerá os dados para a lista suspensa. A consulta deve retornar duas colunas; uma chamada 'value', que conterá os valores dos itens da lista; e a outra chamada 'text', que contém o texto na lista suspensa.

Neste exemplo, é utilizada uma tabela contendo uma lista de nomes de países. Esta é a consulta:
```
SELECT `id` AS value, `title` AS text
FROM `#__countrybase_countries`
WHERE `state` = 1
ORDER BY `title` ASC
```
![Criação de Campo SQL](../../../en/images/fields/fields-sql-edit.png)

**Nota:** Neste exemplo, a inclusão do tipo de campo no Título é apenas para fins de demonstração. Deixe de fora nos títulos dos seus próprios campos.


## Inserção de Dados

Simples - selecione da lista.

![Entrada de dados do campo SQL](../../../en/images/fields/fields-sql-data-entry.png)

## Exibição de Dados

A captura de tela do site a seguir mostra o campo exibido em um artigo. A opção *Exibição automática* é responsável pela posição do campo e seu modelo é responsável pelo design do campo.

![Exibição do campo SQL no site](../../../en/images/fields/fields-sql-site.png)

A saída é um único item ou uma lista de itens separada por vírgula (nomes de países) seguindo o rótulo do campo (País de Origem).

*Traduzido por openai.com*

