<!-- Filename: J4.x:Language_Overrides / Display title: Substituições de Idioma -->

## Localizações dos Arquivos de Idioma

A maioria dos arquivos de idioma do Joomla! estão localizados em pastas de idioma, uma na raiz do site e outra na pasta do administrador. Cada idioma possui sua própria subpasta baseada nos códigos de idioma padrão RFC3066. Cada extensão armazena suas traduções com um nome derivado do nome da extensão. Alguns exemplos:

    raizdosite/language/en-GB/com_content.ini
    raizdosite/administrator/language/en-GB/com_content.ini
    raizdosite/administrator/language/en-GB/com_content.sys.ini

Os arquivos contêm linhas que consistem em uma chave e sua tradução:

    COM_CONTENT="Artigos"
    COM_CONTENT_ADD_NEW_MENU_ITEM="Novo Item de Menu"
    COM_CONTENT_ARTICLE_CONTENT="Conteúdo"
    COM_CONTENT_ARTICLES_TABLE_CAPTION="Tabela de Artigos"
    COM_CONTENT_ARTICLES_TITLE="Artigos"

O código PHP do Joomla usa a chave. Ela é substituída pela tradução do texto em tempo de execução. O arquivo .ini contém traduções usadas pela extensão. Os arquivos sys.ini contêm traduções usadas pelo Joomla para gerenciar a extensão. Pode haver centenas de linhas em um arquivo de idioma.

Extensões de terceiros são aconselhadas a armazenar seus arquivos de idioma em pastas de idioma dentro da extensão. Lá, eles estão a salvo de exclusão caso um administrador decida desinstalar um idioma. Exemplo:

    raizdosite/components/com_countrybase/language/en-GB/com_countrybase.ini
    raizdosite/administrator/components/com_countrybase/language/en-GB/com_countrybase.ini
    raizdosite/administrator/components/com_countrybase/language/en-GB/com_countrybase.sys.ini

**Nunca edite qualquer arquivo de idioma do núcleo do Joomla! ou de terceiros! Quaisquer alterações que você fizer serão perdidas na próxima atualização. Se desejar mudar a redação de qualquer item de idioma, use o componente de Sobrescrita de Idioma formal.**

Sobrecargas de idioma são suas substituições para traduções de chaves de idioma do núcleo ou extensão. Estas são traduções individuais, uma ou duas, não um arquivo inteiro! As sobrecargas de idioma para um determinado idioma são todas armazenadas em um arquivo:

    raizdosite/language/overrides/en-GB.override.ini
    raizdosite/language/overrides/fr-FR.override.ini
    raizdosite/language/overrides/de-DE.override.ini

    raizdosite/administrator/language/overrides/en-GB.override.ini
    raizdosite/administrator/language/overrides/fr-FR.override.ini
    raizdosite/administrator/language/overrides/de-DE.override.ini

### Ordem de Carregamento de Idioma

A cada carregamento de página, as traduções do idioma en-GB são carregadas primeiro. Isso garante que nenhuma chave seja vista pelos usuários do site. Se outro idioma estiver em uso, as traduções para esse idioma são carregadas em seguida, substituindo as traduções en-GB. Outros idiomas tendem a ficar atrás do en-GB na criação de traduções, então os usuários podem ocasionalmente ver palavras ou frases em inglês entre aquelas de seu próprio idioma.

Finalmente, as traduções são carregadas a partir do arquivo de sobrecarga de idioma. Isso permite que o site use palavras ou frases alternativas para se adequar às circunstâncias locais.

## Substituições de Idioma

Ocasionalmente, você pode querer substituir um único item de idioma traduzido por algo mais adequado às circunstâncias locais. Um caso comum é quando você cria uma substituição de template ou layout e deseja adicionar algum conteúdo que usa uma nova chave de idioma. O exemplo a seguir ilustra um caso em que algum texto foi adicionado ao layout de logout do módulo de login, descrito no artigo sobre Layouts de Template. O layout alternativo tem este código:

```html
<p class="text-center">
Sua sessão expirará às <br><?php echo $endTime; ?>
</p>
```

Para um site multilíngue usando Inglês, Francês e Alemão, o código precisa mudar:

```html
<p class="text-center">
<?php echo Text::_('TPL_CASSIOPEIA_MOD_LOGIN_SESSION_EXPIRES_AT')?><br><?php echo $endTime; ?>
</p>
```

Nota: se você seguiu o tutorial de Layout de Template, pode já ter uma chave TPL_CASSIOPEIA_MOD_LOGIN_LAYOUT_EXPIRES que traduz como Expira. Mas isso é usado em siteroot/administrator/language/overrides.

A nova chave agora pode ser traduzida para cada idioma. As traduções serão salvas em siteroot/language/overrides.

- Selecione **Sistema** → **Gerenciar painel** → **Substituições de Idioma**
- Selecione seu idioma e a localização do Site.
- Selecione o botão **Novo** e preencha o formulário. Neste exemplo, a chave de idioma é **TPL_CASSIOPEIA_MOD_LOGIN_SESSION_EXPIRES_AT** e o texto pode ser **Sua sessão expirará às**
- Salve & Feche o formulário.
- Repita o processo de tradução para cada idioma.

![formulário de edição de substituições de idiomas](../../../en/images/languages/language-overrides-edit.png)

Finalmente, verifique se a tradução foi implementada.

![Resultado da Substituição no formulário de login do site](../../../en/images/languages/language-overrides-custom-logout.png) 

*Traduzido por openai.com*

