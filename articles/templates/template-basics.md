<!-- Filename: J4.x:Template_Basics / Display title: Noções Básicas de Template -->

## Introdução

No Joomla!, um template é uma coleção de arquivos que, juntos, definem a aparência do site. O Joomla 4 fornece dois templates: Atum é o template do Administrador usado para gestão do site; e Cassiopeia é o template do Site usado por visitantes do site. Muitos outros templates de site estão disponíveis de fornecedores independentes, seja gratuitamente ou por uma pequena taxa. De fato, há toda uma indústria baseada na provisão de templates de site especializados.

Um template típico de site contém arquivos PHP para estruturar o conteúdo e arquivos CSS para estilizar o conteúdo. Freqüentemente, há arquivos adicionais, como imagens usadas no layout e arquivos JavaScript usados para interagir com recursos do site, como links e botões. A captura de tela a seguir mostra as pastas e arquivos do template Cassiopeia em uma nova instalação do Joomla 4:

![modelos personalizar página cassiopeia](../../../en/images/templates/templates-customise-cassiopeia.png)

Note que os arquivos PHP estão na pasta /templates do site e os arquivos de mídia estão na pasta /media do site.

## Posições do Modelo

O modelo do site define as posições do conteúdo principal, por exemplo, um artigo individual ou um layout de blog com artigos em destaque, e qualquer módulo a ser exibido acima, abaixo, à esquerda ou à direita do conteúdo principal. A ilustração a seguir mostra as posições disponíveis no Cassiopeia:

![diagrama de posições do modelo](../../../en/images/templates/cassiopeia-template-positions.png)

Além disso, você pode ver as posições do modelo em qualquer modelo, configurando Posicionar Módulos em Previsualização para Habilitado no formulário de Opções do Modelo e depois adicionando ?tp=1 à URL. Se já houver uma string de consulta adicionada à URL, adicione &tp=1 em vez disso.

## Estilo do Usuário

Cassiopeia tem algumas opções que você pode alterar para modificar a aparência do site (há um artigo separado sobre Personalização do Cassiopeia). Isso pode não ser suficiente para seus propósitos. Você pode fazer suas próprias alterações na aparência com uma folha de estilo user.css. Você deve criar isso você mesmo no formulário Templates:Customise. Basta selecionar Novo Arquivo e inserir Nome do Arquivo: user, selecionar Tipo de Arquivo: .css e selecionar css na lista de pastas. Em seguida, selecione o arquivo user.css recém-criado no formulário de Edição e insira alguns estilos, por exemplo, para deixar os cabeçalhos em verde escuro:
```css
    h1, h2, h3, h4, h5, h6 {
      color: darkgreen;
    }
```

## Substituições de Template

Além do layout geral definido pelo template do site, cada componente ou módulo possui um template para definir sua aparência dentro do layout geral. Esses templates estão localizados em uma pasta tmpl dentro do componente ou módulo. Alguns plugins também possuem templates. E há layouts que podem ser chamados de qualquer tipo de extensão.

Às vezes, um desses templates de *extensão* não é exatamente do seu agrado. Nesse caso, você pode criar uma substituição de template. Esta é uma cópia do código usado para gerar o layout da extensão, permitindo que você o altere de acordo com suas próprias necessidades. A captura de tela a seguir mostra o formulário Template: Personalizar Criar Substituições:

![substituições de template](../../../en/images/templates/cassiopeia-customisation-create-overrides.png)

Cassiopeia já tem algumas substituições instaladas. Isso pode parecer um problema. Se você alterar qualquer um dos arquivos padrão do Cassiopeia, suas alterações serão sobrescritas (e, portanto, perdidas) na próxima atualização do Joomla. A solução é templates filhos.

## Layouts Alternativos

Um template, ou uma substituição de template, define a aparência de uma extensão em um arquivo específico, como default.php. Em alguns casos, você pode desejar escolher entre o layout padrão e um layout alternativo. Por exemplo, um menu em uma posição superior geralmente precisa de um layout diferente do mesmo menu em uma posição lateral. Em um módulo de menu, há um parâmetro de Layout na aba Avançado do formulário de edição do módulo que permite selecionar entre layouts alternativos disponíveis. Há um tutorial separado sobre Layouts Alternativos de Template.

## Modelos Filhos

Um modelo filho utiliza os arquivos em seu modelo pai, exceto por quaisquer arquivos que estejam no modelo filho. Por exemplo, você poderia ter diferentes arquivos user.css no pai e no filho, para que diferentes páginas pudessem ter esquemas de cores diferentes. Ou você poderia copiar o arquivo index.php do pai para o filho e alterar o filho para produzir um layout diferente do pai. Há um tutorial separado sobre modelos filhos.

*Traduzido por openai.com*

