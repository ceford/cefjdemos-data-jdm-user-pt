<!-- Filename: J4.x:How_to_Show_a_Calendar_Month_List_of_Archived_Articles_Using_a_Module / Display title: Artigos Arquivados -->

## Introdução

Arquivar artigos é uma das maneiras que o Joomla! ajuda a gerenciar os artigos de um site, pois ajuda a reduzir a desordem no backend. Mas quais visitantes do site devem ser capazes de acessar artigos arquivados?

Uma maneira de fazer isso é mostrar uma lista de meses em um calendário dos artigos arquivados usando um dos Módulos principais do Joomla. Neste exemplo, um **Módulo de Artigos Arquivados** será configurado para ser exibido na barra lateral do site.

## Criar o Módulo *Artigos - Arquivados*

Use um dos seguintes métodos:
* Selecione o item **Módulos** do Painel de Controle. Ou...
* Selecione **Conteúdo / Módulos do Site** no menu do Administrador.
* Selecione o item **Artigos Arquivados** da lista de Módulos (Site).

Isso criará o novo módulo e abrirá o módulo para configuração.

## Configurando o Módulo

Para o uso padrão do módulo, há apenas algumas configurações:

- **Título** Insira um nome para o módulo.
- **\# de Meses** Defina o número de meses que deseja exibir. Estes
aparecerão como links no frontend. Defina usando as setas para cima/baixo ou
insira diretamente um número no campo.
- **Exibir/Ocultar Título** Escolha se deseja ou não mostrar o título alternando para
*Exibir* ou *Ocultar*.
- **Posição** Defina uma posição onde você deseja exibir o módulo na
interface do usuário. As posições são ditadas pelo seu template. Este exemplo usa a
posição *Barra Lateral Direita* do template Cassiopeia do Joomla.
- **Status** Por padrão, o status do módulo é **Publicado**. Outras opções são
**Não Publicado** e **Descartado**.
- **Iniciar Publicação** Você pode agendar o início da publicação do
módulo.
- **Concluir Publicação** Você pode agendar quando parar de publicar o
módulo.
- **Acesso** Se você quiser controlar quem pode ver o módulo na
interface do usuário, pode escolher um nível de acesso.
- **Ordenação** Usado para controlar onde o módulo é exibido dentro da
posição que você selecionou. Por exemplo, você pode ter vários
módulos na barra lateral e querer que este seja o primeiro ou último – ou
em algum lugar entre outros na barra lateral. Pode ser um pouco confuso no
início, pois o campo mostra uma posição numerada e um nome de módulo. O nome
pode ser de um módulo que não está publicado. A coisa a lembrar é que o
número mais baixo estará no topo e o número mais alto estará na parte inferior.
- **Nota** Pode ser útil usar o campo de nota se, por exemplo, você estiver
usando o mesmo tipo de módulo em vários lugares.

### Aba de Atribuição do Menu

Por padrão, o módulo será publicado **Em todas as páginas**.

Alternativamente, você pode escolher através de uma lista suspensa **Sem páginas**, **Apenas
nas páginas selecionadas** ou **Em todas as páginas exceto as selecionadas**. As
duas últimas opções oferecem uma árvore de menus dos menus usados no
site onde você pode selecionar/deselecionar páginas.

### Outras Configurações

A aba **Avançado** possui configurações relacionadas ao layout do módulo quando ele é
exibido.

A aba **Permissões** permite que você controle o que os grupos de usuários podem fazer com
o módulo.

## Publicando o Módulo

Quando estiver pronto, selecione o botão **Salvar e Fechar**.

O módulo será publicado na barra lateral do site e exibirá uma lista de links ditada pelo número de meses a serem exibidos definidos no módulo.

![Exemplo de Módulo de Artigos Arquivados](../../../en/images/modules/modules-archived-articles.png)

## Dicas

Quanto mais artigos arquivados você tiver, maior será o número de links exibidos pelo módulo. Pode ser mais apropriado limitar o número de links usando categorias ou você pode usar vários módulos de Artigos Arquivados nomeados de acordo.

*Traduzido por openai.com*

