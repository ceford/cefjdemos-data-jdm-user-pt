<!-- Filename: Robots.txt_file / Display title: O arquivo robots.txt -->

## Sobre Robôs

Robôs web, também conhecidos como rastreadores, web wanderers ou spiders, são
programas que percorrem a web automaticamente. Entre muitos usos, motores de busca
os utilizam para indexar o conteúdo da web.

O arquivo robots.txt implementa o
[Protocolo de Exclusão de Robôs](https://en.wikipedia.org/wiki/Robots_exclusion_standard),
que permite a um administrador de site definir quais partes do site não devem
ser inspecionadas por agentes de usuário de robôs específicos. Por exemplo, o acesso ao
conteúdo de páginas públicas normalmente é permitido, mas o acesso a diretórios cgi, privados e
temporários que não devem ter páginas indexadas geralmente é desautorizado.

## Onde Colocar o Arquivo *robots.txt*

Um arquivo *robots.txt* padrão está incluído no seu diretório raiz do Joomla. O
arquivo *robots.txt* deve residir na raiz do domínio ou subdomínio e
deve ser nomeado como `robots.txt`.

### Joomla em um Subdiretório

Um arquivo robots.txt localizado em um subdiretório não é válido. Os robôs apenas
verificam este arquivo na raiz do domínio. Se o site Joomla estiver
instalado dentro de um subdiretório, como *exemplo.com/joomla/*, o
arquivo *robots.txt* **deve** ser movido para a raiz do site em
*exemplo.com/robots.txt*.

**Nota:** No arquivo robots.txt, o nome do subdiretório **deve** prefixar qualquer
caminho do Joomla não permitido. Por exemplo, a regra de bloqueio para o diretório `/administrator/`
**deve** ser alterada para `Disallow: /joomla/administrator/`.

## Conteúdo do *robots.txt* do Joomla

Este é o conteúdo de um [arquivo padrão robots.txt do Joomla](https://raw.githubusercontent.com/joomla/joomla-cms/refs/heads/5.2-dev/robots.txt.dist):

```
# Se o site Joomla estiver instalado dentro de uma pasta
# por exemplo www.exemplo.com/joomla/ então o arquivo robots.txt
# DEVE ser movido para a raiz do site
# por exemplo www.exemplo.com/robots.txt
# E o nome da pasta joomla DEVE ser prefixado a todos os
# caminhos.
# por exemplo, a regra Disallow para a pasta /administrator/ DEVE
# ser alterada para
# Disallow: /joomla/administrator/
#
# Para mais informações sobre o padrão robots.txt, veja:
# https://www.robotstxt.org/orig.html

User-agent: *
Disallow: /administrator/
Disallow: /api/
Disallow: /bin/
Disallow: /cache/
Disallow: /cli/
Disallow: /components/
Disallow: /includes/
Disallow: /installation/
Disallow: /language/
Disallow: /layouts/
Disallow: /libraries/
Disallow: /logs/
Disallow: /modules/
Disallow: /plugins/
Disallow: /tmp/
```

## Exclusão de Robôs

Você pode excluir diretórios ou bloquear robôs no seu site adicionando uma regra Disallow ao arquivo *robots.txt*. Por exemplo, para impedir que qualquer robô visite o diretório */tmp*, adicione esta regra:

    Disallow: /tmp/

Veja também:

- [Bloquear o acesso ao seu conteúdo](https://support.google.com/webmasters/topic/4598466?hl=pt&amp;ref_topic=9427949) no Centro de Ajuda do Google.

## Verificação de Sintaxe

Para verificar a sintaxe, você pode usar um validador para arquivos *robots.txt*. Experimente um desses:

- [Teste seu <em>robots.txt</em> com o Testador de robots.txt](https://support.google.com/webmasters/answer/6062598) no Google.
- [Verificador de <em>robots.txt</em>](http://www.searchenginepromotionhelp.com/m/robots-text-tester/robots-checker.php) pela Search Engine Promotion Help.

### Informações Gerais

- [The Web Robots Pages](http://www.robotstxt.org/) é o site principal para *robots.txt*.
- [Um Padrão para Exclusão de Robôs](http://www.robotstxt.org/orig.html) é o padrão original.
- [Especificações da meta tag Robots, data-nosnippet e X-Robots-Tag](https://developers.google.com/search/docs/advanced/robots/robots_meta_tag)

*Traduzido por openai.com*

