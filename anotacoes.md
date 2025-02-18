## Inteligência Artificial

- Capacidade de máquinas tomarem decisões inteligentes
- Capacidade de tomar a melhor decisão possível dada a informação disponível. Com a capacidade de se adaptar a novas situações.

## Machine Learning

### Antigo
- Inteligência artificial clássica
- Regras para a tomada de decisão ensinada por humanos
- Decisões inteligentes são complexas

### Atual
- Máquinas aprendendo as regras para a tomada de decisão sozinhas !
- Tomada de decisão via identificação de padrões complexos nos dados
- Regras aprendidas pela máquina
- O cérebro humano é uma caixa preta e machine learning não é

### Problemas práticos de predição (para a tomada de decisão)
- Pouco interesse em interpretar os modelos
- Liberdade para modelar a complexidade do mundo real

### Aprendizado Supervisionado
- Acertar um resultado que existe
    - Classificação
        - Variável categórica
    - Regressão
        - Variável quantitativa

### Aprendizado Não Supervisionado
- Não existe rótulo ("label")
- Algoritmo aprende ser uma resposta certa
- O objetivo é encontrar padrões nos dados
- Mais comuns: clustering (agrupamentos) e redução de dimensões (ACP)

### Aprendizado por Reforço
- Agente interage com um ambiente dinâmico
- Feedbacks constantes em termos de premiações e punições
- Jogos
- Série AlphaGo
- Diferentes etapas do tratamento médico para identificar sequência ótima

### Autosupervisionado
- Um problema não supervisionado é transformado em um problema superviosionado pela geração automática dos rótulos

### Como os algoritmos são treinados?
- Pre Training
- Supervised fine-tuning
- Reinforcement Learning
    - RLHF
    - RLAIF AI - Feedack

### Predição com Machine Learning
- Trade-off entre predição e interpretação
- Em predição estamos interessados em performance preditiva
- Em inferência é entender a relação entre variáveis, normalmente como Y muda com alterações entre seus determinantes.
- Problema: modelos facilmente interpretáveis
- Pensar bem sobre o objetivo da análise, é inferência ou predição?

### Importante
- Dados: preferencialmente muitos e com boa qualidade (preenchidos corretamente e preditores fortes)
- Especialistas ajudam a escolher as variáveis (exemplo profissionais de infarto)
- Algoritmos
    - Inserir os dados no algoritmo de machine learning para aprender os parâmetros (regressão logística/linear) ou estruturas (árvores) que mapeiam os preditores aos resultados
- Testar no Futuro
    - Inserir no algoritmo novos dados para testar a performance preditiva

-- Gemêos digitais

--------------------------------------------------------------------------------------------------------------------------------------------------------

### Artigos para balizar o curso
- Entenda os dados
    - Forma de coleta
    - Se a aplicação prática faz sentido
- Não olhe para todos os seus dados
    - Não analisar os dados de teste
- Certifique-se de que há dados suficientes
    - Rebalanceamento dos dados: não é mais utilizado
    - Para Saúde: Dados desbalanceados
- Balancear melhor com alguns filtros em grupos (tentar melhorar o balanceamento)
- Converse com especialistas no assunto
- Levantamento da Literatura
- Porque você quer construir esse modelo?
    - Pra quem eu vou entregar?
    - Como vou entregar?
    - Faz sentido?

- Vazamento de Dados
    - Vazamento torna modelos inúteis
    - Falta de confiabilidade
    - Pré-Processamento só no treino
    - Seleção de variáveis e otimização de hiperparâmetros só no treino

- Teste vários modelos
    - Não existe um único algoritmo melhor
    - Teorema do almoço grátis
    - Encontrar algortimo que gere a melhor predição
    - Python: scikit learn

- Não use modelos inapropriados
    - Modelos desnecessariamente complexos (deep learning para dados estruturados)
    - Modelos mais recentes nem sempre são melhores (cuidado com artigos de benchmark)

- Otimize os hiperparâmetros
    - Hiperparâmetros: parâmetros externos ao treinamento que afetam a configuração do modelo.
    - Hiperparâmetros afetam o desempenho
    - Estratégias de otimização (random search, grid search, hyperopt etc)

- Cuidado com a otimização de hiperparâmetros e seleção de variáveis
    - Seleção de variáveis antes do data splitting
    - Seleção estatística de variáveis e otimização de hiperparâmetros devem ser feitas com os dados de treino
    - Técnica: Validação Cruzada aninhada (definição de hiperparâmetros e parâmetros dentro da mesma validação cruzada)

- Use um conjunto de teste adequado

- Use um conjunto de validação
    - Pode ser usado para orientar o treinamento, após ajuste de parâmetros

- Salve dados para uma avaliação final
    - Validação Cruzada
    - Usar teste se possível

- Não use a acurácia com dados desbalanceados
    - A acurácia só funciona com amostras balanceadas (mesmo número de observações de ambas as classes)
    - Os dados de saúde costumam ser desbalanceados

- Uma boa performance preditiva não é garantia de um bom algoritmo
    - Analise o artigo

- Use testes estatísticos para comparar modelos

- Faça correlações para múltiplas comparações

- Considere combinações de modelos
    - Bagging e Boosting
    - Como combinar diferentes modelos de base?
    (votação ou usar um algoritmo final para agregação de resultados)
    - Sabedoria das multidões

- Não generalize para além do seu cojunto de dados

- Aprendizado por transferência
    - Ajuste fino no modelo depois de treinado para usar em cidades menores (por exemplo)
    - Muito interessante

- Mostre como o modelo aprendeu e tomou as decisões
    - Objetivo: gerar conhecimento
    - Forneça visualizações
    - Use técnicas de explicabilidade (Shapley)
    - Machine Learning para dados estruturados (predição) não é uma caixa preta, o cérebro sim
        - Não vai ser causal

Artigo: How To Avoid machine learning pitfalls


## Dia 02 - Predição com Machine Learning

- Desenvolver algoritmos que façam boas predições em saúde
- Principais razões técnicas pelas quais algoritmos às vezes não apresentam boa performace preditiva
    - Extrapolação inadequada dos resultados
    - Pré-processamento inadequado aos dados
    - Sobreajuste (mais importante)
    - Validação inadequada da qualidade dos algoritmos

-- Cuidado com a sazonalidade dos dados

-- Aprendizado Federado

### Artigo: Improving the performance of machine learning algorithms for health outcomes predictions in multicentric cohorts

- Os melhores desempenhos preditivos foram obtidos ao usar dados de treinamento do mesmo hospital, que foi a estratégia vencedora para 11 (61%) dos 18 hospitais participantes

### Técnicas de Pré-Processamento
- Seleção das variáveis
    - Preditores plausíveis (bom senso do pesquisador)
    - Coincidências acontecem em análises de big data
        - Correlações de espúria (tylervigen.com)

- Data Leakage
    - Não é a variável que está predizendo o desfecho, mas o desfecho que está predizendo ela

- Padronização
    - Escala das variáveis pode afetar muito a qualidade das predições
    - Alguns algoritmos darão preferência para valores mais altos, por isso é bom escalar
    - Standard Scaler
        - Ajuda muito os algoritmos mais clássicos

- Redução de Dimensão
    - Análise de Componentes Principais (PCA)
    - PCA cria componentes principais não correlacionados

- Variáveis Missing
    - Grande diferença em relação a estudos de inferência, em que valores missing devem ser evitados

- One Hot Enconding
    - Categórica -> Flag numérica
    - **Target Enconding** -> Transformar categóricas em contínuas, o valor da categoria vira o seu valor médio do desfecho entre os individuos dessa categoria

### Artigo: Model Evaluation, Model Selection and Algorithm Selection

- Com dados reais, costumam ganhar mais vezes (gradient boosting, random forest e **type fn**)

- Modelo: função que acreditamos (esperamos) queu seja semelhante a verdadeira
- Algoritmo: conjunto de instruções que permeiam as regras de decisões
- Hiperparâmetros são os parâmetros (meta - parâmetros) que eu devo definir para o algoritmo (dificultando a vida dele)

- Viés Pessimista

Reamostragem
- Bootstraping e incerteza
    - Alta variância - Sobre ajuste
    - Alto viés - Sub ajuste
    - Ajustado

- Validação Cruzada e otimização de hiperparâmetros
    - K-Fold (Geralmente 10 folds, trade off ideal entre viés e variância)
    - Salva os melhores hiperparametros
    - Treina o modelo com esses hiperparametros
    

 


