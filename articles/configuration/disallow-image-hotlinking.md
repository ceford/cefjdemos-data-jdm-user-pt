<!-- Filename: How_do_you_block_direct_hot_linking_to_image_files_using_htaccess%3F / Display title: Proibir Hotlinking de Imagens  -->

## Definição

Hotlinking é a prática de vincular uma imagem em um site a partir de um artigo em outro site. Pode ser uma prática muito útil. Este site utiliza muitas imagens que estão localizadas no site docs.joomla.org. Isso economiza tempo e esforço necessários para criar capturas de tela e na largura de banda deste site. No entanto, podem surgir questões de direitos autorais e você pode querer impedir que suas imagens sejam usadas desta maneira.

O método descrito aqui utiliza um arquivo *.htaccess*, que é um recurso do servidor Apache. Outros servidores web podem fornecer outros métodos para prevenir hotlinking.

## Instruções

Coloque o seguinte código no arquivo *.htaccess* do seu diretório raiz.

```
<IfModule mod_rewrite.c>
    RewriteEngine on
    RewriteCond %{HTTP_REFERER} !^$
    RewriteCond %{HTTP_REFERER} !^http(s)?://(www\.)?seudominio.com [NC]
    RewriteCond %{HTTP_REFERER} !^http(s)?://(www\.)?google.com [NC]
    RewriteRule \.(jpg|jpeg|png|gif|webp|svg)$ - [NC,F,L]
</IfModule>
```

### Explicação

* A primeira RewriteCond permite solicitações diretas usando uma URL - sem referer.
* A segunda RewriteCond permite solicitações do seu próprio domínio. A flag *\[NC\]*
  significa *No Case*, ou seja, corresponde a caracteres maiúsculos e minúsculos.
* A terceira RewriteCond permite solicitações do Google, para que suas imagens
  ainda possam aparecer nos resultados de pesquisa. Você pode adicionar linhas semelhantes para quaisquer
  outros sites que você deseje permitir.
* A RewriteRule bloqueia solicitações para arquivos de imagem de todos os domínios não
  previamente permitidos. A flag F diz ao navegador para retornar um cabeçalho Forbidden
  (403). L significa última regra.

### Bloquear Hot Linking de Domínios Específicos

Para impedir hotlinking de domínios específicos apenas, como *myspace.com*,
*blogspot.com* e *livejournal.com*, enquanto permite que outros sites
façam hotlink para suas imagens, use o seguinte código:

```
<IfModule mod_rewrite.c>
    RewriteEngine On
    RewriteCond %{HTTP_REFERER} ^http(s)?://(.+\.)?myspace\.com/ [NC,OR]
    RewriteCond %{HTTP_REFERER} ^http(s)?://(.+\.)?blogspot\.com/ [NC,OR]
    RewriteCond %{HTTP_REFERER} ^http(s)?://(.+\.)?livejournal\.com/ [NC]
    RewriteRule \.(jpg|jpeg|png|gif|webp|svg)$ - [NC,F,L]
</IfModule>
```

Você pode adicionar quantos domínios diferentes desejar. Cada linha *RewriteCond*
exceto a última deve terminar com as flags *\[NC,OR\]*. *NC*
significa ignorar maiúsculas e minúsculas. *OR* significa "Ou Próxima", ou seja, corresponde a esta linha
**ou** a próxima linha. A última *RewriteCond* omite a flag *OR* para parar
a correspondência após a última *RewriteCond*.

*Traduzido por openai.com*

