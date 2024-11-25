<!-- Filename: Article_Images_and_Links / Display title: Artigo: Editar - Imagens e Links -->

## Introdução

Outros artigos descreveram como incorporar imagens e links no conteúdo de um artigo. Este artigo descreve o uso da aba *Imagens e Links* para adicionar dois tipos de imagens e até três links a serem usados em layouts padronizados. Em resumo:

- A *Imagem de Introdução* é usada em layouts de Blog de Categoria ou Lista como uma amostra visual adicional do tipo de conteúdo que pode ser esperado.
- A *Imagem do Artigo Completo* é colocada no topo do artigo completo como uma introdução visual ao conteúdo.
- Os links: Link A, Link B e Link C são colocados acima do texto do artigo.

## Captura de Tela

Para este artigo, começando com uma imagem de uma perereca verde com 1024 pixels de largura, foram feitas duas imagens menores com 128 e 256 pixels de largura. Nota: é melhor preparar imagens na sua ferramenta favorita de edição de imagens, como o *Gimp*. As imagens de tamanho pequeno e médio foram usadas para criar as capturas de tela a seguir.

![Formulário de edição de artigo, aba de imagens e links](../../../en/images/articles/articles-edit-images-and-links-tab.png)

## Campos do Formulário

### Imagem de Introdução

- **Imagem de Introdução** Selecione uma imagem apropriada para usar em layouts de Blog onde normalmente aparecerá acima do título do artigo. Isso é opcional. Se deixado vazio, não haverá Imagem de Introdução no layout do Blog.
- **Descrição da Imagem (Texto Alternativo)** Insira uma descrição de imagem adequada para leitores de tela.
- **Imagem Decorativa** Se não houver *Descrição da Imagem* e este botão não estiver marcado, a página não passará nos testes de acessibilidade. Se este botão estiver marcado, um atributo `alt` vazio será inserido. Isso pode permitir que a página passe nos testes de acessibilidade. Provavelmente é melhor sempre usar uma boa descrição concisa da imagem.
- **Classe da Imagem** A classe padrão é *esquerda*, significando float-esquerda. Mas qualquer outro valor de float aqui não terá efeito, pois não pode ser usado em itens de grid ou flex.
- **Legenda da Imagem** As palavras inseridas aqui aparecerão como uma legenda abaixo da imagem. **Aviso:** Não use as mesmas palavras exatas tanto para o texto alternativo quanto para a legenda. Leitores de tela anunciarão a informação duas vezes.
    - O texto alternativo deve fornecer uma descrição concisa do que está na imagem.
    - A legenda geralmente deve fornecer contexto para relacionar a imagem ao conteúdo ao redor ou chamar a atenção para uma informação particular.

### Imagem do Artigo Completo

Os mesmos campos que para a Imagem de Introdução, mas a imagem é usada em um contexto diferente. Veja as capturas de tela do site abaixo.

### Link A

- **Link A** Cole o URL completo da página de destino. O URL completo deve ser usado mesmo que a página de destino esteja neste site.
- **Texto do Link A** Digite o texto a ser usado para o link de destino.
- **Janela de Destino de URL** Escolha uma das opções de destino:
  - **Usar Global (Abrir na janela pai)**
  - **Abrir na janela pai** Este é o comportamento preferido, pois o botão *Voltar* do navegador pode ser usado para retornar à página anterior.
  - **Abrir em nova janela** Alguns usuários gostam disso, mas confunde usuários móveis, pois não é óbvio que uma nova janela foi invocada e não há botão *Voltar*.
  - **Abrir em popup** Uma pequena janela popup aparece. A janela principal permanece disponível. Cada clique no link abre outra instância da janela popup.
  - **Abrir em modal** Um diálogo modal é aberto no centro da tela, que fica inativo até que a caixa de diálogo seja fechada.

### Links B e C

A entrada de dados é exatamente a mesma do Link A.

## Capturas de Tela do Site

A captura de tela abaixo mostra um layout de blog de categoria com a *Imagem de Introdução*. Poderia ter sido melhor usar uma imagem panorâmica com a mesma altura, mas com largura muito maior para ocupar o espaço branco vago.

![Página de blog da categoria Anfíbios](../../../en/images/articles/articles-site-amphibians-blog.png)

A captura de tela abaixo mostra a página de um único artigo com a *Imagem do Artigo Completo* e o Link A. A imagem foi alinhada à direita e a legenda visível diz algo para adicionar ao que a Descrição diz, de modo que faça sentido para leitores de tela.

![Página de um único artigo sobre Rãs](../../../en/images/articles/articles-site-amphibians-frogs.png)

*Traduzido por openai.com*

