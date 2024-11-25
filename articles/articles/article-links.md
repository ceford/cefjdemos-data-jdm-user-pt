<!-- Filename: J4.x:Article_Links / Display title: Artigo: Editar - Links   -->

## Links Acessíveis

Selecione um link em um documento e seu navegador abrirá o documento vinculado, seja na mesma janela, em uma nova janela ou em uma nova aba. Uma pessoa que usa um leitor de tela pode estar navegando apenas por links, por isso o texto do link precisa ser significativo.

O seguinte é um exemplo de **boa prática** porque indica para onde o link levará:

- Para saber mais, leia nosso [Manifesto](#)

O seguinte é um exemplo de **má prática** porque não fornece nenhuma pista sobre a natureza do destino e pode ser um de vários links semelhantes na mesma página:

- Para saber mais, clique [aqui](#)

Para saber mais sobre links acessíveis, veja este artigo sobre [Criando links válidos e acessíveis](https://www.a11yproject.com/posts/creating-valid-and-accessible-links/).

## Links Incorporados

Este artigo é sobre links incorporados no conteúdo de um artigo. Há um artigo
separado sobre como usar a aba [Imagens e Links](jdocmanual?article=user/articles/article-images-and-links)
para incluir links associados a um artigo.

Links incorporados em um artigo podem ser para outras páginas dentro do site (links internos) ou para outros sites (links externos). O procedimento para inserir os dois tipos é diferente. Cada um é descrito abaixo.

## Inserir um Link Interno

O processo para inserir um link para um artigo no mesmo site é simples:
- Digite a frase contendo o texto do link. Por exemplo:
  
  *Para mais informações, por favor veja a página sobre Sapos.*
- Selecione o texto do link: *Sapos*

O link pode ser para um único artigo ou para um item de menu de um blog de categoria,
lista de categorias ou artigos em destaque.

### Um Link de Artigo Único

- Selecione *Artigo* na lista suspensa de *Conteúdo do CMS*.
- Selecione o título do artigo desejado no diálogo de Artigo.
- Salve o artigo e teste-o usando o botão de Visualização na Barra de Ferramentas.

### Um Link de Item de Menu

- Selecione *Menu* na lista suspensa de *Conteúdo do CMS*.
- Selecione o item de Menu desejado no diálogo de Menu.
- Salve o artigo e teste-o usando o botão de Visualização na Barra de Ferramentas.

## Inserir um Link Externo

Para um link externo, é melhor copiar o link da barra de URL do navegador. Para esse propósito, é útil ter janelas ou abas separadas abertas para o formulário de *Artigos: Editar* do seu site e o site remoto para o qual você está criando o link. Procedimento:

- Encontre ou crie uma frase que contenha o texto a ser usado como texto do link. Por exemplo:

  *Para mais informações, veja o artigo da Wikipedia sobre Green Tree Frogs.*
  
- Selecione a palavra ou palavras a serem vinculadas, neste caso *Green Tree Frogs*.
- Em seguida, use um dos seguintes métodos:
  - Selecione **Inserir → Link** no menu Texto do Artigo (a primeira barra de ferramentas no topo da aba Conteúdo).
  - Clique duas vezes no texto selecionado para abrir um pequeno menu popup que contém um ícone de link para selecionar.

Qualquer método abrirá uma caixa de diálogo Inserir/Editar Link para ser preenchida da seguinte forma:

- No campo *URL*, cole o link copiado da barra de URL da janela de destino.
- O campo *Texto a exibir* deve conter o texto que você selecionou antes de abrir o diálogo. Se não, qualquer texto que você digitar aqui será inserido no artigo e precisa ser algo que faça sentido no contexto. Lembrete: evite *Clique aqui* ou *Leia mais*.
- O campo *Título* cria um atributo de título do link, mas seu uso por navegadores é inconsistente e controverso para fins de acessibilidade. Em caso de dúvida, deixe em branco.
- O campo *Rel* possui várias opções. Em caso de dúvida, deixe definido como *Nenhum*. Há uma lista de opções disponíveis no artigo *mdn web docs* sobre [Atributo HTML: rel](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/rel).
- O campo *Abrir link em...* é uma escolha simples entre *Janela Atual* e *Nova Janela*. As configurações do navegador controlam se isso resulta em uma nova janela separada ou uma nova aba.
- Salve o artigo e teste usando o botão de Pré-visualização na Barra de Ferramentas.

## Verificação de Links

Na visualização do site da página, verifique se o link está bom e funciona corretamente.  
Além disso, teste-o com um leitor de tela!  

## Remover um Link

Existem várias maneiras de remover um link. Método 1:
- Clique no link.
- Selecione o ícone de reticências (...) para abrir o menu expandido do editor.
- Selecione o ícone *Remover Link*.
- Salve. O texto permanece, mas o link desaparece.

Método 2:
- Dê um clique duplo no link.
- Selecione o ícone de Link no pequeno popup.
- No diálogo Inserir/Editar Link, delete o conteúdo do campo URL.
- Salve. O texto permanece, mas o link desaparece.

Método 3:
- Delete o texto que contém o link. O link e o texto desaparecem.

Método 4:
- Selecione o link.
- Selecione o botão Editar / Link do TinyMCE.
- No diálogo Inserir/Editar Link, delete o conteúdo do campo URL.
- Salve. O texto permanece, mas o link desaparece.

## Alterar um Link

Usando qualquer um dos métodos descritos acima para abrir o diálogo Inserir/Editar Link, cole um novo URL de link. Lembre-se: é sempre melhor copiar o URL da barra de URL de uma janela ou aba do navegador que exibe a página de destino e colá-lo no campo URL do formulário Inserir/Editar Link.

*Traduzido por openai.com*

