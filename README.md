# Intelig-ncia-Artificial
Disciplina de Inteligência Artificial 6B - Victor Gonzaga
________________________________________________________

Exercícios de Lógica em Python

50 exercícios básicos de Python pra praticar:

Entrada e saída de dados (input, print)
Condicionais (if, elif, else)
Loops (for, while)
Listas e dicionários
Strings (inverter, contar, dividir)
Funções e recursão
Algoritmos de ordenação e busca
Bibliotecas: math, random, matplotlib

Cada exercício tá comentado e separado.
________________________________________________________

Exercícios de NumPy, SciPy, Pandas e Matplotlib

Este repositório contém a resolução de 80 exercícios (20 por biblioteca) propostos como prática das principais bibliotecas de ciência de dados em Python. O objetivo foi fixar os conceitos fundamentais de cada uma, desde criação de estruturas de dados até operações mais avançadas de álgebra linear, otimização, manipulação tabular e visualização.

Principais conceitos praticados

NumPy

Criação e manipulação de arrays (np.array, np.zeros, np.eye, np.random)
Estatística: média, mediana, moda, desvio padrão
Fatiamento, reshape e operações elementares
Álgebra linear básica (inversa, determinante, sistemas lineares)

SciPy

Integração numérica (scipy.integrate.quad, dblquad)
Equações diferenciais ordinárias, incluindo redução de EDOs de 2ª ordem para sistemas de 1ª ordem (solve_ivp)
Otimização e busca de raízes (minimize, root, fsolve, brentq)
Interpolação linear, cúbica e spline (interp1d, CubicSpline)
Álgebra linear avançada (autovalores/autovetores, determinante, sistemas lineares)
Transformada de Fourier (fft, ifft)

Pandas

Criação de DataFrames a partir de dicionários de listas
Leitura e escrita de arquivos (CSV, Excel)
Filtragem, ordenação, agrupamento (groupby) e tabelas dinâmicas (pivot_table)
Tratamento de dados ausentes (fillna, dropna, interpolate)
Merge de DataFrames e renomeação de colunas

Matplotlib

Gráficos de linha, dispersão, barras, pizza e histogramas
Subplots e múltiplas séries no mesmo gráfico
Personalização (cores, estilos de linha, grades, legendas, anotações de texto)
Gráficos avançados: dispersão 3D, barras empilhadas, barras horizontais, exportação em PDF
________________________________________________________

Classificação do Dataset Iris com SVM

Atividade de reavaliação do dataset Iris, utilizando dados obtidos diretamente do Kaggle e um modelo de classificação desenvolvido exclusivamente com o algoritmo Support Vector Machine (SVM).

Objetivo
- Usar dados externos obtidos do Kaggle (sem load_iris()).
- Realizar a Análise Exploratória de Dados (EDA).
- Desenvolver um modelo de classificação usando apenas SVM.
- Avaliar o desempenho com métricas clássicas.
- Documentar todo o fluxo de trabalho de Machine Learning.

Dataset
Iris Species — dataset obrigatório da atividade, anexado diretamente ao notebook a partir da própria página no Kaggle.

Tecnologias utilizadas:
- Python 3
- pandas / numpy
- matplotlib / seaborn
- scikit-learn (SVC, StandardScaler, train_test_split, cross_val_score, métricas de avaliação)

Estrutura do notebook
- Setup
- Load Dataset
- Initial Inspection (Análise Exploratória de Dados)
- Data Preparation
- Train/Test Split
- Normalization
- Train SVM Model
- Prediction
- Evaluation
- Visualization

Modelo
- Algoritmo: SVC (Support Vector Classifier)
- Kernel: RBF
- Parâmetros: C=1.0, gamma="scale"

Avaliação
- Acurácia
- Classification report (precision, recall, f1-score)
- Matriz de confusão
- Validação cruzada (5 folds)

________________________________________________________

Esse notebook (summit-dupla-intelig-ncia-artificial.ipynb) cobre a Etapa 1 da atividade — escolha do dataset, import e avaliação do banco, tratamento de dados ausentes e encoding. Ainda não tem as etapas de treino do SVM. Resumo do que ele faz, célula por célula:

1. Import do dataset

Importa pandas, numpy, matplotlib e seaborn.
Carrega o glass.csv (adicionado via painel de Input do Kaggle) com pd.read_csv() e mostra as 5 primeiras linhas com df.head().

2. Avaliação do banco de dados

df.info(): confirma que são 214 registros, 10 colunas, nenhum valor nulo, sendo 9 atributos float64 e a Type (alvo) int64.
df.describe(): estatísticas descritivas — nota que o Silício (Si) domina os valores, que Bário (Ba) é zero em mais de 75% das amostras, possíveis outliers em K e Ca, e que as escalas são bem diferentes entre si (justificando padronização mais adiante).

3. Tratamento de dados ausentes

Conta nulos por coluna (isnull().sum()) e linhas duplicadas (duplicated().sum()).
Resultado: nenhum valor ausente, mas 1 linha duplicada foi identificada (o código só trata nulos com mediana — a linha duplicada é citada no texto mas não chega a ser removida na célula).

4. Tratamento de encoding

Explica que os atributos preditores já são numéricos, então não precisam de encoding.
Mas a Type (alvo) tem classes não sequenciais (1,2,3,5,6,7 — falta o 4), então aplica LabelEncoder, criando a coluna Type_encoded (0 a 5) e imprime a correspondência entre valor original e codificado.

Complemento visual (extra da etapa 2)

Gráfico de barras (countplot) da distribuição de Type, para visualizar o desbalanceamento das classes.
Mapa de calor (heatmap) de correlação entre os 9 atributos numéricos (excluindo Type/Type_encoded).
