<!-- Filename: J3.x:Adding_custom_fields/Textarea_Field / Display title: Campo de Área de Texto -->

## Finalidade

O Campo de Área de Texto (Textarea) é uma área para entrada de texto em várias linhas. Um textarea simples não possui um Editor WYSIWYG.

### Opções

As opções especiais dentro deste campo são:

- **Linhas** A altura da área de texto visível em linhas. Se omitido, a altura é determinada pelo navegador. O valor não limita o número de linhas que podem ser inseridas. As linhas são ativas no backend ao criar um artigo, contato ou um componente de terceiros que suporte campos personalizados. Esta opção não tem impacto no tamanho do campo no frontend.
- **Colunas** A largura da área de texto visível em caracteres. Se omitido, a largura é determinada pelo navegador. O valor não limita o número de caracteres que podem ser inseridos. As colunas são ativas no backend ao criar um artigo, contato ou um componente de terceiros que suporte campos personalizados. Esta opção não tem impacto no tamanho do campo no frontend.
- **Comprimento Máximo** O número máximo de caracteres que pode ser inserido.
- **Filtro** Permite que o sistema salve determinadas tags HTML ou dados brutos.

![criação do campo de área de texto](../../../en/images/fields/fields-textarea-edit.png)

**Nota:** Neste exemplo, a inclusão do tipo de campo no Título é apenas para fins de demonstração. Deixe de fora em seus próprios títulos de campo.

## Entrada de Dados

Simples: insira o texto a ser exibido.

![entrada de dados do campo de área de texto](../../../en/images/fields/fields-textarea-data-entry.png)

## Exibição de Dados

A captura de tela a seguir do Site mostra o campo exibido em um artigo. A opção *Exibição automática* é responsável pela posição do campo, e seu modelo é responsável pelo design do campo.

![exibição do campo de área de texto no site](../../../en/images/fields/fields-textarea-site.png)

O rótulo do campo inicia um único bloco de texto, a menos que você tenha inserido tags HTML, como `<p>...</p>`.

