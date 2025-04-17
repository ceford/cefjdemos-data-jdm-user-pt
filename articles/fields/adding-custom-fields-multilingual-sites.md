<!-- Filename: J3.x:Adding_custom_fields/Multilingual_Sites / Display title: Sites Multilíngues -->

## Introdução

Se você tem um site multilíngue, pode exibir os rótulos e descrições dos campos e grupos de campos no idioma do usuário. Para fazer isso:

1. Defina o Título e a Descrição do seu grupo de campos como constantes de idioma.
2. Defina o Rótulo e a Descrição do seu campo como constantes de idioma.
3. Configure essas constantes de idioma como substituições para cada um dos seus idiomas.

No exemplo a seguir, um grupo de campos de Contato e um campo são criados para as preferências pessoais de um contato. O grupo de campos é chamado de Favoritos e o campo exemplo é chamado de Carro. Claramente, mais campos podem ser adicionados para outras coisas favoritas, como comida ou filmes.

Para seguir este exemplo, assume-se que você configurou um site multilíngue, conforme descrito no tutorial [Sites Multilíngues](jdocmanual?article=user/languages/setup-a-multilingual-site).

## Constantes de Idioma

Constantes de idioma são espaços reservados que são substituídos por valores de idioma quando uma página é renderizada. As constantes e seus valores são armazenados em arquivos de idioma, como JPATH_SITE/languages/en-GB/com_contact.ini e JPATH_SITE/administrator/languages/en-GB/com_contact.ini, para o frontend e backend, respectivamente. Por convenção, a maioria das constantes de idioma começa com o nome da extensão todo em letras maiúsculas, por exemplo, COM_CONTACT_...

Substituições de idioma são substituições definidas pelo usuário para constantes e valores de idioma existentes ou constantes e valores totalmente novos, como neste exemplo. Todos são armazenados em arquivos únicos, um para as páginas do Site e outro para as páginas do Administrador:
```
SITE_ROOT/language/overrides/en-GB.override.ini
SITE_ROOT/administrator/language/overrides/en-GB.override.ini
```
É importante fazer com que as novas constantes de idioma definidas pelo usuário sejam únicas para evitar substituir constantes existentes. Por exemplo:

COM_CONTACT_CUSTOM_FIELDGROUP_FAVOURITES="Favoritos"
COM_CONTACT_CUSTOM_FIELDGROUP_FAVOURITES_DESCRIPTION="Carro favorito, filme, etc."
COM_CONTACT_CUSTOM_FIELD_FAVOURITE_CAR="Carro Favorito"
COM_CONTACT_CUSTOM_FIELD_FAVOURITE_CAR_DESCRIPTION="Às vezes usado como uma pergunta de segurança"

Se houver qualquer erro na sintaxe de um arquivo de idioma, ele não será carregado e todas as constantes nele podem aparecer nas páginas de saída. E note que um arquivo é ordenado em ordem alfabética.

## Definindo as Sobrescrições

É importante criar sobrescrições em inglês (GB). O Joomla carrega os arquivos de tradução en-GB primeiro e, em seguida, sobrescreve os valores com um arquivo de idioma selecionado. Isso garante que os usuários nunca devam ver uma constante de texto. Se um valor traduzido estiver faltando, o inglês aparecerá na saída. Isso pode parecer estranho, mas é melhor do que ver uma constante bastante longa, que geralmente atrapalha os layouts.

No menu do Administrador:

* Selecione **Sistema / Painel de Gestão / Sobrescrições de Idioma**
* Selecione **Inglês (Reino Unido) - Site** na lista *Selecionar Idioma e Cliente*
* Selecione o botão **Novo** na Barra de Ferramentas.
* No campo **Constante de Idioma**, insira *COM_CONTACT_CUSTOM_FIELDGROUP_FAVOURITES*
* No campo **Texto**, insira o valor *Favourites*
* Marque a caixa de seleção **Para Ambas as Localizações**. Isso irá criar
sobrescrições para as páginas do Site e do Administrador.
* Selecione **Salvar & Novo** na lista suspensa *Salvar * Fechar*.
* Repita para cada uma das outras constantes necessárias.
* Selecione **Fechar** após a última entrada ter sido salva.
* Repita para cada um dos idiomas instalados.

A captura de tela a seguir mostra um exemplo de criação de sobrescrição para uma constante de idioma alemã.

![Criação de sobrescrição em alemão](../../../en/images/fields/fields-overrides-creation-de.png)

## Definindo o Grupo de Campos

No menu do Administrador:

* Selecione o item de menu **Componentes / Contatos / Grupos de Campos**.
* Selecione o botão **Novo** na Barra de Ferramentas.
* No campo Título, insira a constante COM_CONTACT_CUSTOM_FIELDGROUP_FAVOURITES
* No campo Descrição, insira a constante COM_CONTACT_CUSTOM_FIELDGROUP_FAVOURITES_DESCRIPTION
* Selecione **Salvar & Fechar** na Barra de Ferramentas.


## Definindo o Campo

Para selecionar um carro favorito, você pode fornecer uma lista suspensa de carros que você define, ou uma lista suspensa de carros obtida a partir de uma tabela de banco de dados, ou uma lista de botões de rádio com rótulos que você define. Neste caso, um campo de entrada de texto simples permitirá a entrada de qualquer marca e modelo de carro de toda a história mundial da indústria automobilística.

No menu do Administrador:

* Selecione o item de menu **Componentes / Contatos / Campos**.
* Selecione o botão **Novo** na Barra de Ferramentas.
* No campo Título, insira a constante COM_CONTACT_CUSTOM_FIELD_FAVOURITE_CAR
* No campo Tipo, selecione **Texto (text)** se já não estiver selecionado.
* No campo Descrição, insira a constante COM_CONTACT_CUSTOM_FIELD_FAVOURITE_CAR_DESCRIPTION
* No campo **Grupo de Campo** (à direita) selecione o Grupo de Campo que você criou.
* Selecione **Salvar & Fechar** na Barra de Ferramentas.

## Editar um Contato

Com o inglês selecionado antes do login do Administrador, o formulário de entrada de dados do Contato deve conter uma aba com o nome em inglês do seu grupo de campos e campos nesse grupo também com valores em inglês.

![Entrada de dados em inglês](../../../en/images/fields/fields-overrides-entry.png)

Com o alemão selecionado antes do login do Administrador, você deverá ver as traduções em alemão das suas constantes de idioma:

![Entrada de dados em alemão](../../../en/images/fields/fields-overrides-entry-de.png)

Atenção: tradução por translate.google.co.uk!

## Exibir um Contato

Em inglês:

![Exibição de dados em inglês](../../../en/images/fields/fields-overrides-display.png)

E em alemão:

![Exibição de dados em alemão](../../../en/images/fields/fields-overrides-display-de.png)

*Traduzido por openai.com*

