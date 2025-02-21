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

## Dia 03 - Predição com Machine Learning

- Métricas de Performance Preditiva
- Estudar Algoritmos (arquitetura para o aprendizado, regras para a tomada de decisão)
- Explicabilidade é mais importante para um estudo de associação, não é um resultado de pesquisa importante

## Otimização de Hiperparâmetros
- Grid Search: método iterativo e automatizado de otimização que testa todas as combinações de valores a partir de uma grade de valores (menos utilizado)
- Random Search: Sorteia as combinações de hiperparâmetros para teste para se obter uma combinação ótima
- HyperOpt (Otimização Bayesiana): busca encontrar hiperparâmetros no ponto mínimo ou máximo da função objetivo.
- Validação Cruzada com combinação de diferentes hiperparâmetros (para definir a melhor combinação de hiperparâmetros)
- Retreino do algoritmo com os dados do treino e com os hiperparâmetros definidos
-- Observação: se a amostra for pequena ele tem mais chance de decorar os casos e ficar sobreajustado

## Tipos de Modelos Preditivos
- Regressão: variável predita é quantitativa
- Classificação: variável a ser predita é uma categoria

## Métricas de Performance
- Regressão:
    - Gráfico de dispersão da predição vs realidade
    - RMSE : Raiz do Erro Quadrático Médio

- Classificação
    - Acurácia: Proporção de acertos
### Importante
    - A maioria das métricas assume uma distribuição balanceada
    - As vezes FN (falso negativo) ou FP (falso positivo) são problemas
    - Ele desconhece a utilização de LLM's para gerar dados ficticios
## Artigo: To SMOTE, or not to SMOTE? --> Interessante

    - Desfecho desbalanceado (Estratégia)
        - Desenvolver algoritmo para as pessoas que tem maior risco com o desfecho para tentar balancear as classes
        - Existe balanceamento minimo necessário? (>= 10%, regra de bolso)
    - Estratégia 2
        - Mudar Threshold (acima da probabilidade da amostra deveria ser sim)
-- Cuidado com rebalanceamento dos dados

## Matriz de Confusão
    - Sensibilidade (Recall) = TP / TP + FN (Proporção dos casos positivos que o algoritmo está capturando)
    - Especificidade = TN / FP + TN (Propoção dos casos negativos que o algoritmo está capturando)
    - Precisão = TP / TP + FP (Valor Predito Positivo, entre os que eu falei que Sim, quantos acertei)
    - FScore = Média da precisão e do Recall (Harmônica)

## Métricas de Ranking
    - Área abaixo da curva ROC
    - Intuição: entre duas pessoas escolhidas aleatoriamente (em que uma tem o desfecho e a outra não), a AUC é a proporção de vezes que a predição será maior para a pessoa que de fato tem o desfecho.
    - Área abaixo da curva ROC de 1 = Perfeito, 0.5 é ineficiente
    - Regra de Bolso
        - Acima de 0.9 -> Excelente
        - Entre 0.8 e 0.9 -> Muito bom
        - Entre 0.7 e 0.8 -> Bom
        - Abaixa de 0.7 - Não tão bom

## Artigo: Neonatal mortality prediction with routinely collected data

## Gráficos de Calibração de Probabilidades
    - Quadratic discriminant analysis e random forests

## Algoritmos
### Artigo: Comparison of gradient Boosting decision three algortihms for cpu performance
- Melhor deles Gradient Boosting
- Random Forest
- Especificações de Gradient Boosting
- Média de 3 a 4% de ganhos realizando a otimização de hiperparâmetros, em alguns casos até 50%
- Escolher o melhor algoritmo e os melhores hiperparâmetros tem ganhos em média de 20%
- XGBoost, LightGBM, CatBoost, Random Forest e TypeFN
-- Obs: tem estratégia melhor que imitar o cérebro humano, por isso que os algoritmos hoje não fazem sentido

- Árvores de decisão
## Random Forest - Mais intuitivo
    - Árvores Independentes uma das outras
        - Paralelização
    - Simples e fáceis de interpretar
    - Uma árvore provavelmente vai sobreajustar seu modelo
    - Solução: Ensemble
    - Ensemble = vários algoritmos combinados (método que generaliza bem)
    - Utilização de Bagging (bootstrap agregation)
    - Bagging: selecionar amostras aleatórias dos dados de treino
        - Introduz variabilidade
    - Cada observação tem a mesma probabilidade de ser sorteada (com reposição)
        - Mesmo tamanho dos dados originais, então cada observação tem 63,2% de probabilidade de ser sorteada em cada rodada
    - Algumas árvores vão usar apenas uma parcela dos preditos (não todas as variáveis do treino)

- Bagging + Seleção de Preditores em cada nós = Random Forest

## GBDT (Gradiente Boosting)
    - Treina árvores sequenciais
    - O resultado predito será a soma das predições de todas as árvores
    - Treinamento iterativo: nasce uma árvore depois da outra com o objetivo de minimizar o erro

XGBoost - 2014 (árvores assimétricas)
LightGM - 2016 (árvores simétricas)
CatBoost - 2017 (árvores simétricas)

### Competições Kaggle

### Regressões Penalizadas
    - Adicionar hiperparâmetros regularizadores
        - L1 Lasso
        - L2 Ridge
### Redes Neurais
    - Inspiradas pelo funcionamento do cerébro
    - Não funciona muito bem para dados estruturados
    - Input Layer | Hidden Layer | Output
    - Apenas uma camada de transformação (1 Hidden Layer)

### Deep Learning
    - Mais de uma camada de transformação sequenciadas antes do output
    - Adaptação de Deep Learning para dados estruturados
        - Geralmente sai artigos sobre isso mais ainda não funciona muito bem (type fn foi o primeiro)

## Pontos de virada do ML
- 2012 -> Alex Net (uso de GPUs para treinar algoritmos de imagem, etc)
- 2016 -> Alpha Go com Aprendizado por Reforço
- 2022 Chat GPT

- Back Propagation:
    - Cada neuronio tem parametros aleatorios para transformar as variáveis
            - Primeira Predição
    - De trás pra frente reajusta os parametros dos neuronios para ajustar a predição e diminuir o erro daquela predição

- Gradient Descent:
    - No caminho de diminuir o erro de predição
    - Mudando os parametros na direção de diminuir o erro de predição

Back Propagation via Gradient Descent

## Playground TensorFlow - dar uma brincada

## TABPFN -> Performou melhor que o XGBoost e CatBoost

## Artigo: When Do Neural Nets Outperform Boosted Tress on Tabular Data?

## Dia 04 - Predição com Machine Learning

- O objetivo do estudo não é explicar a decisão do modelo mas isso é importante para a explicação do algoritmo (não pode ter associação)
- Aprendizado por transferência (readaptar algoritmos de acordo com a população)
- Importante pensar nas variáveis preditoras
- No treino vale tudo (criação de variáveis, etc)
- Padrão Ouro: Área embaixo da curva ROC

### TABPFN (Prier Feature Network) - Artigo da Nature
- Versão 1 (2023)
- Versão 2 (2025) 
- Poucas informações e alta dimensionalidade
    - O Algoritmo vem para resolver esse problema

- Foundation Model para dados tabulares
    - Geração de dados sintéticos
    - In-context learning (ICL) (Modelo aprende com o contexto, Transformers)
    - Redes Neurais Artificiais
    - TabPFN consegue modelar a incerteza sem custo adicional (Ensemble Bayesiano)
- Guardando Conhecimento entre Features
    - Na modelagem de linguagem, o significado de uma palavra é consistente entre diferentes documentos, porém, em conjuntos de dados tabulares, o mesmo valor pode ter significados fundamentalmente diferentes.
- Como capturar o conhecimento entre tabelas?
    - Redes Neurais
- Os dados sintéticos são essenciais para o modelo
    - Os dados são gerados atráves de modelos estruturais causais (SCMs)
- A geração dados incorpora estocasticidade
    - Baseado em DAGs: Complexidade é controlada atráves do número de Nós
        - Neural Network
        - Tree
        - Discretização
    - Amostra Inicial:
        - Gerados a partir de distribuição normal, uniforme e mista
    - Pós-processamento: aplica-se a distribuição kumaraswamy (beta)
    - Resultados da geração de dados sintéticos
        - O modelo consegue aprender comportamentos complexos
            - funções seno, modular, homocesticidade, heterocesticidade
    - Em problemas de classificação, TabPFN performa melhor
    - Ensemble do modelo TabPFN (PHE)
- Comunidade TabPFN
    - Discord
    - Git Hub

- É possível verificar as importâncias com o Shapley (ele é agnóstico a qualquer modelo)
- O modelo aceita no máximo 10 mil linhas e 500 colunas
    Travado na biblioteca do python

## Pré-Processamento de Dados
- 1. Preditores Plausíveis
    - Pré-selecionar variáveis que sejam preditoras plausíveis (bom senso do pesquisador)
        - Não precisam ser causais!!
    - Coincidências acontecem em análises de big data e pode ser que o algoritmo dê muita importância para associações espúrias

- 2. Cuidado com Data Leakage
- 3. Variáveis Colineares

## Seleção de Variáveis
    - Após treinamento do modelo fazer feature selection
 Artigo: Evaluation of variable selection methods for random forests and omics data sets
    - Importância de variáveis Random Forest
        - Embaralha os valores e faz a predição, calcula o erro para saber a importância
    - Eliminação Recursiva das Variáveis
        - Elimino e testo
        - Variável pouco importante na precisa de outras variáveis

## Boruta
    - Compara as importâncias das preditoras reais com "sombras"
    - A cada execução é gerada uma cópia de cada variável
    - Valores das sombras são permutações das variáveis originais
    - Random Forest é treinado com essa extensão dos dados
    - Comparar a importância de variáveis reais com o valor máximo das sombras
        - Variáveis só são relevantes se forem mais importantes que as permutadas
    - Repetir o processo várias vezes e transformar em uma distribuição binomial
    - Hit: quando a variável é mais importante que a sombra mais importante
    - Sombras e variáveis menos importantes são retiradas e o processo é repetido até haver uma classificação para cada variável

## Busca por Algoritmos Interpretáveis
    - Identificar presença de preditores indesejáveis
    - Auxiliar na decisão pelos profissionais
    - Garantir melhor robustez
    - Identificar preconceitos
    - Existem mais casos que você vai precisar esconder a explicação do algoritmo do que explicá-la
        - Manipular o sistema
    - Interpretação Intrinseca
        - Utilizar algoritmos interpretáveis (regressão linear, logística ou árvores simples de decisão)
    - Interpretação Extrínseca (Explicabilidade): utilizar técnas que permitem retirar interpretação de algoritmos complexos após o treinamento

## Artigo: Interpretable machine learning - a brief history, state of the art and challenges
    - Livro Genius Makers (Criadores de Gênios)
    - Regressão Linear e Árvores de Decisão são considerados modelos interpretáveis
        - Em cenários de alta dimensão eles perdem essa interpretabilidade
    - Rede neural convolucional profunda (CNN) - imagens que mapeiam os componentes
    - Random Forest - analisar a estrutura da árvore para quantificar importância das variáveis
    - Sensibilidade do modelo a perturbações
        - Explicações contrafactuais: cenários hipotéticos/filosofia
        - Shapley Values: colaboração/teoria dos jogos

## Shapley Values
    - SHAP (SHapley Additive exPlations)
    - Baseado na teoria dos jogos
        - O objetivo é identificar a contribuição individual de cada jogador
        - O valor de Shapley nos diz quanto cada variável muda a predição da predição média
        - O valor de Shapley é a contribuição média marginal de cada variável ao longo de todas as combinações possíveis das variáveis
        - Diferentes coalizões
    - Última coisa que se faz em uma análise de ML
        - Não é usado para tirar variável do modelo
    - Entender os erros do algoritmo (como ele chegou na decisão errada?)
    - Não coloquem os resultados do Shapley no resumo do artigo

### Dia 05 - Predição com Machine Learning
    - Transfer Learning (TL)
        - Transferência de conhecimento do domínio de origem para o domínio de destino
        - Objetivo: melhorar o desempenho do modelo
        - TL vs ML Tradicional: envolve vários domínios e tarefas, ao contrário do ML Tradicional que utiliza domínio único
    - O que transferir?
        - Conhecimento adquirido (modelo pré-treinado/pesos)
    - Como transferir?
        - Mais comuns: redes neurais (Deep Learning)
    - Quando transferir?
        - Disponibilidade dos dados
        - Similaridade dos outcomes
        - Recursos Computacionais
        - O modelo a ser transferido precisa de boa performance
        - Muito aplicado para imagens e NLP
    - IACOV-BR
        - Aprendizado por transferencia em árvores
            - Modelo pré-treinado na ORIGEM (melhor desempenho preditivo)
            - Dados (ALVO) 
                - Residuo 
                - Ajuste fino: árvores adicionadas para capturar padroes especificos de ALVO
            - Predição do ALVO

## Aprendizado Federado
    - Foco em privacidade
    - Dados não podem sair de certo ambiente
    - Sem transferência de dados do paciente | Transferência do Algoritmo
    - Treinamento em dispositivos remotos
    - Desafios: heterogeneidade e grande quantidade de dados
    - Dados locais
    - Modelo Global
    - Principal Objetivo: preservação de privacidade + aceitação de novas colaborações (sem perda de controle de dados)
    - Exemplo: Aprendizado Federado para predição da palavra seguinte em dispositivos móveis
    
































    

 


