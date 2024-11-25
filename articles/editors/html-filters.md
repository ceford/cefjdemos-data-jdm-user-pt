<!-- Filename: Entering_raw_HTML_in_editors / Display title: Filtros HTML  -->

## Tag de Textarea em HTML

Em HTML, um campo de entrada de várias linhas é conhecido como textarea. Qualquer texto entre as tags de abertura e fechamento é exibido como texto que pode conter marcação HTML. Exemplo:
```
<textarea><p class="poem">O rápido cão castanho<br>
salta sobre o cão preguiçoso.</textarea>
```
Editores, como TinyMCE ou Code Mirror, usam JavaScript para sobrepor o textarea com uma exibição diferente que permite a entrada de dados WYSIWYG e/ou destaque de sintaxe. O botão "Alternar" abaixo de um campo do editor alterna entre a visualização de textarea e a visualização WYSIWYG.

As visualizações do editor são usadas para o conteúdo de Artigos e alguns Módulos. No entanto, você precisa estar ciente de que nem todas as tags e atributos HTML (como class="xyz") são permitidos para todos os usuários. Alguns ou todos podem desaparecer quando você salva o conteúdo de um textarea ou campo de edição.

Isso é causado por mecanismos de filtragem, seja na Configuração Global do Joomla! ou na configuração do editor. Um filtro de editor pode ser contornado selecionando *Sem Editor* nas configurações do seu *Perfil de Usuário*. Você não pode contornar os filtros globais, mas pode alterá-los para atender aos propósitos do seu site.

## Seleção de Editor do Usuário

Você pode selecionar um dos editores disponíveis, incluindo Nenhum, a partir do seu Perfil de Usuário disponível via o menu Conta do Usuário / Editar Perfil no canto superior direito da tela do Administrador. O formulário Editar: Perfil contém uma aba de Configurações Básicas com um campo para selecionar um Editor. Normalmente, está configurado como *- Usar Padrão -*, que geralmente é o TinyMCE. Você pode selecionar *Editor Nenhum*. Isso ignorará qualquer filtragem de tags HTML e atributos não permitidos pelas configurações de configuração do TinyMCE.

**Aviso:** se você selecionar *Editor - Nenhum* para criar conteúdo contendo tags HTML não permitidas por um filtro do editor e depois voltar para o editor padrão, você deve ter cuidado para não editar e salvar esse conteúdo novamente ou perderá quaisquer tags e atributos filtrados. É fácil fazer isso por engano e não há aviso.  

## Configuração Global: Filtros de Texto

No Painel Principal, selecione Configuração Global e depois a aba Filtros de Texto. As configurações padrão têm *Nenhum HTML* selecionado para os grupos de usuários Convidado, Público e Registrado. Qualquer um desses grupos pode ter a oportunidade de preencher um campo de área de texto, por exemplo, em um formulário de contato que busca informações adicionais sobre um problema, então a remoção automática de todas as tags HTML é geralmente apropriada. Outros grupos, exceto Super Usuários, são restringidos pela Lista Padrão de Proibidos. Super Usuários não têm filtragem.

![configuração global de filtros de texto](../../../en/images/configuration/global-configuration-filters-tab.png)

As notas explicam o que está incluído na lista padrão de proibidos e como usar as outras listas.

## Configuração do TinyMCE para Filtros de Texto

Os editores são implementados como Plugins no Joomla. O editor CodeMirror não possui configurações de filtro de texto. Para personalizar o editor TinyMCE, encontre-o e selecione-o na lista de plugins. Na metade da longa lista de configurações, você verá um campo rotulado como *Usar Filtro de Texto do Joomla*, que está **Desligado** por padrão. Os três campos seguintes são:
* **Elementos Proibidos**: uma lista de tags que sempre serão removidas. A lista padrão de *script, applet, iframe* todas têm preocupações de segurança.
* **Elementos Válidos**: use esta lista para limitar as tags válidas a um subconjunto de todas as tags HTML comuns. Exemplo: `a[href|target=_blank],strong/b,div[align],br`
* **Elementos Válidos Estendidos**: use esta lista para adicionar um elemento ao conjunto de regras padrão existente ou para modificar um elemento no conjunto de regras padrão. Exemplo: `img[class|src|border=0|alt|title|hspace|vspace|width|height|align|onmouseover|onmouseout|name]`

Veja a Documentação do TinyMCE para mais explicações.

Para contornar os filtros de texto do TinyMCE e usar os filtros de texto do Joomla, defina *Usar Filtro de Texto do Joomla* como **Ligado**. Os três campos adicionais descritos acima desaparecem, pois não são usados.

*Traduzido por openai.com*

