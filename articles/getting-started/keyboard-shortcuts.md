<!-- Filename: Keyboard_Shortcuts / Display title: Atalhos de Teclado -->

## Introdução

O teclado pode ser usado na interface do Administrador para invocar algumas das ações normalmente realizadas com um mouse ou touchpad. Por exemplo, há atalhos de teclado para salvar a página atual, ir para o *Painel Inicial* ou abrir um formulário de *Opções*.

Existe uma visão geral de todos os atalhos, que é aberta pela seleção sequencial das teclas **J** e **X** (não ao mesmo tempo e sem usar a tecla Shift normalmente usada para capitalização). A menos que você altere as configurações do plugin, você deve pressionar as teclas dentro de 2 segundos.

O recurso está habilitado por padrão. Ele pode ser desabilitado ou configurado em **Administrador → Sistema → Plugins → Sistema - Atalhos de Teclado**. Atualmente, a única configuração é o tempo limite: quanto tempo o sistema aguardará pela sua próxima entrada de tecla. Por padrão, ele aguarda 2000 milissegundos (2 segundos).

## Atalhos Padrão no Joomla

- J + A - Salvar conteúdo atual
- J + S - Para Salvar e Fechar
- J + Q - Cancela a página atual
- J + N - Pressiona o botão *Novo*
- J + F - Foca no campo de Pesquisa
- J + O - Vai para Opções
- J + H - Abre a janela de Ajuda (pode acionar um aviso de pop-up do navegador)
- J + M - Alterna a barra de menu
- J + X - Exibe uma lista de Atalhos disponíveis
- J + D - Vai diretamente para o Painel Inicial

## Atalhos de Terceiros - Informações para Desenvolvedores

Outros desenvolvedores também podem adicionar seus atalhos. O plugin Joomla chama o evento *onLoadShortcuts*, que pode ser utilizado por outros plugins também. O evento precisa ser adicionado à lista de *getSubscribedEvents* dentro do plugin. A função atribuída pode se parecer com isto:

```php
    public function onLoadShortcuts(EventInterface $event): void {
       $shortcuts = $event->getArgument('shortcuts');
       $exampleShortcuts = array('example' => (object)['shortcut' => 'E', 'title' => 'Grande Exemplo', 'selector' => '#menu-collapse']);
       $event->setArgument('shortcuts',  array_merge($shortcuts, $exampleShortcuts));
    }
```
Preste muita atenção à parte do array_merge: Quando os atalhos já existentes não são mesclados com os novos, os antigos são sobrescritos.

Os desenvolvedores podem fornecer um array com objetos de atalho:

    { shortcut: string, selector: string, title: string }

- O *Atalho* precisa ser uma entrada de teclado, separada por um sinal de mais, por exemplo, `Y` ou `ALT + Z + 7` (atualmente não há realmente nenhum filtro). Tenha em mente que toda sequência de atalho começará com **J**.
- *Seletor* são seletores CSS ou URLs para especificar o alvo. Quando é um elemento de entrada, o atalho dá foco, como é o caso do campo de busca. Caso contrário, o elemento será clicado ou o URL será chamado.
- O *Título* será exibido na visão geral. Ele poderia ser, por exemplo, o nome do alvo.

## Razões para usar J + X

Alguns podem se perguntar sobre a decisão de usar atalhos sequenciais ou a
**J** como início, em vez de Ctrl ou outra coisa. As principais razões são
acessibilidade e a evitação de interrupção por outros softwares. Por
exemplo, *Ctrl + S* seria bom para salvar um artigo, mas já é
usado pelos navegadores. O mesmo pode acontecer com leitores de tela ou gerenciadores de senhas. Assim, a opção mais segura foi usar algo específico do Joomla,
como o **J** no início.

Agora, o outro problema é que nem sempre é possível pressionar mais
de uma tecla ao mesmo tempo. O Windows possui o modo de Teclas de Aderência para isso, mas ele só funciona para teclas modificadoras como Shift, Ctrl e Alt. Assim, o
plugin usa a entrada sequencial desde o início, o que o torna
utilizável por mais pessoas, mesmo sem a ajuda de modos do sistema operacional.

*Traduzido por openai.com*

