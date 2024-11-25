<!-- Filename: category-list-override.md / Display title: Substituir Lista de Categorias  -->

## O Item de Menu Listar Contatos em uma Categoria

Pode ser uma opinião pessoal, mas para mim, o layout padrão da lista de categorias de Contato não é muito satisfatório. Meus problemas:

* As fotos de contato são muito grandes, com pouco menos de 500 pixels de largura.
* O nome do contato não é suficientemente destacado.
* A lista com marcadores de detalhes pessoais não tem título e parece isolada.
* A posição não tem título, então pode parecer isolada.
* Os campos de endereço e código postal estão ausentes.
* Os dados de localização estão incompletos.
* A declaração pessoal está faltando.
* A lista está organizada em uma tabela, o que é um pouco melhor em telas estreitas, mas fica bastante apertada.

Então, como consertar para o meu gosto?

## Estilização

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

![comitê de negócios estilizado](../../../en/images/contacts/contact-business-committee-styled.png "Comitê de Negócios Estilizado")

Isso é o máximo que pode ser feito com estilização. Melhor, mas ainda não bom o suficiente. Adicionar mais itens e mudar o layout exigirá uma sobreposição de layout.

## Sobrescrever Layout do Template

A pasta com_contact/tmpl/category contém três arquivos PHP: default.php,
default_children.php e default_items.php. O último da lista contém
o layout da tabela para a lista.

Os arquivos de sobrescrita são criados via Sistema / Templates do Site / Cassiopeia
Detalhes e Arquivos / Criar Sobrescritas. Selecione com_contact e depois category.
A pasta html então contém com_contact/category com os três arquivos de template mencionados acima. O default_items.php é o que deve ser selecionado para
edição. As linhas de 83 a 203 contêm a tabela usada para layout.

Pode não ser óbvio, mas $this->items é um array de membros da categoria e
cada membro realmente contém todos os dados para cada item, não apenas aqueles
mencionados nas configurações do menu.

O seguinte é uma substituição para a seção `<table>...</table>` do
arquivo default_items.php usando uma grade do Bootstrap. Em telas estreitas as três
colunas são empilhadas. Em telas com mais de 768 pixels de largura as colunas ficam lado a lado. Mais explicações seguem após o código.

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
                                'alt'   => 'imagem oficial de ' . $item->name,
                                'class' => 'contact-thumbnail img-thumbnail',
                            ]
                        ); ?>
                    <?php endif; ?>
                <?php endif; ?>
            </div>
            <div class="col-12 col-md-3">
                <a href="<?php echo Route::_(RouteHelper::getContactRoute($item->slug, $item->catid, $item->language)); ?>">
                    <span class="fs-2"><?php echo $this->escape($item->name); ?></span>
                </a>
            </div>
            <div class="col-12 col-md-6 text-start">
                <?php if ($this->params->get('show_position_headings') && !empty($item->con_position)) : ?>
                    <strong>Posição</strong><br>
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
                        <strong>Endereço</strong><br>
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
### Explicação

A lista de contatos pode conter itens que não estão publicados, ou têm datas de publish_up
e publish_down que não são atuais. Eles precisam ser excluídos da
exibição e um contador separado é necessário para manter a alternância das
cores de fundo em cada linha.

A tag img é renderizada como:
```
<img src="/j51/images/parliament/Official_portrait_of_Liam_Byrne_crop_2.jpg"
alt="imagem oficial de Liam Byrne" class="contact-thumbnail img-thumbnail"
width="479" height="639" loading="lazy">
```
A classe `<span class="fs-2">...</span>` define o nome do contato para o tamanho da fonte 2,
que seria o mesmo que Título 2.

O item `show_suburb_headings` está sendo usado como um proxy para mostrar o endereço completo pois alguns dos itens individuais do endereço não possuem seletores de Mostrar/Ocultar no item do menu.

### Estilo Extra

A versão em grade da lista de contatos necessita de estilo adicional no user.css:
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
```

### Resultado

![gridded business committee](../../../en/images/contacts/contact-business-committee-grid.png "Comitê Empresarial em Grade") 

*Traduzido por openai.com*

