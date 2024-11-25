<!-- Filename: J4.x:Workflow / Display title: Fluxo de Publicação  -->

## Introdução

No Joomla, um fluxo de trabalho é uma sequência de etapas na vida de um artigo, desde a concepção até a descontinuação. As etapas geralmente são realizadas por diferentes indivíduos com diferentes responsabilidades. Por exemplo, no mundo dos jornais, um subeditor pega uma história de um repórter e verifica a precisão, gramática, legibilidade e tamanho, e talvez mais. O subeditor passará então a história para o editor, que pode aceitar ou rejeitar a história, decidir onde colocá-la no jornal, e assim por diante.

O componente de Fluxo de Trabalho é usado para adicionar **estágios** aos artigos para aprimorar os estados estáticos (não publicado, publicado, descartado e arquivado) com **transições**. Os estados estáticos e transições são registrados separadamente para que os Fluxos de Trabalho possam ser ativados ou desativados conforme necessário, sem afetar o estado dos itens de conteúdo. Os Fluxos de Trabalho são ativados ou desativados na aba *Integração* da página de *Opções de Artigos*.

Existe uma página de tutorial contendo etapas para a criação de um exemplo de fluxo de trabalho: [Cenários de Fluxo de Trabalho](jdocmanual?article=user/workflows/workflow-scenarios).

## Termos & Definições

- *Fluxo de Trabalho:* Um fluxo de trabalho é uma sequência completa de etapas. Vários fluxos de trabalho diferentes podem ser criados para diferentes finalidades. O componente Fluxo de Trabalho contém um *Fluxo de Trabalho Básico* e os dados de exemplo do Blog têm um *Fluxo de Trabalho de Blog* mais complexo.
- *Etapa:* Uma etapa é um local dentro de um fluxo de trabalho. Por exemplo, um artigo não publicado pode estar na Etapa 1: Em Preparação ou na Etapa 2: Pronto para Revisão, e assim por diante. É a etapa do item que é registrada no banco de dados.
- *Transição:* Uma transição é uma mudança de uma etapa para outra, muitas vezes para a próxima no fluxo de trabalho, mas pode ser para a etapa anterior ou inicial.
- *Estado:* O estado de um artigo pode ser não publicado, publicado, excluído ou arquivado. Um estado pode ser alterado ao executar uma transição de fluxo de trabalho, desde que o usuário tenha permissão para alterar o estado.
- *Categoria:* Quando fluxos de trabalho estão em uso, um fluxo de trabalho específico pode ser selecionado para uma categoria na aba *Fluxo de Trabalho* do formulário *Artigo: Editar Categoria*.

## A Lista de Fluxos de Trabalho

Quando os fluxos de trabalho estão habilitados, a lista de fluxos de trabalho disponíveis pode ser vista selecionando **Conteúdo → Fluxos de Trabalho** no menu do Administrador.

![Lista de Fluxos de Trabalho](../../../en/images/workflows/workflows-list.png)

- O **Status** de um fluxo de trabalho pode ser Ativado, Desativado ou Excluído.
- O **Nome** é um link para o formulário de edição do fluxo de trabalho.
- O item **Padrão** é usado para novos itens que não estão atribuídos a uma categoria que possui um fluxo de trabalho definido.
- O item **Etapas** é um botão que mostra o número de etapas e um link para a lista de etapas do fluxo de trabalho.
- O item **Transições** é um botão que mostra o número de transições e um link para a lista de transições do fluxo de trabalho.
- O **ID** é o valor numérico do fluxo de trabalho usado internamente.

## Etapas

As etapas são acessadas via a lista de *Workflows*. Selecione o botão amarelo
que mostra o número de etapas.

![Lista de etapas de workflow](../../../en/images/workflows/workflow-stages-list.png)

Selecione o nome de uma etapa para editá-la.

![Formulário de edição de etapa do workflow](../../../en/images/workflows/workflow-stage-edit.png)

## Transições

Nos fluxos de trabalho, os artigos transitam de uma etapa para outra. As transições são geridas através da lista de *Transições*.

![A lista de transições](../../../en/images/workflows/workflow-transitions-list.png)

- O *Estágio Atual* define onde esta transição começa.
- O *Estágio Alvo* define onde esta transição termina.

### Estágios de Transição

Os estágios *Atual* e *Alvo* são configurados no formulário *Editar Transição*:

![Formulário de edição de transição](../../../en/images/workflows/workflow-transition-edit.png)

A aba *Ações de Transição* é usada para definir o *Estado* que o item terá após a conclusão da transição.

![Aba de ações do formulário de edição de transição](../../../en/images/workflows/workflow-transition-edit-actions-tab.png)

- **Estado de Destaque** Se o item será ou não *Destacado*.
- **Estado de Publicação** Selecione da lista o estado alvo.

A aba *Notificações de Transição* é usada para definir se uma notificação é enviada para esse estado. Por exemplo, se um artigo foi escrito mas precisa ser revisado, um e-mail pode ser enviado para notificar o editor.

![Aba de notificações do formulário de edição de transição](../../../en/images/workflows/workflow-transition-edit-notifications-tab.png)

- **Enviar Notificação** Se definido como *Sim*, campos extras aparecem.
- **Texto de Mensagem Adicional** Adicione texto adicional à mensagem ou use uma string de idioma para tornar o texto da mensagem traduzível.
- **Grupos de Usuários** Selecione quem receberá a notificação, por exemplo, todos os usuários no grupo de usuários *Editor*.
- **Usuários** Selecione usuários individuais para receber esta notificação.

### Permissões

A aba de permissões controla o acesso a esta transição por grupos de usuários selecionados. Normalmente, as permissões são herdadas das configurações de permissão em *Artigos: Opções*.

### Plugins de Transição de Fluxo de Trabalho

Os plugins de fluxo de trabalho são usados para ações invocadas por transições. Vá para **Sistema → Plugins** e altere o filtro *- Selecionar Tipo -* para *workflow*. Cada um desses plugins pode ser desativado se não for necessário.

![Lista de plugins de fluxo de trabalho](../../../en/images/workflows/workflow-plugins.png)

- **Destaque de Fluxo de Trabalho** Esta ação implementa a mudança do status *Destacado* de um artigo de *Sim* para *Não*.
- **Notificação de Fluxo de Trabalho** Esta ação implementa a notificação de um usuário que uma mudança de estágio requer atenção.
- **Publicação de Fluxo de Trabalho** Esta ação implementa a mudança de estado de um artigo de um para outro dos estados *Publicado*, *Não publicado*, *Descartado* ou *Arquivado*. Se o usuário não tiver permissão para mudar de estado, a operação falhará com uma mensagem explicativa. A transição que solicitou a mudança de estado ainda será realizada!

## Categorias

Os artigos podem ser atribuídos a categorias. Elas correspondem a um determinado fluxo de trabalho e podem ser personalizadas de várias maneiras. Você pode definir um status, categoria pai e também restringir o acesso, assim como as permissões. Esta opção não está na tela de fluxos de trabalho. Para essa opção, você precisa ir para **Conteúdo → Categorias**. Uma vez lá, abra qualquer categoria e você verá uma aba de *Fluxos de Trabalho*.

![Edição de categoria de artigos com fluxo de trabalho](../../../en/images/workflows/workflow-categories-blog.png)

### Exemplo

Certos artigos precisam estar disponíveis apenas para administradores ou usuários de uma categoria superior.

- Crie uma categoria chamada *Restrito*
- Defina todas as permissões como *Permitido* para administradores ou superiores. 
- Mova os artigos em questão para a categoria *Restrito*.

Isso evita a necessidade de definir permissões em artigos individuais.

## Controle de Versões

Quando o fluxo de trabalho está ativado, os campos geridos pelo fluxo de trabalho são excluídos do controle de versões (como "estado" e "destaque") para evitar conflitos de permissão.

## Exemplos

Alguns exemplos específicos estão disponíveis para ilustrar como usar Fluxos de Trabalho para diferentes grupos de usuários:

- [Exemplo 1](jdocmanual?article=user/workflows/workflow-example-1) utiliza os grupos de usuários padrão Autor, Editor e Publicador para preparar itens para um Boletim Informativo.
- [Exemplo 2](jdocmanual?article=user/workflows/workflow-example-2) faz uso de grupos de usuários personalizados para preparar itens para reuniões do comitê.

*Traduzido por openai.com*

