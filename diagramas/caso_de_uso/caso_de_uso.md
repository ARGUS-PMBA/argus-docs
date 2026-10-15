# Diagrama de Casos de Uso

## Descrição

Este diagrama representa as interações entre os usuários do sistema ARGUS PMBA e as funcionalidades disponíveis, de acordo com o perfil de acesso de cada ator.

## Atores

- **Setor de Planejamento** — responsável por cadastrar, editar e excluir ocorrências, além de gerar relatórios.
- **Visualizador** — demais policiais e servidores do batalhão, com acesso apenas à consulta do mapa e das estatísticas.

## Diagrama



## Casos de uso

| Caso de uso | Ator | Descrição | RF relacionado |
|---|---|---|---|
| Realizar login | Setor de Planejamento, Visualizador | Autenticação no sistema por matrícula e senha | RF_001 |
| Cadastrar ocorrência | Setor de Planejamento | Registro de uma nova ocorrência no sistema | RF_003, RF_004 |
| Editar ocorrência | Setor de Planejamento | Alteração de uma ocorrência já cadastrada | RF_005 |
| Excluir ocorrência | Setor de Planejamento | Remoção de uma ocorrência cadastrada incorretamente | RF_006 |
| Consultar mapa | Setor de Planejamento, Visualizador | Visualização do mapa com as estatísticas por bairro | RF_008, RF_009, RF_010 |
| Gerar relatório | Setor de Planejamento | Geração de relatório em PDF/planilha por período | RF_012, RF_013 |