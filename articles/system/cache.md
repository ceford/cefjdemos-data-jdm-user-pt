<!-- Filename: Cache / Display title: Cache -->

## Para Administradores

Como administrador, o Joomla oferece a capacidade de armazenar em cache partes do seu site. Você pode optar por armazenar em cache páginas inteiras da web ou apenas partes dessas páginas. Este guia explica como.

Em uma página da web de um site Joomla, existem 3 elementos que podem ser armazenados em cache:

1. A página inteira – o cache da Página
2. O output do componente Joomla para essa página web – conhecido como o cache da Visualização
3. O output dos módulos mostrados nessa página – conhecido como o cache do Módulo

Você tem várias configurações de cache que permitem controlar o que é armazenado:

1. O plugin do sistema "Sistema – Cache de Página"
2. A Configuração Global, aba Sistema, Configurações de Cache. Aqui a opção de Cache do Sistema pode ser configurada para
   - OFF – Cache desativado
   - ON – Cache conservador
   - ON – Cache progressivo
3. Muitos módulos dentro de suas opções têm uma aba Avançado na qual o Cache pode ser configurado para *Usar global* ou *Sem cache*

Conforme descrito abaixo, também existem regras para cache que são implementadas dentro do código Joomla, sobre as quais você não tem controle.

Você pode limpar o cache através da seleção de menu Administrador → Sistema → Limpar Cache. Em geral, você pode imaginar que o Joomla tem 3 níveis de cache, aumentando em agressividade:

1. Cache conservador
2. Cache progressivo
3. Cache de Página

Além disso, os desenvolvedores do Joomla podem usar funcionalidades de cache para armazenar o resultado de consultas ao banco de dados, por exemplo, para aumentar a capacidade de resposta do site, mas isso está fora do escopo das capacidades do Administrador.

## Cache de Páginas

Para ativar isso, vá para Administrador → Extensões → Plugins. Encontre o plugin Sistema – Cache de Página e habilite-o. Isso significa que as páginas do site agora serão armazenadas em cache e, sempre que forem solicitadas novamente, a página em cache será servida, em vez de ser gerada pelo Joomla a partir das informações no banco de dados. A página em cache continuará a ser servida até expirar – conforme definido pelo parâmetro *Tempo de Cache* em Administrador → Configuração Global → Aba Sistema → Configurações de Cache.

Se estiver lendo esta página como um tutorial e quiser testar o cache de página, é melhor definir as configurações de cache na Configuração Global para:

- Manipulador de Cache – Arquivo
- Caminho para a Pasta de Cache – deixar em branco
- Tempo de Cache – 15 (o padrão de 15 minutos)
- Cache Específico da Plataforma - Não
- Cache do Sistema – DESLIGADO – Cache desativado

Para verificar se o cache de página está funcionando, vá para uma página do site que exiba um artigo. Após exibir essa página, você deverá encontrar no sistema de arquivos um diretório `cache/page` com um arquivo cujo nome é algo como `xxx-cache-page-yyy.php`, onde xxx e yyy são longas sequências de hash. O Joomla precisa armazenar páginas de cache separadas para URLs separadas, portanto, a segunda sequência de dígitos hexadecimais é um hash do URL da página da web, para tornar o nome do arquivo exclusivo para essa página.

Então, use a funcionalidade do Administrador para alterar o texto desse artigo e reexibir a página da web do site. Você deverá encontrar a versão em cache, não o seu texto modificado.

Alterar um artigo (ou outro item do Joomla) não limpa o cache de página para as páginas da web onde esse artigo é exibido. Para limpar o cache da página, vá para Administrador → Sistema → Limpar Cache. Clique na caixa de seleção ao lado do *Grupo de Cache* chamado "page" e pressione o botão Excluir. Quando você reexibir sua página da web, agora ela deve mostrar seu texto alterado.

Se o seu site tiver uma função como um carrinho de compras, aplicar cache de página causará problemas, pois as páginas precisam mostrar o que o cliente já selecionou, em vez de exibir uma página em cache que é comum para todos. No entanto, você pode configurar o plugin Sistema - Cache de Página para excluir o cache de Itens de Menu especificados ou URLs e intervalos de URLs especificados (na aba Avançado), de modo que apenas páginas verdadeiramente estáticas sejam armazenadas em cache.

## Cache Conservadora

Com o Cache Conservadora, você pode armazenar em cache a saída de exibição de componentes e a saída de módulos que permitem cache. Mas note que isso funcionará apenas em páginas que não estão em cache usando o Cache de Página. Para essas páginas, toda a página da web é armazenada em cache, e o Cache Conservadora nem é considerado.

Para ativar o Cache Conservadora:

1. Vá para Administrador → Sistema → Configuração Global → aba Sistema e, dentro das Configurações de Cache, defina Cache do Sistema para ON – Cache conservadora.
2. Vá para Administrador → Extensões → Módulos e selecione os módulos que você gostaria de cachear. Se esse módulo permitir cache, então na aba Avançado você deve conseguir definir Cache para

- Usar Global – este módulo será armazenado em cache (com a opção Global agora configurada para Cache conservadora).
- Sem cache – este módulo não será armazenado em cache.

(Note que o Tempo de Cache na Configuração Global está em minutos, mas o Tempo de Cache nas configurações do Módulo está em segundos.)

Para verificar se está funcionando, acesse seu site, **certifique-se de que você está desconectado**, e navegue até uma página web que exiba um artigo. Verifique seu sistema de arquivos e você deverá encontrar uma pasta `cache/com_content` contendo um arquivo de cache.

Você também encontrará outros diretórios como `cache/com_languages` (já que exibir a página envolve carregar o idioma atual, o que também será armazenado em cache) e também diretórios relacionados ao cache de módulos, por exemplo, `cache/com_modules`. Esses são resultados do uso de cache que os desenvolvedores implementaram dentro da aplicação Joomla.

Se você editar e salvar aquele artigo e depois atualizar a página do site, verá que o site exibe o texto atualizado desta vez. Isso ocorre porque sempre que a edição é salva, o Joomla limpa o cache para aquele artigo.

No entanto, você pode demonstrar que o cache está funcionando se editar o arquivo de cache no diretório `cache/com_content` usando um editor de texto básico. Usando o editor, altere uma letra dentro do texto do artigo no arquivo de cache e salve o arquivo. Então, quando atualizar a página web, você deverá ver a alteração que fez no arquivo de cache.

Como você pode selecionar quais visualizações de componentes serão armazenadas em cache, e em quais circunstâncias? Infelizmente, você não pode fazer isso. Isso é determinado pelos desenvolvedores do núcleo do componente Joomla e codificado no código PHP do componente. Os critérios são diferentes para cada componente. No entanto, você pode descobrir facilmente quais critérios são usados porque, para cada um dos componentes do site, eles estão codificados no arquivo `DisplayController.php` do site. Por exemplo, no momento desta revisão (versão Joomla 5) para o componente Contatos, encontramos em `components/com_contact/src/Controller/DisplayController.php`

```php
public function display($cachable = false, $urlparams = [])
{
    if ($this->app->getUserState('com_contact.contact.data') === null) {
        $cachable = true;
    }
```

Isso significa que as visualizações associadas a contatos serão armazenáveis em cache, a menos que haja dados de sessão associados a com_contact.contact.data – o que será o caso se na sessão do usuário o mesmo tiver exibido um formulário de contato (por exemplo, em uma página apontada por um item de menu do tipo Contatos → Contato Único).

O arquivo equivalente para artigos `components/com_content/src/Controller/DisplayController.php` contém:

```php
public function display($cachable = false, $urlparams = false)
{
    $cachable = true;

    /**
     * Define o nome e formato da visualização padrão do Request.
     * Note que estamos usando a_id para evitar colisões com o roteador e a página de retorno.
     * A interface é um pouco mais confusa do que o backend.
     */
    $id = $this->input->getInt('a_id');
    $vName = $this->input->getCmd('view', 'categories');
    $this->input->set('view', $vName);

    $user = $this->app->getIdentity();

    if (
        $user->get('id')
        || ($this->input->getMethod() === 'POST'
        && (($vName === 'category' && $this->input->get('layout') !== 'blog') || $vName === 'archive'))
    ) {
        $cachable = false;
    }
```

A expressão `$user->get('id')` é verdadeira se este for um usuário conectado. Isso significa que artigos nunca são armazenados em cache para usuários conectados. As expressões subsequentes se referem a outras condições nas quais o cache não é realizado, mesmo que o usuário não esteja conectado.

Dessa forma, você pode descobrir as circunstâncias em que o cache é realizado, mas alterar essas não é aconselhável. Você também pode demonstrar que os módulos estão sendo armazenados em cache usando o módulo Breadcrumbs do Joomla, certificando-se de que ele seja exibido em alguma posição de módulo na página da web, configurando sua opção de Cache e editando manualmente o arquivo de cache em cache/mod_breadcrumbs.

## Cache Progressivo

Assim como o Cache Conservador, o Cache Progressivo também armazena em cache a saída das visualizações dos componentes e dos módulos. A diferença funcional entre os dois é que, com o Cache Progressivo, **para usuários desconectados, todos os módulos são sempre armazenados em cache**. Nesse caso, definir a opção *Sem Cache* para um módulo não tem efeito. Se a opção de armazenamento em cache estiver definida como *Arquivo*, você poderá encontrar o arquivo de cache dos módulos (a saída de todos os módulos é armazenada dentro do mesmo arquivo) no diretório `cache/com_modules`.

Para ativar o Cache Progressivo, vá para Administrador → Sistema → Configuração Global → aba Sistema e dentro de *Configurações de Cache*, defina *Cache do Sistema* para *LIGADO – Cache progressivo*.

No que diz respeito às condições para o cache das visualizações de componentes principais do Joomla, **não há diferença entre cache conservador e progressivo**. Apesar do que você pode ler em alguns sites e respostas a perguntas no Stack Overflow, não é o caso de que o Cache Conservador se relacione a quando o usuário não está conectado e o Cache Progressivo a quando o usuário está conectado.

## Resumo

Segue abaixo um resumo dos tipos de cache.

### Cache de Página Inteira

- **Configuração**: Plugin Embutido (Administrador → Extensões →
  Gerenciador de Plugins → Sistema - Cache de Página)
- **Cache**: cada página inteira do seu site
- **Baseado em**: URL
- **Mais informações**:
  - Cache opcional do navegador: Também armazena no navegador/computador dos seus visitantes
  - Armazena somente páginas para visitantes não autenticados (não para visitantes logados). Tenha cuidado ao usar este plugin se você tiver um site interativo onde deseja servir conteúdo baseado em informações de sessão/cookie em vez de apenas na URL simples. Recursos como um carrinho de compras não funcionarão.

### Cache de Visualização

- **Configuração**: Configuração Global -\> Cache
- **Cache**: cada visualização de um componente
- **Baseado em**: URL, visualização, parâmetros, ...
- **Mais informações**: Desenvolvedores de componentes precisam incluir isso em seu código para funcionar. Na maioria das vezes isso não é feito. O componente principal de conteúdo do Joomla usa isso, mas apenas para visitantes não autenticados do seu site, embora não seja obrigatório para todos os componentes.

### Cache de Módulo

- **Configuração**: Configuração Global -\> Cache
- **Cache**: cada módulo (personalizado individualmente através dos Parâmetros Avançados de cada módulo)
- **Baseado em**: o id do módulo, os níveis de visualização do usuário e o parâmetro *Itemid* na requisição HTTP
- **Mais informações**: Você deve desativá-lo em alguns módulos para evitar problemas

### Cache Adicional

Se você quiser explorar outros sistemas e possibilidades de cache, pode querer conferir as extensões de terceiros relacionadas a cache.

### Mecanismos ou Armazenamentos de Cache

- **Configuração**: Configuração Global -\> Cache

Aqui você pode escolher qual sistema deseja que seu site use para todos os cacheamentos. Algumas opções são: APC, Eaccelorator, Arquivo, Memcache, Redis, XCache.

APC, por exemplo, também armazena o opcode do seu PHP.

## Para Desenvolvedores

<div class="alert alert-warning">
Esta seção precisa de revisão para Joomla! 4/5.
</div>

A classe **JCache** permite vários tipos e níveis diferentes de cache. As seguintes subclasses são feitas especificamente, mas você pode adicionar suas próprias, ou usar a principal de várias maneiras diferentes.

Não se esqueça de que o primeiro nível de cache encontrado irá substituir qualquer cache mais profundo. Presumo que muitos níveis também sejam contraproducentes (*a ser verificado, no entanto*).

- **JCacheView** armazena em cache e retorna a saída de uma determinada visualização (em MVC). Um ID de cache é gerado automaticamente a partir do URI, da visualização específica e do seu método específico, ou você pode fornecer o seu próprio.

Isso pode ser feito automaticamente através da função de exibição do controlador base. Por exemplo, no controlador do seu componente:

    class DeliciousController extends JController {
        function display() {
            parent::display(true); //true solicita cache.
        }
    }

Também existem alguns parâmetros de URL a considerar. Confira este
[Joomla StackExchange](http://joomla.stackexchange.com/questions/5781/how-can-i-use-joomlas-cache-with-my-components-view/7000#7000)

Além disso, esteja ciente de que quaisquer atualizações (como acessos ou contagens de visitas) NÃO serão atualizadas (a menos que você adicione isso fora deste método e, portanto, em qualquer parte profunda do MVC).

- **JCachePage** armazena em cache e retorna o corpo da página.
- **JCacheCallback** armazena em cache e retorna a saída e os resultados de funções ou métodos.

Se você deseja armazenar consultas em cache, esta é uma boa classe para isso, como ilustrado aqui: Usando cache para acelerar seu código

- **JCacheOutput** armazena em cache e retorna a saída.

Isso é mais voltado para armazenar em cache uma parte específica do código PHP. Atua como um buffer de saída, mas em cache.

*Traduzido por openai.com*

