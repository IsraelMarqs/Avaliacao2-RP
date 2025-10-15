# Avaliacao2-RP

1. Carga dos Dados
O script inicia carregando o wine dataset a partir do scikit-learn. Os dados são divididos em duas partes essenciais: X, que contém as 13 características (features) que descrevem cada vinho e será a base para o processamento, e y_true, que armazena a classe real de cada vinho. A variável y_true não é utilizada no treinamento, servindo apenas como referência para a avaliação visual no final do processo.

2. Padronização dos Dados (StandardScaler)
As 13 características em X são normalizadas através do StandardScaler, que ajusta cada uma para que tenha média 0 e desvio padrão 1. Esta etapa é um requisito para o PCA, pois a técnica é sensível a diferentes escalas. Sem a padronização, uma característica com valores naturalmente altos dominaria a análise, enquanto outras com valores baixos seriam sub-representadas. O processo garante que todas as características contribuam de forma equilibrada.

3. Redução de Dimensões (PCA)
O PCA é aplicado sobre os dados já padronizados para reduzir as 13 dimensões a apenas 2 componentes principais. O algoritmo separa as caracteristicas mais significativas e que são projetadas para capturar o máximo de variação possível nos dados. O script também calcula e exibe a porcentagem de "variância explicada", informando o quanto da informação original foi preservada nesses 2 componentes. O objetivo é simplificar os dados com perda mínima de informação relevante.

4. Clusterização (K-Means)
Com os dados agora representados em um espaço 2D, o algoritmo K-Means é executado para identificar os agrupamentos. Ele agrupa os vinhos em 3 clusters (n_clusters=3), atribuindo cada amostra ao cluster cujo centro (centroide) está mais próximo. Os parâmetros random_state e n_init são usados para garantir que o resultado seja consistente e estável, evitando uma solução subótima que poderia surgir de uma única inicialização aleatória.

5. Visualização e Comparação
A etapa final consiste na plotagem de dois gráficos para a interpretação dos resultados. O primeiro gráfico mostra os vinhos no espaço 2D criado pelo PCA, com as cores representando os clusters atribuídos pelo K-Means e os marcadores 'X' indicando os centroides de cada cluster. O segundo gráfico exibe os mesmos pontos, mas com as cores representando as classes verdadeiras (y_true). Esta comparação direta permite avaliar visualmente se os clusters encontrados pelo algoritmo correspondem à estrutura real dos dados.

