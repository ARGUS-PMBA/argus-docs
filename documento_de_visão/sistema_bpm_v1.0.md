##  Sistema ARGUS PMBA - Versão 1.0

<!-- ARGUS = Análise e Registro Geográfico de Urbanidade e Segurança -->

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

O Setor de Planejamento Operacional realiza login no sistema, acessando seu perfil com permissão de cadastro e edição.

Com base nos boletins de ocorrência já lançados no sistema da PMBA, o Setor de Planejamento cadastra, via sistema, as informações da ocorrência, como o tipo (criminal ou não criminal), o bairro, a data, o horário e a companhia responsável pelo atendimento. Após o cadastro, a ocorrência fica disponível automaticamente para consulta pelos demais usuários do sistema.

Os policiais e demais servidores do batalhão, com perfil de visualização, acessam o sistema e podem consultar o mapa interativo, que exibe os bairros com indicadores visuais (cores e números) proporcionais à quantidade de ocorrências registradas. É possível aplicar filtros por tipo de ocorrência, bairro, horário e período (mensal, semestral ou anual), além de comparar a evolução das ocorrências entre diferentes intervalos de tempo. Ao selecionar um bairro no mapa, o usuário visualiza uma tela detalhada com as informações consolidadas daquela região.

O sistema também identifica automaticamente os bairros com maior aumento no número de ocorrências em um determinado período, auxiliando o Setor de Planejamento na definição de prioridades para o reforço do policiamento. A partir dessas informações, o Setor de Planejamento pode gerar relatórios (em PDF ou planilha) consolidando os dados para uso em reuniões internas, prestação de contas ou divulgação institucional.

Todas as ações de cadastro e edição realizadas no sistema ficam registradas em um log de auditoria, identificando o usuário responsável e o momento da alteração, garantindo a rastreabilidade das informações.

 #### **Observações:**
 > [!IMPORTANT]
>  **Observação 1:** Para que todo o fluxo descrito acima ocorra, faz-se necessário o prévio cadastro dos Bairros, das Companhias, dos Colaboradores (usuários do Setor de Planejamento) e dos Tipos de Ocorrência, bem como as configurações de permissões para cada perfil de usuário do sistema.

> [!NOTE]
>  **Observação 2:** Nesta primeira versão, o sistema não realiza integração automática com o sistema já utilizado pela PMBA, sendo o cadastro das ocorrências realizado manualmente pelo Setor de Planejamento com base nos boletins de ocorrência já lançados naquele sistema. A vantagem operacional do uso desta primeira versão é a centralização e a visualização geográfica dos dados, que hoje são apurados manualmente sem apoio de uma ferramenta visual, possibilitando também maior agilidade na geração de relatórios e na identificação de bairros com maior aumento de ocorrências, se comparado ao processo atual.