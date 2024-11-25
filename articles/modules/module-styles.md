<!-- Filename: jdocmanual?manual=user&heading=modules&filename=module-styles.md / Display title: Estilos do Módulo -->

## Conceitos de Estilo

Um formulário de entrada de dados de um módulo possui uma guia **Avançado**. Seus campos variam de acordo com o tipo de módulo, e você pode verificar isso por conta própria selecionando um módulo de Menu e comparando com um módulo de Login ou módulo de Migalhas (Breadcrumbs). Você verá os seguintes três campos do formulário relacionados ao estilo:

* **Classe do Módulo** é um campo de texto que permite adicionar sua própria classe CSS à tag de contêiner do módulo, geralmente um `<div>`.
* **Classe do Cabeçalho** é um campo de texto que permite adicionar sua própria classe CSS à tag de Cabeçalho, que por padrão é uma tag `<h3>`.
* **Estilo do Módulo** é uma lista que permite selecionar um entre vários estilos padrão. A lista contém none, html5, outline, table, card e noCard. O padrão é card, dos estilos do modelo Cassiopeia.

Você pode experimentar as opções de *Estilo do Módulo* editando um módulo e alterando o valor para ver como ele afeta a exibição do site.

* **html5** fornece `<div class="moduletable ">`
* **none** remove completamente o `<div>` externo e também a tag `<h3>` do módulo.
* **outline** fornece `<div class="mod_preview_info">`, com informações de posição e estilo substituindo a tag `<h3>` do módulo.
* **table** fornece um layout de tabela começando com `<table class="moduletable ">`, com a antiga tag h3 agora sendo uma tag `<th>`.
* **card** fornece `<div class="sidebar-right card ">`, o padrão.
* **noCard** fornece `<div class="sidebar-right no-card ">`.

## A Classe do Módulo

Nesta etapa, você precisa saber um pouco sobre Folhas de Estilo em Cascata ou CSS. Se você inserir uma única palavra no campo Classe do Módulo, como **green**, já que as classes CSS são, por convenção, todas em letras minúsculas, e com o Estilo do Módulo definido como **herdado**, a saída conterá `<div class="sidebar-right card green">`.

Não há mudança visível na aparência do site porque a classe green não está definida. Para defini-la, faça uma entrada no arquivo user.css do modelo.

No menu Administrador:
* Selecione **Sistema / Modelos de Site / Modelos e Arquivos Cassiopeia**.
* Selecione **Novo Arquivo** na *Barra de Ferramentas*.
* Selecione **css** na coluna esquerda, o destino para o novo arquivo.
* Digite **user** no campo Nome do Arquivo.
* Selecione **css** na lista Tipo de Arquivo.
* Selecione o botão **Criar**.

Agora você pode abrir a pasta css para encontrar e abrir o arquivo user.css para edição. Insira essas declarações de estilo e observe a grafia americana de *color*:
```
.sidebar-right.card.green {
    background-color: #ddffdd;
}
.sidebar-right.card.green .card-body {
    background-color: #eeffee;
}
```
O estilo poderia ter usado apenas `.green`, mas isso poderia ter afetado outras tags com esse estilo em outras páginas.

## A Classe Header

Volte para o formulário de edição do módulo e adicione **azul** no campo Classe Header. O módulo não apresenta alterações visíveis no site, mas o cabeçalho agora aparece como `<h3 class="card-header blue">`. Volte a editar o arquivo user.css para adicionar uma entrada para o estilo do cabeçalho:
```
.card-header.blue {
    color: navy;
}
```
O cabeçalho do módulo agora está em azul escuro. Existem várias maneiras de especificar cores em CSS. As mais comuns são hexadecimais e nomes de cores padrão. Leia mais sobre isso em outro lugar!

## Desafio CSS

* Altere a cor da borda do módulo para azul marinho!
* Altere também a borda inferior do cabeçalho.
* Aplique este estilo a vários módulos em vez de um por vez.

![Exemplo de Módulo de Artigos Arquivados](../../../en/images/modules/modules-archived-articles.png)

*Traduzido por openai.com*  

