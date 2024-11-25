<!-- Filename: J6.x:Workflow_Scenarios_Example_1 / Display title: Exemplo de Fluxo de Trabalho 1  -->

## Introdução

Um fluxo de trabalho consiste em *etapas* e *transições* entre essas etapas. Para qualquer artigo, é a etapa atual que é registrada no banco de dados e usada para identificar o fluxo de trabalho e as transições usadas por esse fluxo de trabalho.

Um único site pode ter muitos fluxos de trabalho. Aqui, um *Fluxo de Trabalho de Newsletter* é usado como exemplo para explicar como três indivíduos com diferentes funções podem estar envolvidos na produção de um artigo de newsletter. O exemplo usa os grupos de usuários padrão do Joomla: Autor, Editor e Publicador. Isso tem um problema: um Autor só pode ver artigos Publicados e, portanto, não pode reeditar artigos Não Publicados. Um método para evitar esse problema é abordado em [Exemplo 2](jdocmanual?article=user/workflows/workflow-example-2).

![Lista de fluxos de trabalho](../../../en/images/workflows/example-1-workflows-list.png)

Observe que o *Fluxo de Trabalho Básico* está definido como *Padrão*. Isso pode ter consequências problemáticas abordadas mais adiante neste artigo! 

## Os Usuários

- *Arthur* é um usuário atribuído ao **Grupo de Autores** do Joomla. Ele pode criar novos artigos e editar seus próprios artigos, mas não pode editar artigos escritos por outros usuários ou alterar o status dos artigos. Portanto, ele não pode publicar seus próprios artigos. Seu trabalho é redigir novos artigos.
- *Eddie* é um usuário atribuído ao **Grupo de Editores** do Joomla. Ele pode editar artigos criados por qualquer outro usuário, incluindo por Arthur e por ele mesmo. Ele também não pode alterar o estado de um artigo. Seu trabalho é revisar os artigos submetidos por Eddie, verificar a precisão, a ortografia e a gramática, a qualidade das imagens e assim por diante.
- *Pru* é uma usuária atribuída ao **Grupo de Publicadores** do Joomla. Ela pode fazer tudo o que Eddie e Arthur podem fazer. Além disso, ela pode alterar o estado de um artigo. É trabalho dela decidir se um artigo é aceitável para publicação e publicá-lo.

## As Etapas

Existem quatro etapas neste Workflow:

![Lista de Workflows](../../../en/images/workflows/example-1-workflow-stages.png)

- **Rascunho** é a etapa criada por Arthur para um novo artigo.
- **Revisão** é a etapa onde Eddie assume para revisar o conteúdo.
- **Aprovar** é a etapa onde Pru decide se o artigo é bom o suficiente para ser publicado.
- **Publicar** é a etapa quando o artigo foi aprovado e publicado.

Os formulários de entrada de dados das etapas precisam de pouca explicação, apenas um Nome e uma Descrição.

## As Transições

São necessárias duas transições entre cada etapa: uma para reverter a etapa se mais trabalho for necessário na etapa anterior; e uma segunda para migrar para a próxima etapa. Transições extras são necessárias para lidar com o fim de um artigo:

![Lista de fluxos de trabalho](../../../en/images/workflows/example-1-workflow-transitions.png)

- **Rascunho/Revisão** para mover a etapa de Rascunho para Revisão.
- **Revisão/Rascunho** para reverter a etapa de Revisão para Rascunho.
- **Revisão/Aprovar** para mover a etapa de Aprovação para Revisão.
- **Aprovar/Revisão** para reverter a etapa de Aprovação para Revisão.
- **Revisão/Publicar** para mover a etapa para Publicado e mudar o status do artigo
  para *Publicado*.
- **Publicar** Para definir o estado do artigo como *Publicado* quando a transição é
  executada por um Autor ou Editor.
- **Despublicar** para mudar o status do artigo para *Não publicado*.
- **Arquivar** para mudar o status do artigo para *Arquivado*.
- **Lixo** para mudar o status do artigo para *Lixo*.

As últimas três transições permitem que Pru altere o status de um artigo quando já não é necessário.

### Editar Transição

O formulário de entrada de dados possui quatro abas, começando pela aba *Transição*:

![Lista de fluxos de trabalho](../../../en/images/workflows/example-1-edit-transition.png)

- **Nome** É melhor usar as etapas Atual e Alvo no nome.
- **Etapa Atual** A etapa antes da transição ocorrer.
- **Etapa Alvo** A etapa após a transição ter ocorrido.
- **Nota** Notas explicativas para ajudar a explicar a transição.

#### A aba *Ações de Transição*:

![Lista de fluxos de trabalho](../../../en/images/workflows/example-1-edit-transition-actions.png)

- **Estado em Destaque** Defina o estado de destaque que um item deve ter após
  executar esta transição. Deixe como *-Não Selecionado-* se o usuário que
  provavelmente executará esta transição não tiver permissão para destacar artigos.
- **Estado de Publicação** Defina o estado de publicação que um item deve ter após
  executar esta transição. Deixe como *-Não Selecionado-* se o usuário que
  provavelmente executará esta transição não tiver permissão para mudar o estado do artigo.

#### A aba *Notificações*:

![Lista de fluxos de trabalho](../../../en/images/workflows/example-1-edit-transition-notification.png)

- **Enviar Notificação** Defina como *Sim* quando notificações forem necessárias, por
  exemplo, quando Arthur precisar notificar Eddie de que um artigo está pronto para revisão.
- **Texto Adicional da Mensagem** Este é um texto adicional genérico para ajudar o
  destinatário.
- **Grupos de Usuários** Você pode escolher enviar a notificação para um ou mais grupos de usuários ou não e enviar notificações para indivíduos.
- **Usuários** Selecione usuários individuais da lista de usuários.

#### A aba *Permissões*:

Note que *Autor* tem *Executar Transição* definido como Permitido (Herdado). Não
altere essas configurações para outras transições que um Autor não deve usar, pois isso também afetará Editores e Publicadores.

## A Categoria do Artigo

Cada artigo é atribuído a um fluxo de trabalho na primeira gravação. Se o artigo for inicialmente atribuído a uma Categoria que tem um Fluxo de Trabalho selecionado, ele é atribuído a esse fluxo de trabalho. Caso contrário, ele é atribuído ao fluxo de trabalho padrão. Isso pode ser problemático, pois o componente de Fluxo de Trabalho não fornece um método para mudar o fluxo após ele ser alocado. Ele pode ser alterado por um Super Usuário utilizando a Ação em Lote na página de lista de Artigos.

### Criar uma Categoria de Newsletter

É necessária uma nova categoria de Newsletter para exibir a Newsletter como um Blog de Categoria e garantir que os artigos da Newsletter sejam atribuídos ao Fluxo de Trabalho da Newsletter.

![Lista de Fluxos de Trabalho](../../../en/images/workflows/example-1-newsletter-category.png)

## O Item de Menu do Boletim Informativo

Para que os visitantes do site vejam o Boletim Informativo, ele precisa ser a página inicial ou estar vinculado a um item de menu. Para seguir este exemplo, crie um novo item de menu do tipo *Blog de Categoria* usando a categoria *Boletim Informativo*.

Experimente o item de menu do site. É provável que apareça uma página em branco com esta mensagem:

<div class="alert alert-info">
Não há artigos nesta categoria. Se subcategorias forem exibidas nesta página, elas podem ter artigos.
</div>

## Entrar como Arthur

Lembra do Arthur, o Autor? Após o login, a página de Newsletter deve ter um botão rotulado como **Novo Artigo**. Selecione-o para compor um novo artigo.

### Compor um Artigo

Preencha o formulário de edição do artigo como faria para qualquer artigo. Exceto, antes de salvar pela primeira vez, olhe para a aba *Publicação*.

- **Estágio do Fluxo de Trabalho** deve ser definido como **Executar Transição** *Rascunho/Revisão*.
- **Categoria** deve ser definida como *Newsletter*.

Quando terminar de editar o artigo, selecione *Salvar* ou *Salvar e Fechar*.

<div class="alert alert-danger">Depois de fechar o artigo, Arthur não poderá editá-lo novamente porque usuários no grupo Autor não podem visualizar artigos Não Publicados.</div>

## Login como Eddie

Eddie, o Editor, tem permissão para visualizar artigos não publicados, de modo que a página de Newsletter exibe quaisquer itens não publicados para ele editar.

### Revisar o Artigo

Selecione o artigo rascunhado por Eddie e faça as alterações necessárias para melhorá-lo. Quando estiver satisfeito, na *Aba de Publicação*:

- **Estágio do Workflow** deve ser configurado para **Executar Transição** em *Revisão/Aprovação*.

Ao contrário de Arthur, que não pode ver seu artigo após salvá-lo, Eddie pode ver e editar o artigo novamente. Ele também pode definir a transição para a próxima etapa de Aprovação/Publicação. A transição funcionará, mas o artigo não será publicado, pois Eddie não tem permissão para Publicar.

## Login como Pru

Quando a etapa de Aprovação foi definida no fluxo de trabalho, Pru deveria ter recebido uma mensagem solicitando uma ação. Então, faça login como Pru para revisar o artigo e definir sua Etapa do Fluxo de Trabalho para **Executar Transição** *Publicar*. *Salvar & Fechar* o artigo para ver o resultado publicado. Faça logout para ver o resultado sem o link de Edição.

Reflexão: é necessário outra etapa para permitir que Pru reverta a etapa de Publicar para Revisar caso ela queira que Eddie corrija algo.

## Fluxo de Trabalho do Backend

Os grupos de usuários Autor, Editor e Publicador são destinados para uso no frontend. O problema para Arthur é que ele não pode acessar seus artigos em rascunho a partir do frontend porque seu grupo de usuários não tem acesso de visualização para artigos não publicados.

Você pode permitir o acesso ao backend para todos os membros desses grupos da seguinte forma:

- Vá para a página **Configuração Global**.
- Selecione a aba **Permissões**.
- Selecione *Autor* e defina **Login de Administrador** como *Permitido*.
- **Salvar**
- Vá para a página **Artigos: Opções**.
- Selecione sua aba **Permissões**.
- Selecione *Autor* e defina **Acesso à Interface de Administração** como *Permitido*.

Isso permitirá que Arthur, Eddie e Pru façam login no backend com acesso aos itens de Conteúdo. Um Painel de Controle Inicial muito reduzido:

![Painel de controle inicial para Arthur](../../../en/images/workflows/example-1-backend-home.png)

Mas Arthur tem acesso aos seus artigos em rascunho:

![Lista de artigos para Arthur](../../../en/images/workflows/example-1-backend-articles.png)

Observe que Arthur não pode editar o último item na lista porque não é um de seus próprios artigos. O título do artigo não está vinculado. Da mesma forma, Arthur não pode editar nenhuma das categorias existentes porque ele não tem permissão e elas também não estão vinculadas. Ele pode criar uma nova Categoria, mas ela está Não Publicada e ele não pode publicá-la!

## Correção para Fluxo de Trabalho Errado

Se você atribuir um artigo ao fluxo de trabalho errado, existem dois métodos disponíveis para corrigir o problema.

### Método de Super Usuário

- Vá para a lista de **Artigos**.
- Selecione a caixa de seleção do artigo com problema.
- Selecione o botão **Ações** na Barra de Ferramentas.
- Selecione o botão **Lote** da lista.
- Selecione **Mudar Etapa** no diálogo *Processar em Lote Artigos Selecionados*.
- Selecione um Fluxo de Trabalho e Etapa apropriados de destino.
- Selecione o botão **Processar**.

![Lista de artigos para Arthur](../../../en/images/workflows/example-1-backend-batch.png)

### Método Alternativo

Alternativamente, você pode editar uma tabela do banco de dados com phpMyAdmin ou similar.

Informações necessárias:

- O ID do artigo da última coluna na lista de Artigos.
- O ID de uma etapa no fluxo de trabalho desejado da última coluna da
  lista de Etapas do Fluxo de Trabalho que você gostaria de usar.

No phpMyAdmin:

- Procure a tabela #__workflow_associations para encontrar o item_id que contém
  o ID do seu artigo.
- Altere o valor stage_id para o ID da etapa que você pesquisou no fluxo de trabalho necessário.

Volte para sua lista de artigos e verifique se o item problema agora está usando 
o fluxo de trabalho correto.

*Traduzido por openai.com*

