# Documento de Requisitos — ARGUS PMBA

Documento consolidado com os requisitos organizados por módulo.

## Sumário

- [Módulo de Pessoas](#modulo-de-pessoas)
- [Módulo de Ocorrências](#modulo-de-ocorrências)
- [Módulo de Mapa](#modulo-de-mapa)
- [Módulo de Relatórios](#modulo-de-relatorios)
- [Módulo de Auditoria](#modulo-de-auditoria)
- [Requisitos Não Funcionais](#requisitos-nao-funcionais)

---

## Módulo de Pessoas

### Organização do módulo


Esta pasta contém os requisitos funcionais do sistema ARGUS para o módulo de pessoa.

| Código      | Requisito | Descrição |
|-------------|-----------|-----------|
| [RF_001](./RF_001.md) | Login por matrícula | O sistema deve permitir login utilizando matrícula e senha. |
| [RF_002](./RF_002.md) | Perfis de acesso | O sistema deve permitir dois perfis de acesso: Setor de Planejamento (cadastra/edita/exclui) e Visualizador (apenas consulta). |

## RF_001: O sistema deve permitir o login por matrícula
**Descrição do requisito:** O sistema deve permitir login utilizando matrícula e senha.

**Prioridade:** [x] Essencial  [ ] Importante  [ ] Desejável

**Entradas e pré-condições:**
- O usuário deve estar previamente cadastrado no sistema.
- O usuário deve informar matrícula e senha válidas.

**Saídas e pós-condição:**
- O usuário é autenticado e direcionado à tela inicial de acordo com seu perfil de acesso.

**Fluxo de eventos principal:**
- O usuário acessa a tela de login.
- O usuário informa matrícula e senha.
- O sistema valida as credenciais.
- O sistema redireciona o usuário para a tela principal.

**Fluxos secundários:**
- Caso a matrícula ou senha estejam incorretas, o sistema deve exibir mensagem de erro e não permitir o acesso.

**RNFs vinculados:** RNF_001, RNF_002

## RF_002: O sistema deve permitir perfis de acesso distintos
**Descrição do requisito:** O sistema deve permitir dois perfis de acesso: Setor de Planejamento (cadastra/edita/exclui) e Visualizador (apenas consulta).

**Prioridade:** [x] Essencial  [ ] Importante  [ ] Desejável

**Entradas e pré-condições:**
- O usuário deve estar autenticado no sistema.
- O perfil do usuário deve estar previamente definido no cadastro.

**Saídas e pós-condição:**
- As funcionalidades disponíveis na interface são restritas conforme o perfil do usuário autenticado.

**Fluxo de eventos principal:**
- O usuário realiza login no sistema.
- O sistema identifica o perfil associado à matrícula.
- O sistema libera apenas as ações permitidas para aquele perfil.

**Fluxos secundários:**
- Caso o usuário do perfil Visualizador tente acessar uma funcionalidade de cadastro/edição/exclusão, o sistema deve bloquear a ação e exibir mensagem informativa.

**RFs vinculados:** RF_003, RF_005, RF_006

## Módulo de Ocorrências

### Organização do módulo


Esta pasta contém os requisitos funcionais do sistema ARGUS para o módulo de ocorrência.

| Código      | Requisito | Descrição |
|-------------|-----------|-----------|
| [RF_003](./RF_003.md) | Cadastro de ocorrência | O sistema deve permitir que o Setor de Planejamento cadastre uma ocorrência, informando tipo, bairro, data, horário e companhia responsável. |
| [RF_004](./RF_004.md) | Dados estatísticos opcionais | O sistema deve permitir o cadastro opcional de sexo e idade na ocorrência, para fins estatísticos. |
| [RF_005](./RF_005.md) | Edição de ocorrência | O sistema deve permitir que o Setor de Planejamento edite uma ocorrência já cadastrada, sem exigência de justificativa. |
| [RF_006](./RF_006.md) | Exclusão de ocorrência | O sistema deve permitir que o Setor de Planejamento exclua uma ocorrência cadastrada incorretamente. |
| [RF_007](./RF_007.md) | Restrição de dados sensíveis | O sistema não deve permitir o cadastro ou exibição de dados pessoais sensíveis (nomes de vítimas ou autores, endereços exatos). |

## RF_003: O sistema deve permitir o cadastro de ocorrência
**Descrição do requisito:** O sistema deve permitir que o Setor de Planejamento cadastre uma ocorrência, informando tipo, bairro, data, horário e companhia responsável.

**Prioridade:** [x] Essencial  [ ] Importante  [ ] Desejável

**Entradas e pré-condições:**
- O usuário deve estar autenticado com perfil Setor de Planejamento.
- Os bairros, tipos de ocorrência e companhias devem estar previamente cadastrados no sistema.

**Saídas e pós-condição:**
- A ocorrência é registrada e passa a ser exibida no mapa e nos filtros de consulta.

**Fluxo de eventos principal:**
- O usuário acessa a opção de cadastrar ocorrência.
- O usuário informa tipo, bairro, data, horário e companhia responsável.
- O sistema valida os dados e salva a ocorrência.

**Fluxos secundários:**
- Caso algum campo obrigatório não seja preenchido, o sistema deve impedir o salvamento e indicar o campo pendente.

**RNFs vinculados:** RNF_001, RNF_002

## RF_004: O sistema deve permitir dados estatísticos opcionais na ocorrência
**Descrição do requisito:** O sistema deve permitir o cadastro opcional de sexo e idade na ocorrência, para fins estatísticos.

**Prioridade:** [ ] Essencial  [x] Importante  [ ] Desejável

**Entradas e pré-condições:**
- O usuário deve estar cadastrando ou editando uma ocorrência.

**Saídas e pós-condição:**
- Os campos de sexo e idade, quando preenchidos, ficam associados à ocorrência e disponíveis para consolidação estatística.

**Fluxo de eventos principal:**
- O usuário preenche os dados obrigatórios da ocorrência.
- O usuário, opcionalmente, informa sexo e idade.
- O sistema salva a ocorrência com os dados informados.

**Fluxos secundários:**
- Caso os campos não sejam preenchidos, a ocorrência é salva normalmente, sem essas informações.

**RFs vinculados:** RF_003

## RF_005: O sistema deve permitir a edição de ocorrência
**Descrição do requisito:** O sistema deve permitir que o Setor de Planejamento edite uma ocorrência já cadastrada, sem exigência de justificativa.

**Prioridade:** [ ] Essencial  [x] Importante  [ ] Desejável

**Entradas e pré-condições:**
- O usuário deve estar autenticado com perfil Setor de Planejamento.
- A ocorrência a ser editada deve existir previamente no sistema.

**Saídas e pós-condição:**
- Os dados da ocorrência são atualizados e refletidos no mapa e nos relatórios.

**Fluxo de eventos principal:**
- O usuário seleciona uma ocorrência existente.
- O usuário altera os campos desejados.
- O sistema salva as alterações.

**Fluxos secundários:**
- Nenhum fluxo de justificativa é exigido, conforme definido com o cliente.

**RNFs vinculados:** RNF_001, RNF_002

## RF_006: O sistema deve permitir a exclusão de ocorrência
**Descrição do requisito:** O sistema deve permitir que o Setor de Planejamento exclua uma ocorrência cadastrada incorretamente.

**Prioridade:** [x] Essencial  [ ] Importante  [ ] Desejável

**Entradas e pré-condições:**
- O usuário deve estar autenticado com perfil Setor de Planejamento.
- A ocorrência a ser excluída deve existir previamente no sistema.

**Saídas e pós-condição:**
- A ocorrência deixa de ser exibida no mapa, nos filtros e nos relatórios.

**Fluxo de eventos principal:**
- O usuário seleciona uma ocorrência existente.
- O usuário confirma a exclusão.
- O sistema remove a ocorrência.

**Fluxos secundários:**
- O sistema pode solicitar uma confirmação adicional antes de excluir, para evitar exclusões acidentais.

**RFs vinculados:** RF_014
**RNFs vinculados:** RNF_001

## RF_007: O sistema não deve permitir o cadastro de dados sensíveis
**Descrição do requisito:** O sistema não deve permitir o cadastro ou exibição de dados pessoais sensíveis (nomes de vítimas ou autores, endereços exatos).

**Prioridade:** [x] Essencial  [ ] Importante  [ ] Desejável

**Entradas e pré-condições:**
- O formulário de cadastro/edição de ocorrência deve estar acessível ao usuário.

**Saídas e pós-condição:**
- Nenhum campo do sistema permite o registro de nomes ou endereços exatos vinculados a pessoas envolvidas.

**Fluxo de eventos principal:**
- O usuário preenche o formulário de ocorrência.
- O sistema disponibiliza apenas os campos permitidos (tipo, bairro, data, horário, companhia, sexo, idade).

**Fluxos secundários:**
- Não se aplica, pois os campos restritos não existem na interface do sistema.

**RFs vinculados:** (sem vinculação)

## Módulo de Mapa

### Organização do módulo


Esta pasta contém os requisitos funcionais do sistema ARGUS para o módulo de Mapa.

| Código      | Requisito | Descrição |
|-------------|-----------|-----------|
| [RF_008](./RF_008.md) | Visualização por bairro | O sistema deve exibir um mapa dos bairros de Guanambi, destacando visualmente (cores e/ou números) a quantidade de ocorrências registradas. |
| [RF_009](./RF_009.md) | Filtros do mapa | O sistema deve permitir a filtragem das ocorrências por tipo, bairro, horário e período (mensal, semestral, anual). |
| [RF_010](./RF_010.md) | Detalhamento por bairro | O sistema deve exibir uma tela detalhada com as informações consolidadas ao selecionar um bairro no mapa. |
| [RF_011](./RF_011.md) | Destaque de bairros críticos | O sistema deve identificar automaticamente os bairros com maior aumento no número de ocorrências em um período selecionado. |

## RF_008: O sistema deve exibir mapa por bairro
**Descrição do requisito:** O sistema deve exibir um mapa dos bairros de Guanambi, destacando visualmente (cores e/ou números) a quantidade de ocorrências registradas.

**Prioridade:** [x] Essencial  [ ] Importante  [ ] Desejável

**Entradas e pré-condições:**
- Deve existir ao menos uma ocorrência cadastrada para exibição no mapa.
- Os bairros devem estar previamente cadastrados com seus limites geográficos.

**Saídas e pós-condição:**
- O usuário visualiza o mapa com os bairros destacados proporcionalmente à quantidade de ocorrências.

**Fluxo de eventos principal:**
- O usuário acessa a tela inicial do sistema.
- O sistema carrega o mapa e os dados consolidados por bairro.
- O sistema exibe as cores/números correspondentes.

**Fluxos secundários:**
- Caso não haja ocorrências registradas em um bairro, ele deve ser exibido sem destaque (neutro).

**RNFs vinculados:** RNF_001

## RF_009: O sistema deve permitir filtros no mapa
**Descrição do requisito:** O sistema deve permitir a filtragem das ocorrências por tipo, bairro, horário e período (mensal, semestral, anual).

**Prioridade:** [x] Essencial  [ ] Importante  [ ] Desejável

**Entradas e pré-condições:**
- O mapa deve estar carregado com dados de ocorrências.

**Saídas e pós-condição:**
- O mapa é atualizado exibindo apenas as ocorrências que atendem aos critérios selecionados.

**Fluxo de eventos principal:**
- O usuário abre o menu/botão de filtros.
- O usuário seleciona os critérios desejados (tipo, bairro, horário, período).
- O sistema atualiza a visualização do mapa conforme os filtros aplicados.

**Fluxos secundários:**
- Caso nenhum resultado seja encontrado para os filtros aplicados, o sistema deve informar ao usuário.

**RNFs vinculados:** RNF_001

## RF_010: O sistema deve detalhar informações do bairro
**Descrição do requisito:** O sistema deve exibir uma tela detalhada com as informações consolidadas ao selecionar um bairro no mapa.

**Prioridade:** [x] Essencial  [ ] Importante  [ ] Desejável

**Entradas e pré-condições:**
- O usuário deve estar visualizando o mapa com ao menos um bairro contendo dados.

**Saídas e pós-condição:**
- O usuário visualiza uma tela com os dados detalhados das ocorrências do bairro selecionado.

**Fluxo de eventos principal:**
- O usuário clica em um bairro no mapa.
- O sistema exibe a tela detalhada com os dados consolidados daquele bairro.

**Fluxos secundários:**
- Caso o bairro não possua ocorrências registradas, a tela detalhada deve informar a ausência de dados.


**RFs vinculados:** RF_008, RF_009
**RNFs vinculados:** RNF_001

## RF_011: O sistema deve destacar bairros críticos automaticamente
**Descrição do requisito:** O sistema deve identificar automaticamente os bairros com maior aumento no número de ocorrências em um período selecionado.

**Prioridade:** [ ] Essencial  [x] Importante  [ ] Desejável

**Entradas e pré-condições:**
- Devem existir dados de ao menos dois períodos distintos para comparação.

**Saídas e pós-condição:**
- O sistema exibe destaque visual indicando os bairros com maior variação de aumento.

**Fluxo de eventos principal:**
- O usuário seleciona um período de análise.
- O sistema compara automaticamente com o período anterior.
- O sistema destaca no mapa os bairros com maior aumento.

**Fluxos secundários:**
- Caso não haja dados suficientes para comparação, o sistema não realiza o destaque.


**RFs vinculados:** RF_008, RF_013
**RNFs vinculados:** RNF_001

## Módulo de Relatórios

### Organização do módulo


Esta pasta contém os requisitos funcionais do sistema ARGUS para o módulo de relatórios.

| Código      | Requisito | Descrição |
|-------------|-----------|-----------|
| [RF_012](./RF_012.md) | Geração de relatório | O sistema deve permitir a geração de relatórios em PDF e/ou planilha, com os dados consolidados por período. |
| [RF_013](./RF_013.md) | Comparativo entre períodos | O sistema deve permitir, mediante solicitação, a geração de relatório comparativo entre o período atual e o anterior. |

## RF_012: O sistema deve permitir geração de relatórios
**Descrição do requisito:** O sistema deve permitir a geração de relatórios em PDF e/ou planilha, com os dados consolidados por período (semanal, mensal, anual).

**Prioridade:** [x] Essencial  [ ] Importante  [ ] Desejável

**Entradas e pré-condições:**
- Devem existir ocorrências cadastradas no período selecionado pelo usuário.

**Saídas e pós-condição:**
- O sistema gera um arquivo (PDF ou planilha) contendo os dados consolidados do período.

**Fluxo de eventos principal:**
- O usuário seleciona o período desejado.
- O usuário escolhe o formato de exportação (PDF ou planilha).
- O sistema gera e disponibiliza o arquivo para download.

**Fluxos secundários:**
- Caso não existam dados no período selecionado, o sistema deve informar ao usuário antes de gerar o arquivo.


**RNFs vinculados:** RNF_001

## RF_013: O sistema deve permitir relatório comparativo entre períodos
**Descrição do requisito:** O sistema deve permitir, mediante solicitação, a geração de relatório comparativo entre o período atual e o anterior.

**Prioridade:** [ ] Essencial  [x] Importante  [ ] Desejável

**Entradas e pré-condições:**
- Devem existir dados cadastrados tanto no período atual quanto no período anterior.

**Saídas e pós-condição:**
- O sistema gera um relatório apresentando a variação entre os dois períodos.

**Fluxo de eventos principal:**
- O usuário solicita explicitamente o relatório comparativo.
- O usuário seleciona os dois períodos a serem comparados.
- O sistema gera o relatório com a variação percentual/numérica entre eles.

**Fluxos secundários:**
- Caso um dos períodos não possua dados suficientes, o sistema deve informar a limitação antes de gerar o relatório.


**RFs vinculados:** RF_012
**RNFs vinculados:** RNF_001

## Módulo de Auditoria

### Organização do módulo


Esta pasta contém os requisitos funcionais do sistema ARGUS para o módulo de auditoria.

| Código      | Requisito | Descrição |
|-------------|-----------|-----------|
| [RF_014](./RF_014.md) | Registro de responsável | O sistema deve registrar em log de auditoria o usuário responsável por cada ação de cadastro, edição ou exclusão.

## RF_014: O sistema deve registrar responsável por ação
**Descrição do requisito:** O sistema deve registrar em log de auditoria o usuário responsável por cada ação de cadastro, edição ou exclusão.

**Prioridade:** [x] Essencial  [ ] Importante  [ ] Desejável

**Entradas e pré-condições:**
- O usuário deve estar autenticado no sistema.

**Saídas e pós-condição:**
- Toda ação de cadastro, edição ou exclusão fica associada ao usuário que a executou.

**Fluxo de eventos principal:**
- O usuário realiza uma ação de cadastro, edição ou exclusão.
- O sistema registra automaticamente a matrícula do usuário responsável.

**Fluxos secundários:**
- Não se aplica, pois o registro é automático e obrigatório em toda ação.


**RFs vinculados:** RF_003, RF_005, RF_006

## Requisitos Não Funcionais

### Organização do módulo


Esta pasta contém os requisitos não-funcionais gerais do sistema ARGUS, que impactam todas as funcionalidades.

| Código      | Requisito | Descrição |
|-------------|-----------|-----------|
| [RNF_001](./RNF_001.md) | Respostas rápidas | O sistema deve retornar o resultado das operações em até 10 segundos sob condições normais de uso. |
| [RNF_002](./RNF_002.md) | Identificação de campos obrigatórios | Todos os campos obrigatórios dos formulários do sistema devem ser identificados com um asterisco (*) imediatamente após o seu label. |

## RNF_001: O sistema deve apresentar respostas rápidas
**Descrição do requisito:** O sistema deve retornar o resultado das operações em até 10 segundos sob condições normais de uso.

**Prioridade:** [x] Essencial  [ ] Importante  [ ] Desejável

**Entradas e pré-condições:**
- A operação solicitada pelo usuário deve estar dentro do escopo funcional do sistema.
- A infraestrutura de rede deve estar operando normalmente.

**Saídas e pós-condição:**
- O usuário recebe o retorno da operação em até 3 segundos.

**Fluxo de eventos principal:**
- O usuário executa qualquer operação coberta por um RF (ex.: cadastrar, listar, detalhar, editar ou excluir Pessoa).
- O sistema processa a operação e retorna o resultado ao usuário.
- O tempo de resposta medido entre o envio da solicitação e o recebimento da resposta não deve ultrapassar 10 segundos.

**Fluxos secundários:**
- Caso o tempo de resposta ultrapasse 10 segundos, o sistema deve registrar log da operação e notificar o administrador.

**RFs vinculados:**

## RNF_002: Identificação de campos obrigatórios em formulários
**Descrição do requisito:** Todos os campos obrigatórios dos formulários do sistema devem ser identificados com um asterisco (*) imediatamente após o seu label.

**Prioridade:** [ ] Essencial  [x] Importante  [ ] Desejável

**Entradas e pré-condições:**
- O usuário acessa qualquer formulário do sistema.
- O formulário contém campos obrigatórios definidos pelo modelo de dados ou pela regra de negócio.

**Saídas e pós-condição:**
- O usuário visualiza claramente quais campos são obrigatórios.
- O asterisco (*) é exibido após o label de cada campo obrigatório, em conformidade com o padrão definido.

**Fluxo de eventos principal:**
- O usuário acessa um formulário (ex.: cadastro, edição ou exclusão de Pessoa).
- O sistema exibe os labels dos campos.
- Para cada campo obrigatório, o sistema adiciona um asterisco (*) após o label.
- O usuário preenche o formulário ciente de quais campos não podem ser deixados em branco.

**Fluxos secundários:**
- Caso algum campo obrigatório não esteja identificado corretamente com o asterisco, deve-se registrar a não conformidade e incluir a correção no backlog do projeto.
