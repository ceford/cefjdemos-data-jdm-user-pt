<!-- Filename: J3.x:Plugin_Joomla_Update_Notification / Display title: Notificação de Atualização do Joomla! -->

## Ícone e Tarefa

Existem dois plugins com nomes semelhantes:

* **Ícone Rápido - Notificação de Atualização do Joomla!**
* **Tarefa - Notificação de Atualização do Joomla!**

O primeiro verifica atualizações do Joomla e notifica você quando visita a
página principal do Painel de Controlo. Ele tem um parâmetro: o Grupo deste
plugin (este valor é comparado com o valor do grupo usado nos módulos de Ícones Rápidos
para injetar ícones).

O segundo verifica periodicamente a disponibilidade de novas versões do
Joomla! Quando uma é encontrada, ele aciona uma tarefa para enviar um email
de lembrete de atualização para os Super Usuários. O email pode ser
personalizado através de *Sistema → Modelos de Email*.

Os emails enviados pelos plugins do Sistema de Notificação de Atualização do
Joomla! têm como objetivo ajudar a manter o software atualizado, o que
contribui para a segurança do site. As atualizações devem ser instaladas o
mais rapidamente possível após o seu lançamento.

## Status do Plugin

Os dois plugins separados podem estar Ativados ou Desativados.

- Com **Ícone Rápido ... Desativado** o ícone do *Verificando o Joomla ...* no Painel Principal permanece inativo, embora você possa selecioná-lo para ir até a página de atualização do Joomla.
- Com **Tarefa ... Desativada:** a tarefa de enviar um e-mail não é acionada.

## Parâmetros de Tarefa

No menu do Administrador, vá para **Sistema / Tarefas Agendadas** e selecione o item **Notificação de Atualização** na lista de *Tarefas Agendadas*. Há várias abas de parâmetros e informações ali para visualizar e alterar, se apropriado.

### Frequência dos Emails de Notificação

A frequência de execução da tarefa é configurada para 24 horas por padrão. Isso significa que o site Joomla verificará se há atualizações para o núcleo e todas as extensões, plugins, módulos e templates instalados em intervalos de 24 horas. Um valor de 0 enviaria um email de atualização toda vez que o site fosse acessado. 0 é apenas para testes!

Note que a tarefa é acionada pela atividade no site. Se você for o único usuário, ela será acionada na sua próxima visita, caso essa ocorra após mais de 24 horas.

### Emails de Super Usuários

A notificação por email é enviada apenas para usuários que têm o privilégio de Super Usuário. Este campo permite selecionar quais Super Usuários receberão as notificações por email.

- Se deixado em branco, todos os Super Usuários do site receberão o email de notificação de atualização.
- Para limitar quais Super Usuários receberão a notificação de atualização, insira os endereços de email dos Super Usuários aqui. Se houver múltiplos endereços de email de Super Usuários, use uma vírgula para separá-los.

### Idioma do Email

A notificação pode ser enviada em qualquer idioma que você esteja usando no seu site.

- **Auto (padrão)** envia o email de notificação de atualização no idioma padrão do site.
- Selecionar um idioma diferente de Auto (padrão) força o envio dos emails de notificação de atualização nesse idioma específico.

## Dicas

- Para desativar as notificações de atualização do Joomla! por e-mail, basta desabilitar o plugin.
- O assunto e o texto do corpo do e-mail podem ser modificados na lista de **Sistema / Modelos de E-mail**. Selecione o item **Joomla: Notificação de Atualização**. Em um site multilíngue, estará no idioma atualmente selecionado.
  - **Assunto** Note que os espaços reservados {SITENAME} – {URL} são substituídos quando a mensagem é enviada.
  - **Corpo** Mais espaços reservados lá também!

*Traduzido por openai.com*

