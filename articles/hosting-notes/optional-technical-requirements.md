<!-- Filename: J4.x:Optional_Technical_Requirements / Display title: Requisitos Técnicos Opcionais -->

Esta página lista os requisitos técnicos *opcionais* que não são necessários para instalar e executar o Joomla!, mas são necessários para algumas APIs internas. A lista foi criada para o Joomla 4.

| Item                      | Descrição                                                                                                                                       |
|---------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| **Aplicação**             |                                                                                                                                                 |
| JApplicationDaemon        | Requer `ext/pcntl` e `ext/posix` do PHP                                                                                                         |
| **Arquivo**               |                                                                                                                                                 |
| BZ2                       | Requer `ext/bz2` do PHP                                                                                                                         |
| GZip                      | Requer `ext/zlib` do PHP                                                                                                                        |
| Zip                       | Requer `ext/zip` ou `ext/zlib` do PHP                                                                                                           |
| **Cache**                 |                                                                                                                                                 |
| APC                       | Requer `ext/apc` do PHP nas versões 5.3 ou 5.4, `ext/apcu` nas versões 5.5 ou 5.6; não é compatível com o PHP 7.x (Nota: ISSO PRECISA SER VERIFICADO) |
| APCu                      | Requer `ext/apcu` do PHP nas versões 5.3+                                                                                                       |
| CacheLite                 | Requer o pacote PEAR Cache_Lite (testado na versão 1.7.16, funcionará com 1.8)                                                                  |
| Memcache                  | Requer `ext/memcache` do PHP e um servidor Memcache (Nota: A extensão Memcache não é compatível com o PHP 7.x)                                  |
| Memcached                 | Requer `ext/memcached` do PHP e um servidor Memcached                                                                                           |
| Redis                     | Requer `ext/redis` do PHP e um servidor Redis                                                                                                   |
| Wincache                  | Requer `ext/wincache` do PHP (apenas para Windows)                                                                                              |
| XCache                    | Requer `ext/xcache` do PHP                                                                                                                      |
| **Adaptadores de Cliente**|                                                                                                                                                 |
| LDAP                      | Requer `ext/ldap` do PHP                                                                                                                        |
| HTTP/Curl                 | Requer `ext/curl` do PHP                                                                                                                        |
| HTTP/Socket               | Requer que a função `fsockopen()` do PHP esteja habilitada                                                                                      |
| HTTP/Stream               | Requer a função `fopen()` do PHP e que `allow_url_fopen` esteja habilitado                                                                      |
| **Criptografia**          |                                                                                                                                                 |
| JCrypt                    | Requer `ext/mcrypt` do PHP para todos os cifradores exceto o SodiumCipher que requer `ext/sodium`                                               |
| JKeychain                 | Requer `ext/openssl` do PHP                                                                                                                     |
| **Banco de Dados**        |                                                                                                                                                 |
| Microsoft SQL Azure       | Requer `ext/sqlsrv` do PHP (a extensão PHP 5.x só suporta Windows, uma versão compatível com Linux da extensão está disponível para PHP 7.x)    |
| Microsoft SQL Server      | Requer `ext/sqlsrv` do PHP (a extensão PHP 5.x só suporta Windows, uma versão compatível com Linux da extensão está disponível para PHP 7.x)    |
| MySQL                     | Requer `ext/mysql` do PHP (não é compatível com PHP 7.x)                                                                                        |
| MySQLi                    | Requer `ext/mysqli` do PHP                                                                                                                      |
| Oracle                    | Requer `ext/pdo` do PHP com suporte Oracle (disponível apenas para 3PD; o CMS não funciona com ele)                                             |
| PDO MySQL                 | Requer `ext/pdo` do PHP com suporte MySQL                                                                                                       |
| PostgreSQL                | Requer `ext/pgsql` do PHP                                                                                                                       |
| SQLite                    | Requer `ext/pdo` do PHP com suporte SQLite (disponível apenas para 3PD; o CMS não funciona com ele)                                             |
| **Imagem**                |                                                                                                                                                 |
|                           | Requer `ext/gd` do PHP                                                                                                                          |
|                           | Requer `ext/fileinfo` do PHP                                                                                                                    |
| **Sessão**                |                                                                                                                                                 |
| APC                       | Requer `ext/apc` do PHP nas versões 5.3 ou 5.4, `ext/apcu` nas versões 5.5 ou 5.6; não é compatível com o PHP 7.x (Nota: ISSO PRECISA SER VERIFICADO) |
| Memcache                  | Requer `ext/memcache` do PHP e um servidor Memcache (Nota: A extensão Memcache não é compatível com o PHP 7.x)                                  |
| Memcached                 | Requer `ext/memcached` do PHP e um servidor Memcached                                                                                           |
| Wincache                  | Requer `ext/wincache` do PHP (apenas para Windows)                                                                                              |
| XCache                    | Requer `ext/xcache` do PHP                                                                                                                      |
| **MELHORIAS OPCIONAIS**   |                                                                                                                                                 |
| **String**                |                                                                                                                                                 |
| mbstring                  | Habilitar o `ext/mbstring` do PHP para que a biblioteca phputf8 use funções nativas                                                             |

*Traduzido por openai.com*

