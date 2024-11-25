<!-- Filename: J6.x:Article_Access_Restriction / Display title: Artigo: Restrição de Acesso  -->

## Introdução

Existem várias razões para restringir o acesso a artigos em um site. Alguns conteúdos podem ser privados para usuários específicos, como membros de um comitê. Ou o site pode conter conteúdo comercial pago. O Joomla oferece um poderoso sistema de Lista de Controle de Acesso (ACL) para restringir o acesso. Ele é descrito em um artigo separado sobre [Controle de Acesso](jdocmanual?article=user/users/access-control) na seção de Usuário deste manual.

Este artigo descreve a implementação da restrição de acesso no formulário *Artigo: Editar*.

## Restrição por Nível de Acesso

O Joomla fornece os Níveis de Acesso vistos na captura de tela a seguir:

![Níveis de acesso do usuário](../../../en/images/articles/article-access-user-groups.png)

Os níveis de acesso aparecem na aba *Conteúdo* do formulário *Artigo: Editar*.

- **Público** Pode ser visualizado por todos - tanto usuários que estão
  logados quanto usuários que não estão logados.
- **Convidado** Este nível de acesso restringe o acesso a usuários que **NÃO**
  estão logados.
- **Registrado** Este nível restringe o acesso a usuários que estão logados.
  Um artigo com *Acesso* definido como *Registrado* exigirá um login no 
  front-end antes que o artigo possa ser visualizado.
- **Especial** Este nível restringe o acesso a usuários que estão logados e
  fazem parte de um grupo de usuários específico diferente de Registrado. Além disso, é
  possível diferenciar o conteúdo que alguns usuários logados podem acessar
  mas outros não. Tipicamente, isso pode ser um site onde são necessárias assinaturas
  para acessar conteúdo adicional.
- **Super Usuários** Definir este nível significa que apenas um Super Usuário pode acessar
  o artigo. Isso pode ser usado para artigos sobre gerenciamento do site.

Note que esta lista é sobre **Visualização** ou ter permissão para visualizar conteúdo.
Você pode criar níveis de acesso adicionais e grupos de usuários para personalizar quem pode
ver o quê.

## Restrição Parcial para Ler Mais

Às vezes, você pode querer restringir o acesso a um artigo, mas permitir acesso irrestrito a uma prévia do artigo. Esta é uma maneira comum de implementar o acesso pago a conteúdo comercial. Procedimento:

- Encontre o artigo a ser parcialmente restrito na lista de *Artigos* e abra-o para edição.
- Insira uma *Quebra de Página* após o primeiro parágrafo. A ferramenta de Quebra de Página está próxima ao final da lista de *Conteúdo do CMS* no formulário de edição do artigo TinyMCE.
- Defina o nível de *Acesso* do artigo como *Registrado*.
- Selecione **Salvar & Fechar** na Barra de Ferramentas.

### Restringindo o acesso a Artigos individualmente

Abra o item de menu *Blog de Categoria* ou *Artigos em Destaque* onde o artigo aparecerá.

- Na aba **Opções**, defina **Links Não Autorizados** como **Sim**. Está no final da lista de Opções.
- Selecione **Salvar & Fechar** na Barra de Ferramentas.

### Restringindo o acesso a Artigos Globalmente

* Defina as Categorias relevantes com nível de visualização *Público*, caso contrário, os itens de menu não estarão visíveis para usuários que não estejam logados.
* Defina os artigos nas Categorias relevantes com nível de visualização Registrado. Isso pode ser feito selecionando os artigos e usando o botão *Batch*.
* Vá para **Conteúdo → Artigos → Opções**
* Defina **Links Não Autorizados** como **Sim** na aba de Artigos. Se definido como Sim, links para conteúdo registrado serão mostrados mesmo que você não esteja logado. Você precisará fazer login para acessar o item completo.

**Nota:** O texto em um Artigo sem uma quebra *Leia Mais* é tratado como todo o texto de Introdução. Se você tiver um Artigo que se destina a ser restrito apenas para usuários Registrados, mas não tiver um Leia Mais, então o artigo inteiro será visível para todos os usuários. Portanto, adicione um Leia Mais ao artigo!

*Traduzido por openai.com*

