📊 Desafio TOTVS – Clusterização de Clientes com RFM e HDBSCAN
🎯 Desafio

O desafio foi proposto pela TOTVS com o objetivo de clusterizar clientes a partir de variáveis comportamentais e contratuais, de forma a apoiar a jornada do cliente e possibilitar ações estratégicas de marketing, fidelização e retenção.

📌 RFM – Introdução

A segmentação RFM (Recência, Frequência, Monetário) é uma técnica de ranqueamento e agrupamento de consumidores baseada em seu comportamento de compras.

📊 Critérios Utilizados na Clusterização

Monetário (M): MRR do cliente nos últimos 12 meses.

Recência (R): data da última assinatura de contrato (cliente mais recente).

Frequência (F): quantidade de contratações nos últimos 12 meses.


🛠️ Metodologia

1. Preparação dos Dados

Construção das variáveis RFM.

Aplicação de transformações estatísticas:

Box-Cox: variáveis positivas.

Yeo-Johnson: variáveis com valores zero/negativos.

Padronização com StandardScaler.

2. Clusterização – HDBSCAN

Utilizou-se o algoritmo HDBSCAN (Hierarchical Density-Based Spatial Clustering of Applications with Noise), que:

Executa DBSCAN em múltiplos valores de epsilon e integra os resultados.

Encontra clusters com densidades variadas.

É mais robusto na presença de ruído e menos sensível a parâmetros do que o DBSCAN.

📊 Resultados

Número de clusters: 5

Tamanho dos clusters: [2485, 3816, 827, 1689, 1785]

Ruído identificado: 13 clientes

Métricas de avaliação:

Silhouette Score → 0.67 (boa separação)

Davies-Bouldin → 0.74 (baixo, indicando coesão dos clusters)

Calinski-Harabasz → 45.970 (alto, clusters bem definidos)

Estabilidade (ARI bootstrap) → 0.97 ± 0.016 (alta robustez)
