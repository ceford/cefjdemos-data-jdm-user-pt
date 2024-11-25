<!-- Filename: J6.x:Media_File_Locations / Display title: Localizações de Arquivos de Mídia  -->

## Introdução

Por padrão, o Joomla armazena tanto imagens de usuários quanto arquivos de documentos na pasta */images* da instalação do Joomla. Quaisquer links para essa mídia não são processados diretamente pelo Joomla. O servidor web os envia quando são solicitados pelo navegador.

Se você tiver muitos documentos, pode querer mantê-los em uma pasta separada, mais evidentemente uma pasta */files* também na raiz do site do Joomla.

Para configurar um local para arquivos que seja separado das imagens, primeiro crie uma nova pasta na raiz da sua instalação, por exemplo, **files**. Lembre-se, será parte de um link URL, então use letras minúsculas e sem espaços ou sinais de pontuação.

### Plugin FileSystem - Local

Encontre o plugin *FileSystem - Local* na lista de plugins e abra-o. Adicione sua recém-criada pasta *files* à lista de locais onde você pode manter a mídia. Basta clicar no botão + e selecionar **files** da lista de pastas disponíveis.

![Plugin Sistema de Arquivos](../../../en/images/plugins/plugin-group-file-system-local.png)

A opção **Criar Miniaturas** configurada como **Sim** causa a criação de pequenas imagens com uma altura ou largura máxima de 200 pixels em media/cache/com_media/thumbs com a mesma estrutura de pastas da pasta de mídia. Isso deve aumentar muito a velocidade de exibição de uma pasta com muitas imagens. Não é necessário para arquivos, pois eles são representados por ícones.

Certifique-se de que o plugin está habilitado. **Salvar & Fechar**.

*Traduzido por openai.com*

