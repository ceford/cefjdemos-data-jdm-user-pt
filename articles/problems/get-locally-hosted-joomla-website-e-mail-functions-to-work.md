<!-- Filename: Get_locally_hosted_Joomla!_website_e-mail_functions_to_work / Display title: Email do Host Local  -->

## Hospedagem Local

A maioria dos ISPs bloqueia a porta 25, então você não pode enviar emails do servidor SMTP do seu próprio computador. Isso é para bloquear spammers. Se você não pretende enviar spam, pode usar o servidor de email do seu ISP.

Para usar a função de email do servidor SMTP do seu ISP mesmo se você estiver hospedando seu próprio site Joomla em seu próprio computador, entre no seu site Joomla como Super Usuário e vá até a aba **Servidor** na página de **Configuração Global**. Na seção **Email**, seus dados devem se parecer com o seguinte:

    De Email: alguem@example.com (geralmente você)
    De Nome: AlgumNome

    Correio: SMTP
    Host SMTP: smtp.charter.net (O que seu ISP informa para você usar nos seus servidores SMTP)
    Caminho Sendmail: /usr/sbin/sendmail
    Porta SMTP: 25
    Segurança SMTP: STARTTLS
    Autenticação SMTP: Sim (ou Não)
    Nome de Usuário SMTP: johndoe (nome de usuário em uma de suas contas de email no seu ISP)
    Senha SMTP: trr33459 (senha em uma de suas contas de email no seu ISP)
Envie uma mensagem de teste para verificar se está funcionando.

O Nome de Usuário SMTP, Senha e Host são os mesmos campos que você preenche ao adicionar uma Conta do Outlook Express, ou Eudora, ou qualquer cliente de email que você use no seu computador.

Você pode encontrar problemas com extensões que mudam o endereço *De* nos emails sendo enviados. Por exemplo, a extensão ProjectFork às vezes envia emails como se eles estivessem vindo da pessoa responsável pelo projeto. Isso pode causar um problema porque alguns servidores SMTP de ISP não permitirão um endereço "de" que não corresponda ao nome de usuário (por exemplo, Rogers no Canadá). Você receberá uma mensagem como esta: "PHPMAILER_FROM_FAILEDname@whatever.com." Uma solução alternativa é garantir que você sempre use um endereço de email válido do seu ISP para seus usuários.

*Traduzido por openai.com*

