<!-- Filename: J4.x:Template_Layouts / Display title: Layouts de Modelo  -->

## Estrutura de Arquivos de Layout

Em um **template**, cada extensão que gera saída em HTML coloca o código de saída em um arquivo de template dentro da estrutura de arquivos da extensão, geralmente em uma pasta chamada tmpl. Alguns exemplos:

- /modules/mod_login/tmpl/default.php
- /modules/mod_login/tmpl/default_logout.php
- /components/com_content/tmpl/article/default.php
- /plugins/content/vote/tmpl/vote.php

Em uma **sobrescrição de template**, um arquivo com o mesmo nome é criado dentro da estrutura de arquivos do template e é usado em vez do arquivo na estrutura de arquivos da extensão. Exemplos correspondentes:

- /templates/cassiopeia/html/mod_login/default.php
- /templates/cassiopeia/html/mod_login/default_logout.php
- /templates/cassiopeia/html/com_content/article/default.php
- /templates/cassiopeia/html/plg_content_vote/vote.php

Isso permite personalizar a saída para atender às suas necessidades. No entanto, você não tem a opção de escolher se deseja ou não usar sua sobrescrição. Ela é sempre usada.

Em um **layout alternativo de template**, você cria um arquivo com um nome diferente do original, mas na mesma pasta de template. O novo nome não deve conter um caractere de sublinhado. Você também cria qualquer arquivo que compartilhe a primeira parte do nome original. Um exemplo:

- /templates/cassiopeia/html/mod_login/expires.php
- /templates/cassiopeia/html/mod_login/expires_logout.php

Então, torna-se possível escolher entre usar o layout padrão original ou o layout alternativo. A escolha é feita no formulário de edição do módulo ou componente (Aba Avançada para módulos, Aba de Opções para Artigos). Note que nem todas as extensões permitem sobrescrições ou layouts alternativos.

**Atenção:** os plugins não fornecem um mecanismo para selecionar layouts alternativos.  

## Layouts Alternativos de Módulos

Criar um layout alternativo para um módulo é semelhante a criar uma substituição de template para um módulo. Em ambos os casos, você cria uma pasta chamada `templates/.../html/`. Por exemplo, a pasta para uma substituição de template "mod_login" ou layout alternativo para o template cassiopeia seria `templates/cassiopeia/html/mod_login/`.

Existem duas diferenças importantes entre uma substituição de template e um layout alternativo. A primeira é o nome do arquivo. Para a substituição de template, você nomearia o arquivo `default.php` para corresponder ao nome do arquivo principal. Para um layout alternativo, você usa um nome diferente. A única regra é que **o nome do arquivo não deve conter underscores**.

A segunda diferença importante é que, ao contrário dos arquivos de substituição de template, que são usados automaticamente sempre que o módulo é exibido usando o template com a substituição, um arquivo de layout alternativo é usado apenas se você selecioná-lo como um parâmetro nas configurações de parâmetros do Módulo.

### Um exemplo prático - mod_login

- Vá para **Sistema** → **Templates do Site** → **Detalhes e Arquivos Cassiopeia**
- Selecione a aba **Criar Substituições**.
- Na lista de Módulos, selecione o item **mod_login**.
- Na aba do Editor, selecione **html** → **mod_login** para ver suas cópias recém-criadas dos templates de saída do mod_login.
- Renomeie **default.php** para algo sem underline, **expires.php** neste exemplo.
- Renomeie **default_logout.php** para **expires_logout.php**.

Agora você tem dois arquivos com exatamente o mesmo conteúdo dos originais. Altere o conteúdo de expires_logout.php para adicionar uma mensagem informando ao usuário a que hora a sessão irá expirar após cada carregamento de página.

Na linha 16, imediatamente abaixo das declarações de uso existentes, adicione o seguinte:

```php
use Joomla\CMS\Factory;

date_default_timezone_set('Europe/London');
$config = Factory::getContainer()->get('config');
$lifetime = $config->get('lifetime', 0);
$time = time() + $lifetime * 60;
$endTime = date('H:i:s', $time); // time() já retorna o tempo em segundos
```

E na linha 36, imediatamente após a linha contendo uma declaração endif, adicione este código:

```html
<p class="text-center">
Sua sessão expirará às <br><?php echo $endTime; ?>
</p>
```

Feche os arquivos do Cassiopeia. Selecione **Conteúdo** → **Módulos do Site** e abra o módulo Login. Na aba Avançado, item Layout, você encontrará a escolha entre **-- Do Módulo -- / Padrão** e **-- Do Template cassiopeia -- / expires**.

![módulo de login mostrando layouts alternativos](../../../en/images/templates/layouts-module-login.png)

Uma maneira de utilizar esse recurso é ter dois formulários de Login, um com acesso Público e o outro com acesso para Super Usuários. Neste último, selecione a opção **expires** e somente Super Usuários verão o lembrete do tempo de expiração da sessão.

É importante entender que, se especificado na tela de parâmetros do Módulo, um arquivo de layout alternativo para um módulo será usado para esse módulo independentemente do template usado para exibir a página onde o módulo é mostrado. Portanto, é responsabilidade do administrador garantir que o arquivo de layout funcionará como desejado em quaisquer templates onde esse módulo possa ser exibido.

### Tradução

Você pode traduzir o nome do arquivo usando Substituições de Idioma. Tente o seguinte procedimento:

- Selecione **Sistema** → **Painel de Gerenciamento** → **Substituições de Idioma**
- Selecione seu idioma e o local do Administrador.
- Selecione o botão **Novo** e preencha o formulário. Neste exemplo, a chave de idioma é **TPL_CASSIOPEIA_MOD_LOGIN_LAYOUT_EXPIRES** e o texto pode ser **Login / Logout com tempo de expiração**
- Salve e feche e volte ao formulário do módulo Login.

![formulário de edição de substituições de idiomas](../../../en/images/templates/layouts-language-override-form.png)

O campo de seleção de layout do módulo com **expires** traduzido:

![selecione layouts alternativos do módulo](../../../en/images/templates/layouts-example-translated.png)

## Layouts Alternativos de Componentes

Os layouts alternativos de componentes funcionam de maneira semelhante aos layouts de módulos. Um arquivo é colocado na mesma pasta onde você colocaria um arquivo de substituição de template. Por exemplo, para criar um layout alternativo para um artigo para o template "cassiopeia", você colocaria um arquivo na pasta `templates/cassiopeia/html/com_content/article/`. Assim como nos layouts de módulos, o arquivo não deve ter o mesmo nome do arquivo principal e não deve incluir underscores no nome. Além disso, não deve haver um arquivo XML com o mesmo nome nesta pasta. (Discutiremos arquivos XML abaixo, em Layouts Alternativos de Item de Menu.)

Você pode definir um valor global para layouts de componentes na janela Opções do componente. Por exemplo, na janela Artigo: Opções, há um parâmetro *Escolher um Layout* conforme mostrado abaixo:

![formulário de opções de artigos com lista de layouts alternativos](../../../en/images/templates/layouts-articles-options.png)

Assim como nos layouts de módulos, os layouts de componentes são mostrados como opções de parâmetro na tela de edição do componente individual. Por exemplo, para um artigo, o parâmetro é exibido na aba Artigos: Editar Opções conforme mostrado abaixo.

![formulário de edição de artigo mostrando lista de layouts alternativos](../../../en/images/templates/layout-article-edit.png)

Como em outros parâmetros, a configuração Usar Global utilizará a configuração do parâmetro Opções. A configuração Do Padrão do Componente utilizará o layout padrão do componente. Layouts alternativos que você criou para diferentes templates são mostrados sob o título de cada template.

Os nomes dos arquivos podem ser traduzidos. A linha abaixo:
```ini
    TPL_CASSIOPEIA_COM_CONTENT_ARTICLE_LAYOUT_MYLAYOUT="Apenas Título Sem XML"
```
traduzirá um arquivo chamado "mylayout.php" como "Apenas Título Sem XML".

Você pode ter mais de um arquivo para um layout. O arquivo inicial deve ser nomeado sem underscores e quaisquer arquivos adicionais devem ter underscores.

Layouts alternativos de componentes podem ser usados com artigos, contatos ou feeds de notícias.

Os layouts alternativos de componentes só são usados quando duas condições são atendidas: (1) eles são especificados nos parâmetros do componente; e (2) não há um item de menu para este componente específico. Por exemplo, se você tiver um ou mais itens de menu do tipo "Artigo Único" configurados para um determinado artigo, o layout alternativo para esse artigo não será utilizado. Em vez disso, o layout especificado no item de menu será utilizado. Isso é consistente com a forma geral como os parâmetros de componentes funcionam, onde o mais específico (neste caso, um item de menu de artigo único) substitui o menos específico (neste caso, os parâmetros do artigo).

## Layouts Alternativos de Categoria

Os layouts alternativos de categoria funcionam como layouts de componentes. As regras para especificar arquivos de layout são as mesmas. A única diferença é que a pasta é a pasta da categoria, não a pasta do componente. Por exemplo, um layout alternativo de categoria de contato para cassiopeia estaria na pasta `templates/cassiopeia/html/com_contact/category`.

Você pode definir layouts de categoria globalmente, na tela de Opções de cada componente. Abaixo está um exemplo das Opções dos Contatos: Opções / Formulário de Categoria:

![formulário de opções do componente de contatos mostrando layouts alternativos](../../../en/images/templates/layouts-contacts-options.png)

Os layouts alternativos de categoria aparecem quando você adiciona ou edita uma categoria no formulário Componente: Editar Categoria / Opções, como mostrado abaixo.

![formulário de opções do componente de contatos mostrando layouts alternativos](../../../en/images/templates/layouts-contacts-category-options.png)

Os layouts alternativos de categoria podem ser usados para artigos, banners, contatos e feeds de notícias.

Assim como nos layouts de componentes, um layout de categoria só será usado se:

1. ele for selecionado nos parâmetros globais ou da categoria.
2. não houver um item de menu especificamente para a categoria.

Se houver um item de menu configurado para uma categoria específica, o layout selecionado no menu será usado em vez do layout alternativo de categoria.

## Categoria de Artigo Blog e Lista

Para artigos, existem dois layouts de categoria principais disponíveis: Blog e Lista. Cada um desses layouts aparece no formulário de Opções de Artigos, na aba Categoria, sob o título "Do Componente". Layouts alternativos também aparecem na lista, permitindo que os layouts de Blog, Lista ou templates alternativos sejam selecionados como o layout de categoria padrão, seja globalmente ou ao editar uma única categoria de artigo.

![formulário de opções do componente de contatos mostrando layouts alternativos](../../../en/images/templates/layouts-articles-options-category.png)

Isso significa que, como outras opções de layout, você pode controlar se os links da categoria de artigos usam layouts de blog ou lista. É importante compreender que, assim como outros parâmetros de layout, essa opção só terá efeito quando não houver um item de menu de categoria única para a categoria.

## Itens de Menu Alternativos

Os Itens de Menu Alternativos têm uma diferença importante em relação aos outros. Para criar um layout alternativo de item de menu, você deve incluir um arquivo XML cujo nome corresponda ao arquivo de layout inicial. Por exemplo, para criar um item de menu alternativo chamado "meuartigo" para um artigo no template cassiopeia, você criaria dois arquivos na pasta `templates/cassiopeia/html/com_content/article` chamados `meuartigo.php` e `meuartigo.xml`. Se você quiser incluir mais arquivos de layout, deve adicionar esses arquivos com underscores nos nomes dos arquivos.

O arquivo XML usa o mesmo formato que os arquivos XML de Item de Menu do núcleo. Isso permite não apenas criar um layout personalizado para este item de menu, mas também criar parâmetros personalizados. Por exemplo, você pode ocultar alguns parâmetros ou adicionar novos parâmetros.

Os Itens de Menu Alternativos aparecem quando você seleciona um Tipo de Item de Menu, como mostrado abaixo.

![lista de seleção de item de menu](../../../en/images/templates/layouts-menu-blog-menu-creation.png)

Os Itens de Menu Alternativos são usados e funcionam da mesma maneira que os itens de menu padrão. Uma vez que já são baseados em layouts personalizados, substituições de template não se aplicam a itens de menu alternativos.

Como indicado acima, os layouts de item de menu têm prioridade sobre layouts alternativos de componente ou categoria.

A tradução dos itens de menu alternativos é feita com as seguintes tags nos arquivos XML. O formato é `"TPL_"<nome do template>_<componente>_<visualização>_<nome do item de menu>_<tipo de tag>`. Por exemplo, as linhas abaixo traduzirão o título, a opção e a descrição para um item de menu alternativo chamado "catmenuitem".
```
    TPL_CASSIOPEIA_COM_CONTENT_CATEGORY_VIEW_CATMENUITEM_TITLE="Layout Personalizado de Categoria cassiopeia"
    TPL_CASSIOPEIA_COM_CONTENT_CATEGORY_VIEW_CATMENUITEM_OPTION="Personalizado cassiopeia"
    TPL_CASSIOPEIA_COM_CONTENT_CATEGORY_VIEW_CATMENUITEM_DESC="Descrição para layout personalizado de categoria cassiopeia."
```
Essas strings devem ser adicionadas em
`administrator/language/overrides/en-GB.override.ini`, mas você pode usar o formulário de Substituições de Idioma descrito acima.

O catmenuitem.xml começaria com:

```xml
<?xml version="1.0" encoding="utf-8"?>
<metadata>
   <layout title="TPL_CASSIOPEIA_COM_CONTENT_CATEGORY_VIEW_CATMENUITEM_TITLE" option="TPL_CASSIOPEIA_COM_CONTENT_CATEGORY_VIEW_CATMENUITEM_OPTION">
      <help
         key = "JHELP_MENUS_MENU_ITEM_ARTICLE_SINGLE_ARTICLE"
      />
      <message>
         <![CDATA[TPL_CASSIOPEIA_COM_CONTENT_CATEGORY_VIEW_CATMENUITEM_DESC]]>
      </message>
   </layout>
```

## Controlando o Modelo para Itens de Menu Alternativos

Conforme discutido acima, a presença de um arquivo XML torna um layout alternativo em um item de menu. O formato do arquivo XML é o mesmo que o formato para arquivos XML de itens de menu principais. Com este arquivo XML, você pode adicionar os parâmetros que deseja incluir para este item de menu. Eles podem ser os mesmos que um dos itens de menu principais, ou você pode omitir parâmetros principais ou adicionar novos. Observe que, se você adicionar novos parâmetros, estes podem ser usados no arquivo de layout, mas não serão utilizados nos arquivos de modelo ou de visão principais.

Também é possível substituir configurações de parâmetros para parâmetros principais. Um exemplo disso é controlar com quais modelos um layout de item de menu alternativo pode ser exibido. Em alguns casos, você pode querer permitir que um item de menu personalizado seja exibido com qualquer modelo do site. Em outros casos, você pode desejar limitar o layout desse item de menu a um modelo específico. Nesta situação, você simplesmente adicionaria o seguinte parâmetro ao arquivo XML do item de menu:

```xml
<fields>
  <field
    name="template_style_id"
    type="templatestyle"
    label="COM_MENUS_ITEM_FIELD_TEMPLATE_LABEL"
    description="COM_MENUS_ITEM_FIELD_TEMPLATE_DESC"
    filter="int"
    template="cassiopeia"
    class="inputbox">
  </field>
 </fields>
```

Isso irá substituir o parâmetro principal `template_style_id`. Definir o template como "cassiopeia" neste caso irá limitar o usuário a selecionar apenas estilos de template para o template "cassiopeia".

## Informações Adicionais

- Noções Básicas de
  Template
- Pastas e Arquivos do
  Template Cassiopeia
- Personalização do 
  Template Cassiopeia
- Substituições de
  Template
- Layouts de
  Template
- Template Cassiopeia Simplificado - Um Estudo de Caso - um template simples baseado no Cassiopeia

*Traduzido por openai.com*  

