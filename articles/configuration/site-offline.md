<!-- Filename: J4.x:Site_Offline / Display title: Site Fora do Ar -->

## Apenas Usuários do Site

Pode haver ocasiões em que você precise deixar seu site Joomla! indisponível para visitantes por um curto período de tempo. Há um simples interruptor de configuração chamado **Site Offline** para este fim, que pode ser alterado de **Não** para **Sim**, conforme necessário. Quando configurado como *Sim*, todos os visitantes do site veem uma página de mensagem offline com formulário de login. O formulário Offline padrão pode ser personalizado com uma imagem:

![Tela de site offline](../../../en/images/configuration/site-offline.png)

O interruptor Site Offline não se aplica à interface do administrador, e os usuários que podem fazer login no backend podem continuar a fazer login no frontend. O login no frontend é negado apenas para usuários nos grupos de usuários Registrado, Autor, Editor e Editor Chefe.

## Para Alternar Offline

- Selecione **Painel Inicial → Configuração Global** no menu do Administrador.
- Na aba **Site**, altere o interruptor **Site Offline** para **Sim**.
- Você pode então escolher usar:
  - **Usar Mensagem Personalizada**, que é o texto na caixa de Mensagem Personalizada. Ou...
  - **A Mensagem Padrão do Idioma do Site**, que é **Este site está em
    manutenção. Por favor, volte novamente em breve.** em inglês ou o equivalente
    no idioma selecionado do site. Isso também permite a seleção de uma imagem. Ou...
  - **Ocultar** para não mostrar mensagem alguma.
- Selecione **Salvar e Fechar** na Barra de Ferramentas.
- Faça a manutenção necessária.
- Retorne ao formulário de Configuração Global.
- Altere o interruptor Site Offline para **Não**.
- Selecione **Salvar e Fechar** na Barra de Ferramentas.

## Todos os Usuários

Você pode limitar o acesso ao seu site protegendo o diretório do Joomla com senha. Somente os usuários que souberem o nome de usuário e a senha de acesso ao diretório poderão acessar o site. Você pode configurar mais de um usuário desse tipo. Com o Painel de Controle de Hospedagem cPanel:

- Faça login na sua conta cPanel.
- Na seção Arquivos, selecione **Privacidade do Diretório**.
- Se a raiz do seu site estiver em um subdiretório de public_html
  - Selecione o diretório public_html
- Selecione o botão Editar para o diretório que contém o seu site (public_html se o seu site estiver na raiz web).
- Marque a caixa de seleção **Proteger este diretório com senha**.
- Insira um nome para o diretório protegido: o padrão pode ser suficiente.
- Selecione o botão **Salvar**.
- Haverá uma página de mensagem de Sucesso com um link Voltar, selecione-o.
- Crie um usuário para acesso ao diretório protegido.
- Insira um nome de usuário
- Insira uma senha e repita (lembre-se dela ou anote).
- Selecione **Salvar**.

Agora, verifique se o diretório requer uma senha para acesso via web. Quando você visitar seu site, será solicitado que insira o nome de usuário e a senha de acesso ao diretório. Eles podem ser completamente diferentes do seu nome de usuário e senha do Joomla.

Para remover a proteção de senha do diretório:

- Faça login na sua conta cPanel.
- Na seção Arquivos, selecione **Privacidade do Diretório**.
- Se a raiz do seu site estiver em um subdiretório de public_html
  - Selecione o diretório public_html
- Selecione o botão **Editar** para o diretório que contém o seu site (public_html se o seu site estiver na raiz web). Agora ele mostrará um símbolo de cadeado e Sim sob o título Privado.
- **Desmarque** a caixa de seleção **Proteger este diretório com senha**.
- Selecione o botão **Salvar**.

Para verificar se a proteção por senha foi removida, use um navegador diferente para acessar seu site ou feche e reabra seu navegador existente e depois acesse seu site novamente.

*Traduzido por openai.com*

