<!-- Filename: J4.x:Privacy_Workflow / Display title: Fluxo de Trabalho de Privacidade -->

## Criando uma Solicitação

O processamento de solicitações de informações pessoais é o principal objetivo do componente de privacidade. Os usuários podem solicitar um resumo de seus dados pessoais ou a remoção de todos os seus dados pessoais. Uma solicitação pode ser criada por um usuário autenticado através do formulário de solicitação ou por um superusuário.

Neste contexto, um usuário significa qualquer indivíduo ou organização que fez uma solicitação, independentemente de haver uma conta de usuário registrada. Por exemplo, as solicitações podem chegar ao administrador do site de indivíduos ou organizações que foram adicionados ao site como contatos.

Os dados pessoais são baseados em endereços de e-mail e o processamento automatizado é limitado a extensões que relatam capacidades de privacidade.

*IMPORTANTE* Para criar e processar solicitações de informações, seu site DEVE ser capaz de enviar e-mails devido à necessidade do proprietário da informação confirmar a solicitação.

### Solicitação de Usuário Autenticado

Usuários registrados podem enviar uma solicitação de informações através de um link de menu *Solicitação de Informação de Privacidade* disponível apenas após o login. Um bom lugar para este link é no mesmo menu onde há um link para a **Política de Privacidade** do site. Um Menu Inferior no rodapé do site é frequentemente uma localização preferida. Ao enviar uma solicitação de informações, o usuário deve fornecer:

- O tipo de solicitação: Exportar ou Remover, selecionado da lista suspensa.

![fluxo de trabalho de privacidade solicitação de usuário](../../../en/images/privacy/privacy-workflow-user-request.png)

Na submissão, uma mensagem indicará que a solicitação foi aceita e um e-mail de verificação está a caminho:

![fluxo de trabalho de privacidade solicitação de usuário aceita](../../../en/images/privacy/privacy-workflow-user-request-accepted.png)

ou que *Sua solicitação de informações não pôde ser criada. Já existe uma solicitação de informações ativa para este endereço de e-mail e tipo de solicitação. Por favor, entre em contato com o proprietário do site para atualizações sobre esta solicitação.*

### Criação pelo Superusuário

Através da página **Privacidade: Solicitações de Informações**, qualquer superusuário pode criar uma nova solicitação de informações. Esta é a única maneira de criar solicitações de informações para usuários que NÃO têm contas no site. Para criar uma solicitação:

- Selecione **Usuários → Privacidade → Solicitações** no menu do Administrador.
- Selecione o botão **Novo** na Barra de Ferramentas.
- No campo **E-mail**, insira o endereço de e-mail do usuário.
- No campo **Tipo de Solicitação**, selecione Exportar ou Remover da lista suspensa.
- **Salvar & Fechar**.

Uma vez criada, a solicitação não pode ser editada. Ela pode apenas ser Invalidada ou Processada.

## Confirmando uma Solicitação

Uma vez que uma solicitação for criada, independentemente de como ela é criada, o usuário receberá um e-mail contendo um link para um formulário de confirmação.

![fluxo de privacidade solicitação do usuário confirmar](../../../en/images/privacy/privacy-workflow-user-request-confirm.png)

O usuário deve inserir o token fornecido no e-mail e enviar o formulário. O token é válido por 24 horas. Se uma solicitação não for confirmada nesse período, ela será marcada como **Inválida** na lista de Solicitações de Privacidade e uma nova solicitação deverá ser feita.

Uma vez que o usuário confirme a solicitação, um e-mail será enviado aos Super Usuários para indicar que é necessária uma ação.

- Selecione **Usuários → Privacidade → Solicitações** no menu do Administrador.
- Solicitações que requerem ação serão marcadas como **Confirmadas**.

![fluxo de privacidade lista de solicitações de informação](../../../en/images/privacy/privacy-workflow-information-requests-list.png)

## Processando uma Solicitação de Exportação

Uma vez que uma solicitação de exportação tenha sido confirmada, há duas ações disponíveis para superusuários.

- Exportar Dados: Isso irá coletar todos os dados referentes ao assunto da solicitação de informações e criar um arquivo XML que será baixado para o seu computador. Isso é útil para permitir que os proprietários do site revisem a exportação de dados antes de enviá-la ao usuário.
- Enviar Exportação de Dados por Email: Isso irá coletar todos os dados referentes ao assunto da solicitação de informações, criar um arquivo XML (o mesmo gerado pela ação Exportar Dados) e enviar um email para o usuário com o arquivo de dados exportado anexado.

**Importante:** A ação de exportação só pode coletar dados de extensões que têm suporte à privacidade. Portanto, o superusuário que está atendendo à solicitação deve revisar a exportação e, se necessário, incluir dados contidos em extensões que armazenam dados pessoais, mas não têm suporte à privacidade.

## Processando um Pedido de Remoção

Uma vez que um pedido de remoção tenha sido confirmado, há apenas uma ação disponível para superusuários.

- Excluir Dados: Este processo irá anonimizar e/ou remover dados relacionados ao sujeito da informação. Para os pedidos onde o proprietário da informação também possui uma conta de usuário registrada, este processo irá anonimizar o nome, nome de usuário e endereço de e-mail da conta, além de bloquear a conta para que não se possa fazer login, e desconectar o usuário do site se ele estiver logado no momento em que o pedido for processado.

**Importante:** A ação de exclusão só pode coletar dados de extensões que têm suporte à privacidade. Portanto, o superusuário que está atuando no pedido deve revisar a exportação e, se necessário, anonimizar ou remover manualmente dados contidos em extensões que armazenam dados pessoais, mas não têm suporte à privacidade.

Ao selecionar o botão **Excluir Dados**, há uma mensagem de confirmação **Dados Removidos**, mas a lista de Pedidos de Informação de Privacidade permanece inalterada. Os dados do usuário são removidos ou anonimizados, mas não os dados nas tabelas \#\_\_action_logs, \#\_\_messages e \#\_\_privacy_requests (veja abaixo).

## Concluindo uma Solicitação

Após o processamento, a solicitação deve ser marcada como concluída.
Isso indicará que a solicitação foi atendida e não há mais ações a serem tomadas.

- Na lista **Privacidade: Solicitações de Informação**, selecione o endereço de e-mail
  da solicitação que está sendo processada.
- No formulário **Privacidade: Revisar Solicitação de Informação**:
  - Revise os dados.
  - Selecione o botão adequado **Exportar**, **E-mail** ou **Excluir**
    na Barra de Ferramentas, se isso ainda não foi feito na visualização de lista.
- Selecione o botão **Concluir** na Barra de Ferramentas (ou o botão **Invalidar**
  se for uma solicitação considerada inválida).

![revisão da solicitação de informação do fluxo de trabalho da privacidade](../../../en/images/privacy/privacy-workflow-review-information-request.png)

## Finalmente

Para remover os dados do Log de Ações do Usuário:

- Selecione **Usuários → Log de Ações do Usuário** no menu do Administrador.
- Procure o nome de usuário ou endereço de email do usuário deletado.
- Marque a caixa **Marcar Todos os Itens**.
- Selecione o botão **Excluir** na Barra de Ferramentas.

Para remover os dados de Mensagens Privadas e Solicitações de Privacidade:

- Não há uma maneira fácil de remover em lote qualquer um desses tipos de dados
  de dentro do Joomla. O método mais rápido é buscar o Nome de Usuário
  (endereço de email) no banco de dados com o phpMyAdmin e deletar os registros
  lá. Aqui está um exemplo de captura de tela:

![exclusão de fluxo de trabalho de privacidade com phpmyadmin](../../../en/images/privacy/privacy-workflow-delete-with-phpmyadmin.png)

## Recursos Adicionais

- [Guia do Desenvolvedor para o Conjunto de Ferramentas de Privacidade](https://docs.joomla.org/Special:MyLanguage/J3.x:Integrate_Extensions_with_the_Privacy_Component)

*Traduzido por openai.com*

