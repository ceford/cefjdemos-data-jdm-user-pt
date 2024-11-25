<!-- Filename: J6.x:_Article_Publishing / Display title: Artigo: Editar - Publicação -->

## Introdução

Uma parte essencial de um Sistema de Gerenciamento de Conteúdo (CMS) é sua capacidade de entregar conteúdo a usuários selecionados por períodos selecionados. O Joomla! faz isso com níveis de acesso e datas de início e término de publicação.

As datas de início e término podem ser definidas para artigos *Destacados* e artigos *Não Destacados* igualmente. Por exemplo, um novo artigo pode ser destacado por um período definido, digamos 30 dias, após o qual ele se tornaria um artigo comum não destacado. Ele desapareceria dos layouts de artigos destacados, mas ainda apareceria em outros layouts de Blog ou Artigo Único.

Na maioria das vezes, os artigos são publicados no dia em que são criados e permanecem assim até serem despublicados, arquivados ou excluídos.

## Captura de Tela

![A guia de publicação do formulário de edição do artigo](../../../en/images/articles/articles-edit-publishing-tab.png)

O painel de *Metadados* é explicado em um artigo separado. Este artigo aborda o painel de *Publicação*.

## Painel de Publicação

Alguns dos campos no formulário são destinados para informação e não podem ser alterados
diretamente no formulário. Eles são exibidos com fundos cinza. Outros campos podem ser
alterados se necessário.

### Iniciar Publicação

Este campo é definido para a data e hora atuais quando o artigo é salvo pela primeira vez.
Se você deseja que o artigo fique embargado até uma data e hora futuras, pode
definir seu valor usando a ferramenta de Calendário ou editando diretamente os valores do campo.

### Finalizar Publicação

Por padrão, este campo está em branco. Se você quiser que o artigo desapareça
após uma data e hora especificadas, use a ferramenta de Calendário ou digite uma data e
hora futuras diretamente no campo. Nesse ponto, o artigo desaparecerá do
site. Na lista de Artigos, ele será marcado como *Publicado, mas Expirado*.

### Iniciar Destaque

Se o artigo estiver marcado como um *Artigo em Destaque*, este campo pode ser definido para que 
ele apareça em um layout de *Artigos em Destaque* na data especificada. Note que a
data não será salva se o artigo não estiver marcado como um *Artigo em Destaque*.

### Finalizar Destaque

Se o artigo estiver marcado como um Artigo em Destaque, este campo pode ser definido para que
ele desapareça de um layout de *Artigos em Destaque* na data especificada. O
artigo permanece publicado e ainda pode aparecer em outros layouts. Na lista de Artigos,
ele será marcado como *Destacado, mas Expirado*.

### Data de Criação

Esta data é definida quando o artigo é salvo pela primeira vez. Você pode querer mudá-la
se tiver criado uma série de artigos em ordem aleatória e desejar organizá-los
em uma ordem de data de criação.

### Criado Por

O ID do Usuário do criador é salvo na hora da criação e o Nome desse usuário aparece neste campo. 
Você pode mudar o Criador selecionando o ícone de pessoa para revelar um diálogo pop-up 
*Selecionar Usuário* de onde você pode encontrar e selecionar um usuário diferente.

### Criado por Alias

Se você não deseja que o Nome de Usuário do criador apareça no bloco de informações do
artigo, pode inserir um Alias aqui. Insira seu alias, salve o artigo e 
verifique com o botão de Visualização na Barra de Ferramentas.

## Agendamento da Publicação de um Artigo

Por padrão, os artigos são definidos como **Publicado** assim que são salvos. O salvamento inicial do artigo cria as datas de **Data de Criação** e **Início da Publicação**.

Agendar um artigo envolve definir manualmente uma data e hora de **Início da Publicação** para adiar a publicação. Você também pode definir datas e horas para **Concluir a Publicação**.

**Nota:** Para que o agendamento funcione, o **Status** do artigo deve estar definido como **Publicado**.

Antes da data de Início da Publicação, os artigos são considerados **Pendentes** e, após a data de Conclusão da Publicação, são considerados **Expirados**. Apesar de o artigo em si estar definido como publicado, o Joomla usa as configurações de início e conclusão para substituir o estado padrão de publicado.

Os valores de data e hora podem ser digitados nos campos de data ou selecionados com a ferramenta de Calendário, aberta ao selecionar o ícone de calendário no final de cada campo de data.

![Datas de Publicação](../../../en/images/articles-access/article-schedule-publishing.png)

O calendário se move entre dias, meses e anos usando as setas do teclado para frente, para trás, para cima e para baixo. O botão **Hoje** define a data atual. O botão **Limpar** limpa a data e a hora.

* Selecione a data desejada.
* Defina o horário usando as caixas de seleção.
* Selecione o botão **Fechar** do Calendário para definir a data e hora selecionadas.
* Selecione **Salvar** ou **Salvar & Fechar** na barra de ferramentas para salvar as alterações.

## Ícones de Visualização de Lista

Na lista de Artigos, o ícone de *Destacado* é geralmente um círculo cinza ou uma estrela amarela. Da mesma forma, o ícone de *Status* costuma ser um tique verde ou uma cruz cinza. Cada um possui um Tooltip e a ação usual é alternar o estado.

- Publicado e está Atualizado: <span class="icon-publish" aria-hidden="true"></span>
- Não Publicado: <span class="icon-unpublish" aria-hidden="true"></span>
- Destacado: <span class="icon-featured" aria-hidden="true"></span>
- Não Destacado: <span class="icon-unfeatured" aria-hidden="true"></span>

Os ícones para artigos com datas de início e término agendadas são diferentes.

- Publicado, mas está Pendente: <span class="icon-pending" aria-hidden="true"></span>
- Publicado, mas Expirado: <span class="icon-expired" aria-hidden="true"></span>
- Destacado, mas está Pendente: <span class="icon-pending" aria-hidden="true"></span>
- Destacado, mas Expirado: <span class="icon-expired" aria-hidden="true"></span>

Em cada caso, um Tooltip mostra informações extras sobre as datas agendadas.

## Dicas

- Você pode agendar a publicação de artigos pela interface frontal também.
- Também é possível agendar através do item de menu do artigo.
- O agendamento também está disponível para Contatos e Módulos.

*Traduzido por openai.com*

