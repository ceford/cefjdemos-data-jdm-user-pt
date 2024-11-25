<!-- Filename: J4.x:Apache_PHP_Handler / Display title: Manipuladores PHP do Apache  -->

## Notas

Para determinar qual método seu servidor web está usando para lidar com arquivos PHP, use os links **Administrador / Sistema / Informações do Sistema** e selecione a guia Informações do PHP. Procure na página por **Server API**. As maneiras comuns de um servidor web Apache lidar com arquivos PHP incluem as seguintes:

### DSO (mod_php)

- **Vantagem**: um dos manipuladores mais rápidos disponíveis.
- **Desvantagem**: funciona apenas com uma única versão de PHP; arquivos salvos por scripts PHP são de propriedade do usuário Apache **exceto** quando usado em conjunto com mod_ruid2.
- **Para reconhecer**: Server API - Apache 2.0 Handler

### CGI/FastCGI

- **Vantagem**: scripts rodam como o usuário do domínio ou subdomínio, manipulador muito rápido.
- **Desvantagem**: mais lento que mod_php, não é possível colocar alterações de configuração PHP em um arquivo .htaccess.
- **Para reconhecer**: Server API - CGI/FastCGI

### FPM/FastCGI

- **Vantagem**: muito rápido, nível adicional de flexibilidade.
- **Desvantagem**: usa mais memória do que a maioria dos outros, não é possível colocar alterações de configuração PHP em um arquivo .htaccess.
- **Para reconhecer**: Server API - FPM/FastCGI

### LSAPI (mod_lsapi)

- **Vantagens:**
   - Oferece suporte para cache.
   - É o manipulador mais performante com um baixo consumo de memória.
   - Nenhuma configuração é necessária.
   - Pode funcionar com várias versões de PHP em uma única configuração.
   - Suporta diretivas de configuração PHP através de arquivos .htaccess.
   - Seguro porque os scripts são executados como o proprietário do domínio.
- **Desvantagens:**
   - Não disponibiliza todas as capacidades do LSAPI.
- **Para reconhecer**: Server API - ?

Em um computador local ou laptop, você pode usar mod_php, mas pode ser necessário definir o usuário do Apache para o seu próprio nome de usuário e apontar o diretório raiz do documento para um local no seu próprio espaço de arquivos. Caso contrário, você terá problemas de permissões de arquivos e pastas.

Em um serviço de hospedagem, você precisa usar uma das alternativas FastCGI ou LSAPI. Os serviços de hospedagem podem lhe dar uma escolha.

*Traduzido por openai.com*

