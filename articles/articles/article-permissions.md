<!-- Filename: J6.x:Access_Control / Display title: Artigo: Editar - Permissões -->

## Introdução

O Joomla oferece um sistema sofisticado de *Controle de Acesso* baseado em *Níveis de Acesso* e *Grupos de Usuários*. Ele é descrito no artigo sobre [Controle de Acesso](jdocmanal?article=user/users/access-control) na seção de *Usuários* deste manual.

A descrição aqui é para a aba *Permissões* do formulário *Artigo: Editar*. Suas configurações podem parecer estranhas a menos que você esteja familiarizado com o sistema de Controle de Acesso do Joomla.

## Captura de Tela

![A guia de permissões do artigo com autor selecionado](../../../en/images/articles/articles-edit-permissions-tab.png)

Pode ser surpreendente que um Autor não pareça ter permissão para Editar um artigo!

## Grupos de Usuários do Frontend e Backend

Se você não está familiarizado com os Grupos de Usuários padrão do Joomla, é útil saber que
*Autor*, *Editor* e *Publicador* são grupos de usuários do frontend. Eles não podem entrar no backend. O trabalho deles de criar, editar e publicar artigos é realizado com formulários de edição de artigos do frontend. *Gerente* e *Administrador* são grupos de usuários com acesso tanto ao frontend quanto ao backend e podem editar artigos usando formulários de edição do backend ou do frontend.

## Acesso de Edição do Autor

Por que o formulário de Permissões aparece mostrando *Editar* como **Não Permitido (herdado)**
para o grupo de Autor?

Há uma explicação simples. Se você fechar o formulário de edição e for para a
página *Artigos: Opções* através do botão *Opções* na lista de *Artigos* na Barra de Ferramentas,
a aba de *Permissões* lá mostra que um membro do grupo de Autor tem 
permissões adicionais: *Criar* e *Editar Próprios*. Estas são as permissões que 
permitem a um autor criar artigos e editar os seus próprios artigos.

Portanto, as permissões no formulário *Artigos: Editar* não permitem que um membro do
grupo de Autor edite artigos criados por outra pessoa.
*Traduzido por openai.com*

