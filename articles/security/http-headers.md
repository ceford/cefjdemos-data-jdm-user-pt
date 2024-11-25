<!-- Filename: https://magazine.joomla.org/all-issues/may-2022/joomla-new-http-headers-plugin-for-j4 / Display title: Cabeçalhos HTTP  -->

## Artigo de Revista

Este artigo é baseado em um artigo da Joomla! Community Magazine por Brendan Hedges na edição de maio de 2022.

Embora tenha sido escrito para o Joomla 4, o conteúdo se aplica igualmente ao Joomla 5.

## Novo Plugin de Cabeçalhos HTTP do Joomla Para J4

Como continuidade do artigo do mês passado sobre segurança, senhas e o plugin WebAuthn do Joomla, neste mês, vamos examinar outro recurso de segurança do Joomla que foi lançado com o J4. Esse é o plugin de Cabeçalhos HTTP, que agora faz parte das funções principais do Joomla.

A internet está sempre se desenvolvendo, e o Joomla nunca fica para trás. É por isso que o escolho como minha plataforma de desenvolvimento web preferida. Não importa se o seu site é pequeno, como um site familiar, ou uma plataforma completa de comércio eletrônico com milhões em vendas, o framework do Joomla tem algo para todos e está sempre buscando implementar novas tecnologias, algumas até inovadoras.

> A introdução do plugin de Cabeçalhos HTTP no núcleo do Joomla 4 é um grande avanço para ajudar a proteger seu site de ataques e atividades maliciosas.

Este plugin de segurança do sistema ajuda os proprietários de sites a configurarem facilmente os Cabeçalhos de Segurança HTTP a partir do painel de controle familiar do Joomla, em vez de terem que vasculhar o arquivo htaccess ou outros arquivos de configuração. Ou, pior ainda, o Cpanel da sua hospedagem na web.

Veja quão complicado é configurar isso no Cpanel e diga-me que você não vai cometer um erro! E tudo isso assumindo que, uma vez que o framework esteja instalado no Apache e os diretórios criados, você conheça o formato correto para adicionar os cabeçalhos HTTP que deseja integrar.

Quantas vezes você tentou implementar um comando no htaccess apenas para recarregar seu site e então enfrentar um erro http500?

O maior problema é que, se você não acertar o formato do seu Cabeçalho HTTP, você quebrará seu site.

Mesmo assim, o que funciona para um site pode não funcionar para outro. Um bom exemplo disso é meu arquivo htaccess e a forma como configurei o navegador para carregar uma versão https sem www do meu site:
```
##www para não www e http para https mixin
RewriteCond %{HTTPS} off [OR]
RewriteCond %{HTTP_HOST} ^www\. [NC]
RewriteRule ^ https://mywebsite.co.uk%{REQUEST_URI} [R=301,L,NE]
##Fim www para não www e http para https mixin
```

Isso funcionou bem para minha empresa de hospedagem anterior. Mas quando mudei para um host diferente, parou de funcionar. Vai entender!

O código htaccess que agora tenho que usar para conseguir o mesmo resultado é assim:
```
##www para não www e http para https mixin
RewriteCond %{HTTP_HOST} ^www\.(.*)$ [NC]
RewriteRule ^(.*)$ https://%1/$1 [R=301,L]
RewriteCond %{ENV:HTTPS} !on
RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [R=301,L]
##Fim www para não www e http para https mixin
```

Confuso, não é? E se você cometer um único erro na formatação, BAM! Você quebrou seu site! Bem, pelo menos até você corrigir seu código.

É por isso que manter as coisas simples, como parte do núcleo do Joomla, significa menos frustração, menos tempo perdido procurando no Google por seus erros e mais tempo para celebração enquanto você se senta na cadeira e admira seu novo site.

Então, vamos ver o que os cabeçalhos HTTP realmente são, como você pode encontrar o plugin e o que pode fazer com eles. Vale a pena mencionar aqui que essa função do Joomla é uma função avançada do Joomla, mais adequada para sites sensíveis a dados, em vez do novo site que você criou carinhosamente sobre seus gatinhos fofos. No entanto, dizendo isso, mesmo sites simples devem ser o mais seguros possível para impedir a execução de código malicioso após terem invadido seu site.

## O que são Cabeçalhos HTTP?

Os cabeçalhos HTTP não devem ser confundidos com a seção &lt;head&gt; do seu documento HTML. Eles são completamente diferentes. Os cabeçalhos HTTP são o preâmbulo entre o seu servidor web e o navegador. Um conjunto de instruções que dizem ao navegador o que, ou mais importante, o que não exibir ao visitante.

Você pode ver os Cabeçalhos HTTP e como eles se relacionam com objetos HTML individuais nas Ferramentas do Desenvolvedor do seu navegador. No Google Chrome, abra as Ferramentas do Desenvolvedor e depois a aba Rede. Agora, atualize a página web e clique em um item HTML no painel esquerdo. Ele exibirá o Cabeçalho HTTP para esse item no painel direito.

Você pode ver na imagem abaixo que a imagem destacada está retornando um status HTTP de 200, então o navegador a encontrou. Há também uma variedade de outras informações vinculadas a esse item, como tamanho do arquivo e datas de edição.

![Joomla http headers 1](../../../en/images/security/http-headers-dev-tools-headers.png)

Se um dos seus itens HTML falhou em exibir, você pode também obter uma pista sobre o motivo nos cabeçalhos HTTP. Neste exemplo, a segunda imagem falhou em exibir e você pode ver pelas informações exibidas no painel direito que não há informações de Cabeçalho HTTP.

Exceto pela mensagem enigmática:

**Política de Referência:** 'strict-origin-when-cross-origin'

'Strict-origin-when-cross-origin' significa simplesmente que quando um item HTML (uma imagem neste caso) é servido de uma fonte diferente (não o seu servidor), a política de cabeçalho HTTP definida naquele momento deve ser seguida. Neste exemplo, os Cabeçalhos HTTP, conforme definido no plugin do Joomla, rejeitarão todas as imagens que não se originam deste site, ou de um site diferente que esteja especificamente 'incluído' nos parâmetros de Cabeçalho HTTP configurados no plugin de cabeçalho HTTP do Joomla.

Assim, quando a imagem é chamada a partir do documento HTML, o navegador a rejeita e ela não é carregada.

![Joomla http headers 2](../../../en/images/security/http-headers-dev-tools-headers-reject.png)

O que difere de não ser encontrada e retornar uma mensagem de erro HTTP 404 não encontrada. Nesta situação, a imagem ainda está sendo procurada no servidor que a hospeda, mas o navegador não a encontrou.

![Joomla http headers 3](../../../en/images/security/http-headers-dev-tools-headers-not-found.png)

## O que o Plugin de Cabeçalhos HTTP do Joomla faz

Além de informar ao navegador o que exibir e retornar informações gerais sobre o documento HTML, os Cabeçalhos HTTP ajudam a mitigar ataques e vulnerabilidades de segurança que você pode ter no seu site Joomla. É aí que o plugin de Cabeçalhos HTTP do Joomla se destaca. Ele consegue isso ao exibir explicitamente o conteúdo HTML com base nas suas configurações no próprio plugin de Cabeçalhos HTTP do Joomla.

Ao adicionar cabeçalhos de HTTP baseados em segurança extra ao seu site Joomla com o plugin de Cabeçalho HTTP, você estará proporcionando mais uma camada de segurança para o seu site Joomla.

Isso é importante, porque, por padrão, uma página HTML exibirá todo o seu conteúdo ao seu visitante, seja bom ou ruim. Isso a menos que seja explicitamente informado para não fazer isso nos cabeçalhos HTTP da página web. O plugin faz isso permitindo que você configure as opções de segurança avançadas disponíveis na Política de Segurança de Conteúdo para o seu site. O plugin pode ser configurado de maneira diferente para cada site, dependendo de suas necessidades, então é uma verdadeira arma flexível no seu arsenal contra hackers.

## Por que eu preciso deste plugin?

Em um mundo ideal, você não precisaria. No entanto, no mundo em que vivemos, há muitas pessoas inescrupulosas tentando encontrar maneiras de ganhar dinheiro às custas dos inocentes e desavisados. Em nosso mundo, nos referimos a essas pessoas como hackers. Hackers se esforçam para explorar vulnerabilidades em software para ganho monetário, muitas vezes em detrimento do proprietário do site.

Ao usar o plugin de Cabeçalho HTTP do Joomla para controlar qual conteúdo está sendo servido aos seus visitantes, você reduz as chances de hackers conseguirem servir conteúdo malicioso do site aos seus visitantes por meio de plugins vulneráveis desatualizados. Isso ajuda a impedir injeções de scripts maliciosos em seu site.

**Então, vamos pensar neste situação hipotética por um minuto.**

Você tem um belo site Joomla 3. Ele foi criado há 5 anos e ainda parece e funciona perfeitamente. Todos os seus componentes, plugins e módulos estão atualizados. Perfeito, certo?

Bem, não exatamente, porque quando você criou seu site há 5 anos, instalou o Plugin Foo Bar da moda para imprimir "FOO BAR" na sua página inicial. Parecia legal no início, mas depois de um tempo você mudou de ideia e deletou o shortcode do plugin {foo}FOO - BAR{/bar} do seu artigo na página inicial.

Mas, aqui está o problema: você não despublicou ou desinstalou o próprio plugin e seu uso foi esquecido. **Isso é algo que TODOS nós somos culpados de fazer, tenho certeza.**

Avançando até hoje, 5 anos depois, esse plugin ainda está lá, publicado e ativo em seu site, mas não foi atualizado há 5 anos porque você há muito tempo esqueceu o plugin, ou o autor parou de oferecer suporte a ele. Agora, algum sujeito nefasto percebeu que esse plugin tem uma vulnerabilidade de segurança que pode ser explorada para iniciar um ataque de **Cross Site Scripting (XSS)** em seu site e transformar seus visitantes desavisados em vítimas.

A injeção de scripts entre sites, também conhecida como XSS, é uma vulnerabilidade de segurança em seu site que permite a um invasor comprometer as interações que seus usuários têm com seu site agora vulnerável.

O atacante/hacker usa XSS para explorar seu site vulnerável para enviar um script malicioso ao seu usuário desavisado. Como o script veio do seu site, o navegador do seu usuário não sabe ou suspeita que o script não deve ser confiável e executa o script quando a página da web é carregada e aberta.

Scripts maliciosos executados dessa forma podem causar muitos problemas para o seu usuário, desde roubar senhas de login e dados de nome de usuário guardados em cookies, até enviar seu usuário para sites de phishing falsos. Scripts podem até mudar a aparência da página web que seu site está servindo e mostrar anúncios diferentes.

Usar o **plugin de Cabeçalhos HTTP do Joomla** ajuda a impedir a injeção de scripts entre sites garantindo que apenas os scripts e o conteúdo que você deseja servir ao seu visitante sejam realmente servidos. Tudo o mais é bloqueado.

Assim, no exemplo acima, você poderia ter configurado o plugin de Cabeçalhos HTTP para servir apenas os arquivos JavaScript (script) do seu site a partir de uma pasta específica, ou talvez de um CDN se você usar um, para impedir o ataque.

Você também poderia impedir que o site execute JavaScript embutido no HTML. Mas, esteja ciente de que dependendo de como você projetou seu HTML, isso poderia causar problemas mais adiante.

Isso ajudaria a impedir que códigos JavaScript maliciosos fossem executados em seu site. Mesmo se o seu plugin vulnerável Foo Bar fosse o responsável por um hacker ser capaz de injetar código malicioso em seu site inicialmente.

**Nota:**

> Pontos fracos comuns em sites que são propensos a ataques XSS são formulários de entrada de usuário (páginas de login de usuários, formulários de inscrição em newsletters, formulários de contato, etc.) sem validação e criptografia.

## Onde está o Plugin de HTTP Headers?

Você pode encontrar o plugin de HTTP Headers do Joomla junto com todos os outros plugins do Joomla, e ele é acessado da mesma maneira que você está acostumado a fazer.

![Joomla http headers 4](../../../en/images/security/http-headers-plugins.png)

## Usando o Plugin de Cabeçalhos HTTP

Usar o Plugin de HTTP do Joomla é relativamente simples, embora possa ser uma boa ideia, antes de fazer alterações nas configurações padrão, se familiarizar com alguns dos termos especiais relacionados ao seu uso. Apesar disso, é provável que alguns desses termos já sejam familiares para você.

**Por exemplo:**

Ao lidar com imagens, você verá o termo 'img-src', onde 'img' refere-se a imagens e 'src' à fonte válida da imagem. Esses são termos com os quais já estamos familiarizados a partir do HTML básico.

No final deste artigo, há uma lista de sites úteis com informações adicionais para ajudá-lo a usar este plugin do Joomla.

