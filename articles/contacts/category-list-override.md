<!--
{
<<<<<<< HEAD
  "source": "https://docs.joomla.org/category-list-override.md",
  "title": "Substituir Lista de Categorias ",
  "description": "", 
  "author": ""
=======
    "source": "https://docs.joomla.org/category-list-override.md",
    "title": "Substitui\u00e7\u00e3o da lista de categorias",
    "description": "Saiba como criar uma substitui\u00e7\u00e3o de template para melhorar o layout de uma lista de contatos em uma categoria ",
    "author": ""
>>>>>>> newbranch
}
-->

## A lista de contatos em uma categoria

O layout padrão dos contatos em uma categoria é controlado por um template no 
código do componente com_contacts. O layout padrão é semelhante a este:

![comitê cultural usando o layout e o estilo padrão](../../../en/images/contacts/category-list-override/01-contacts-culture-committee.png)

Pode ser uma opinião pessoal, mas, para mim, o layout padrão dos contatos não é muito 
satisfatório. Meus problemas:

* As imagens originais dos retratos tinham 500 pixels de largura e eram muito dominantes.
* O nome do contato não recebe ênfase suficiente.
* A lista de marcadores com os dados pessoais não tem um título e parece isolada.
* A função do indivíduo não tem um título.
* Os campos de endereço e código postal estão ausentes.
* Os dados de localização estão incompletos.
* Os dados de cada contato são dispostos em uma tabela e ficam bastante apertados em telas estreitas.

Então, como corrigir isso de acordo com a minha preferência? Minha solução é criar uma substituição de template 
e adicionar alguns estilos personalizados. Veja o resultado:

![comitê empresarial usando uma substituição de template e estilos personalizados](../../../en/images/contacts/category-list-override/02-contacts-business-committee.png)

<<<<<<< HEAD
A imagem possui o estilo CSS `contact-thumbnail img-thumbnail`. As Ferramentas de Desenvolvedor do navegador indicam que img-thumbnail está configurado para `max-width: 100%;`, mas contact-thumbnail não está sendo utilizado. A única ocorrência deste estilo em todo o site é neste local, portanto, parece seguro definir uma substituição em user.css para restringir a largura da imagem. E o tamanho da fonte do nome de contato pode ser aumentado usando sua tag `a` envolvente:

```css
.contact-thumbnail {
  max-width: 200px;
  margin-right: 1rem;
}
a:has(.contact-thumbnail) {
  font-weight: 700;
  font-size: larger;
}
```

A lista de marcadores dos campos personalizados pode ser melhorada removendo os marcadores e o preenchimento, selecionando apenas listas de marcadores que aparecem dentro de uma tag que possui a classe contactList:
```css
#contactList ul {
  list-style-type: none;
  padding-left: 0;
}
```

![comitê de negócios estilizado](../../../en/images/contacts/category-list-override/01-contact-business-committee-styled.png)

Isso é o máximo que pode ser feito com estilização. Melhor, mas ainda não bom o suficiente. Adicionar mais itens e mudar o layout exigirá uma sobreposição de layout.

## Sobrescrever Layout do Template
=======
## Substituição do layout do template
>>>>>>> newbranch

A pasta com_contact/tmpl/category contém três arquivos PHP: default.php,
default_children.php e default_items.php. O último da lista contém
o layout em tabela da lista.

Os arquivos de substituição são criados em Sistema / Templates do site / Cassiopeia
Detalhes e arquivos / Criar substituições. Selecione com_contact e depois category.
A pasta html passa então a conter com_contact/category com os três arquivos de template
mencionados acima. 

### Alterar o arquivo default.php para mydefault.php

O arquivo `default.php` contém uma linha que especifica qual layout usar para 
cada registro individual. Selecione este arquivo para edição e **renomeie-o** para 
`mydefault.php` (ou use qualquer prefixo de sua preferência em vez de `my`). Não use 
um sublinhado no nome do arquivo!

Quando você acessar posteriormente o formulário Contatos / Categoria / Editar, o campo
Layout da aba Opções permitirá escolher entre o layout do componente e o layout
da sua substituição. Ele será semelhante a este:

```
---From Global Options---
  Use Global
---From Component---
  Default
---From cassiopeia Template---
  mydefault
```

### Editar o arquivo mydefault.php

A linha 20 de `mydefault.php` contém `$this->subtemplatename = 'items';`.
Altere `items` para `myitems`, de modo que as linhas 18 a 23 fiquem assim:

```html
<div class="com-contact-category">
    <?php
        $this->subtemplatename = 'myitems';
        echo LayoutHelper::render('joomla.content.category_default', $this);
    ?>
</div>
```

### Alterar o arquivo default_items.php para mydefault_myitems.php

O arquivo `default_items.php` contém o layout de cada contato. Ele precisa ser
renomeado para preservar a opção de usar o layout original. A primeira parte do nome
não é importante. É a parte `myitems`, mencionada no arquivo
`mydefault.php`, que é usada para o layout.

### Editar o arquivo mydefault_myitems.php

A seção `<table>...</table>` deste arquivo abrange as linhas 85 a 204. Para a
substituição do layout, substituí a marcação da tabela pela seguinte marcação de
grade do Bootstrap. Em telas estreitas, as três colunas são empilhadas. Em telas
com mais de 768 pixels de largura, as colunas ficam lado a lado. A marcação revisada
moveu os campos personalizados para baixo do nome do contato.

```
<div class="container-fluid text-center border border-2">
<?php $nrows = 0; foreach ($this->items as $i => $item) : ?>
    <?php if ($item->published !== 1 ||
        (!empty($item->publish_up) && strtotime($item->publish_up) > strtotime(Factory::getDate())) ||
        (!empty($item->publish_down) && strtotime($item->publish_down) < strtotime(Factory::getDate()))) { continue; } ?>
        <div class="row cat-list-row<?php echo $nrows % 2; $nrows += 1; ?> align-items-center">
            <div class="col-12 col-md-3">
                <?php if ($this->params->get('show_image_heading')) : ?>
                    <?php if ($item->image) : ?>
                        <?php echo LayoutHelper::render(
                            'joomla.html.image',
                            [
                                'src'   => $item->image,
                                'alt'   => 'official image of ' . $item->name,
                                'class' => 'contact-thumbnail img-thumbnail',
                            ]
                        ); ?>
                    <?php endif; ?>
                <?php endif; ?>
            </div>
            <div class="col-12 col-md-3">
                <div class="parliament-committee-fields">
                <a href="<?php echo Route::_(RouteHelper::getContactRoute($item->slug, $item->catid, $item->language)); ?>">
                    <span class="fs-2"><?php echo $this->escape($item->name); ?></span>
                </a>
                    <?php echo $item->event->beforeDisplayContent; ?>
                </div>
            </div>
            <div class="col-12 col-md-6 text-start">
                <?php if ($this->params->get('show_position_headings') && !empty($item->con_position)) : ?>
                    <strong><?php echo Text::_('COM_CONTACT_FIELD_INFORMATION_POSITION_LABEL'); ?></strong><br>
                    <?php echo $item->con_position; ?><br>
                <?php endif; ?>
                <?php if ($this->params->get('show_suburb_headings')) : ?>
                    <?php $location = []; ?>
                    <?php if (!empty($item->address)) : ?>
                        <?php $location[] = $item->address; ?>
                    <?php endif; ?>
                    <?php if (!empty($item->suburb)) : ?>
                        <?php $location[] = $item->suburb; ?>
                    <?php endif; ?>
                    <?php if (!empty($item->state)) : ?>
                        <?php $location[] = $item->state; ?>
                    <?php endif; ?>
                    <?php if (!empty($item->postcode)) : ?>
                        <?php $location[] = $item->postcode; ?>
                    <?php endif; ?>
                        <strong><?php echo Text::_('COM_CONTACT_FIELD_INFORMATION_ADDRESS_LABEL'); ?></strong><br>
                    <?php echo implode("<br>\n", $location); ?><br>
                <?php endif; ?>
                <?php if (!empty($item->misc)) : ?>
                    <?php echo $item->misc; ?>
                <?php endif; ?>
            </div>
        </div>
    <?php endforeach; ?>
</div>
```

## Estilos

As classes de estilo do Bootstrap podem ser definidas no arquivo `mydefault_myitems.php`.
Por exemplo, `<span class="fs-2">...</span>` é usado para aumentar o tamanho da fonte do nome
do contato. Outros estilos podem ser adicionados ao arquivo `user.css`, por
exemplo, a personalização de listas com marcadores que aparecem apenas dentro de uma tag
que tenha uma classe `contactList`.

Veja os estilos inseridos no arquivo user.css para obter o layout
do Comitê Empresarial ilustrado acima.

```
.contact-thumbnail {
  max-width: 200px;
  margin-right: 1rem;
}
a:has(.contact-thumbnail) {
  font-weight: 700;
  font-size: larger;
}
#contactList ul {
  list-style-type: none;
  padding-left: 0;
}
.cat-list-row0 {
  background-color: #efefef;
}
.cat-list-row0:hover, .cat-list-row1:hover  {
  background-color: #ddd;
}
div.parliament-committee-fields {
  text-align: left;
  margin-top: 1rem;
}
div.parliament-committee-fields ul.fields-container {
  list-style-type: none;
  padding-left: 0;
}
div.parliament-committee-fields ul.fields-container span.field-label {
  font-weight: 700;
}
```

<<<<<<< HEAD
### Resultado

![gridded business committee](../../../en/images/contacts/category-list-override/02-contact-business-committee-grid.png) 

*Traduzido por openai.com*

=======
*Traduzido por openai.com*
>>>>>>> newbranch
