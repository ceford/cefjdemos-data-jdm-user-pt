<!-- Filename: J4.x:Module_Positions / Display title: Posições do Módulo -->

## Introdução

As posições dos módulos de um template são definidas em um arquivo templateDetails.xml e usadas em um arquivo index.php do template. Vários módulos podem ser atribuídos a uma única posição, portanto, raramente há necessidade de criar mais posições. Se você realmente quiser mais posições, precisará criar seu próprio template, mas isso não é abordado aqui.  

## Visualizar Posições dos Módulos

Existe uma opção de template que permite visualizar os locais dos módulos nos templates do Site e do Administrador, incluindo posições que não têm módulos atribuídos. Para habilitar este recurso:

- Selecione **Sistema **→** Templates do Site** no menu do Administrador.
- Selecione o botão `Opções` na Barra de Ferramentas.
- No formulário Template: Opções, defina **Visualizar Posições dos Módulos** como **Habilitado**.
- Salvar e Fechar

Para visualizar as posições dos módulos, você precisa adicionar ?tp=1 ou &tp=1 à URL.

- Se a URL não contiver um ponto de interrogação, adicione ?tp=1.
- Se a URL já contiver um ponto de interrogação, adicione &tp=1.

### Posições do Template do Administrador Atum

![templates atum template positions](../../../en/images/modules/template-positions-templates-page.png)

### Posições do Template do Site Cassiopeia

![templates cassiopeia template positions](../../../en/images/modules/template-positions-site-page.png)

Você também pode achar este diagrama de posições de módulo útil:

![cassiopeia template position diagram](../../../en/images/modules/cassiopeia-template-positions.png)

## Locais de Produção

Lembre-se de alterar a opção **Visualizar Posições dos Módulos** para **Desativado** nos locais de produção.

*Traduzido por openai.com*

