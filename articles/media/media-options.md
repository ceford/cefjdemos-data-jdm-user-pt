<!-- Filename: J4.x:Media:_Options / Display title: Mídia: Opções -->

## Introdução

A página *Mídia: Opções* é usada para controlar o upload e armazenamento de mídia, tanto imagens quanto arquivos. **Atenção:** existem implicações de segurança associadas a alguns tipos de arquivos - uma porta de entrada para hackers.

Para acessar o formulário *Mídia: Opções*, selecione o botão **Opções** na barra de ferramentas na página de Mídia. Os campos são bem comentados e vêm com valores padrão que devem ser adequados para quase todos os sites. Normalmente, você só precisa usar o formulário de opções se desejar manter Arquivos separados de Imagens ou se tiver um formato de arquivo incomum que não esteja incluído na lista padrão.

## Captura de Tela

![O formulário de Opções de mídia](../../../en/images/media/media-options.png)

## Caminho para Arquivos e Pastas

Estes são itens separados no formulário de configuração, mas ambos apontam para a pasta *images* em uma nova instalação do Joomla. Se você gostaria de armazenar mídias não-imagens separadamente (por exemplo, PDFs, Planilhas e Arquivos de Texto), use os passos a seguir:

1. Crie uma pasta chamada *files* na raiz da sua instalação do Joomla.
2. Ative o plugin *FileSystem - Local* e o configure, conforme descrito no artigo sobre [Localizações de Arquivos de Mídia](jdocmanual?article=user/media/media-file-locations).
3. Insira o nome da pasta, *files*, no campo *Caminho para a Pasta de Arquivos* do Formulário de Opções de Mídia.

No formulário de Opções, insira o nome da pasta no campo **Caminho para a Pasta de Arquivos**. Certifique-se de não usar o nome de uma pasta existente no núcleo do Joomla.

Após a configuração, você poderá escolher entre as pastas de imagens e arquivos na parte Local da visualização de Mídia.

![A página de mídia](../../../en/images/media/media-sample-data-cassiopeia.png)

## Tipos Adicionais de Imagem ou Documento

Você pode descobrir que uma Imagem ou Documento não pode ser carregado. Se isso acontecer, verifique se sua extensão está entre as *Extensões Permitidas*, se sua extensão está entre os *Tipos de Extensões Legais* para o meio, e se está entre os *Tipos de MIME Legais* (pode ser necessário pesquisar isso). Todos os três devem estar corretos ou o upload será negado. 
*Traduzido por openai.com*

