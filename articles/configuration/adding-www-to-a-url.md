<!-- Filename: Adding_www_to_a_url / Display title: Adicionando www a uma URL -->

## Expressões Regulares do Apache .htaccess

Para uma solução simples, adicione o seguinte ao seu arquivo `.htaccess`:

```bash
    RewriteEngine On
    RewriteCond %{HTTP_HOST} !^(www\.example\.com)?$ [NC]
    RewriteRule (.*) https://www.example.com/$1 [R=301,L]
```

Neste caso, uma URL do tipo `https://example.com/index.php?item=1` será redirecionada para `https://www.example.com/index.php?item=1`.

No exemplo acima:

* `RewriteCond` define uma condição de teste.
* `%{HTTP_HOST}` utiliza a variável host da solicitação (example.com).
* `!` significa NÃO e `^` significa INÍCIO - então, não começa com www.example.com
* `(` e `)` capturam o que está entre os parênteses para uso em referência posterior.
* `\` transforma o próximo caractere de um caractere de controle para um caractere real.
* `.` normalmente significa qualquer caractere, mas precedido por \ significa ponto final.
* `?` torna a correspondência opcional.
* `$` significa FIM (da correspondência opcional).
* `[NC]` significa No Case, ou seja, insensível a maiúsculas e minúsculas.
* `RewriteRule` é válido se a URL não começa com www.
* `(.*)` é um padrão, neste caso um único caractere repetido 0 ou mais vezes, significando a parte do caminho da URL. É capturado como $1.
* `https://www.example.com/` é a substituição para a parte do host da URL.
* `$1` é o caminho capturado.
* `[]` contém flags - instruções sobre o que fazer.
* `R=301` é uma instrução para enviar um cabeçalho Moved Permanently.
* `L` significa Último no conjunto - como uma correspondência foi encontrada, ignore qualquer regra subsequente.

Uma solução mais completa corrigindo vários outros problemas de canonização ao mesmo tempo:

```bash
    RewriteEngine On
    #
    RewriteCond %{THE_REQUEST} ^[A-Z]{3,9}\ /([^/]+/)*index\.html?\ HTTP/
    RewriteRule ^(([^/]+/)*)index\.html?$ http://www.example.com/$1 [R=301,L]
    #
    RewriteCond %{THE_REQUEST} !^POST
    RewriteCond %{THE_REQUEST} ^[A-Z]{3,9}\ /([^/]+/)*index\.php\ HTTP/
    RewriteCond %{SERVER_PORT}>s ^(443>(s)|[0-9]+>s)$
    RewriteRule ^(([^/]+/)*)index\.php$ http%2://www.example.com/$1 [R=301,L]
    #
    RewriteCond %{HTTP_HOST} !^(www\.example\.com)?$
    RewriteRule (.*) http://www.example.com/$1 [R=301,L]
```

Se você quiser entender o que tudo isso significa, pode ler estes artigos:

* [Introdução ao Apache mod_rewrite](https://httpd.apache.org/docs/2.4/rewrite/intro.html)
* [Introdução aos Redirecionamentos .htaccess](https://www.danielmorell.com/guides/htaccess-seo/redirects/introduction-to-redirects)

*Traduzido por openai.com*

