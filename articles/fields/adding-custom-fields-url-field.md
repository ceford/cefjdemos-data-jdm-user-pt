<!-- Filename: J3.x:Adding_custom_fields/Url_Field / Display title: Campo de URL -->

## Propósito

O campo de URL fornece um link para outro documento. Se você preferir usar uma tag de âncora, como `<a href="url">Texto Explicativo</a>`, use um campo de texto.

## Criação de Campo

As opções especiais dentro deste campo são:

- **Esquemas** Os esquemas permitidos são HTTP, HTTPS, FTP, FTPS, MAILTO, URL e
  FILE. Todos são permitidos por padrão. Qualquer um selecionado na lista é
  permitido enquanto aqueles não selecionados são desativados. Isso é evidente
  durante a entrada de dados: quando um tipo não selecionado é inserido, por
  exemplo http://, há uma mensagem de erro e o campo não é salvo.
- **Relativo** Use esta opção para determinar se URLs relativas são permitidas
  ou não.
- **Mostrar URL** Se configurado como *Não*, na exibição do Artigo o URL é
  substituído pelas palavras *Visitar Site*.

![criação de campo url](../../../en/images/fields/fields-url-edit.png)

**Nota:** Neste exemplo, a inclusão do tipo de campo no Título é apenas para
fins de demonstração. Deixe-o de fora nos títulos de campo próprios.

## Entrada de Dados

Simples: basta inserir uma URL de destino.

![entrada de dados do campo de URL](../../../en/images/fields/fields-url-data-entry.png)

## Exibição de Dados

A captura de tela do Site a seguir mostra o campo exibido em um artigo. A opção *Exibição automática* é responsável pela posição do campo e o seu template é responsável pelo design do campo.

![exibição do campo de URL do site](../../../en/images/fields/fields-url-site.png)

A URL segue o Rótulo do campo.

