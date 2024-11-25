<!-- Filename: J6.x:_Article_Options / Display title: Artigo: Editar - Opções  -->

## Introdução

A palavra *Opções* é ambígua no Joomla! Às vezes, é usada de forma intercambiável com *Parâmetros* e a maioria das visões de lista de componentes têm um botão *Opções* na Barra de Ferramentas. Isso leva a uma página de Opções onde os parâmetros para o componente como um todo são definidos. Além disso, muitos formulários de edição de itens de componente têm uma aba rotulada como *Opções* usada para definir parâmetros para aquele único item.

Este artigo é sobre a aba *Opções* no formulário *Artigo: Editar*. É onde os parâmetros são definidos para afetar a aparência geral do artigo que está sendo editado. As opções para artigos como um todo são abordadas em um artigo separado.

## Captura de Tela

A aba *Opções* do formulário *Artigo: Editar* possui uma série de painéis, em sua maioria com a escolha de *Usar Global (Ocultar ou Mostrar)*, *Ocultar* ou *Mostrar*. A captura de tela parcial a seguir mostra o layout geral.

![Aba de opções de edição de artigos](../../../en/images/articles/articles-edit-options-tab.png)

## Painel de Layout

Um artigo, ou parte dele, pode aparecer como uma única página ou em um layout de blog de categoria controlado por um item de menu. Em um item de menu de blog, a maioria dos campos de layout possui opções de *Usar Global*, *Sim/Não* ou *Mostrar/Ocultar* e *Usar Configurações do Artigo*. As opções neste painel não têm efeito em layouts de blog a menos que a opção *Usar Configurações do Artigo* seja selecionada no item de menu.

Caso contrário, essas opções afetam a aparência do artigo único que está sendo editado.

- **Layout** Em uma instalação padrão, as duas primeiras opções são oferecidas:
  - **---Das Opções Globais--- / Usar Global** Isso se refere à configuração *Artigos: Opções* disponível a partir do botão *Opções* na barra de ferramentas da visualização de lista de *Artigos*. Seu valor *Escolher um Layout* está configurado como *Padrão*.
  - **---Do Componente--- / Padrão** Isso se refere à configuração nas configurações *Artigos: Opções*. Em uma instalação padrão, é efetivamente o mesmo que a opção *Usar Global*. Mas se existir uma substituição chamada default.php, essa substituição é usada para o layout.
  - **---Do Modelo cassiopeia--- / nomeDaSubstituição** Se uma substituição de modelo foi criada com um nome diferente de *default*, ela aparecerá aqui e poderá ser selecionada como um layout alternativo.
- **Título** É normal mostrar o título de um artigo, mas pode haver circunstâncias em que isso não é apropriado. Selecione *Ocultar* para omitir o título do artigo da exibição da página.
- **Títulos Vinculados** O comportamento padrão é fazer do título do artigo um link para o artigo onde aparece em layouts de blog ou lista. Esta configuração é controlada pelo item de menu. Pode ser configurada para *Usar Global (Sim)*, *Usar Configurações do Artigo*, *Não* ou *Sim*. Se o item de menu estiver configurado para *Usar Configurações do Artigo*, então o valor de *Títulos Vinculados* no artigo será usado. Caso contrário, essa configuração não tem efeito. Se o título não estiver vinculado, você pode usar um link *Leia Mais* para acessar o artigo a partir de um layout de blog ou lista.
- **Tags** Mostrar ou Ocultar tags na página do artigo único.
- **Texto de Introdução** Mostrar ou Ocultar o texto de introdução na página do artigo único. Existem algumas circunstâncias em que você pode desejar ter um texto de introdução completamente diferente para layouts de blog que é omitido no texto completo do artigo.
- **Posição das Informações do Artigo** Isso se refere ao bloco de informações sobre um artigo com o cabeçalho *Detalhes* e contendo informações de *Autor*, *Categoria*, *Publicado* e *Visualizações*. O padrão é ter isso acima do texto do artigo. Configure para Abaixo para mover para abaixo do texto do artigo em uma visualização de artigo único. Se configurado para *Dividir*, o item *Visualizações* se move para abaixo do texto do artigo.
- **Título das Informações do Artigo** Mostrar ou Ocultar a palavra *Detalhes* acima da lista de informações do artigo na visualização de artigo único.

## Painel de Categoria

O campo neste painel funciona como você pode esperar. Nas visualizações de blogs, as configurações dos itens do menu têm precedência, a menos que esteja configurado para *Usar Configurações do Artigo*.

- **Categoria** Mostrar ou Ocultar o nome da Categoria.
- **Link da Categoria** Vincular (Sim ou Não) o nome da Categoria. Se configurado para *Sim*, o nome da Categoria é vinculado ao seu blog de categoria.
- **Categoria Pai** Se configurado para Sim, a categoria pai aparece como um item separado acima da Categoria nas informações do artigo *Detalhes* no layout de artigo único.
- **Link da Categoria Pai** Se configurado para Sim, o nome da Categoria Pai é vinculado à sua página de blog de categoria.

## Painel de Associações

Este painel está presente apenas em sites multilíngues.

- **Associações** Se definido para Mostrar, um item extra é colocado na 
  informação do artigo começando com *Também disponível em:* seguido de 
  bandeiras para representar as versões deste artigo disponíveis em outros idiomas.
- **Usar Bandeiras de Imagem** Este item aparece se *Associações* estiver 
  definido para *Mostrar*. O padrão *Sim* exibe botões como bandeiras de idioma. 
  A alternativa *Não* exibe botões como códigos de idioma, por exemplo, *en-GB*. 

## Painel do Autor

- **Autor** Mostrar ou ocultar o nome do autor deste artigo na visualização
  de artigo único. A linha nas informações do artigo lerá 
  *Escrito por: Nome do Autor*
- **Link para a Página de Contato do Autor** Sim ou não para vincular o Nome do Autor à
  página de contato do autor, se houver uma.

## Painel de Datas

Os artigos do Joomla armazenam várias datas. Se exibidas, cada uma das
seguintes ocorre como linhas separadas nas informações de um único artigo.
Lembre-se, os layouts de blog usam as configurações do item de menu a menos que
sejam definidas como *Usar Configurações do Artigo*. O formato da data é
03 de novembro de 2024, mas isso pode ser alterado...[Para Fazer]

- **Data de Criação** Oculta por padrão.
- **Data de Modificação** Oculta por padrão.
- **Data de Publicação** Exibida por padrão.

## Painel de Opções

- **Navegação** Para um artigo que faz parte de uma série de artigos em uma categoria, há botões *Anterior* e *Próximo* abaixo do texto do artigo para navegar para as páginas anteriores ou seguintes. Se definido como *Ocultar*, os botões de navegação não serão exibidos em páginas de um único artigo.
- **Visualizações** O número total de vezes que o artigo foi exibido como um artigo único, exibido na lista de informações do artigo.
- **Links Não Autorizados** Isso afeta layouts de blog, portanto, o item de menu do blog da categoria relevante deve ter seu valor *Opções: Links Não Autorizados* definido como *Sim* ou *Usar Configurações do Artigo*. Então, se o *Acesso* deste artigo estiver definido como *Registrado* e a configuração no artigo não for *Não*, o *Texto de Introdução* do artigo será exibido no layout do blog, mas o rótulo do botão Leia mais será *Registre-se para ler mais...*. Clicar no link Leia mais exigirá login para ver o conteúdo completo do artigo.
- **Posição dos Links** Refere-se ao posicionamento dos links na aba Imagens e Links, Links A, B e C. A posição padrão é acima do texto do artigo. Esta opção permite que os links sejam colocados abaixo do texto do artigo ou não sejam exibidos.
- **Texto Leia Mais** O texto normal, *Leia Mais:* seguido pelo título do artigo, é retirado dos valores da chave/string do idioma. Uma substituição personalizada apenas para este artigo pode ser inserida aqui, por exemplo, *Veja o artigo completo:* seguido pelo título do artigo.
- **Título da Página do Navegador** O título da página geralmente é o título do artigo. Se isso for inconveniente, um título alternativo para a página pode ser inserido aqui para uso na página de artigo único. Ele aparece na aba do navegador e na área `<head>...</head>` da página. Será usado pelos motores de busca.
*Traduzido por openai.com*

