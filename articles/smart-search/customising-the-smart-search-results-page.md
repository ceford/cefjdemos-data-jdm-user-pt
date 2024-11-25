<!-- Filename: Customising_the_Smart_Search_results_page / Display title: Substituições de Layout da Pesquisa Inteligente   -->

## Páginas de Resultados

O componente de Busca Inteligente possui cinco arquivos de layout que você pode substituir para criar um layout de acordo com seu gosto. Para iniciar o processo a partir do menu do Administrador:

* Selecione **Sistema / Modelos de Sites / Detalhes e Arquivos Cassiopeia**.
* Selecione a aba **Criar Substituições**.
* No painel Componentes, selecione **com_finder**.
* Selecione o item **Pesquisa**
* No painel do Editor, selecione **html / com_finder / search** para ver a lista de arquivos de substituição criados.

Esses arquivos não serão afetados por atualizações do Joomla, mas você pode ser lembrado de verificá-los se as fontes originais forem atualizadas.

## A Visualização de Pesquisa (Layout Padrão)

A visualização de pesquisa no layout padrão é dividida em várias partes: o layout padrão, o layout do formulário, o layout dos resultados e o layout de ordenação.

### O layout padrão (default.php)

Este layout é muito simples. Ele apenas define a estrutura na qual o formulário de pesquisa e os resultados da pesquisa são exibidos. Este layout também é responsável por carregar a folha de estilo CSS padrão para a Pesquisa Inteligente, localizada em `media/com_finder/css/finder.css`, então talvez você queira alterá-la para carregar suas próprias regras de CSS para a Pesquisa Inteligente.

### O layout do formulário (default_form.php)

Este layout define o código necessário para o formulário de pesquisa operar corretamente. O layout utiliza código JavaScript, por isso é preciso tomar cuidado para preservar os seletores que não devem ser alterados, a menos que você saiba o que está fazendo.

O método de visualização `getFields` inclui uma série de campos ocultos que são necessários para uma busca confiável. O termo de pesquisa é definido pelo campo de entrada com o nome "q".

### O layout dos resultados (default_results.php)

Este layout produz a lista de resultados correspondentes para o termo de pesquisa. Ele também lida com a paginação e carrega layouts para cada resultado individual de pesquisa.

### O layout do resultado (default_result.php)

Este é o layout carregado para exibir um único resultado.

### O layout de ordenação (default_sorting.php)

Este item está presente apenas se a opção Mostrar Campos de Ordenação estiver configurada como Sim e um ou mais Campos de Ordenação Adicionais forem selecionados na guia Avançado do Item de Menu.

*Traduzido por openai.com*

