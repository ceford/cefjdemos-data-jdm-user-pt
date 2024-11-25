<!-- Filename: Enabling_Search_Engine_Friendly_(SEF)_URLs_on_Apache / Display title: URLs SEF no Apache -->

## Verifique se o .htaccess está Ativado

Verifique se o arquivo de configuração do Apache permite substituições de .htaccess. Você deve garantir que as substituições estejam ativadas ou o arquivo .htaccess no diretório raiz do seu Joomla! será ignorado ou causará um erro. Na seção do arquivo de configuração do host virtual ou no arquivo de configuração principal (`httpd.conf`), você deve ter algo semelhante ao exemplo abaixo, que habilita as substituições:

```bash
<Directory "/home/user/public_html">
  AllowOverride All
</Directory>

<Directory "/path/to/htdocs">
  AllowOverride All Options=[uma opção],[outra opção],...
</Directory>
```

Existem outras maneiras de testar se o `.htaccess` está ativado, caso você não tenha acesso aos arquivos de configuração do seu site. Consulte o [tutorial de .htaccess](http://httpd.apache.org/docs/current/howto/htaccess.html) no site da *The Apache Software Foundation* para obter informações adicionais.

## Passo a Passo

Estas são instruções passo a passo. Por favor, siga-as na ordem apresentada aqui. Se algum passo falhar, **não** continue até resolver o problema.

1. Renomeie o arquivo `htaccess.txt` na pasta base do seu Joomla! para `.htaccess`.
2. *Este passo pode não ser necessário.* Abra o `.htaccess` em um editor de texto. Descomente `RewriteBase /` (remova o primeiro caractere, \#). Se o Joomla estiver instalado em sua própria pasta, insira o nome da pasta do Joomla após a barra. por exemplo, `RewriteBase /suapastadojoomla`.
3. Faça login no seu Back-end e abra a Configuração Global.
4. Ative a opção **Usar reescrita de URL/Reescrita do Apache mod_rewrite** e *Salve*. Esta opção usa a função *mod_rewrite* do Apache para eliminar a parte "index.php" do URL.

    Verifique se o seu site funciona corretamente. Seus URLs agora devem parecer:

        `http://www.example.com/the-news/1-latest-news/1-welcome-to-joomla`

    Se esta opção causar erros, por favor veja 
    [Como verificar se o mod rewrite está habilitado no seu servidor](https://docs.joomla.org/How_to_check_if_mod_rewrite_is_enabled_on_your_server).

    - Se não estiver habilitado e você tiver acesso ao arquivo
      `apache/conf/httpd.conf`, abra esse arquivo e verifique se a linha
      `LoadModule rewrite_module modules/mod_rewrite.so` está descomentada.
      Se necessário, descomente a linha e reinicie o servidor web Apache.
    - Se *mod_rewrite* não puder ser habilitado, deixe esta opção desativada. Não importa se você deixar o arquivo `.htaccess` renomeado.
5. *Se você considerar necessário*, ative **Adicionar sufixo aos URLs** e *Salve*. Esta opção adiciona `.html` ao final dos URLs. Há opiniões diferentes sobre se isso é necessário ou útil. Os motores de busca parecem não se importar se seus URLs terminam em `.html` ou não.
6. Abra o Gerenciador de Plugins e ative o plugin **Sistema - SEF**. Este plugin adiciona suporte SEF aos links em seus artigos do Joomla. Ele opera diretamente no HTML e não requer uma tag especial.

*Traduzido por openai.com*

