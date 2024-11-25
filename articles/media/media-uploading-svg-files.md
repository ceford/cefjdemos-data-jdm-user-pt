<!-- Filename: J4.x:Media:_Uploading_SVG_files / Display title: Fazendo upload de arquivos SVG   -->

## Introdução

Arquivos SVG (Scalable Vector Graphics) não são suportados no Joomla por
padrão. Algumas etapas são necessárias para permitir que o componente de Mídia os suporte.

## Opções de Mídia

No menu do Administrador:

* Selecione **Mídia** no *Painel Inicial* ou no menu *Conteúdo*.
* Selecione o botão **Opções** na *Barra de Ferramentas* de Mídia.

Existem 3 campos que precisam ser atualizados, todos são listas separadas por vírgulas, então você só precisa adicionar uma vírgula e o valor apropriado:

- Em *Extensões Permitidas*, adicione no final da lista já disponível: `,svg`.
- Em *Extensões de Imagem Legais*, adicione no final da lista já disponível: `,svg`.
- Em *Tipos MIME Legais*, adicione no final da lista já disponível: `,image/svg+xml`.
- **Salvar & Fechar**

A partir de agora, você deverá ser capaz de fazer upload de arquivos SVG no Gerenciador de Mídia. A menos que...

## O Joomla ainda impede o upload de arquivos SVG?

SVG não é um formato de imagem raster (como arquivos PNG, que contêm pixels), ele é escrito em XML (Linguagem de Marcação Extensível). É baseado em texto, utilizável diretamente dentro do DOM (Modelo de Objeto de Documento), CSS pode mudar propriedades e JavaScript pode adicionar interatividade.

Como tal, arquivos SVG são suscetíveis a todos os padrões de ataque relacionados a XML:

- Cross-site scripting – ou XSS (através de sua tag `<script>` e eventos).
- Injeções de HTML (através do elemento `<foreignObject>` – foreignObject permite que você inclua elementos de um namespace XML diferente).
- Negação de serviço (se o elemento `<xlink:href>` for mal utilizado).

A partir do Joomla 4.1, uma ferramenta de sanitização é usada para verificar o conteúdo de qualquer arquivo SVG enviado através do Gerenciador de Mídia. As regras são rigorosas e garantem que os arquivos não prejudiquem o site. Portanto, alguns arquivos podem precisar ser **limpos** manualmente (lembre-se de que arquivos SVG são arquivos de texto e podem ser editados em um editor de texto) ou através de uma ferramenta externa antes de serem enviados com sucesso.

**Dica:** estes sites limparão arquivos SVG criados no *Inkscape*:

* [SVG Sanitizer Test](https://svg.enshrined.co.uk/)
* [SVG Cleaner & Optimizer](https://iconly.io/tools/svg-cleaner)
* [SVGminify.com](https://www.svgminify.com/)

*Traduzido por openai.com*

