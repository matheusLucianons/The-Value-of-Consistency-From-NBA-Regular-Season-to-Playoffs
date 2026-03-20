# The Value of Consistency: From NBA Regular Season to Playoffs (2012-2024) 🏀

Este repositório contém o desenvolvimento de uma solução completa de **Business Intelligence (BI)** para análise de performance de jogadores da NBA, abrangendo as temporadas de **2012-13 a 2023-24**. O objetivo central é avaliar a consistência e eficiência dos atletas na transição entre a **Temporada Regular** e os **Playoffs**.

## 🚀 Tecnologias e Ferramentas
*   **Banco de Dados:** MySQL (Data Warehouse dimensional).
*   **ETL (Extração, Transformação e Carga):** Pentaho Data Integration (PDI).
*   **Visualização de Dados:** Microsoft Power BI.
*   **Gestão do Projeto:** ProjectLibre.

## 🏗️ Modelagem Dimensional
Foi utilizado a **metodologia de Kimball** para estruturar um modelo **Star Schema** (Esquema Estrela), otimizando a performance analítica e clareza dos dados.

*   **Tabela Fato (`Fato_Jogador`):** Concentra métricas quantitativas por jogador e por partida, como pontos, rebotes e assistências.
*   **Dimensões:**
    *   `Dim_Equipe`: Informações sobre franquias e conferências.
    *   `Dim_Tempo`: Contextualização temporal (ano, temporada e tipo de fase).
    *   `Dim_Desempenho_Jogador`: Agrupamento de índices de eficiência.

## 🔄 Processo de ETL
O fluxo de dados foi automatizado no **Pentaho PDI** através de *Jobs* e *Transformations*:
1.  **Limpeza e Padronização:** Remoção de duplicatas, tratamento de valores nulos e uniformização de nomes.
2.  **Enriquecimento:** Criação de métricas derivadas, como o índice de eficiência geral (EFF).
3.  **Orquestração:** Garantia de integridade referencial carregando as dimensões antes da tabela fato .

## 📊 Visualização e KPIs
O dashboard no **Power BI** foi desenhado para facilitar a tomada de decisão estratégica, focando em seis **Indicadores-Chave de Desempenho (KPIs)** fundamentais:
*   **PPG:** Média de pontos por partida (volume ofensivo).
*   **FG%:** Eficiência de arremessos de quadra.
*   **APG / RPG:** Médias de assistências e rebotes por jogo.
*   **EFF:** Índice de eficiência consolidado para comparação global.
*   **MIN:** Minutos em quadra para contextualização das médias.

### Funcionalidades do Painel
*   Filtros dinâmicos por temporada, fase (Regular/Playoffs), equipe e jogador.
*   Análise de evolução histórica dos arremessos de 3 pontos.
*   Gráficos de dispersão correlacionando tempo de jogo e desempenho.
