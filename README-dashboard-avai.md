# Dashboard Avaí FC 2025 — Power BI

Projeto de portfólio desenvolvido em **Power BI** para análise do desempenho do **Avaí Futebol Clube** durante a temporada de 2025, abrangendo o **Campeonato Catarinense** e o **Campeonato Brasileiro Série B**.

O projeto tem como objetivo transformar dados esportivos em informações visuais que auxiliem na análise de **desempenho, utilização do elenco, produção ofensiva e disciplina dos jogadores**.

## Motivação

A ideia surgiu a partir de projetos de análise esportiva vistos no LinkedIn, com dashboards voltados ao desempenho de clubes de futebol.

Como torcedor do Avaí, decidi desenvolver um projeto próprio utilizando dados da temporada 2025, aplicando conceitos de **Business Intelligence, modelagem de dados, Power Query e DAX**.

Durante o desenvolvimento, ferramentas de **Inteligência Artificial foram utilizadas como apoio** na construção do projeto.

Além de servir como projeto de portfólio, o dashboard foi desenvolvido com foco em demonstrar como dados podem ser transformados em informações úteis para análise e tomada de decisão.

## Fontes de dados

| Competição                       | Fonte                                                  | Formato coletado        |
| -------------------------------- | ------------------------------------------------------ | ----------------------- |
| Campeonato Catarinense           | [OGol.com.br](https://www.ogol.com.br/)                | Coleta manual           |
| Série B do Campeonato Brasileiro | [FutPythonTrader](https://www.futpythontrader.com.br/) | Arquivo XLS estruturado |

Os dados foram posteriormente tratados, padronizados e organizados para utilização no Power BI.

## Estrutura dos dados

O projeto utiliza um modelo relacional composto por quatro tabelas principais:

### `Jogos`

Contém informações das partidas disputadas pelo Avaí:

* ID da partida
* Data e horário
* Competição
* Rodada
* Mando de campo
* Adversário
* Gols do Avaí
* Gols do adversário
* Placar
* Resultado
* Informações relacionadas a pênaltis

### `Jogadores`

Cadastro dos jogadores:

* ID do jogador
* Nome
* Posição

### `estatisticas_jogador`

Estatísticas agregadas por jogador e competição:

* Jogos
* Gols
* Assistências
* Titularidades
* Reservas
* Minutos jogados
* Cartões amarelos
* Segundo amarelo
* Cartões vermelhos

### `participacao_gols`

Registro das participações individuais em gols, relacionando jogador e partida:

* ID da partida
* Competição
* Placar
* Jogador
* Gols
* Assistências

A estrutura foi desenvolvida buscando reduzir duplicidades e permitir análises cruzadas entre partidas, competições e jogadores.

## Tratamento e modelagem

O processo de preparação dos dados foi realizado principalmente no **Power Query**, incluindo:

* Padronização de tipos de dados
* Limpeza e organização das tabelas
* Padronização de identificadores
* Tratamento das informações de partidas e jogadores
* Criação das dimensões necessárias para análise
* Estruturação dos relacionamentos entre as tabelas
* Criação da tabela calendário

O modelo foi posteriormente utilizado para construção das medidas e dos visuais no Power BI.

## Dashboard

### Visão Geral

A primeira página apresenta uma visão consolidada da temporada, incluindo:

* Total de jogos
* Vitórias
* Gols marcados
* Gols sofridos
* Saldo de gols
* Distribuição dos resultados
* Desempenho em casa e fora
* Evolução temporal de gols marcados e sofridos
* Aproveitamento por competição
* Resumo das competições

A página também conta com filtros interativos por **mês, competição, resultado e rodada**, permitindo explorar diferentes recortes da temporada.

### Análise de Jogadores

A segunda página é dedicada ao desempenho individual do elenco.

Indicadores apresentados:

* Jogador
* Gols
* Assistências
* Minutos
* Titularidades
* Cartões amarelos
* Jogos

Visuais desenvolvidos:

* **Participação em gols por jogador**
* **Minutos por participação em gol**
* **Titularidade × participação em gols**
* **Tabela da disciplina**

O gráfico de dispersão permite analisar a relação entre a quantidade de titularidades e a participação direta em gols, com diferenciação dos jogadores por posição.

O indicador de minutos por participação considera um **mínimo de 300 minutos jogados**, reduzindo possíveis distorções causadas por jogadores com poucas oportunidades em campo.

## Principais conceitos aplicados

* Power BI
* Power Query
* Modelagem relacional
* Modelo dimensional
* DAX
* Medidas e indicadores
* Segmentações de dados
* Visualização de dados
* Análise exploratória
* Business Intelligence

## SQL

O **SQL não foi utilizado na versão atual do projeto**.

A utilização de SQL está prevista como uma futura evolução, permitindo incorporar uma etapa adicional de consulta e preparação dos dados e comparar diferentes abordagens de tratamento e análise.

## Status do projeto

* [x] Definição do escopo
* [x] Coleta dos dados
* [x] Estruturação das tabelas
* [x] Tratamento dos dados no Power Query
* [x] Criação da tabela calendário
* [x] Modelagem e relacionamentos
* [x] Criação das medidas DAX
* [x] Desenvolvimento da página **Visão Geral**
* [x] Desenvolvimento da página **Análise de Jogadores**
* [x] Criação dos filtros interativos
* [x] Padronização visual do dashboard
* [x] Organização do projeto em formato PBIP
* [x] Versionamento do projeto no Git/GitHub
* [x] Documentação do projeto
* [x] Documentação e publicação final do projeto

---

**Projeto desenvolvido como parte da construção de portfólio em Business Intelligence e Análise de Dados.**
