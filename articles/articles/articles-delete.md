<!-- Filename: J4.x:Deleting_an_Article / Display title: Artigos: Excluir -->

## Introdução

No Joomla, a exclusão de um artigo é um processo em duas etapas. A primeira etapa envia o artigo para a *Lixeira*, de onde ele pode ser restaurado. A segunda etapa o exclui da Lixeira, após o que o artigo é removido permanentemente.

## Considerações

Considere por que você deseja excluir o artigo:

- Ele não é mais necessário? Se sim, a exclusão provavelmente é a
  ação correta.
- É um artigo que pode ser reutilizado no futuro? Pode ser muito
  frustrante saber que você tinha um artigo que seria um bom ponto de
  partida para outro, mas o excluiu – considere arquivá-lo
  em vez disso.

## Movendo o Artigo para a Lixeira

- Selecione **Conteúdo -> Artigos** no menu do Administrador.
- Marque a caixa de seleção para escolher o artigo que deseja excluir. Um artigo 
  **deve** ser selecionado para habilitar o botão **Ações** na barra de ferramentas.
- Selecione o botão **Ações** na Barra de Ferramentas.
- Selecione **Lixeira** no menu suspenso.

![Artigo selecionado para exclusão](../../../en/images/articles/articles-selected-to-trash.png)

Haverá uma mensagem de confirmação e o artigo terá desaparecido da lista atual de artigos, pois normalmente não inclui itens na lixeira.

## Filtrar para Restaurar ou Excluir

Nesta etapa do processo, o artigo ainda não foi completamente removido. Esta é uma funcionalidade útil caso você tenha deletado o artigo por engano.

Para ver a lista de artigos excluídos:

- Selecione o botão **Opções de Filtro** para abrir a lista de filtros.
- Selecione **Excluídos** na lista *-- Selecionar Status --*.

![Visualização da lixeira de artigos](../../../en/images/articles/articles-trash-list.png)

### Para Restaurar

Se você mudou de ideia, pode selecionar o símbolo de **Excluídos** na coluna *Status*. O artigo voltará para o estado *Publicado* e desaparecerá da lista de artigos excluídos.

### Para Excluir

Selecione a caixa de seleção na coluna esquerda dos dados do artigo. Isso ativará os botões *Ações* e *Excluir* na Barra de Ferramentas. O botão *Ações* permite aplicar a mesma ação a todos os artigos selecionados. Se você tiver certeza absoluta:

1. Selecione o botão *Excluir* na Barra de Ferramentas. Uma caixa de mensagem aparecerá:<br>
   <div class="alert alert-light">
   Você tem certeza de que deseja excluir? Confirmar excluirá permanentemente o(s) item(ns) selecionado(s)!</div>
2. Selecione **OK** para confirmar e o artigo será excluído da Lixeira. O artigo será excluído do banco de dados. Ele se foi, permanentemente!
3. Selecione o botão **Limpar** ao lado de **Opções de Filtro** para retornar à lista não filtrada de **Artigos**.


## Dicas

- Lembre-se, excluir um artigo não é o mesmo que arquivar um artigo.
  Uma vez que ele foi excluído da Lixeira, ele se foi para sempre.
- Se você excluir um artigo por engano, mas não o tiver excluído da
  Lixeira, você pode mudar seu status. Você tem as opções de defini-lo como
  *Arquivado*, *Publicado* ou *Não Publicado*.
- O Joomla não permitirá que você salve mais de um artigo com o mesmo
  alias. Se um artigo for excluído, mas deixado na Lixeira, ele ainda existe. Se
  você tentar salvar um artigo e receber um erro indicando que o alias
  já existe, pode ser que ele esteja na Lixeira! Portanto, você deve
  esvaziá-lo da lixeira ou pode inserir um alias diferente para seu novo
  artigo.
- O Joomla mantém versões anteriores de um artigo, a menos que as Versões estejam desativadas. Se
  você estiver excluindo um artigo porque de alguma forma ele "quebrou", tente revertê-lo
  para uma versão anterior.

*Traduzido por openai.com*

