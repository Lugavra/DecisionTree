# DecisionTree

💳 Credit Scoring Risk Predictor: Árvore de Decisão com Validação Cruzada
Este repositório apresenta o modelo preditivo de Credit Scoring desenvolvido. O projeto utiliza um algoritmo de Árvore de Decisão (Decision Tree Classifier) focado em identificar o risco de inadimplência (default) de clientes bancários a partir de variáveis comportamentais e financeiras.

🚀 Diferenciais Técnicos deste Repositório
Split Treino/Teste Estrito (89,91% de Acurácia Global): Avaliação do modelo realizada em um conjunto de teste com dados nunca vistos pelo algoritmo (holdout de 30%), blindando o projeto contra o otimismo exagerado (overfitting).

Robustez via Validação Cruzada (Cross-Validation): Implementação de validação em 5 folds (cv=5) no conjunto de treino, garantindo a estabilidade estatística das partições.

Foco Pragmático em Risco Financeiro: Modelagem estruturada com a variável alvo parametrizada para Inadimplente = 1, priorizando a análise de Recall (Sensitividade) para mitigar a concessão de crédito nocivo.

🛠️ Tecnologias e Bibliotecas Utilizadas
Linguagem: Python 3.x

Machine Learning & Validação: scikit-learn (DecisionTreeClassifier, train_test_split, cross_val_score)

Métricas de Performance: confusion_matrix, classification_report, ConfusionMatrixDisplay

Engenharia de Dados: pandas, numpy

Visualização Gráfica: matplotlib, seaborn

📖 Metodologia e Pipeline do Projeto
Saneamento de Dados: Conversão automatizada de strings monetárias com formatação regional para tipos numéricos flutuantes (float).

Codificação de Categóricas (Dummies): Aplicação de One-Hot Encoding sem eliminação do primeiro nível (drop_first=False) para assegurar a leitura direta e literal das regras lógicas mapeadas nos nós da árvore.

Controle de Complexidade (Poda): Fixação de profundidade máxima (max_depth=3) e tamanho mínimo de amostra por folha (min_samples_leaf=50) para a construção de uma árvore altamente interpretável e generalizável.

🔍 Regras de Negócio Extraídas (Mapeamento do Risco)
A topologia da árvore revelou padrões claros de comportamento financeiro:

O Grande Divisor (Nó Raiz): A Quantidade de Transações (12 meses) com ponto de corte em 54.5 é o principal separador de risco. Clientes com alto volume transacional (> 54) entram em uma zona de segurança com apenas 5% de taxa de inadimplência base.

O Perfil Crítico: Clientes de baixo engajamento (<= 54.5 transações) associados a um baixo volume financeiro gasto (valor_transacoes_12m <= 1001.57) acionam o alerta máximo do modelo, concentrando 88% de taxa de inadimplência no nó folha mais puro.

📊 Estrutura de Execução Modulares (#%%)
O script está estruturado de forma limpa e modular para execução em blocos:

# 1 e # 2: Importação e Pré-processamento dos dados.

# 3 e # 4: Divisão da base e aplicação da Validação Cruzada.

# 5 e # 6: Treinamento do classificador e plotagem do fluxograma da árvore.

# 7: Geração da Matriz de Confusão e Relatório de Classificação nos dados de teste.

## 📈 Visualizações do Projeto

### Estrutura de Decisão Gerada:
![Árvore de Decisão](images/nome_da_foto_da_arvore.png)

### Matriz de Confusão (Dados de Teste):
![Matriz de Confusão](images/nome_da_foto_da_matriz.png)
