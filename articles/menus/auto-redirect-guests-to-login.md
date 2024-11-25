<!-- Filename: Auto_redirect_guests_to_login / Display title: Redirecionar automaticamente convidados para o login  -->

## Funcionalidade Desejada

Suponha que você tenha algumas opções de menu que exigem que um usuário esteja logado, como *Enviar um Artigo*. Você gostaria que todos os usuários pudessem ver o item de menu restrito, independentemente de estarem logados ou não. O comportamento desejado é o seguinte:

* Se o usuário estiver logado, ele vai diretamente para o item de menu restrito.
* Se o usuário não estiver logado, ele é apresentado ao formulário de login e, após um login bem-sucedido, continua para a página restrita.
* Se o usuário não estiver registrado, ele tem a opção de se registrar ou navegar para outra página.

## Solução

Aqui está como você pode fazer isso no Joomla!.

1. Crie um novo menu na lista de **Menus**, nomeado, por exemplo, **Menu Oculto**.
2. Adicione qualquer item de menu que será acessível apenas para usuários registrados (por exemplo, *Enviar um Artigo*). Defina os níveis de acesso necessários desses itens de menu para **Registrado**.
3. NÃO crie um módulo para o *Menu Oculto*. Ele não será exibido em nenhuma página, então não precisa de um módulo.
4. Crie seu menu *real*, nomeado, por exemplo, **Menu do Site**, e o item de menu que será exibido para todos os usuários, por exemplo, *Enviar um Artigo*.
    - O item de menu terá um tipo de item de menu do tipo **Alias de Item de Menu** encontrado em **Links do Sistema**.
    - O parâmetro *Item de Menu* será o item de menu *Enviar um Artigo* no *Menu Oculto**.
    - O Nível de Acesso para este item de menu será **Público**, pois todos precisam ser capazes de ver e usá-lo.
5. Crie um módulo para o *Menu do Site* assim como você faz para qualquer menu.
6. Se você quiser sub-menus, certifique-se de ter adicionado os itens de sub-menu no **Menu do Site** e não no **Menu Oculto**.

Agora, quando um visitante (usuário não logado) acessa a opção de menu *Enviar um Artigo*, ele é redirecionado para a página de login. Se o login for bem-sucedido, o usuário é redirecionado para a página restrita **Enviar um Artigo**. Se já estiver logado, o redirecionamento é imediato.

## Exemplo

Para os seguintes itens de menu:

1. Início
2. Blog
3. Wiki
4. Diretório
5. Classificados
6. FAQs
7. Loja
8. Contate-Nos

Todos os itens do menu devem ser visíveis por todos no front-end, mas os itens 3, 4, 5, 6 e 7 devem ser acessíveis apenas para usuários **Registrados**.

Neste caso, os itens de menu 3 a 7 estão localizados no menu *oculto* com o parâmetro de **Acesso** configurado para **Registrado**. Os itens 3 a 7 têm itens de menu *Alias* no menu *real* com seus parâmetros de **Acesso** configurados para **Público**.

*Traduzido por openai.com*

