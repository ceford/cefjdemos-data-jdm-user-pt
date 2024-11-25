<!-- Filename: J4.x:Article_Check-out_and_Check-in / Display title: Artigo: Check-in -->

## Introdução

Muitos sites Joomla têm múltiplos usuários que têm permissão para editar artigos. Para evitar que dois usuários tentem editar o mesmo artigo ao mesmo tempo, cada artigo tem um campo de banco de dados **checked_out** para indicar se ele está ou não em uso. Este campo é definido quando um artigo é aberto para edição e é desmarcado quando o formulário de edição é fechado usando os botões *Salvar & Fechar* ou *Fechar*.

Às vezes, um formulário de edição de artigo não é fechado corretamente, por exemplo, ao usar o botão voltar do navegador ou quando a sessão do usuário é encerrada. Nesse caso, o campo checked_out permanece definido. Isso é marcado nas listas de artigos com um pequeno ícone de cadeado. O ícone de cadeado também é visto onde um link de edição deveria estar ao fazer login no frontend do site.

Para restaurar a operação normal, os itens marcados como checked out precisam ser checkados novamente (checked in).

## Verificação de Artigo

Existem vários métodos disponíveis para fazer a verificação de um artigo.

- Se você foi a última pessoa a editar o artigo, poderá editá-lo a partir do backend ou frontend sem a necessidade de verificar.
- Entre em contato com a última pessoa que editou o artigo para ver se ela já terminou. Você pode passar o cursor sobre o cadeado e o pop-up de dica exibirá o nome do usuário que marcou a saída do artigo.
- Se você for um Super Usuário ou Administrador, pode selecionar o ícone de cadeado para fazer a verificação deste item.
- Você também pode selecionar vários artigos e usar o item *Verificar* no botão *Ações* na Barra de Ferramentas.
- Se você não puder fazer a verificação do item, peça a um Super Usuário ou Administrador para fazê-lo.

## Registro Global

Se você é um Super Usuário ou Administrador, pode usar a ferramenta de Registro Global para selecionar itens a serem registrados.

Esta ferramenta deve ser usada com muito cuidado, especialmente em ambientes com múltiplos usuários. Ela registra todos os itens previamente retirados, independentemente de terem sido retirados por você ou não. Possíveis efeitos colaterais indesejáveis podem incluir múltiplos editores trabalhando no mesmo documento. Nesse caso, quem clicar no botão de salvar por último terá sua versão salva como a cópia final.

Você também deve estar ciente de que muitas outras extensões têm campos **checked_out**. Por exemplo, módulos e categorias podem ser retirados para edição e deixados acidentalmente nesse estado.

No menu do Administrador:

- Selecione **Início Dashboard → Registro Global** ou
  **Sistema → Painel de Manutenção → Registro Global**.
- A lista mostra o número de itens retirados.

![Página de registro global](../../../en/images/articles/global-checkin.png)

- Na lista de tabelas do banco de dados, selecione a caixa de seleção para o tipo de item a ser registrado.
- Selecione *Registrar* na Barra de ferramentas.

Todos os itens retirados naquela tabela serão registrados.

## Tabelas com o campo checked_out

Você pode descobrir quais tabelas têm uma coluna checked_out com esta consulta
usada no phpMyAdmin:

```sql
SELECT DISTINCT TABLE_NAME FROM INFORMATION_SCHEMA.COLUMNS WHERE COLUMN_NAME IN ('checked_out') AND TABLE_SCHEMA='j423sd';
```

E o resultado deve ser assim:

```plaintext
TABLE_NAME
bi2hb_banner_clients
bi2hb_banners
bi2hb_categories
bi2hb_contact_details
bi2hb_content
bi2hb_extensions
bi2hb_fields
bi2hb_fields_groups
bi2hb_finder_filters
bi2hb_menu
bi2hb_modules
bi2hb_newsfeeds
bi2hb_scheduler_tasks
bi2hb_tags
bi2hb_update_sites
bi2hb_user_notes
bi2hb_workflow_stages
bi2hb_workflow_transitions
bi2hb_workflows
```

*Traduzido por openai.com*

