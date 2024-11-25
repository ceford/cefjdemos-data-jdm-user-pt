<!-- Filename: J4.x:Module_and_Menu_Styles / Display title: Estilos de Módulo e Menu  -->

## Sobre Folhas de Estilo em Cascata

Uma página de website gerada pelo Joomla! consiste em tags HTML com atributos de estilo na forma de declarações de classe. Por exemplo, um cabeçalho dentro de um artigo pode ser `<h3 class="special-warning">Cuidado!</h3>`. Este cabeçalho pode ser formatado para aparecer em uma fonte maior, com cores diferentes para texto e fundo, e talvez uma borda e ícone de aviso. As classes de estilo seriam definidas no arquivo user.css no template, assim:

```css
    h3.special-warning {
      color: #900;
      background-color: #fee;
      border: 1px solid #900;
      padding: 1rem;
      font-size: 2rem;
    }
```

Isso funciona porque a folha de estilo user.css é carregada por último e qualquer estilo que ela contenha tem precedência sobre os mesmos estilos em arquivos css carregados anteriormente. O estilo `special-warning` não se aplica a outras tags `<h3>`, apenas àquelas com esta classe específica. Funciona dentro de um artigo porque lá você digita o nome da classe por conta própria.

Mas e se você quiser estilizar um módulo ou uma página inteira? Por exemplo, você poderia aplicar cores de fundo diferentes a diferentes módulos ou páginas. Ou poderia estilizar o cabeçalho da sua página inicial para diferir dos cabeçalhos de outras páginas. Tudo isso pode ser alcançado adicionando nomes de classes no formulário de edição do módulo ou no formulário de edição do item de menu. As classes de estilo são então inseridas no arquivo user.css.

## Estilos de Módulo

Este exemplo simples aplica estilos personalizados ao módulo de Login e ao seu título. A captura de tela a seguir mostra os nomes dos estilos inseridos na aba Avançada do formulário de edição Módulos: Login. A Classe do Módulo foi definida como `make-me-light-green` e a Classe do Cabeçalho foi definida como `make-me-dark-green`. Observe que você pode incluir sinais de menos ou sublinhados nos nomes das classes, mas espaços separam diferentes nomes de classes.

![formulário de edição do módulo de login aba avançada mostrando classe personalizada](../../../en/images/templates/templates-edit-module-style.png)

As seguintes declarações de estilo são usadas no arquivo user.css:
```css
    .make-me-light-green {
      background-color: #efe;
      border-color: darkgreen;
    }
    .make-me-dark-green {
      color: darkgreen;
      border-color: #264f71;
    }
```
Preste atenção no ponto (.) que é usado em css para definir uma classe com esse nome. O ponto não deve ser usado no formulário de entrada de dados do módulo. O resultado neste exemplo é o seguinte:

![aparência do site do módulo personalizado com ferramentas de desenvolvedor](../../../en/images/templates/templates-edit-module-style-result.png)

A parte inferior da imagem mostra o painel de Ferramentas de Desenvolvedor do navegador com a tag `<div>` que envolve o módulo de Login selecionada. Você pode ver que o estilo personalizado da Classe do Módulo foi adicionado aos estilos já definidos no modelo do módulo. A linha seguinte mostra a tag `<h3>` também com a Classe do Cabeçalho personalizada adicionada aos estilos já definidos.

Você pode ou não gostar desse estilo de módulo! Mas esta é apenas uma lição sobre como fazer, não sobre o que faz um bom esquema de cores!

## Estilos de Página

Existem várias maneiras de personalizar a aparência geral de uma página. Tudo funciona através do formulário de edição do item nos menus:

- Na aba Detalhes, há uma opção de Estilo de Template, onde você pode selecionar um template específico para usar.
- A aba Layout do Blog possui campos Classe de Artigo Principal e Classe de Artigo nos quais você pode digitar um nome de classe.
- A aba Opções possui o campo Escolher um Layout, no qual você pode escolher entre os layouts disponíveis para todos os itens.
- A aba Tipo de Link tem campos para uma Classe de Link, uma Classe de Ícone de Link e uma Classe de Imagem.
- A aba Exibir Página possui campos para uma Classe de Página.

É sobre o último item dessa lista que este artigo trata. O que acontece quando `make-me-aliceblue` é inserido neste campo? E o seguinte é inserido em user.css:
```css
    .make-me-aliceblue {
      background-color: aliceblue;
    }
```
A classe é adicionada à tag body da página:

![aparência do site da página personalizada com ferramentas de desenvolvedor](../../../en/images/templates/templates-edit-page-class-result.png)

*Traduzido por openai.com*

