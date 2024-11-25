<!-- Filename: Moving_the_site_among_directories/sub-directories / Display title: Movendo o Diretório de Instalação -->

Muitas vezes você instala o Joomla em um subdiretório e depois quer movê-lo para um diretório de nível superior. Aqui está um pequeno tutorial sobre como fazer isso.

Digamos que você tenha instalado o Joomla na seguinte pasta: public_html/tryjoomla. Agora que você está satisfeito com o site, vai querer mover para public_html.

1. Mova todos os arquivos do subdiretório (ou seja, public_html/tryjoomla) para o diretório de nível superior (ou seja, public_html). Você pode usar seu cliente FTP favorito ou o painel de controle que o serviço de hospedagem fornece.
2. Baixe e abra o arquivo configuration.php em um editor de texto.
3. Simplesmente remova o nome da pasta tryjoomla do caminho. Procure as seguintes linhas
    ```
    var $live_site = '';
    var $log_path = '/home/username/public_html/tryjoomla/administrator/logs';
    var $tmp_path = '/home/username/public_html/tryjoomla/tmp';
    var $ftp_root = 'public_html/tryjoomla';
    ```
    Altere para:
    ```
    var $live_site = '';
    var $log_path = '/home/username/public_html/administrator/logs';
    var $tmp_path = '/home/username/public_html/tmp';
    var $ftp_root = 'public_html';
    ```
    Nota: A variável \$live_site raramente precisa receber um valor. Mas se foi dado um valor durante a instalação, edite esse caminho também.
    ```
    var $live_site = 'http://www.example.com/tryjoomla';
    ```
    Altere para:
    ```
    var $live_site = 'http://www.example.com';
    ```
4. Verifique o arquivo .htaccess do seu site. O subdiretório também deve ser removido dali. A diretiva RewriteBase deve ser comentada. Verifique se há uma RewriteRule que contém o subdiretório antigo.
5. Verifique se não há ordens de redirecionamento para o subdiretório antigo no painel de controle de hospedagem.
6. Se tiver cache habilitado, faça login no back-end administrativo (que agora estará em `http://www.example.com/administrator` e não mais em `http://www.example.com/tryjoomla/administrator`). Vá para Sistema / Cache e exclua todos os arquivos de cache.

*Traduzido por openai.com*
