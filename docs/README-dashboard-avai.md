# Dashboard Avaí FC 2025 — Power BI

Projeto de portfólio desenvolvido em Power BI para análise de desempenho do Avaí Futebol Clube durante a temporada de 2025, contemplando o **Campeonato Catarinense** e o **Campeonato Brasileiro Série B**.

O projeto busca demonstrar como dados esportivos podem ser organizados, modelados e transformados em indicadores e visualizações capazes de auxiliar na análise de desempenho.

## Motivação

A ideia surgiu a partir de projetos de análise esportiva vistos no LinkedIn, com dashboards voltados ao desempenho de clubes de futebol.

Como torcedor do Avaí, decidi aplicar essa abordagem ao clube, construindo um dashboard próprio a partir de dados coletados de diferentes fontes e posteriormente tratados e modelados no Power BI.

Além do resultado visual, o projeto tem como objetivo aplicar conceitos de:

- Power Query
- Modelagem de dados
- Modelo dimensional
- DAX
- Data visualization
- Indicadores de desempenho (KPIs)

## Escopo

O dashboard contempla a temporada **2025** do Avaí FC nas seguintes competições:

- Campeonato Catarinense 2025
- Campeonato Brasileiro Série B 2025

As análises envolvem informações de partidas, resultados, gols, jogadores, participações em gols e estatísticas individuais.

## Fontes de dados

| Competição | Fonte | Formato coletado |
|---|---|---|
| Campeonato Catarinense | [OGol.com.br](https://www.ogol.com.br/) | Coleta manual |
| Série B do Brasileirão | [FutPythonTrader](https://www.futpythontrader.com.br/) | Arquivo XLS estruturado |

Os dados foram posteriormente organizados e tratados para utilização no Power BI.

## Organização e modelagem dos dados

Os dados foram inicialmente estruturados em quatro tabelas principais:

### Jogos

Contém informações de cada partida:

- `id_jogo`
- `data`
- `hora`
- `competição`
- `rodada`
- `mando`
- `adversário`
- `gols_avai`
- `gols_adversario`
- `placar`
- `resultado`
- `penaltis`

### Jogadores

Cadastro dos jogadores:

- `id_jogador`
- `jogador`
- `posição`

Essa tabela passou a atuar como **DIM_Jogador** no modelo.

### estatisticas_jogador

Contém estatísticas agregadas por jogador e competição:

- jogos
- gols
- assistências
- titularidades
- reservas
- minutos
- cartões amarelos
- segundos amarelos
- cartões vermelhos

### participacao_gols

Registra as participações individuais em gols:

- `id_jogo`
- `competição`
- `placar`
- `id_jogador`
- `gols`
- `assistências`

Essa estrutura permite relacionar os eventos de uma partida aos jogadores envolvidos sem duplicar informações desnecessariamente.

## Modelo de dados

Durante a modelagem no Power BI foram criadas dimensões auxiliares para organizar os dados e facilitar a construção das análises.

### Dimensões

- **DIM_Jogador** — identificação, nome e posição dos jogadores
- **DIM_Calendario** — datas, meses e informações temporais
- **DIM_Rodada** — competição, rodada e chave de relacionamento

### Tabelas de dados

- **Jogos**
- **estatisticas_jogador**
- **participacao_gols**

A modelagem utiliza relacionamentos **1:N**, com as dimensões filtrando as tabelas de dados.

A `DIM_Calendario` foi configurada como tabela de datas no Power BI.

## Tratamento dos dados

O tratamento foi realizado no **Power Query**, incluindo:

- Padronização dos tipos de dados
- Limpeza das tabelas
- Remoção de colunas desnecessárias
- Organização das informações para modelagem
- Criação de dimensões auxiliares
- Criação de chaves para relacionamentos
- Estruturação da tabela calendário

## Medidas DAX

Foram criadas medidas para alimentar os indicadores e visuais do dashboard, incluindo:

- Total de jogos
- Vitórias
- Empates
- Derrotas
- Gols marcados
- Gols sofridos
- Saldo de gols
- Aproveitamento
- Estatísticas individuais dos jogadores

O aproveitamento é calculado considerando o sistema de pontuação do futebol:

**Pontos conquistados ÷ pontos possíveis**

## Dashboard

### 1. Visão Geral

A primeira página apresenta uma visão consolidada do desempenho do Avaí em 2025.

Principais elementos:

- Total de jogos
- Total de vitórias
- Gols marcados
- Gols sofridos
- Saldo de gols
- Resultado dos jogos (Vitória / Empate / Derrota)
- Desempenho como mandante e visitante
- Evolução mensal de gols marcados e sofridos
- Aproveitamento
- Filtros interativos

A página possui uma barra lateral com filtros por:

- Competição
- Mês
- Resultado
- Rodada

### 2. Jogadores

A segunda página é dedicada ao desempenho individual dos jogadores.

Atualmente, a página possui:

- Filtro por jogador
- Filtro por competição
- Filtro por posição
- Total de jogadores
- Gols
- Assistências
- Minutos
- Titularidades
- Jogos
- Cartões amarelos

Os indicadores de **minutos, titularidades e jogos** são exibidos quando há seleção de jogador, evitando agregações pouco representativas quando nenhum jogador está selecionado.

## Identidade visual

O dashboard utiliza uma identidade visual inspirada no Avaí FC, com predominância de:

- Azul
- Azul escuro
- Branco

A interface foi estruturada com fundo escuro, cards destacados, barra lateral de filtros e elementos visuais consistentes entre as páginas.

## Tecnologias utilizadas

- **Power BI**
- **Power Query**
- **DAX**
- **Excel**
- **Git / GitHub**

O desenvolvimento também contou com apoio de ferramentas de Inteligência Artificial para auxiliar na organização, modelagem e desenvolvimento de algumas soluções do projeto.

## Status do projeto

- [x] Definição do escopo
- [x] Coleta dos dados
- [x] Estruturação das quatro tabelas principais
- [x] Tratamento dos dados no Power Query
- [x] Criação da DIM_Calendario
- [x] Criação da DIM_Jogador
- [x] Criação da DIM_Rodada
- [x] Modelagem e relacionamentos
- [x] Criação das principais medidas DAX
- [x] Construção da página **Visão Geral**
- [x] Construção inicial da página **Jogadores**
- [x] Implementação dos filtros interativos
- [x] Desenvolvimento da identidade visual
- [ ] Finalização dos visuais da página Jogadores
- [ ] Desenvolvimento das demais páginas
- [ ] Revisão e validação dos indicadores
- [ ] Documentação final
- [ ] Publicação do projeto e divulgação no LinkedIn

## Próximos passos

1. Finalizar os visuais de desempenho individual dos jogadores
2. Desenvolver as demais páginas analíticas
3. Revisar medidas e relacionamentos
4. Validar os resultados com os dados originais
5. Refinar a identidade visual e a experiência de navegação
6. Finalizar a documentação do projeto
7. Publicar o projeto no GitHub e utilizá-lo como parte do portfólio profissional