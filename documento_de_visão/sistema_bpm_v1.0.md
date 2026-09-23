##  Sistema ARGUS PMBA - Versão 1.0

### Documento de Visão

### **Descrição geral deste documento:**

Este documento descreve o cliente (bem como a problemática a ser automatizada com o sistema), os usuários do sistema, e também fornece uma visão geral do Sistema ARGUS em sua versão 1.0.

### **1.1 Cliente:** 

O 17º Batalhão da Polícia Militar da Bahia (17º BPM), unidade integrante da Polícia Militar da Bahia (PMBA), atua no atendimento e acompanhamento de ocorrências policiais em sua área de responsabilidade. No contexto deste projeto, destaca-se a atuação do setor de planejamento operacional, que utiliza informações referentes às ocorrências para acompanhar os registros e produzir estatísticas que auxiliam nas atividades de planejamento do batalhão.

Atualmente, o registro das ocorrências realizadas durante o serviço policial é efetuado pelos próprios policiais militares por meio do Sistema de Gestão de Segurança Pública (SIGESPOL), uma aplicação online utilizada para o lançamento das ocorrências. Após o registro, as informações ficam disponíveis para os usuários que possuem acesso ao sistema, permitindo que sejam consultadas posteriormente pelo setor de planejamento.

No setor de planejamento, as ocorrências registradas são consultadas periodicamente para o acompanhamento dos eventos ocorridos na área de atuação do batalhão. A partir dessas informações, um policial responsável realiza o levantamento e a organização dos dados para a produção das estatísticas do batalhão, utilizando também planilhas para registrar e consolidar as ocorrências.

As informações utilizadas nesse processo são organizadas de acordo com diferentes categorias de ocorrências e de produtividade policial. Entre os registros considerados estão apreensão de armas brancas, apreensão de armas de fogo, apreensão de drogas, apreensão de menores, autos de resistência lavrados, encaminhamento de pessoas à Delegacia de Polícia, mandados de prisão cumpridos, pessoas presas em flagrante, termos circunstanciados lavrados, veículos notificados, apreendidos ou recuperados, além de ocorrências relacionadas a crimes contra instituições financeiras e outros tipos de ocorrências, como homicídio, tentativa de homicídio, furto, roubo, extorsão e ocorrências envolvendo a Lei Maria da Penha.

Nesse contexto, o ARGUS será proposto como uma ferramenta para apoiar a organização, consulta e visualização dessas informações. O sistema deverá possibilitar a representação das ocorrências associadas às diferentes regiões da área de atuação do batalhão, permitindo consultar os registros por meio de um mapa e visualizar informações estatísticas relacionadas às ocorrências.

Dessa forma, o ARGUS busca contribuir para a centralização e a visualização das informações utilizadas pelo setor de planejamento operacional, facilitando a consulta aos registros e o acompanhamento da distribuição das ocorrências nas diferentes regiões atendidas pelo 17º BPM.


### **1.2 Grupos de usuários do sistema:** 

Para esta primeira versão do sistema, os grupos/perfis de usuários serão:
- Setor de planejamento operacional
- Demais policiais
  
**Observações:**
  
 - Os grupos/perfis de usuários, serão cadastrados no sistema como Colaboradores.

 - As funcionalidades disponíveis para cada grupo/perfil de usuário serão definidas por meio da concessão de permissões, determinando se o usuário poderá adicionar, editar, excluir, visualizar ou detalhar informações.

 - O Setor de Planejamento será responsável pelo lançamento e edição das informações das ocorrências, enquanto os demais policiais terão acesso apenas à visualização dos dados.
  
### **1.3 Visão geral do Sistema ARGUS - versão 1.0:**

A versão 1.0 do Sistema ARGUS PMBA tem como principal objetivo apoiar a organização, consolidação e visualização geográfica das estatísticas de ocorrências atendidas pelo 17º Batalhão, atualmente produzidas pelo Setor de Planejamento Operacional.
 
 #### Fluxo do Sistema ARGUS em sua primeira versão: 

O TARM, o Médico Regulador, o Rádio Operador e a Equipe Assistencial, realizam login no sistema, acessando seus respectivos perfis.

Ao receber um chamado pelo 192, o TARM atende a ligação e preenche, via sistema, as informações da ocorrência, como a hora do chamado, o nome do solicitante, o local da ocorrência, a quantidade de vítimas, a queixa principal, entre outras informações relevantes. Ao finalizar o preenchimento das informações sob sua responsabilidade, o TARM encaminha a ligação para o Médico Regulador e, via sistema, ele também encaminha o fluxo para a etapa de Regulação. 

O Médico Regulador pode então conferir as informações de todos os chamados em sua tela, podendo escolher o chamado que preferir para dar andamento. O Médico Regulador consegue observar as informações já preenchidas pelo TARM e realizar as atualizações necessárias com base nas informações passadas a ele via telefone. O Médico Regulador realiza a avaliação da gravidade do caso e, com base nessa análise, determina o recurso mais apropriado selecionando, via sistema, a quantidade e tipo de unidade móvel que deseja liberar para o atendimento. O Médico Regulador encaminha a ligação para o Rádio Operador e via sistema ele também encaminha o fluxo para a etapa de Rádio. 

O Rádio Operador observa a solicitação designada pelo Médico Regulador podendo gerar a Ficha Individual de Regulação Médica, que apresentará um preenchimento automático de todas as informações descritas pelo TARM e pelo Médico Regulador. O sistema também permite gerar a Ficha de Atendimento Pré-hospitalar. O Rádio Operador poderá então liberar a saída da unidade móvel designada para a ocorrência.

A equipe assistencial recebe o chamado, podendo observar algumas informações no próprio sistema e também gerar o arquivo pdf da Ficha de Atendimento Pré-hospitalar. 

 #### **Observações:**
 > [!IMPORTANT]
>  **Observação 1:** Para que todo o fluxo de Receber Chamado e Realizar Regulação, descrito acima, ocorra, faz-se necessário o prévio cadastro das Bases de atendimento, dos Setores, dos Colaboradores, das Unidades (ou seja, da frota de ambulâncias e demais veículos), e por fim, das configurações de permissões para cada Colaborador em seus respectivos Setores.

> [!NOTE]
>  **Observação 2:** Nesta primeira versão, grande parte dos procedimentos são realizados pelo sistema, porém, ainda será necessária a impressão dos formulários para preenchimento manual complementar. A vantagem operacional do uso desta primeira versão é que boa parte dos dados serão preenchidos pelo TARM e pelo Médico Regulador por meio do sistema, sendo possível gerar os formulários parcialmente preenchidos. O preenchimento do formulário via sistema possibilita também a correção de erros de digitação de maneira mais prática, se comparado à versão impressa do formulário, evitando rasuras ou até mesmo a elaboração de uma nova ficha manualmente.
