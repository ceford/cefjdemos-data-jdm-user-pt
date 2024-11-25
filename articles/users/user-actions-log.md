<!-- Filename: J4.x:User_Actions_Log / Display title: Registro de Ações do Usuário -->

## Introdução

O componente Registro de Ações do Usuário (com_actionlogs) fornece uma infraestrutura para criar um registro de auditoria das atividades do site. As ações que são registradas podem ser ajustadas pelo administrador do site. Extensões de terceiros podem integrar-se ao componente para adicionar mensagens personalizadas ou fazer com que o sistema processe ações padrão do administrador.

**Nota:** Apenas Super Usuários têm acesso ao componente Registro de Ações do Usuário.

## Registro de Ações do Usuário

Para visualizar a lista de Registro de Ações do Usuário:

- Selecione **Usuários → Registro de Ações do Usuário** no menu do Administrador.

![página da lista de registro de ações do usuário](../../../en/images/users/user-actions-log-list.png)

A partir desta página, um Super Usuário tem uma visão global de todas as atividades
realizadas por usuários em um site.

- Exportar Selecionados como CSV: este botão exporta apenas os itens selecionados na
  lista visível.
- Exportar Todos como CSV: este botão exporta todos os registros. Os filtros são
  ignorados.
- Excluir: este botão exclui os itens selecionados.
- Limpar Registro: este botão exclui todas as entradas do registro.
- Opções: um formulário de configuração para definir as opções de registro.

## Opções

O formulário de Opções do Registro de Ações do Usuário permite que o Superusuário selecione quais eventos registrar e se deve incluir endereços IP nos dados do registro.

![página de opções do registro de ações do usuário](../../../en/images/users/user-actions-log-options.png)

## Plugins

O sistema de registro de ações usa vários plugins:

### Log de Ações - Joomla

Quando ativado, este plugin registra as ações principais dos usuários, incluindo ações como login/logout, atualização de artigo, adição de módulo. O plugin não possui parâmetros.

### Sistema - Log de Ações do Usuário

Quando ativado, este plugin define o número de dias após os quais os registros serão excluídos. Um valor de zero significa que os registros nunca serão excluídos automaticamente.

### Privacidade - Logs de Ações

Quando ativado, este plugin exporta os dados do log de ações para uma solicitação de privacidade do usuário.

## Módulo de Ações Mais Recentes

Este módulo é exibido apenas para Super Usuários no Painel Inicial.

![módulo de registro de ações do usuário](../../../en/images/users/user-actions-log-module.png)

