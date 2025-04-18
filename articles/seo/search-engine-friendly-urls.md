<!-- Filename: Search_Engine_Friendly_URLs / Display title: URLs Amigáveis para Motores de Busca   -->

## Caminhos e Rotas

URLs SEF fazem sentido tanto para humanos quanto para mecanismos de busca porque explicam o caminho para a página específica a que se referem. Um **caminho** é a localização de um arquivo em uma árvore de diretórios ou sua simulação em código. Internamente, a parte local de uma URL SEF (a parte após o nome do domínio) é chamada de **rota**. Criar e processar URLs SEF é, portanto, chamado de **roteamento**, e o código relevante é chamado de **roteador**.

URLs amigáveis para mecanismos de busca podem ser ativadas com os seguintes passos:
* Na **Configuração Global**
    - Defina a opção **URLs Amigáveis para Mecanismos de Busca** como **Sim**.
    - Defina a opção **Usar Reescrita de URL** como **Sim**.
    - Opcional: Defina a opção **Adicionar Sufixo à URL** como **Sim**.
* Na raiz do site, renomeie htaccess.txt para .htaccess se estiver usando um servidor Apache, ou consulte a documentação externa para NginX ou outros servidores.

Um exemplo de roteamento pode ser visto no efeito incremental que essas mudanças têm na URL da página Blog da Categoria **Artigos** nos dados de exemplo.

- Com as URLs SEF desativadas na Configuração Global e o .htaccess desativado, a URL é algo como `https://www.exemplo.com/index.php?option=com_content&view=category&layout=blog&id=16&Itemid=125` e o caminho de navegação mostra:<br>
 *Você está aqui: Início / Layouts de Exemplo / Artigos*
- Com as URLs SEF ativadas, mas sem reescrita de URL, ela se torna:
  `https://www.exemplo.com/index.php/layouts-exemplo/artigos`
- Com as URLs SEF ativadas, reescrita de URL ativada e .htaccess habilitado, ela se torna
  `https://www.exemplo.com/layouts-exemplo/artigos.html` (Adicionar Sufixo à URL
  definido como Sim).

## Números em URLs não-SEF

Na parte da URL que diz `id=16&Itemid=125`, os números são os parâmetros necessários para localizar a URL interna e mostrar a página requerida. Neste caso, o primeiro numeral é o ID de uma Categoria e o segundo numeral é o ID do item de menu Blog de Categoria para essa Categoria.

*Traduzido por openai.com*

