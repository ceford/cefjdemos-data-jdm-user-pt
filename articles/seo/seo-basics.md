<!-- Filename: jdocmanual?manual=user&heading=seo&filename=seo-basics.md / Display title: Noções Básicas de SEO -->

## Definição

Otimização para Motores de Busca é o processo de melhorar uma ampla gama de características de um site com a intenção de melhorar a posição em que ele é classificado nos motores de busca.

O processo de otimização de um site é multifacetado, pois há muitos fatores que afetam onde uma página pode ser classificada em um motor de busca.

- Garantir que o conteúdo tenha uma estrutura apropriada usando HTML Semântico
- Melhorar a qualidade do conteúdo de páginas individuais.
- Assegurar que o site possa lidar com solicitações rapidamente
- Habilitar URLs Amigáveis para Motores de Busca para tornar o endereço web das páginas 'legível por humanos'
- Adicionar Marcação Semântica Contextual usando dados de Schema

Recurso: Guia Inicial de Otimização para Motores de Busca (SEO)

## Estrutura do Site e URLs Descritivas

Nos primeiros dias, os sites eram estruturados como arquivos HTML individuais em uma hierarquia de árvore. Alguns sites ainda são estruturados assim. CMSs são diferentes. Páginas individuais são montadas a partir de conteúdo armazenado em tabelas de banco de dados. Os URLs para o primeiro e o último são diferentes, talvez assim:
```
https://www.exemplo.com/usuario/seo/introducao-seo.html
https://www.exemplo.com/index.php?option=com_jdocmanual&view=manual&manual=usuario&heading=seo&filename=introducao-seo
```
Claramente, o primeiro é mais fácil de lembrar e digitar. Os motores de busca preferem eles.

No CMS Joomla, um URL da primeira forma pode ser configurado da seguinte maneira:

1. Crie uma Categoria de Conteúdo chamada **Usuário**.
2. Crie uma Categoria de Conteúdo chamada **SEO**, que seja um filho de *Usuário*.
3. Crie um artigo e atribua-o à categoria *SEO*.
4. Crie uma entrada de menu **Usuário** do tipo **Lista de Categorias** usando a categoria *Usuário*.
5. Crie uma entrada de menu **SEO** do tipo **Lista de Categorias** usando a categoria *SEO*.
6. Configure a funcionalidade de SEO do Joomla em *Configuração Global*.

Teste-o com o seu URL SEO: navegue através das listas de Usuário e SEO até a página Introdução ao SEO. O Breadcrumbs deve mostrar: `Você está aqui: Início / Usuário / SEO / Introdução ao SEO`. Mas não se você criou um tipo de entrada de menu Artigo Único para *Introdução ao SEO*!

## Reduzir Duplicação

O problema com os CMSs é que o mesmo conteúdo pode estar disponível com URLs diferentes. No exemplo acima, ambas as URLs funcionarão (mas não neste site), assim como `https://example.com/index.php?option=com_content&view=category&id=18&ItemID=17`. Apenas uma delas deve ser reconhecida pelos mecanismos de busca e definida como a URL **canônica**. Mas qual delas e como?

O plugin **Sistema - SEF** fornece alguma ajuda. Ele tem três configurações:

* **Domínio do Site:** Se o seu site pode ser acessado através de mais de um domínio, insira o domínio preferido (às vezes referido como canônico) aqui. **Nota:** `https://example.com` e `https://www.example.com` são domínios diferentes.
* **Tratamento rigoroso de index.php:** Esta opção permite um tratamento mais rigoroso de 'index.php' em URLs quando 'Usar a Reescrita de URL' está habilitado na Configuração Global. Ele irá remover 'index.php' se uma URL ainda o contiver e redirecionar solicitações recebidas com 'index.php' para a versão sem o 'index.php'.
* **Barra final para URLs:** Força o Joomla a usar apenas URLs com ou sem a barra final. Quando configurado, forçará o URL correto com redirecionamentos e só é aplicado quando 'Adicionar sufixo à URL' está desativado.

Explicação das **Tags Canônicas** por Daniel Morell:

* Como Criar Tags Canônicas no Joomla
* Plugin e Documentação:

Para Joomla 4 e 5, antes de habilitar, o plugin precisa que `if ($app->isAdmin()) {` seja alterado para `if ($app->isClient('admin')) {` nas linhas 72 e 99 de *plugins /system / customcanonical / customcanonical.php*.

Em um artigo, selecione a aba de Publicação e, em seguida, o botão *URL Canônico* **Auto**. Isso colocará um link como o seguinte em qualquer página que exiba o artigo único:
```
    <link href="/jdm3/en/user/seo/seo-basics.html" rel="canonical" />
```

## Qualidade do Conteúdo

Faça o que você escreve ser interessante e fácil de ler. Parágrafos longos são frequentemente avassaladores e difíceis de ler. Parágrafos de uma linha parecem errados! Talvez devessem realmente ser pontos de lista. Busque parágrafos de cerca de três linhas. Leia o que você escreve e edite para remover quaisquer palavras desnecessárias.

Mantenha seu conteúdo atualizado e evite copiar informações de outros sites. Se possível, verifique seu conteúdo.

### HTML Semântico

O conteúdo deve consistir em uma hierarquia de títulos e parágrafos com outros elementos conforme necessário (listas, tabelas e assim por diante). Não confunda estrutura com aparência - portanto, não use um título para dar ênfase ou ênfase para um título. Este é um exemplo de marcação semântica de um artigo:

```html
  <h2>Usando títulos</h2>
  <p>Este é um artigo sobre a importância dos títulos.</p>

  <h2>Por que usar títulos?</h2>
  <p>É importante usar títulos para que os bots dos motores de busca possam identificar qual é a parte <strong>importante</strong> do seu artigo.</p>

  <h3>Tipos de títulos</h3>
  <p>Você pode usar tipos definidos de títulos, mas eles devem ser ordenados e estruturados dentro da sua página. H1 será o título da página inserido pelo Joomla, com H2 sendo usado para subtítulos da página. Qualquer título dentro dos seus subtítulos deve ser ordenado usando H3, H4, e H5 conforme apropriado.</p>

  <h2>É difícil implementar títulos?</h2>
  <p>Implementar títulos é muito fácil, você só precisa usar o código HTML apropriado.</p>
```
Note que o *Título* de um artigo se tornará um título `<h1>` se necessário, então não use isso no corpo de um artigo.

## Antecipe Termos de Busca

Escolha títulos explícitos para suas páginas e cabeçalhos dentro das páginas. Por exemplo, se você não sabe o que é *HTML Semântico* ou quer mais informações sobre esse tópico, essas seriam as palavras que você inseriria em um mecanismo de busca. Pense nas pessoas que podem estar interessadas nas informações que você está fornecendo. O que elas irão buscar? Mas mantenha Títulos e Cabeçalhos relativamente curtos - algumas fontes dizem no máximo 60 caracteres.

## Cuidado com Anúncios

Nada afasta mais os visitantes do site do que anúncios aparecendo aqui, ali e em todos os lugares, movendo as informações reais diante dos seus olhos. Anúncios que mudam a cada poucos segundos também são irritantes e consomem recursos do usuário final. Muitos usarão bloqueadores de anúncios!

## Cuidado com Links

Links são uma bênção e uma maldição! Eles podem afetar a classificação de SEO do seu site para o bem ou para o mal, dependendo se você tem links para fontes respeitáveis ou fontes não confiáveis. E eles precisam ser mantidos. Você pode ter links para artigos internos ou externos que desapareceram, apresentam informações desatualizadas ou não são mais relevantes. Melhor conselho: linkar se o destino realmente adiciona benefícios para os visitantes do seu site e use o atributo de link `nofollow` se você não quiser que o site de destino esteja associado ao seu site.

Existem muitas ferramentas de verificação de links disponíveis, algumas gratuitas ou freemium e outras pagas, muitas vezes como parte de um serviço de monitoramento de sites.

## Título e Descrição da Página

Em cada página, dentro da `<head>`, deve haver uma tag `<title>` e uma tag `<description>`. O Joomla torna muito fácil definir um título diferente para cada página. Infelizmente, também torna muito fácil negligenciar a definição de um Título e Descrição adequados em todas as páginas.

Como exemplo, veja a página de lista de categoria **SEO** mencionada acima. O `<title>` na origem da página diz **SEO** e a `<description>` está ausente. No formulário **Menus: Editar Item** para este item de menu, há uma aba **Exibição de Página** com um campo **Título da Página do Navegador**. Insira `SEO - Lista de Artigos` lá e isso é o que aparecerá na tag `<title>` e na aba do navegador.

Na aba **Metadados**, com o campo **Descrição Meta** definido como `Lista de artigos sobre Otimização de Motores de Busca`, é exatamente isso que aparecerá no campo `<description>`. A Descrição às vezes é usada para acompanhar um Título de página nos resultados de busca, por isso vale a pena torná-la relevante.

Mais informações:
* Artigo de revista: Tags de título SEO no Joomla
* Explore o Núcleo: Opções Nativas de SEO

## Otimizar Imagens

Não é preciso dizer que imagens atraentes podem melhorar enormemente um site. Mas muitas que são muito grandes atraem penalidades de SEO. Aqui estão algumas dicas:

* Coloque as imagens próximas ao texto que ilustram.
* Utilize texto **alt** descritivo.
* Use palavras separadas por hífen para os nomes das imagens, por exemplo, gato-no-telhado-quente.jpg.
* Use o tipo certo de imagem para o trabalho: png para cartazes, jpg para fotografias.
* Utilize imagens responsivas - há um plugin do Joomla que cria dinamicamente versões webp de imagens png e jpg em vários tamanhos.

*Traduzido por openai.com*
