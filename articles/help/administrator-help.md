<!-- Filename: jdocmanual?manual=user&heading=help&filename=administrator-help.md / Display title: Ajuda do Administrador -->

## Introdução

Quase todas as páginas do Administrador do Joomla têm uma Barra de Ferramentas contendo um botão de **Ajuda** próximo ao canto superior direito da página. Apenas os Painéis não possuem uma Barra de Ferramentas e, portanto, um botão de Ajuda.

Muitas páginas também têm um botão rotulado como **Alternar Ajuda Inline**. Isso simplesmente exibe ou oculta uma descrição do campo, se disponível. Seu propósito é reduzir a desordem, mas fornecer um mecanismo de lembrete onde isso seria útil. Não é coberto em detalhes aqui.

O botão de **Ajuda** aciona a abertura de uma nova janela usando uma URL incorporada no botão. Um exemplo:
```
data-url="https://help.joomla.org/proxy/index.php?keyref=Help51:Articles&lang=en"
```
Nesse caso, o conteúdo da página de Ajuda vem de uma fonte externa.

## The Help Source - um site MediaWiki

MediaWiki é o software usado pela Wikipedia. É um pacote de Software Livre e de Código Aberto (FOSS) que utiliza PHP e MySQL, assim como o Joomla. Você pode baixá-lo e instalá-lo por conta própria. Em teoria, você poderia criar seu próprio servidor de Ajuda e usá-lo em vez do servidor de Ajuda comunitário do Joomla. Na prática, é necessário saber que as páginas do MediaWiki precisam de algum processamento para serem adequadas à exibição como páginas de Ajuda.

É aí que entra o **proxy**. Ele busca a página necessária da instalação do MediaWiki e a prepara para exibição como uma página de Ajuda. Você pode ver uma página original do MediaWiki neste exemplo em https://docs.joomla.org/Help5.x:Articles e pode editá-la se encontrar algo errado.

## A URL de Ajuda Global

O arquivo **configuration.php** na raiz de uma instalação do Joomla contém uma variável `$helpurl`:

```
$helpurl = 'https://help.joomla.org/proxy/index.php?keyref=Help{major}{minor}:{keyref}&lang={langcode}';
```

Quando um botão de Ajuda é selecionado, cada um dos itens entre chaves é substituído. Os valores {major} e {minor} são as configurações de versão para sua instalação. O {langcode} é o código do idioma atualmente selecionado para o Administrador, que pode ser en, de ou fr.

A variável {keyref} é o nome do arquivo de uma página no servidor de Ajuda, sem o seu namespace. Então, para a página Artigos, o nome de arquivo relevante é *Articles*.

**Nota:** `https://docs.joomla.org/` é o site para editar páginas de Ajuda. Mas `https://help.joomla.org/proxy` é o site para recuperar páginas de Ajuda.

Não há provisão para alterar a URL do servidor de Ajuda padrão a partir dos formulários de Configuração Global do Administrador, mas você pode alterá-la com um editor de texto.

A lista completa de códigos de substituição disponíveis é:

| Código        | Será substituído por                                                          |
|---------------|--------------------------------------------------------------------------------|
| {app}         | Nome da aplicação (por exemplo, "Administrator" no back-end do Joomla CMS)     |
| {component}   | Nome do componente (por exemplo, "com_content" no Gerenciador de Artigos)      |
| {keyref}      | Referência da chave da tela de Ajuda (após passar pelo sistema de tradução)    |
| {major}       | Número de revisão maior do Joomla (por exemplo, "5" no Joomla 5.6).            |
| {minor}       | Número de revisão menor do Joomla (por exemplo, "1" no Joomla 5.1)             |
| {maintenance} | Número de revisão de manutenção do Joomla (por exemplo, "3" no Joomla 5.1.1).  |
| {language}    | Código completo do idioma (por exemplo, "en-GB")                               |
| {langcode}    | Parte do código do idioma (por exemplo, "en" se o código completo é "en-GB")   |
| {langregion}  | Parte do código de região do idioma (por exemplo, "GB" se o código completo é "en-GB") |

## Ajuda Global no Futuro

O uso de um site MediaWiki para a entrega de páginas de Ajuda é um tanto quanto um fardo para aqueles que mantêm a documentação, e o procedimento pode mudar no futuro. Se houver uma mudança, é provável que a fonte consista de arquivos HTML pré-construídos acessados com uma simples alteração do domínio de origem de $helpurl.

## Ajuda Local para Componente Personalizado

Se você possui um componente personalizado e está confortável em editar o código fonte PHP e criar conteúdo, pode criar suas próprias páginas de ajuda individuais. Tome o componente Jdocmanual como exemplo. Sendo um componente personalizado, não há páginas de ajuda no site MediaWiki docs.joomla.org. Componentes de terceiros não têm permissão para servir páginas de ajuda a partir de lá.

Veja este fragmento de código de administrator/components/com_jdocmanual/src/View/Manual/ViewHtml.php:
```
        $tmpl = $app->input->getCmd('tmpl');
        if ($tmpl !== 'component') {
            ToolbarHelper::help('jdocmanual', true);
        }
```
A especificação da chamada ToolbarHelper::help é a seguinte:
```
@param $ref: O nome do arquivo alvo (excluindo a extensão do arquivo).
@param $useComponent: Usar o arquivo de ajuda no diretório do componente.
@param $url: Usar este URL em vez de qualquer outro.
@param $component: Nome do componente para obter Ajuda (null para o componente atual)
function Toolbar::help(
    string $ref,
    bool $useComponent = false,
    string $url = null,
    string $component = null
): HelpButton
Escreve um botão de ajuda para uma determinada opção (abre uma janela popup).
```
Neste exemplo, **$ref** é um nome de arquivo a ser usado, neste caso `'jdocmanual'` (deve corresponder ao caso do arquivo alvo) e **$useComponent** é `true`, significando que a página de ajuda a ser usada estará localizada dentro dos arquivos do componente em administrator/component/com_jdocmanual/help/en-GB/jdocmanual.html

Usar um arquivo de ajuda dentro do componente deve significar que a Ajuda nunca está ausente e, talvez, sempre atualizada.

## Ajuda Remota de Componente Personalizado

Na criação do botão de Ajuda, você pode definir $useComponent = false e configurar
a URL para apontar para um local específico no seu próprio site ou um site remoto.

```
    ToolbarHelper::help('jdocmanual', false, 'http://example.com/help/pt-BR/jdocmanual.html');
```

Assim, tudo o que é necessário é uma página HTML com o nome correto no local correto.

*Traduzido por openai.com*

