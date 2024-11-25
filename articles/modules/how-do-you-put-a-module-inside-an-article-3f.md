<!-- Filename: How_do_you_put_a_module_inside_an_article%3F / Display title: Módulos dentro de Artigos  -->

## Introdução

Normalmente, você desejará associar módulos a artigos de alguma forma. Os módulos geralmente são alocados em posições de módulo, e as posições de módulo aparecem em algum lugar na página da web, conforme determinado pelo template. No entanto, às vezes é útil ter um módulo realmente incorporado em um artigo. O Joomla possui um plugin chamado *Content - Load Modules* para fazer isso. Quando ativado, um módulo pode ser incorporado em um artigo de três maneiras diferentes:

```
    {loadposition position,[style]}
    {loadmodule mod_type,the title,[style]}
    {loadmoduleid moduleId}
```

Onde `style` é um dos valores de Estilo do Módulo da aba Avançado do formulário de entrada de dados do módulo, por exemplo, html, outline, table, card ou noCard.

## loadposition

Para inserir um módulo dentro de um artigo, você deve publicar o módulo em uma posição e carregar essa posição no artigo da seguinte forma:

1. Crie um módulo e defina sua posição como ***minhaposição***. ***minhaposição*** pode ser qualquer valor que não conflite com uma posição de modelo existente. No formulário de edição do módulo, digite a posição ***minhaposição*** e pressione enter ao invés de selecioná-la da lista suspensa.
2. Atribua o módulo a **Todos** os Itens de Menu. Isso garantirá que ele sempre apareça, independentemente de como o visitante chegou ao artigo. O módulo não será exibido a menos que você use o comando para carregá-lo em um artigo.
3. Edite o artigo e insira o texto ***{loadposition minhaposição}*** no local onde você deseja que o módulo apareça.

**Observação:** Se o plugin *Conteúdo - Carregar Módulos* estiver desativado, o texto *{loadposition minhaposição}* aparecerá inalterado no artigo. Além disso, o nome da posição deve estar todo em letras minúsculas. A CapitalizaçãoComCamelos não funcionará.  

## loadmodule

A sintaxe *{loadmodule yyy}* procura o primeiro módulo cujo **tipo** corresponde à string 'yyy'. Assim, você poderia carregar um módulo *mod_login* colocando {loadmodule login} no seu texto. O tipo não é tão óbvio! Por exemplo, o Seletor de Idiomas tem o tipo **languages**. Para encontrar o tipo, você precisa vasculhar a lista de pastas de módulos com um gerenciador/explorador de arquivos e retirar a parte *mod_* do nome da pasta.

Se você deseja carregar uma instância específica de um módulo, porque você tem mais de um módulo de login, por exemplo, intitulado como Login 1, Login 2, etc., você deve usar {loadmodule mod_modType, modTitle} onde **mod_modType** seria mod_login e **modTitle** seria o nome/título dado à sua instância daquele módulo. Assim, no exemplo acima, você acaba com **{loadmodule mod_login Login 2}**.

Você também pode adicionar o estilo usado para renderizar o módulo. Para fazer isso, adicione o estilo como terceiro parâmetro, como em {loadmodule login,Login 2,xhtml}. Se você não adicionar um estilo, então nenhum será usado.

## loadmoduleid

A sintaxe *{loadmoduleid z}* procura pelo módulo cujo `id` corresponde ao número `z`. Assim, você pode carregar o módulo com id 200 inserindo *{loadmoduleid 200}* no seu texto. Esta variante não utiliza parâmetros adicionais como o parâmetro `style`.  

## Botão do Editor

Se o plugin editor-xtd *Botão - Módulo* estiver ativado, você pode usar o botão do editor *Módulo* para inserir as tags descritas acima mais facilmente no texto do editor. A lista de Módulos possui um botão na coluna Título para inserir por ID e um botão na coluna Posição para inserir por posição.  

## Módulos dentro de Módulos

É possível incluir um módulo dentro de um módulo *HTML Personalizado*. Eles são processados por plugins de conteúdo da mesma forma que os artigos.

Pode haver problemas de formatação, pois o estilo do módulo *HTML Personalizado* envolverá o estilo do módulo incluído. É por isso que o botão do editor *Módulo* não está disponível em módulos do tipo *Personalizado*.

*Traduzido por openai.com*

