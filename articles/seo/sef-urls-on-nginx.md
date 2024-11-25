<!-- Filename: Enabling_Search_Engine_Friendly_(SEF)_URLs_on_Nginx / Display title: URLs SEF no Nginx  -->

## Introdução

URLs amigáveis para motores de busca (SEF), legíveis para humanos ou limpas são URLs que fazem sentido tanto para humanos quanto para motores de busca, pois explicam o caminho para a página específica à qual apontam. O Joomla! é capaz de criar e interpretar URLs em qualquer formato, incluindo URLs SEF. Isso não depende da reescrita de URLs executada pelo servidor web, então funciona mesmo que o Joomla! execute em um servidor diferente do Apache com o módulo mod_rewrite. As URLs SEF seguem um certo padrão fixo, mas o usuário pode definir um texto descritivo curto (alias) para cada segmento da URL.

Internamente, a parte local de uma URL SEF (a parte após o nome de domínio) é chamada de rota. Portanto, criar e processar URLs SEF é referido como roteamento, e o código relevante é chamado de roteador.

Este artigo aborda URLs SEF no popular servidor web Nginx de código aberto.

## Etapas para Servidores NginX¶

- Adicione o seguinte código à configuração do seu servidor (vhost) no arquivo nginx.conf:

```
    # Suporte a URLs Limpos (também conhecidos como URLs Amigáveis para Motores de Busca)
    location / {
       try_files $uri $uri/ /index.php?$args;
    }
```
- Se o código acima não funcionar, adicione o seguinte código à configuração do seu servidor no arquivo nginx.conf: (Isto funcionou com nginx 1.4.6 no Ubuntu.)
```
    server {
      ....
      location / {
      expires 1d;

      # Habilitar URLs SEF do Joomla dentro do Nginx
      try_files $uri $uri/ /index.php?$args;
      }
      ....
    }
```
- Faça login no seu Backend e abra a Configuração Global
- Habilite a opção **URLs Amigáveis para Motores de Busca** e Salve. Esta opção converte as URLs do formato nativo do Joomla! para o formato SEF. Verifique se seu site funciona corretamente. Suas URLs agora devem parecer com `http://www.exemplo.com/index.php/the-news/1-latest-news/1-welcome-to-joomla`. Se seu site não funcionar corretamente, consulte [Por que seu site fica bagunçado quando você ativa as URLs Amigáveis para Motores de Busca (SEF)?](https://docs.joomla.org/Why_does_your_site_get_messed_up_when_you_turn_on_SEF_(Search_Engine_Friendly_URLs)%3F)
- Habilite a opção **Usar reescrita de URL do Apache mod_rewrite** e Salve. Esta opção utiliza a função mod_rewrite do Apache para eliminar a parte *index.php* da URL. Verifique se seu site funciona corretamente. Suas URLs agora devem parecer com `http://www.exemplo.com/the-news/1-latest-news/1-welcome-to-joomla`. Se esta opção causar erros, consulte [Como verificar se o mod rewrite está habilitado no seu servidor](https://docs.joomla.org/How_to_check_if_mod_rewrite_is_enabled_on_your_server). Se não estiver habilitado e você tiver acesso ao arquivo `apache/conf/httpd.conf`, abra esse arquivo e verifique se a linha `LoadModule rewrite_module modules/mod_rewrite.so` não está comentada. Se necessário, descomente a linha e reinicie o servidor web Apache. Se *mod_rewrite* não puder ser habilitado, deixe esta opção desativada. Não importa se você deixar o arquivo `.htaccess` renomeado.
- *Se você achar necessário*, habilite **Adicionar sufixo às URLs** e *Salve*. Esta opção adiciona `.html` ao final das URLs. Existem opiniões divergentes sobre se isso é necessário ou mesmo útil. Os motores de busca não parecem se importar se suas URLs terminam em `.html` ou não.
- Abra o Gerenciador de Plugins e habilite o plugin **Sistema - SEF**. Este plugin adiciona suporte SEF aos links em seus artigos do Joomla. Ele opera diretamente no HTML e não requer uma tag especial.

*Traduzido por openai.com*

