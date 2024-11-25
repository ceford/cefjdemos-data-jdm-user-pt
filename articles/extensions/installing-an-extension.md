<!-- Filename: Installing_an_extension / Display title: Instalando uma extensão  -->

## Documentação da Extensão

Antes de começar, é sempre prudente ler a documentação associada a uma extensão. A maioria das extensões possui páginas iniciais e fóruns, e é uma boa ideia consultá-los primeiro. Se houver um arquivo README incluído com a extensão, você deve lê-lo. Pode haver instruções especiais de instalação ou configuração.

## Sistema Instalar Extensões

O formulário Sistema / Instalar / Extensões está bastante bem documentado na tela de Ajuda. O que não é tão óbvio é que cada um dos métodos de instalação é um plugin. Nas primeiras edições do Joomla 4, o plugin Instalar da Web era o primeiro da lista e é possível que ainda seja o caso em versões que foram atualizadas. Ter esse método primeiro é inconveniente se você normalmente usa um dos outros métodos porque leva alguns segundos para buscar dados do site do Diretório de Extensões Joomla.

Para mudar a ordem:

- Vá para **Painel Inicial / Plugins**
- Selecione **instalador** no filtro suspenso **Selecionar Tipo**.
- Selecione o ícone **Ordem de Classificação** para revelar os alças de movimentação para ordenação (elipses verticais).
- Arraste o item **Instalador - Instalar da Web** para o final da lista.
- Volte para **Sistema / Instalar / Extensões** para ver o resultado.

Você estará então pronto para usar um dos métodos padrão de instalação.

### Enviar Arquivo de Pacote

Para a maioria das extensões e a maioria dos usuários, o procedimento será:

- Baixe a extensão para o seu computador local como um pacote de arquivo zip.
- No backend do seu site Joomla (administração) selecione **Sistema → Instalar → Extensões**.
- Na aba **Enviar Arquivo de Pacote**, selecione o botão *Procurar arquivo* e selecione o pacote de extensão no seu computador local ou arraste e solte o arquivo do seu gerenciador de arquivos.
- O processo de envio e instalação começa automaticamente.
- Algumas extensões podem fornecer instruções adicionais sobre a instalação.
- Note que módulos e plugins geralmente precisam ser habilitados antes de funcionarem.

### Instalar de Pasta

Algumas extensões podem ser muito grandes para usar o método Enviar Arquivo de Pacote, geralmente um limite no *Tamanho Máximo de Upload de Arquivo* definido pelo seu host. Nesse caso, você pode usar o método Instalar de Pasta.

- Crie um diretório temporário no seu disco rígido local e descompacte o arquivo de arquivamento da Extensão neste diretório temporário.
- Usando FTP, envie o conteúdo deste diretório (incluindo arquivos e subdiretórios) para o diretório /tmp na raiz do Joomla no seu servidor para que você tenha um caminho como /tmp/suaextensao.
- No campo de Diretório de Instalação, especifique o diretório do servidor onde você enviou os arquivos e subdiretórios do pacote, por exemplo, /home/usuario/public_html/tmp/suaextensao.
- Selecione o botão **Verificar e Instalar** e o Joomla! irá instalar o conteúdo do diretório fornecido.

### Instalar de URL

Em vez de baixar um arquivo zip para o seu computador local, você pode simplesmente usar o URL de download. O Joomla buscará o arquivo zip diretamente e economizará as etapas de download e upload dos métodos anteriores.

### Instalar da Web

Esta opção permite que você instale uma extensão diretamente do Diretório de Extensões Joomla!. A lista inicial está em ordem de número de avaliações, mas você pode selecionar por Categoria para encontrar rapidamente uma lista de extensões que podem atender às suas necessidades.

## Descoberta de Instalação do Sistema

Conforme descrito na tela de Ajuda, a função Descoberta permite que você instale extensões que são grandes demais para alguns sistemas, especialmente ambientes de hospedagem compartilhada de baixo custo. Algo que pode não ser óbvio é que você pode precisar criar pastas em diferentes locais no seu serviço de hospedagem, tipicamente:

- Carregar arquivos do site em siteroot/components/com_mybigcomponent
- Carregar arquivos de administrador em siteroot/administrator/components/com_mybigcomponent
- Carregar mídia (CSS e JavaScript) em siteroot/media/com_mybigcomponent
- Carregar arquivos de idioma do site em siteroot/language/en-GB se eles não estiverem em uma pasta de idioma na pasta do site do componente.
- Carregar arquivos de idioma do administrador em siteroot/administrator/language/en-GB se eles não estiverem em uma pasta de idioma na pasta de administração do componente.

Com isso feito, o Descoberta deve encontrar e permitir a instalação do componente e pode realmente funcionar.

## Idiomas de Instalação do Sistema

O idioma padrão é o inglês GB. Ele não pode ser removido ou instalado. 
Pode não ser óbvio, mas cada página carrega as strings apropriadas de en-GB 
primeiro para garantir que as chaves de idioma usadas pelos programadores 
não apareçam na saída da página. Se o idioma selecionado pelo usuário 
não for o inglês, então o idioma do usuário é carregado, substituindo as 
strings em inglês. Se um idioma não foi totalmente traduzido, o resultado 
será uma mistura de strings no idioma do usuário e em inglês. Isso pode 
parecer estranho, mas é melhor do que uma mistura de chaves de usuário 
e chaves de programador.

Na lista de idiomas disponíveis, selecione aqueles que você precisa instalar.
Alguns estão marcados com um botão verde para indicar que estão atualizados 
com a versão atual do Joomla. Outros estão marcados com um botão amarelo para 
indicar que não estão totalmente atualizados. Vá em frente e instale mesmo assim. 
Você pode ver algumas palavras em inglês em lugares que deveriam estar no seu 
idioma selecionado. Mas isso pode ser raro.

*Traduzido por openai.com*

