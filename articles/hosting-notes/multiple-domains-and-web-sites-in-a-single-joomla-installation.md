<!-- Filename: Multiple_Domains_and_Web_Sites_in_a_single_Joomla!_installation / Display title: Vários Domínios e Sites em uma única instalação do Joomla! -->

**Nota:** Este artigo foi atualizado pela última vez em 2012!

Embora seja uma prática recomendada dar a cada site seu próprio domínio,
instalação do Joomla! e banco de dados, podem existir condições especiais nas quais uma solução de múltiplos sites sob uma única instalação do Joomla! é justificada.

## Um Exemplo de Aplicação

Uma pequena empresa, 'Johnson Candies', possui duas marcas separadas, mas relacionadas: *Red Candy* e *Yellow Candy*. Eles precisam de um único site baseado em Joomla! onde ambos os tipos de doces sejam visíveis, cada um com sua própria página inicial no site Joomla! que corresponda aos domínios `www.redjohnsoncandy.com` e `www.yellowjohnsoncandy.com`.

Além disso, cada marca e site **requer seu próprio design**: um modelo amarelo para uma; um modelo vermelho, para a outra.

## Benefícios

Ao incluir ambas as marcas em uma única instalação Joomla!, a Johnson Candies consegue economizar tempo de edição (apenas um login), compartilhar artigos e dados entre as duas marcas (ou sites) e usar um único recurso, como um formulário de Contato, para ambas as marcas.

## Procedimento de Implementação

### Prepare Seus Domínios

Use um único domínio para sua conta de hospedagem, como de costume. Crie os domínios adicionais necessários no painel de controle da sua conta de hospedagem. Para fins deste tutorial, usaremos `www.redjohnsoncandy.com` além do domínio base `www.yellowjohnsoncandy.com`.

### Instale e Configure o Joomla!

Instale e configure o Joomla! normalmente. Em seguida, desenvolva artigos, menus e módulos para cada site.

### Crie Modelos

Em seguida, desenvolva e instale os modelos necessários - um para cada site que deseja ter. No exemplo acima, você criaria um modelo para *red candy* chamado *Modelo Vermelho* e um modelo para *yellow candy* chamado *Modelo Amarelo*. Depois que os modelos estiverem instalados, atribua-os aos itens de menu relevantes, usando o gerenciador de modelos do Joomla! na área do Administrador do Joomla!.

### Adicione um Redirecionamento

#### Opção #1: Crie um redirecionamento .htaccess (Apache)

**Nota** *Habilite URLs SEF no Joomla! Primeiro*

Uma opção é usar .htaccess (Apache) para redirecionar consultas de um determinado domínio para uma página específica do Joomla!.

Nosso objetivo é redirecionar qualquer consulta para o nome de domínio Red Candy para uma página específica no site Joomla!. Neste exemplo, redirecionamos qualquer consulta para `www.redjohnsoncandy.com` para uma página de blog de categoria. Você terá previamente atribuído o modelo 'red candy' a este item de menu, para criar a ilusão de um site separado.
```
#A seguinte regra funciona, mas altera o nome de domínio exibido.
RewriteCond %{HTTP_HOST} ^(www\.)?redjohnsoncandy\.com$
RewriteRule (.*) http://www.yellowjohnsoncandy.com/index.php?option=com_content&view=category&layout=blog&id=3&Itemid=12 [R=301,L]
```
Bem, isso funciona - mas você pode ver a desvantagem imediatamente. Embora o usuário esteja visualizando com sucesso o site Red Candy, ele ainda verá o nome de domínio Yellow Candy. Infelizmente, se você estiver usando tanto .htaccess quanto estacionamento de domínio (tecnicamente um redirecionamento) - isso é necessário para evitar a criação de um LOOP.

#### Opção #2: Crie um Redirecionamento de Cabeçalho PHP

Esta solução tem o benefício de manter a ilusão de domínios/sites separados aparente para o visitante. Em vez de usar .htaccess (Apache) para nosso redirecionamento, usamos um dos modelos no site.

Neste exemplo, o domínio base é `www.redjohnsoncandy.com`. Você criou um modelo para essa área chamado *Modelo Vermelho*. O truque é abrir o arquivo index.php do 'Modelo Vermelho' e adicionar o seguinte **como as primeiras linhas** do index.php principal da instalação.

```php
<?php
$domain = $_SERVER["HTTP_HOST"];
$uri = $_SERVER["REQUEST_URI"];
$url = $domain . $uri;

if (($url == "redjohnsoncandy.com/") ||
   ($url == "www.redjohnsoncandy.com/")) {
   header("Status: 301 Moved Permanently");
   header("Location: http://www.redjohnsoncandy.com/index.php?option=com_content&view=category&layout=blog&id=3&Itemid=12");
}
?>
```

Aqui está o benefício: O visitante agora será redirecionado para a página apropriada do *Site Vermelho*, que tem o *Modelo Vermelho* atribuído a ele **somente** no caso em que eles tenham chegado ao nome de domínio do 'site vermelho'. Caso contrário, a regra condicional PHP é ignorada, e o Site Amarelo carrega.

É importante lembrar de solicitar também o URI (URL que segue o domínio puro) para que você possa realizar redirecionamentos para o mesmo domínio. Quando o URI é invisível na URL, a variável se torna um sinal de "/". É por isso que você deve comparar seu URL puro com um sinal de "/" no final. Desta forma, você poderá fazer redirecionamentos 301 no mesmo domínio. Caso contrário, você criará um loop infinito no processo de redirecionamento.

#### Opção #3: Crie um Redirecionamento de Cabeçalho PHP, para múltiplos domínios com redirecionamentos de domínios específicos para modelos personalizados

Solução para um único espaço web, com diferentes domínios, uma única instalação Joomla e, dependendo do domínio de chegada do usuário, redireciona para uma página padrão diferente. Cole o seguinte código PHP **como a primeira coisa** no arquivo index.php principal da instalação. Para atribuir outro domínio, basta copiar/colar a função "if" e editá-la com os valores do outro domínio da mesma forma. Para configurar as visualizações de modelos, você terá que atribuir diferentes alias de item/link de módulo e configurar as visualizações de modelos no gerenciador de modelos do Joomla!. A configuração de alias é necessária quando você usa configurações SEF.
```php
<?php
$domain = $_SERVER["SERVER_NAME"];
$requri = $_SERVER['REQUEST_URI'];
if (($domain == "www.example.de" && $requri == "/" ||
   $domain == "example.de"))  {
   header("Status: 301 Moved Permanently");
   header("Location: http://www.example.de/index.php?option=com_content&view=article&id=6");
}
?>
```
*Traduzido por openai.com*

