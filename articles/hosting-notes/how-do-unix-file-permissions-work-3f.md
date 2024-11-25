<!-- Filename: How_do_UNIX_file_permissions_work%3F / Display title: Permissões de Arquivos UNIX -->

As permissões de arquivos Unix/Linux podem ser confusas. As permissões básicas do UNIX vêm em três tipos:

    Permissões do Proprietário: Controlam seu próprio acesso aos arquivos.
    Permissões de Grupo: Controlam o acesso para você e qualquer um no seu grupo.
    Outras Permissões: Controlam o acesso para todos os outros.

No Unix, quando as permissões são configuradas, o servidor permite que você defina permissões diferentes para cada uma dessas três categorias de usuários. Em um ambiente de servidor Web, as permissões são usadas para controlar quais proprietários de sites podem acessar quais diretórios e arquivos.

## Como são as permissões do Unix?

Ao visualizar seus arquivos via linha de comando usando o comando Unix `ls -l`, você verá linhas como as seguintes, uma para cada arquivo e diretório:
```
drwxr-xr-x@  7 nomeusuario  grupousuario    224 13 Feb 10:48 includes
-rw-r--r--@  1 nomeusuario  grupousuario   1060 13 Apr 21:00 index.php
```
Explicação:
* O primeiro caractere na linha é d para diretório ou - para arquivo, ou ...
* Os próximos 9 caracteres são 3 grupos de 3 representando leitura (r), escrita (w) e execução (x) ou um símbolo de menos (-) indicando nenhuma permissão para cada um de Proprietário, Grupo e Outros.
* O símbolo @ é um dos possíveis atributos estendidos,
* O número antes do nome de usuário é a profundidade do diretório.
* Os dois nomes são o nome de usuário do proprietário e o grupo de usuário,
* O número seguinte é o tamanho do arquivo em bytes.
* A data seguinte tem a hora para itens recentes ou o ano para itens mais antigos.
* Por último, está o nome do arquivo ou diretório.

Em uma ferramenta de FTP, a ordem pode ser diferente e pode haver mais ou menos informações.

### Proprietário (Usuário) refere-se ao nome de usuário

O Proprietário (Usuário) normalmente é você, essas permissões serão aplicadas ao nome da sua conta de hospedagem.

### Grupo refere-se ao grupousuario

As permissões do Grupo serão aplicadas a outras pessoas que estão no mesmo grupo que você; em um ambiente de hospedagem, é muito raro haver outras pessoas no mesmo grupo que você. Isso protege seus arquivos e diretórios de serem disponibilizados para qualquer outra pessoa que também tenha uma conta de hospedagem no mesmo servidor que você.

### Outros refere-se a todos os demais

As permissões de Outros serão aplicadas a qualquer outra pessoa no servidor que não seja você ou não esteja no seu grupo. Portanto, em um ambiente de Servidor Web, lembrando que normalmente ninguém mais está no seu grupo, isso é para todos os outros acessando o servidor, exceto você. Cada um dos três conjuntos de permissões é definido da seguinte maneira:

    r = Permissões de Leitura
    w = Permissões de Escrita
    x = Permissões de Execução

    Proprietário Grupo Outro
    r w x r w x r w x

Como muitos de vocês já sabem, as permissões são normalmente expressas como um valor numérico, algo como 755 ou 644. Então, como isso se relaciona ao que discutimos acima? Cada caractere das permissões é atribuído a um valor numérico, isto é atribuído em cada conjunto de três, portanto, precisamos usar apenas três valores e reutilizá-los para cada conjunto.

    Proprietário Grupo Outro
    r w x r w x r w x
    4 2 1 4 2 1 4 2 1

Agora que temos um valor que representa cada permissão, podemos expressá-las em termos numéricos. Os valores são simplesmente somados nos respectivos conjuntos de 3, o que nos dará três números que nos dirão quais permissões estão sendo definidas. Se disserem que um arquivo tem as permissões de 777, isso significaria que o seguinte é verdade.

    Proprietário Grupo Outro
    r w x r w x r w x
    4 2 1 4 2 1 4 2 1

Assim...

      4+2+1 4+2+1 4+2+1
    =   7     7     7

O Proprietário do arquivo teria permissões completas de Leitura, Escrita e Execução, o grupo também teria permissões completas de Leitura, Escrita e Execução, e o resto do mundo também poderia Ler, Escrever e Executar o arquivo. As permissões padrão, atribuídas pelo servidor aos arquivos e diretórios, são normalmente:

    Arquivos = 644
    Diretórios = 755

Essas permissões permitiriam, para arquivos;

    644 = rw- r-- r--
    Proprietário tem Leitura e Escrita
    Grupo tem apenas Leitura
    Outro tem apenas Leitura

e para diretórios;

    755 = rwx r-x r-x
    Proprietário tem Leitura, Escrita e Execução
    Grupo tem apenas Leitura e Execução
    Outro tem apenas Leitura e Execução

Agora, as coisas podem se complicar um pouco quando começamos a falar sobre Servidores Web compartilhados, o software do Servidor Web estará rodando com seu próprio nome de usuário e nome de grupo, a maioria dos servidores está configurada para usarem "apache" e "apache" ou "nobody" e "nobody" como nome de usuário e nome de grupo. Aqui está o problema. Seu Servidor Web executa como seu próprio usuário, e este usuário não é você nem está no seu grupo, portanto, os dois primeiros conjuntos de permissões não se aplicam a ele. Apenas as permissões do mundo (outro) se aplicam. Portanto, se você configurar um conjunto de permissões semelhante a 640 em seus arquivos do site, seu Servidor Web não poderá executar seus arquivos do site.

    640 = rw- r-- ---
    Proprietário tem Leitura e Escrita
    Grupo tem apenas Leitura
    Outro não tem direitos

O Servidor Web não recebe permissões e não pode Executar, Escrever ou, mais importante, sequer Ler o arquivo para entregar seu conteúdo ao navegador do visitante do site. Se um diretório fosse atribuído com permissões 750, isso teria o mesmo efeito, pois o Servidor Web não teria permissões para ler arquivos no diretório, mesmo que os arquivos dentro desse diretório tivessem permissões favoráveis.

    750 = rw- r-x ---
    Proprietário tem Leitura e Escrita
    Grupo tem Leitura e Execução
    Outro não tem direitos

Os diretórios têm uma peculiaridade extra: se um diretório não tiver a permissão de Execução definida no conjunto Mundial, então, mesmo que Leitura e Escrita estejam configuradas, se o programa não for executado como usuário ou grupo, ele ainda não poderá acessar os arquivos dentro do diretório. A configuração de Execução permite que o programa "Execute" comandos no diretório, portanto, sem isso, o programa (neste caso, um Servidor Web) não pode executar o comando "Ler" e, assim, não pode entregar seu arquivo ao navegador dos usuários.

## Como isso se Relaciona com o Joomla?

Boa pergunta, bem, na primeira instância, isso seria importante durante o processo de Instalação na Web. Se você se lembra de quando executou o Instalador Web de Joomla!, estávamos procurando por diretórios específicos para serem designados como graváveis. Vimos um bom número de postagens afirmando que houve problemas durante a instalação com permissões ou perguntando quais permissões são recomendadas. Alguns até consideram que a mensagem, pedindo permissão "Gravável", é muito vaga.

Infelizmente, como o Instalador Web não sabe como seu servidor está configurado, ele não pode ser mais específico, no entanto, uma vez que você entende as configurações de permissões e sabe um pouco sobre ambientes de Servidor Web, você realmente achará que o termo *gravável* é, na verdade, muito específico e uma descrição mais do que adequada do que o Joomla! precisa. Pensando na informação acima, você pode se lembrar que há três lugares onde as permissões de *gravação* podem ser definidas;

    Gravável pelo Proprietário
    Gravável pelo Grupo
    Gravável por Outros

Também lembrando que o Servidor Web geralmente não roda como seu próprio usuário ou no mesmo grupo. Quando você executa o Instalador Web a partir de um navegador, é o Servidor Web que tenta acessar os arquivos, assim, são as permissões "Outros" que se aplicarão a ele. Se as permissões "Outros" não permitem que o Servidor Web Leia, Grave ou Execute comandos nos diretórios do Joomla!, você receberá a mensagem dizendo que os diretórios não são *graváveis*.

Nesse caso, você precisará configurar as permissões "Outros" para ser "7" nos diretórios listados no Instalador Web. Assim, suas permissões totais podem ser algo como 757, e, no pior dos casos, pode ser necessário definir 777. Essas permissões muito abertas podem ser redefinidas para 755 após a execução do instalador, para ajudar na segurança dos seus diretórios e arquivos.

    757 = rwx r-x rwx
    O Proprietário tem Leitura, Escrita e Execução
    O Grupo tem Leitura e Execução
    Outros têm Leitura, Escrita e Execução

Para complicar ainda mais as coisas, muitas empresas de hospedagem usam software chamado phpsuExec ou suExec, essas ferramentas mudam a forma como o Servidor Web roda, onde ele normalmente não rodaria como seu nome de usuário, neste caso, roda. O uso das permissões *outros* pode não ser necessário, agora você pode precisar apenas configurar os diretórios para serem *graváveis* para seu próprio nome de usuário e nome de grupo, permitindo que as permissões do diretório sejam definidas como 755 ou 775 em vez de 757 ou 777.

    755 = rwx r-x r-x
    O Proprietário tem Leitura, Escrita e Execução
    O Grupo tem Leitura e Execução
    Outros têm Leitura e Execução

    775 = rwx rwx r-x
    O Proprietário tem Leitura, Escrita e Execução
    O Grupo tem Leitura, Escrita e Execução
    Outros têm Leitura e Execução

O Servidor Web ainda precisará da permissão de Execução para o nome de usuário e permissão de Leitura e Execução para o grupo, para que ele possa executar o comando de Leitura nos arquivos dentro do diretório. Novamente, estas permissões podem ser rebaixadas para 755 após o Instalador Web ser concluído. Isso cobre o básico para diretórios, e sobre os arquivos? Aqui as coisas ficam um pouco mais simples. A maioria dos arquivos que o Joomla! utiliza ficará bem com as permissões padrão 644.

    644 = rw- r-- r--
    O Proprietário tem Leitura e Escrita
    O Grupo tem Leitura
    Outros têm Leitura

Isso é válido se você não precisa gravar nos arquivos a partir do Servidor Web, as mesmas regras se aplicam aos diretórios se você tiver essa necessidade. Um arquivo que você pode querer ter "Gravável" pelo Servidor Web é seu arquivo configuration.php. Este é o arquivo de configuração do Joomla!, se você planeja mudar a configuração através da interface de administração Web, então este arquivo precisará ser Gravável pelo Servidor Web.

Se seu servidor precisou que as permissões de diretório fossem definidas como "Outros" Gravável para a instalação, então, provavelmente, esse arquivo também necessitará de 757 ou 777. Deixar este arquivo como 757 ou 777 é perigoso, pois você está permitindo que todos tenham acesso de "Escrita", muitas explorações de Web Site aproveitam-se desse fato; portanto, em geral, não é recomendado deixar este arquivo com estas permissões.

Se o seu Servidor Web tiver uma das ferramentas SU instaladas e você só precisou configurar 755 nos diretórios para a instalação, então, provavelmente, você só precisará definir 755 ou 775 neste arquivo para permitir edição através da interface Admin, e estas permissões são geralmente aceitas como mais seguras que 757 ou 777.

Em conclusão, quais permissões devem ser definidas para a instalação do Joomla!? Bem, como você pode ver, isso depende!

Sei que isso não é tão útil quanto você gostaria e certamente não é uma resposta definitiva, mas, em geral, após a instalação, qualquer configuração insegura de "7" pode ser redefinida para algo mais seguro. Por exemplo:

    Arquivos = 644
    Diretórios = 755

Essas permissões permitiriam, para arquivos:

    644 = rw- r-- r--
    O Proprietário tem Leitura e Escrita
    O Grupo tem apenas Leitura
    Outros têm apenas Leitura

e para diretórios,

    755 = rwx r-x r-x
    O Proprietário tem Leitura, Escrita e Execução
    O Grupo tem apenas Leitura e Execução
    Outros têm apenas Leitura e Execução

Se você tiver acesso ao shell SSH, os seguintes comandos podem ser executados a partir da linha de comando para redefinir todos os arquivos e diretórios de volta para os padrões do servidor de 755 e 644. Mude de diretório para o diretório superior ("/") da sua instalação do Joomla!, então execute:

    find . -type f -exec chmod 644 {} \;
    find . -type d -exec chmod 755 {} \;

Se você tiver apenas acesso FTP, isso pode ser um trabalho muito demorado, no entanto, a menos que você tenha alterado mais diretórios durante a instalação do que o solicitado, você deve precisar redefinir apenas cerca de 10 diretórios e o arquivo *configuration.php*.

Lembre-se que para instalar quaisquer extensões ou templates após a instalação real do Joomla! você pode precisar elevar as permissões padrão novamente nos diretórios apropriados apenas para o período de instalação, você pode então rebaixá-los novamente após o add-on ser instalado.

Se você decidir usar *cache*, o diretório de cache precisará ser *gravável* pelo usuário do servidor Web para permitir que ele escreva seus arquivos temporários.

## Corrigir permissões recursivamente

Em uma janela de terminal, começando a partir do diretório raiz do site Joomla, use os seguintes comandos para definir as permissões de arquivos e pastas para os padrões do Joomla.

```bash
find . -type f -exec chmod 644 {} \;
find . -type d -exec chmod 755 {} \;
```

Nota: O comando find assume que deve começar a partir do diretório atual. Para garantir, vá para o seu diretório public_html e especifique um caminho como o primeiro argumento. Alguns shells, como o bash no Apple OS X, devem ter um caminho especificado no comando find.

Teste todas as extensões de terceiros após alterar as permissões.

*Traduzido por openai.com*

