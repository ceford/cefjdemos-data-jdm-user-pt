<!-- Filename: J4.x:Child_Templates / Display title: Modelos Filhos -->

## Introdução

Os templates filhos utilizam todos os arquivos de seus templates pais, exceto por quaisquer arquivos de mesmo nome que você coloque no template filho. Os arquivos de templates filhos não são afetados por atualizações do Joomla. Assim, você pode colocar seu próprio arquivo index.php em um template filho e fazê-lo entregar algo bastante diferente do template padrão, como posições de módulos extras ou substituições alternativas de extensões.

Um exemplo de cenário: suponha que você queira que algumas de suas páginas apareçam com um tema azul, as cores padrão do Cassiopeia, e outras páginas apareçam com um tema verde. Uma maneira fácil de fazer isso é com um template filho que utiliza sua própria folha de estilo user.css.

## Exemplo Trabalhado

Começando de **Sistema → Painel de Templates → Templates do Site**

- Selecione *Detalhes e Arquivos de Cassiopeia*.
- Selecione o botão *Criar Template Filho*.
- Preencha o diálogo popup do Template Filho e selecione o botão Criar
  Template Filho:

![formulário de criação de modelo filho](../../../en/images/templates/child-templates-create-green.png)

A seleção de Cassiopeia - Padrão no campo Estilos de Templates Adicionais
parece desnecessária (isso é um bug?).

- Selecione *Fechar* na Barra de Ferramentas para fechar o formulário do template pai.
- Selecione o novo template, *Detalhes e Arquivos de Cassiopeia_green*, na
  lista de Templates.

Neste estágio, há uma estrutura de pastas, mas apenas um arquivo:
templateDetails.xml. Esse arquivo pode ser modificado caso deseje alterar
aspectos da configuração do template, por exemplo, acrescentar ou remover
posições de template.

### Crie um arquivo user.css

- Selecione o botão *Novo Arquivo* na Barra de Ferramentas.
- No formulário *Criar ou Enviar um novo arquivo* certifique-se de selecionar a
  pasta `css`.
- Preencha o nome do arquivo com `user`. NÃO adicione um sufixo!
- Selecione o Tipo de Arquivo `.css`.
- Selecione o botão *Criar*.

![formulário de criação de user css do modelo filho](../../../en/images/templates/child-templates-create-green-user-css.png)

O arquivo user.css está vazio, pronto para você inserir alguns estilos personalizados.
Insira o seguinte para iniciar o tema verde:
```css
    .container-header {
      background-color: darkgreen;
      background-image: none;
    }
    h1, h2, h3, h4, h5, h6 {
      color: darkgreen;
    }
    .h1, .h2, .h3, .h4, .h5, .h6 {
      color: darkgreen;
    }
    a, a:hover, a:focus {
      color: darkgreen;
    }
    .btn-info {
        background-color: darkgreen;
        border-color: #30638d;
        color: #fff;
    }
    .btn-primary, .btn-primary:focus, .btn-primary:hover {
        background-color: darkgreen;
        border-color: var(--cassiopeia-color-hover);
    }

    .btn-check:focus + .btn-info, .btn-info:focus, .btn-info:hover {
        background-color: darkgreen;
        border-color: #264f71;
        color: #fff;
    }
```
Você pode precisar voltar a este arquivo user.css para adicionar mais estilos
posteriormente.

- Selecione *Salvar & Fechar* ou separadamente, *Salvar* e então *Fechar Arquivo*.
- Selecione *Fechar* para fechar o formulário Customizar.

### Item do Menu

Neste estágio, é necessário um item de menu para utilizar o template filho. Uma
nova instalação do Joomla 4 tem o Menu Principal na posição da barra lateral direita
com um item nele. Esse parece ser um bom lugar para um novo
item de menu.

- Selecione **Menus → Menu Principal** do menu do Administrador.
- Selecione o botão *Novo* na Barra de Ferramentas.
- Insira um título adequado, *Artigos Destacados Verdes* parece apropriado
  neste caso.
- Selecione o botão **Tipo de Item de Menu → Selecionar**.
- Selecione um tipo de item de menu do diálogo popup Tipo de Item de Menu -
  Artigos Destacados neste exemplo.
- Selecione *cassiopeia_manual - Padrão* no campo do formulário *Estilo do Template*.

![formulário de edição de item do menu de modelo filho](../../../en/images/templates/child-templates-create-green-menu-item.png)

- Para fins da captura de tela seguinte, o Layout de Blog foi configurado para 
  Artigos Principais: 0, Artigos de Introdução: 3 e Direção da Coluna Mult: Através.

### Visualização do Site

- Na página inicial do seu site, selecione o item de menu recém-criado.

![site mostrando o template de tema verde personalizado](../../../en/images/templates/child-templates-green-site-result.png)

### Editar o Estilo

- Selecione **Sistema → Painel de Templates → Estilos de Template do Site** no
  menu do Administrador.
- Selecione *Cassiopeia_green - Padrão* na lista de Estilos.
- Altere o Nome do Estilo para *Cassiopeia Verde*. Isso apenas organiza o
  nome como aparece nas listas.
- Selecione *Salvar e Fechar*.

*Traduzido por openai.com*

