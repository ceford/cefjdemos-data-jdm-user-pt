<!-- Filename: jdocmanual?manual=user&heading=extensions&filename=vulnerable-extensions.md / Display title: Extensões Vulneráveis  -->

## Fontes de Extensões

Qualquer pessoa pode escrever e distribuir uma extensão do Joomla! como um serviço para a comunidade global. Essas extensões de **terceiros** podem ser encontradas em sites de desenvolvedores profissionais de extensões, sites de blogs pessoais, GitHub e repositórios similares, bem como no site do Diretório de Extensões Joomla.

## Extensões Vulneráveis

Muito poucas fontes oferecem extensões deliberadamente maliciosas. Normalmente, uma **extensão vulnerável** é aquela que foi identificada como contendo (ou contribuindo para) uma vulnerabilidade de segurança após seu lançamento inicial.

Extensões vulneráveis não são necessariamente mal codificadas. À medida que a Web evolui, os requisitos técnicos e as práticas de codificação comumente aceitas mudam. Projetos ativos lançam novas versões de suas extensões conforme os requisitos mudam e rapidamente corrigem quaisquer vulnerabilidades relatadas.

Se você estiver preocupado com qualquer uma de suas extensões, deve consultar a lista de Extensões Vulneráveis do Joomla (VEL), que contém informações sobre mais de 240 extensões, em sua maioria antigas.  

## O Verificador JED

Se você está preocupado com uma extensão que não aparece na VEL, você pode usar a extensão JED Checker. Esta é uma extensão utilizada para verificar extensões submetidas para aparecer na lista do Diretório de Extensões Joomla. É instalada como qualquer outra extensão. Durante o uso, ela aceita um arquivo zip de uma extensão e examina seu conteúdo para verificar a conformidade com os padrões JED. É extremamente útil mesmo para extensões que não aparecem na lista JED. Aqui está um exemplo de captura de tela:

![resultado do verificador jed](../../../en/images/extensions/extensions-jed-checker.png)

Os 400 arquivos PHP sem o Aviso de Licença GPL estão em bibliotecas de terceiros com uma Licença diferente. Os 30 arquivos identificados pelo Script de Varredura Anti-Malware Joomla também estão nessas bibliotecas de terceiros. Há trabalho a fazer nos arquivos que estão sem a segurança JEXEC!  

## Removendo uma Extensão Vulnerável

### Faça uma Lista de Arquivos para Remover

Se você puder localizá-lo, leia o arquivo XML da extensão para determinar exatamente quais diretórios, arquivos, e tabelas do banco de dados foram adicionados ao seu sistema. O arquivo XML está no arquivo zip original usado durante o processo de instalação da extensão. Por exemplo, o arquivo zip para uma extensão chamada mod_vulnerable conteria um arquivo XML chamado mod_vulnerable.xml, e poderia conter uma lista de arquivos como a seguinte:

```
    mod_vulnerable.php
    mod_vulnerable/vulnerable_file.txt
    mod_vulnerable/another_vulnerable_file.txt
    mod_vulnerable/yet_another_vulnerable_file.txt
    mod_vulnerable/index.html
```

### Desinstale via o Instalador do Joomla

Usando o Instalador no backend do Administrador do Joomla, desinstale a extensão vulnerável. Você também pode precisar desinstalar módulos, componentes ou plugins relacionados.

### Verifique se o Processo de Desinstalação foi Completo

Não confie que a extensão removerá com segurança todos os seus arquivos. Compare diretórios e arquivos no seu sistema com a lista XML da extensão para garantir que todos os arquivos relacionados foram realmente removidos.

### Opcionalmente, Remova as Tabelas de Banco de Dados Relacionadas

Verifique seu banco de dados e remova quaisquer tabelas criadas pela extensão. Para facilitar o processo de atualização para novas versões, muitos scripts de desinstalação não removem as tabelas de banco de dados relacionadas. Você pode encontrar a lista de tabelas no arquivo XML de cada extensão.

Se você planeja instalar uma versão mais segura e compatível da mesma extensão e deseja reutilizar os dados existentes, geralmente você pode deixar as tabelas do banco de dados como estão.

### Remova os Links de Menu

Simplesmente remover os links do menu para uma extensão, ou despublicar um módulo **não** é suficiente para proteger seu site! Enquanto os arquivos da extensão existirem no seu servidor, você está vulnerável. Observe como, nos exemplos a seguir, um atacante pode ignorar o arquivo index do Joomla para direcionar diretamente a qualquer arquivo, de qualquer extensão.

```
    www.seu_site.org/components/com_bad_component/vulnerable_file.php
    www.seu_site.org/modules/mod_bad_module/vulnerable_file.php
```

*Traduzido por openai.com*

