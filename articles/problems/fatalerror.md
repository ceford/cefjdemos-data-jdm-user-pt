<!-- Filename: J4.x:FatalError / Display title: ErroFatal -->

## Introdução

De vez em quando, o Joomla pode exibir uma página de erro em vez da página que você esperava. Existem dois tipos de páginas de erro:

- A página de erro do sistema tem um fundo vermelho. Ela é acionada se houver um erro grave antes que o template do site ou do administrador seja renderizado.
- A página de erro do template se parece com o template normal do site ou do administrador, mas a área de conteúdo é substituída por uma mensagem de erro. Isso é acionado quando o erro ocorre no código de conteúdo.

### Página de Erro do Sistema

![Página de erro fatal do sistema](../../../en/images/problems/fatal-error.png)

### Página de Erro do Template

![Página de erro do template](../../../en/images/problems/template-error.png)

## Como Resolver

Existem várias razões possíveis para que ocorram erros fatais. Aqui estão apenas algumas:

- Uma mudança em seu host, por exemplo, uma versão atualizada do PHP que não é compatível com o Joomla ou um de seus Extensões.
- Um problema com espaço em disco, uso de memória ou tempo de execução do script.
- Uma Extensão recém-instalada ou habilitada que não é compatível com o Joomla. Um plugin defeituoso pode desabilitar o login de Administrador!

### Habilitar Depuração

Se sua interface de Administrador **ainda** está funcionando:
- Vá para **Painel Inicial → Painel do Sistema → Configuração Global**. 
- Na aba Sistema, defina *Sistema de Depuração* como *Sim*.
- Na aba Servidor, defina *Relatório de Erros* como *Máximo*. 
- Então, clique em *Salvar & Fechar*.

Se sua interface de Administrador **não** está funcionando, edite o arquivo *configuration.php* na pasta raiz do seu site Joomla.

1. Altere as permissões de *444* ou *-r--r--r--* (ninguém tem permissão para escrever no arquivo) para *644* ou *-rw-r--r--* (apenas o Proprietário tem permissão para escrever).
2. Edite o arquivo com um editor de texto e configure `$debug` para `true` e `$error_reporting` para `'maximum'`.
3. *Salve* o arquivo.

Com as mudanças feitas, recarregue a página que estava causando o erro. Agora você deve ver uma trilha de execução. Exemplo:

![Página de erro de template](../../../en/images/problems/template-error-stack-trace.png)

O primeiro item na trilha de execução indica onde o erro foi disparado. Às vezes isso é suficiente para identificar a Extensão com defeito. Às vezes, a Extensão com defeito está mais abaixo na trilha de execução. Pode não significar muito para você, mas a trilha de execução é inestimável para os especialistas que respondem perguntas nos Fóruns do Joomla.

Se você puder identificar a Extensão com defeito, desative-a. Você pode fazer isso usando a interface de Administrador, se ela estiver funcionando. Caso contrário, use o phpMyAdmin para encontrar a Extensão na tabela de banco de dados `#__extensions` e defina seu valor `enabled` para `0`. Você não deve precisar desabilitar nenhuma Extensão principal do Joomla.

## Assistente de Postagem no Fórum

Para ajudar a resolver problemas, você deve baixar o [Assistente de Postagem no Fórum (FPA)](https://forumpostassistant.github.io/docs/) e carregá-lo na raiz do seu site Joomla. O link para encontrá-lo também está próximo do topo de cada página do Fórum Joomla. O FPA é um script PHP independente que analisa sua instalação do Joomla e informa o que pode estar errado. Novamente, isso pode não significar muito para você, mas os especialistas que respondem perguntas nos Fóruns podem pedir para vê-lo.

## Limpeza

Quando o seu problema for resolvido:

1. Vá para **Painel Inicial → Painel do Sistema → Configuração Global**
2. Selecione a aba Sistema e defina *Depurar Sistema* como *Não*.
3. Selecione a aba Servidor e defina *Relatório de Erros* como *Padrão do Sistema*.
4. *Salvar & Fechar*.
5. Remova o Assistente de Postagens do Fórum.

As permissões do `configuration.php` são definidas como somente leitura (444 ou *r--r--r--*) 
quando o formulário de Configuração Global é salvo. Não há necessidade de fazê-lo 
manualmente.

*Traduzido por openai.com*

