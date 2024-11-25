<!-- Filename: J4.x:User_Password_Reset / Display title: Redefinição de Senha do Usuário   -->

## Redefinição do Usuário

Se os seus usuários tiverem permitida a entrada no Site e um usuário não conseguir lembrar seu Nome de Usuário ou Senha, é melhor exigir que o indivíduo redefina as credenciais por conta própria usando os links no formulário de Login:

![módulo de login do usuário do site](../../../en/images/users/user-site-login-module.png)

Em cada caso, selecionar um link leva a um formulário para inserção do endereço de e-mail associado à conta:

![formulário de redefinição de senha esquecida do site](../../../en/images/users/user-forgot-password-reset.png)

Todo o processo é realizado pelo usuário sem necessidade de intervenção de um Administrador. Este é o formulário de verificação de senha perdida:

![formulário de confirmação de senha esquecida do site](../../../en/images/users/user-forgot-password-confirm.png)

E, finalmente, o usuário precisa inserir uma nova senha:

![formulário de redefinição de senha completada do site](../../../en/images/users/user-forgot-password-complete.png)

## Redefinição pelo Administrador

Se houver apenas o login de Administrador, a redefinição da senha de um usuário deve ser realizada por um Super Usuário ou Administrador. Se for o único Super Usuário que não conhece as credenciais de login, consulte o artigo separado sobre Recuperação de Senha do Administrador. Caso contrário:

- Selecione **Usuários → Gerenciar** no menu do Administrador ou selecione *Usuários* no painel do Site do Dashboard Inicial.
- Encontre o usuário que precisa de redefinição de senha.
- Selecione o **Nome** vinculado para abrir o formulário *Usuário: Editar*.
- Digite uma nova senha nos campos Senha e Repetir Senha.
- Defina o campo **Exigir Redefinição de Senha** como *Sim*.
- **Salvar & Fechar**

![formulário de edição de usuário dos administradores](../../../en/images/users/users-edit-user-john-doe.png)

Você precisará enviar um e-mail para o usuário com a nova senha provisória em texto simples. Após o login, o usuário poderá ver a página inicial do site, mas qualquer tentativa de navegar para outra página levará o usuário ao formulário de nova senha.

*Traduzido por openai.com*

