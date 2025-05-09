<!-- Filename: J5.x:Improving_SEO_with_Strict_Routing_and_SEF_URLs / Display title: SEO Roteamento Estrito -->

## Introdução

A opção de Roteamento Estrito, introduzida no Joomla 5.2, aprimora o desempenho de SEO da plataforma permitindo regras de roteamento mais rígidas através de um interruptor no plugin *System - SEF*. Ela ajuda a eliminar conteúdo duplicado aplicando URLs mais consistentes e redirecionando duplicatas para o URL correto com um redirecionamento 301.

![system sef plugin settings](../../../en/images/seo/seo-system-sef-plugin.png)

### Impor Sufixos

Atualmente, o Joomla permite o acesso a URLs com ou sem um sufixo quando esta opção está ativada nas opções de *Configuração Global*.

A opção **Impor um sufixo por redirecionamento** no plugin *System - SEF* aplica um comportamento consistente de sufixo. Quando ativada, ela redireciona requisições GET para uma URL com um sufixo se ele estiver ausente. Também redirecionará URLs com um parâmetro de formato de consulta para a URL mais limpa, substituindo o sufixo pelo parâmetro de formato onde necessário.

Esta funcionalidade deverá se tornar o comportamento padrão no Joomla 6.0, onde a opção de ativá-la ou desativá-la será removida, e essa funcionalidade será integrada ao sistema de roteamento principal. Por enquanto, essa opção permite que os usuários testem o comportamento em sistemas ao vivo e a desativem caso surjam problemas imprevistos durante o período de transição do Joomla 5.1 para o 6.0.

## Como Acessar

Para ativar o roteamento estrito para SEO:

1. Selecione o item **Plugins** no *Painel Principal*.
1. Encontre e abra o plugin **System - SEF**.
2. Defina **Roteamento Estrito** para *Sim* para ativar um tratamento de URL mais rigoroso.
3. Defina **Aplicar um Sufixo por Redirecionamento** para Sim ou Não, dependendo da sua preferência por aplicar sufixos de URL.

Uma vez ativado, o Joomla irá redirecionar automaticamente os URLs duplicados para o correto com um redirecionamento 301, melhorando o SEO ao consolidar o conteúdo sob um único URL autoritativo.

## Notas Adicionais

Este recurso foi projetado para funcionar como uma etapa preparatória para futuras melhorias de SEO e é habilitado automaticamente para novas instalações do Joomla 5.2. Ele estabelece as bases para futuros aprimoramentos no sistema de roteamento do Joomla.  
*Traduzido por openai.com*

