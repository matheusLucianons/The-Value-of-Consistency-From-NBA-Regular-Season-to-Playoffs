# The Value of Consistency: From NBA Regular Season to Playoffs (2012-2024) 🏀

Este repositório contém o desenvolvimento de uma solução completa de **Business Intelligence (BI)** para análise de performance de jogadores da NBA, abrangendo as temporadas de **2012-13 a 2023-24**. O objetivo central é avaliar a consistência e eficiência dos atletas na transição entre a **Temporada Regular** e os **Playoffs**.

## 🚀 Tecnologias e Ferramentas
*   **Banco de Dados:** MySQL (Data Warehouse dimensional).
*   **ETL (Extração, Transformação e Carga):** Pentaho Data Integration (PDI).
*   **Visualização de Dados:** Microsoft Power BI.
*   **Gestão do Projeto:** ProjectLibre.

## 📂 Estrutura do Repositório
A organização deste repositório reflete as etapas de Business Intelligence detalhadas na documentação do projeto, contendo os seguintes arquivos e diretórios:

```
├── Dados/
│   ├── nba.csv                                           # Dataset bruto com estatísticas de 2012 a 2024 
│   └── Relatorio Final - NBA - Inteligência de Negócios  # Documentação técnica com justificativas e insights 
|
├── ETL/
│   ├── nba_job.kjb                                       # Job principal de orquestração no Pentaho PDI 
│   ├── nba_dim_equipe.ktr                                # ETL para processamento da dimensão Equipe 
│   ├── nba_dim_desempenho_jogador.ktr                    # ETL para a dimensão de índices de eficiência 
│   ├── nba_dim_tempo.ktr                                 # ETL para contextualização de temporadas e fases 
│   └── nba_fato_jogador.ktr                              # ETL da tabela Fato com cruzamento de chaves 
|
├── Modelagem de Dados/
│   └── script_dw_nba.sql                                 # Scripts para criação do Star Schema no MySQL 
|
├── Visualização de Dados/
│   └── nba_analytics.pbix                                # Dashboard interativo com KPIs e medidas DAX 
|    └── Tela 1.png                                       # Imagem Dashboard Parte 1
|    └── tela 2.png                                       # Imagem Dashboard Parte 2 
|
├── README
└── README.md                                             # Guia principal com tecnologias e resultados 
```

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

## Funcionalidades do Painel
*   Filtros dinâmicos por temporada, fase (Regular/Playoffs), equipe e jogador.
*   Análise de evolução histórica dos arremessos de 3 pontos.
*   Gráficos de dispersão correlacionando tempo de jogo e desempenho.

## 📊 Resultados e Insights Obtidos

A implementação desta solução de BI transformou dados brutos em um ecossistema analítico de alto impacto, consolidando os seguintes resultados técnicos e analíticos:

*   **Fonte de Dados e Confiabilidade:** O projeto processou com sucesso o dataset extraído do **Kaggle**, cobrindo o período de 2012-13 a 2023-24.
*   **Eficiência da Modelagem Dimensional:** Utilizando a **metodologia de Kimball**, estruturamos um modelo *Star Schema* no **MySQL** centrado na tabela `Fato_Jogador`. Isso permitiu uma granularidade por partida que suporta análises complexas sem perda de performance.
*   **Automação via ETL (Pentaho PDI):** O processo de ETL garantiu a integridade referencial através da orquestração de *Jobs* e *Transformations*, realizando a limpeza de duplicatas, tratamento de nulos e a criação de métricas derivadas (como o índice de eficiência EFF) de forma automatizada.
*   **Análise de Consistência (Regular Season vs. Playoffs):** O dashboard no **Power BI** revelou como a pressão das fases eliminatórias impacta os seis KPIs principais (**PPG, FG%, APG, RPG, EFF e MIN**). Foi possível identificar quais atletas mantêm a regularidade estatística sob alta intensidade defensiva.
*   **Insights sobre o Jogo Moderno:** A visualização de dados evidenciou a evolução tática da liga, destacando o crescimento exponencial nas tentativas e conversões de **arremessos de 3 pontos** ao longo da última década.
*   **Correlação Eficiência vs. Minutagem:** Através de gráficos de dispersão, validamos a correlação direta entre o tempo em quadra e o desempenho global, permitindo diferenciar jogadores de impacto imediato daqueles que sustentam a performance por longos períodos.
*   **Ferramentas Integradas:** O sucesso do projeto foi sustentado pela integração entre **MySQL** (Data Warehouse), **Pentaho** (ETL), **Power BI** (Visualização) e **ProjectLibre** (Gestão).

Para uma compreensão aprofundada de toda a jornada analítica, modelagem de dados e justificativas estatísticas, consulte o documento oficial:
👉 **Relatório Final:** [./Dados/Relatorio Final - NBA - Inteligência de Negócios.pdf](./Dados/Relatório%20Final%20-%20NBA%20-%20Inteligência%20de%20Negócios.pdf).

 ## 📚 Referências e Fonte de Dados
A base de dados utilizada para este projeto de Business Intelligence foi extraída da plataforma **Kaggle**, abrangendo estatísticas detalhadas de jogadores e partidas da NBA.

*   **Dataset Principal:** [NBA Stats Dataset for last 10 years](https://www.kaggle.com/datasets/shivamkumar121215/nba-stats-dataset-for-last-10-years) – Fonte primária dos dados históricos das temporadas 2012-13 a 2023-24.
*   **Referência Analítica:** [NBA Data Visualization (Kaggle Notebook)](https://www.kaggle.com/code/ugureker/nba-data-visualization/notebook) – Utilizado como material de apoio para exploração de dados e visualização.
