<!-- Filename: jdocmanual?manual=user&heading=migration&filename=migration-basics.md / Display title: Noções Básicas de Migração -->

## Terminologia

Os documentos do Joomla! utilizam uma variedade de termos para significar a mudança de uma versão mais antiga para uma versão mais nova:

* **Migração ou mini-migração** é um termo geralmente aplicado a uma mudança de uma versão *Major* mais antiga para uma mais nova, às vezes passando por várias versões *Major* intermediárias.
* **Atualização** é um termo geralmente aplicado a uma mudança de uma versão recente para a próxima versão em uma sequência de versões *Minor*.
* **Atualização** é um termo geralmente usado para o processo de atualização utilizando o componente Atualização do Joomla. É a palavra vista na interface do Administrador no Joomla! 3, 4 e 5. A partir de agora, o termo *Atualização* será usado neste artigo.

Também é importante saber que o Joomla segue o padrão de Versionamento Semântico. Resumidamente, dado um número de versão MAJOR.MINOR.PATCH, como 5.1.0:

* A versão **MAJOR** permite quebras de compatibilidade para trás.
* A versão **MINOR** permite funcionalidades adicionais de forma compatível com versões anteriores dentro da versão Major.
* A versão **PATCH** permite correções de bugs compatíveis com versões anteriores.

Pode haver sufixos adicionais como *alpha*, *beta* ou *rc*, mas não em versões estáveis destinadas a sites de produção.

## Razões para Atualizar

As razões para atualizar são muitas e variadas:

* **Segurança** Embora o Joomla! seja reconhecido como um CMS muito seguro, ocasionalmente
são descobertas vulnerabilidades que são corrigidas em lançamentos Minor ou Patch.
* **Mudanças de hospedagem** O Joomla usa a linguagem de script *PHP* e um servidor de banco de dados
como *MySQL*, *MariaDB* ou *PostGres*. Eles progridem por meio de alterações,
e os serviços de hospedagem precisam se manter atualizados. Então, você pode descobrir que uma versão mais antiga do Joomla não funciona mais ou falha ao trocar o serviço de hospedagem.
* **Mudanças de design** Você pode desejar que seu site pareça melhor, funcione melhor
com dispositivos móveis e tenha uma pontuação mais alta nos motores de busca. Pode ser necessário
atender a requisitos legais de *Acessibilidade*.
* **Funcionalidade** Você pode querer usar uma extensão Joomla que ofereça algum
recurso não fornecido pelas extensões principais do Joomla. As opções podem ser limitadas pela sua
versão Major atual. 

## Backup antes de Atualizar

**Isto é muito importante!** Mesmo que você tenha realizado várias atualizações intermediárias, é possível que algo dê errado durante o processo de atualização. Isso pode deixar seu site quebrado. O conselho padrão oferecido nos Fóruns é voltar ao seu último backup, descobrir por que o backup falhou, corrigir o problema e tentar novamente.

**Akeeba Backup** é uma ferramenta gratuita disponível no Diretório de Extensões do Joomla (JED), ao qual você tem acesso direto através de Sistema / Instalar Extensões / Instalar da Web. Leva apenas um ou dois minutos para baixar e instalar. Ele analisa seu sistema para configurar um perfil usando um Assistente de Configuração. Em seguida, faz um backup que você pode baixar para manter em segurança.

## Autoavaliação

Antes de realizar uma atualização de versão *Major* ou *Minor*, é necessário avaliar o seu sistema e as suas extensões de terceiros existentes para compatibilidade com a versão alvo do Joomla. É uma boa ideia fazer uma lista das extensões de terceiros que você instalou. No Joomla 4 e 5, a lista *Sistema / Extensões / Gerenciar* possui um filtro para selecionar **Extensões não-core**. Isso não está presente no Joomla 3.

Você também pode usar o **Assistente de Postagem no Fórum**. Esta é uma ferramenta destinada a analisar um site e criar um relatório adequado para publicação nos Fóruns Joomla para ajudar os especialistas do Fórum a diagnosticar problemas em seu site. No entanto, possui uma interface de usuário privada que informa tudo sobre o seu site. Suas listas de extensões (Componentes, etc.) indicam quais são de *Terceiros*.

Os problemas que surgem durante as atualizações geralmente estão associados a extensões de terceiros que não são compatíveis em termos de código com a versão alvo do Joomla. Você deve verificar a compatibilidade de cada extensão e **desinstalar** qualquer uma que seja conhecida por ser incompatível. Pode ser possível instalar versões compatíveis posteriormente.

Você deve definir um dos modelos padrão do site como seu **modelo padrão**:

* Os modelos padrão do Joomla! 1.5 são Rhuk_milkyway, JA Purity, Beez.
* Os modelos padrão do Joomla! 2.5 são Atomic, Beez3, e Beez25.
* Os modelos padrão do Joomla! 3 são Protostar e Beez3.
* O modelo padrão do Joomla! 4 é apenas Cassiopeia.

## Testes Locais

Se possível, é melhor configurar um ambiente de teste local no seu laptop ou estação de trabalho doméstica para testar seu procedimento de atualização. Você pode usar o backup do seu site online para preencher seu site de teste. Seu site local deve ser capaz de executar uma cópia do seu site ativo e ter especificações adequadas de PHP e Banco de Dados para executar o site atualizado. Há um artigo separado que descreve como configurar um ambiente de teste em casa.

## Informações Adicionais

Existem vários artigos que descrevem cenários específicos de atualização que não estão incluídos neste manual porque são antigos ou repetitivos.

* https://docs.joomla.org/Why_Migrate
* https://docs.joomla.org/Migration_Step_by_Step_Self_Assessment
* https://docs.joomla.org/J3.x:Updating_Joomla_(Install_Method)
* https://docs.joomla.org/J3.x:Updating_Joomla_(Update_Method)
* https://docs.joomla.org/Planning_Migration_-_Joomla_1.5_to_4
* https://docs.joomla.org/Planning_for_Migration
* https://docs.joomla.org/Pre-Update_Check
* https://docs.joomla.org/Template_Considerations_During_Migration
* https://docs.joomla.org/J3.x:Update_fails_with_an_error_message
* https://docs.joomla.org/Converting_an_existing_website_to_a_Joomla!_website
* https://docs.joomla.org/Potential_backward_compatibility_issues_in_Joomla_4
->
*Traduzido por openai.com*

