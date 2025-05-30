<!-- Filename: Localhost / Display title: Schema.org - Personalizado -->

## Finalidade

O plugin de esquema personalizado é usado para inserir informações personalizadas no formato bruto JSON-LD. Não é um tipo do Schema Org.

Abra um formulário de edição de artigo e selecione a aba Esquema para escolher um tipo de Esquema e definir os dados para esse tipo. Se um Tipo de Esquema não estiver presente na lista, seu Plugin pode estar desativado. Os valores a serem inseridos em cada campo são, na maioria das vezes, autoexplicativos.

Este é um exemplo de um trecho rico feito à mão:

```json
{
  "@context": "https://schema.org",
  "@type": "WebPage",
  "name": "Your Article Title",
  "description": "A brief description of the article.",
  "timeRequired": "PT5M"
}
```

A propriedade *timeRequired* representa o tempo estimado de leitura no formato de duração ISO 8601. Neste caso, PT5M significa *5 minutos*.

## Captura de Tela de Exemplo

Abaixo está um exemplo de um campo de esquema personalizado em um formulário de edição de artigo.

![A custom schema edit form](../../../en/images/schemas/edit-schema-custom.png)

*Traduzido por openai.com*

