<!-- Filename: J6.x:_Article_Metadata / Display title: Artigo: Editar - Metadados  -->

## Introdução

Metadados são informações sobre uma página web contidas na primeira parte da página, entre as tags `<head>...</head>`. A maioria dessas informações não é vista pelos visitantes do site, mas é usada por motores de busca para fornecer resultados apropriados para as solicitações de pesquisa. Portanto, é do seu interesse usar metadados informativos.

Alguns dos itens de metadados são fornecidos pelo modelo em uso e você não precisa configurá-los. Exemplos comuns:

```html
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta name="generator" content="Joomla! - Open Source Content Management">
```
Existem outras formas de metadados, como os Dados Open Graph usados pelo Facebook e esquemas usados para descrever tipos específicos de página, como Pessoa, Lugar ou Produto. Eles não são abordados aqui.

Os itens de metadados que são frequentemente negligenciados são o **Título** da página, que ocorre dentro das tags `<title>...</title>` no `<head>` da página, e a **Descrição** da página, que ocorre dentro das tags `<meta>`, mas pode estar ausente. Eles são abordados aqui.

## O Título da Página

Um título de artigo é necessário para qualquer nova página. Algumas diretrizes e dicas do Mozilla Developer Network para compor bons títulos:

>* Evite títulos de uma ou duas palavras. Use uma frase descritiva ou um par termo-definição para páginas de glossário ou de referência.
>* Motores de busca normalmente exibem cerca dos primeiros 55–60 caracteres de um título de página. O texto além disso pode ser perdido, então tente não ter títulos mais longos que isso. Se você precisar usar um título mais longo, certifique-se de que as partes importantes venham antes e que nada crítico esteja na parte do título que é provável ser cortada.
>* Não use "aglomerados de palavras-chave". Se o seu título for apenas uma lista de palavras, algoritmos frequentemente reduzem a posição da sua página nos resultados de busca.
>* Tente garantir que seus títulos sejam o mais exclusivo possível dentro do seu próprio site. Títulos duplicados — ou quase duplicados — podem contribuir para resultados de busca imprecisos.

Recomendações adicionais do Google:

>- Especifique um título único para cada página
>- Faça seu título descritivo em relação ao conteúdo da página, e conciso
>- Evite o enchimento de palavras-chave (usar repetidamente palavras semelhantes como "Foobar, foo bar, foobars, foo bars")
>- Evite usar títulos genéricos - cada página deve ter um título único, idealmente atualizado dinamicamente em relação ao conteúdo exibido
>- Marque seus títulos com sua marca, mas faça isso de forma concisa e em relação ao conteúdo sendo servido

Existem várias Ferramentas para Webmasters que podem ser usadas para identificar se há problemas com suas listagens em um motor de busca específico - vale sempre a pena prestar atenção e corrigir quaisquer problemas. Um exemplo:

[Artigo de suporte do Google sobre uso de títulos para suas páginas web](http://support.google.com/webmasters/bin/answer.py?hl=pt-BR&amp;answer=35624)

No Joomla, para uma única página, o título do artigo torna-se o título da página usado no cabeçalho e exibido na aba do navegador. Para uma página composta, como *Artigos em Destaque* ou um *Blog de Categoria*, o Título do item de menu torna-se o título da página. Portanto, você precisa pensar bem na composição de bons títulos descritivos tanto para artigos quanto para itens de menu.

## Descrição da página

O artigo *Meta Description* é um campo na guia *Publishing* do formulário de entrada de dados do artigo:

![A guia de publicação do formulário de edição do artigo](../../../en/images/articles/articles-edit-publishing-tab.png)

Se não houver uma descrição de metadados do artigo, será usada uma descrição de metadados de um único item de menu do artigo, se estiver definida. Se não houver descrição de metadados do item de menu, então será usada a meta descrição global do site, se estiver definida. Caso contrário, o campo de descrição de metadados será omitido.

O Google recomenda o seguinte para garantir que você obtenha o máximo do seu índice de motores de busca:

>- Garanta que cada página tenha meta descrições únicas e relevantes
>- Certifique-se de aplicar metadados para páginas de listagem (por exemplo, blog e layouts de lista) além de artigos individuais - isso é comumente negligenciado em sites Joomla!
>- Inclua informações factuais se relevante (por exemplo, artigos de blog podem incluir o autor, produtos podem incluir o preço ou fabricante)
>- Considere usar metadados gerados automaticamente - mas certifique-se de que sejam relevantes, legíveis e precisos.
>- Faça suas descrições descritivas!

Outra referência:

[Artigo de suporte do Google sobre o uso de metadados](http://support.google.com/webmasters/bin/answer.py?hl=pt&amp;answer=35624)

## Palavras-chave

Era uma vez, os Motores de Busca usavam palavras-chave para ajudar a classificar o conteúdo. Assim, os autores enchiam os metadados de suas palavras-chave com um grande número de termos, na esperança de aumentar seu ranking de SEO. Em resposta, o Google parou de usar palavras-chave para fins de classificação. Procure conselhos na web e você encontrará algumas fontes dizendo para não se preocupar e outras afirmando que elas ainda têm valor.

Palavras-chave não são usadas pelo núcleo do Joomla. Se estiver em dúvida, não se preocupe.

## Robôs

O valor padrão de *Usar Global* não coloca uma meta tag no cabeçalho da página HTML. Outros valores fazem isso. Existe um arquivo `robots.txt` na raiz do site Joomla. Se você deseja controlar os robôs, deve ler este arquivo. Ele contém uma explicação de como usá-lo.

## Autor

Você pode inserir o nome formal do autor para aparecer como metadados.  

## Direitos

Você pode inserir um aviso de direitos autorais para aparecer como metadados.   

## Exemplo de metadados

É assim que os metadados aparecem na visualização de origem do artigo:
Aqui está um exemplo do conteúdo do `<head>` após a conclusão de todos os 
campos de metadados:

```html
    <meta charset="utf-8">
    <meta name="rights" content="Charles Darwin © 1859">
    <meta name="author" content="Charles Darwin">
    <meta name="robots" content="noindex, nofollow">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta name="description" content="Divulgação de A Origem das Espécies.">
    <meta name="generator" content="Joomla! - Gerenciamento de Conteúdo de Código Aberto">
    <title>Divulgação</title>
```
Note que o campo de saída de palavras-chave está ausente.

*Traduzido por openai.com*

