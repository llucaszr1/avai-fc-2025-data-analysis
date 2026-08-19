# Dashboard Avaí FC 2025 — Power BI

Projeto de portfólio com análise de desempenho do Avaí Futebol Clube na temporada 2025, cobrindo o **Campeonato Catarinense** e a **Série B do Campeonato Brasileiro**.

## Motivação

A ideia surgiu a partir de projetos semelhantes vistos no LinkedIn, com painéis de desempenho de clubes como São Paulo FC e Atlético Mineiro. Como torcedor do Avaí, decidi aplicar a mesma lógica ao clube, construindo um dashboard próprio a partir de dados coletados manualmente.

## Fontes de dados

| Competição | Fonte | Formato coletado |
|---|---|---|
| Campeonato Catarinense | [OGol.com.br](https://www.ogol.com.br/) | Coleta manual |
| Série B do Brasileirão | [futpythontrader.com.br](https://www.futpythontrader.com.br/) | Arquivo XLS já estruturado |

## Processo de organização dos dados

Com apoio de IA, os dados coletados nas duas fontes foram organizados em um modelo relacional com quatro tabelas, pensado para se comportar como um modelo estrela no Power BI:

- **Jogos** — uma linha por partida (data, hora, competição, rodada, mando, adversário, placar, resultado)
- **Jogadores** — elenco do clube (id, nome, posição)
- **estatisticas_jogador** — estatísticas agregadas por jogador e por competição (jogos, gols, assistências, titularidade x reserva, minutos, cartões)
- **participacao_gols** — registro individual de cada gol/assistência, vinculado à partida e ao jogador

Essa estrutura evita duplicar informação (por exemplo, o placar de um jogo não é repetido em cada linha de gol) e permite montar relacionamentos 1-para-N entre `Jogadores` → `estatisticas_jogador` e `Jogos` → `participacao_gols`.

## Status atual

- [x] Definição do escopo (Catarinense + Série B, temporada 2025)
- [x] Coleta dos dados nas fontes originais
- [x] Estruturação em 4 tabelas relacionadas (Excel)
- [ ] Tratamento de tipos de dados e modelagem no Power Query
- [ ] Criação da tabela calendário
- [ ] Construção das medidas DAX
- [ ] Montagem das páginas do dashboard no Power BI
- [ ] Publicação e documentação final (LinkedIn/GitHub)

## Próximos passos

1. Padronizar o tipo de `id_jogador` entre as abas (texto x número) no Power Query
2. Criar tabela calendário a partir de `Jogos[data]`
3. Construir medidas DAX (aproveitamento, saldo de gols, artilharia)
4. Montar as páginas: Visão geral, Desempenho por competição, Casa x Fora, Artilharia, Elenco
