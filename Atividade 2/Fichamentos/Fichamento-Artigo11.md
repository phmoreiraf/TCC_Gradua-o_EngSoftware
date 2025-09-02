# Towards Predicting Architectural Design Patterns: A Machine Learning Approach

Schindler, Patrick; Rausch, Andreas. "Towards Predicting Architectural Design Patterns: A Machine Learning Approach," in *ResearchGate preprint*, Oct. 2024. [Link](https://www.researchgate.net/publication/364321415_Towards_Predicting_Architectural_Design_Patterns_A_Machine_Learning_Approach)

## 1. Fichamento de Conteúdo

[cite_start]Este artigo apresenta uma abordagem baseada em Machine Learning (ML) para prever padrões de projeto arquiteturais, especificamente **Model-View-Presenter (MVP)** e **Model-View-ViewModel (MVVM)**, a partir de métricas de código-fonte[cite: 2757]. [cite_start]O estudo foi motivado pela falta de datasets de benchmark e de abordagens de ML mais precisas para a detecção de arquitetura de software[cite: 2756]. [cite_start]Para resolver isso, os autores criaram e disponibilizaram um novo e robusto dataset, contendo **5.973 projetos Java de código aberto** recuperados do GitHub, todos rotulados como MVP ou MVVM[cite: 2758, 2820]. [cite_start]Utilizando a ferramenta CK para extrair métricas de código, eles treinaram nove algoritmos de ML populares, incluindo Regressão Logística, SVM, Redes Neurais e CatBoost[cite: 2759, 2949, 2985]. [cite_start]Os resultados foram muito positivos, com os modelos de melhor desempenho (SVM e Redes Neurais) alcançando **83% de precisão, recall, acurácia e F1-score**[cite: 2760, 3161]. [cite_start]A abordagem proposta superou significativamente os trabalhos estado-da-arte existentes[cite: 2761, 3090]. [cite_start]Além disso, o estudo utilizou modelos de ML interpretáveis para identificar as métricas de código mais importantes para a predição, destacando o "número de métodos default em uma classe" e o "número de retornos em um método" como os indicadores mais fortes[cite: 3052].

## 2. Fichamento Bibliográfico

* **Padrões Arquiteturais (MVP e MVVM)**: O estudo foca em dois padrões arquiteturais comuns no desenvolvimento de aplicações com interface de usuário, especialmente em Android.
    * **MVP (Model-View-Presenter)**: Derivado do padrão MVC, o MVP separa as responsabilidades em três componentes. [cite_start]O **Model** contém os dados e a lógica de negócios[cite: 2835]. [cite_start]A **View** é uma interface passiva que exibe os dados e delega os eventos do usuário ao Presenter[cite: 2836]. [cite_start]O **Presenter** atua como um intermediário, buscando dados do Model e atualizando a View[cite: 2837].
    * **MVVM (Model-View-ViewModel)**: Semelhante ao MVP, mas com um acoplamento ainda menor entre a View e a lógica de apresentação. [cite_start]O **ViewModel** expõe os dados do **Model** para a **View** através de *data bindings*, que atualizam a UI automaticamente quando o estado dos dados muda[cite: 2854, 2855].

* **Metodologia (Extração de Métricas + Classificação ML)**: A abordagem do artigo segue um pipeline bem definido para a predição de padrões:
    1.  [cite_start]**Criação do Dataset**: Extração de 5.973 repositórios Java do GitHub usando a API de busca com as palavras-chave "Android MVP" e "Android MVVM"[cite: 2758, 2934, 2946]. [cite_start]Este dataset é uma das principais contribuições do trabalho[cite: 2820].
    2.  [cite_start]**Extração de Features**: Uso da ferramenta de código aberto **CK** para calcular um conjunto de métricas de código estático para cada projeto, como métricas de coesão, acoplamento, complexidade e contagem de elementos (métodos, classes, etc.)[cite: 2949].
    3.  [cite_start]**Treinamento e Avaliação**: Aplicação de **nove algoritmos de ML** sobre o dataset de métricas para treinar modelos capazes de classificar um projeto como MVP ou MVVM[cite: 2759]. [cite_start]O desempenho foi medido com precisão, recall, F1-score, acurácia e validado com validação cruzada (k-fold com k=5)[cite: 2760, 2761].

* [cite_start]**Métricas de Código Mais Relevantes**: Utilizando modelos interpretáveis como Random Forest e CatBoost, o estudo identificou as métricas de código que mais contribuem para a distinção entre MVP e MVVM[cite: 3050]. As duas mais importantes foram:
    * [cite_start]**`class_defaultMethodsQty`**: O número de métodos com modificador de acesso *default* (nível de pacote) em uma classe[cite: 3052].
    * [cite_start]**`method_returnsQty`**: O número de declarações de retorno (`return`) em um método[cite: 3052].
    [cite_start]Essas métricas servem como fortes indicadores da estrutura implementada, alinhando-se com a teoria de implementação de ambos os padrões em Java[cite: 3053].

* [cite_start]**Comparação com o Estado-da-Arte**: A performance do método proposto foi comparada com dois trabalhos recentes e proeminentes na área (referidos como "Rimaz" e "Coach")[cite: 3089]. [cite_start]O modelo dos autores alcançou um **F1-score de 83%** para ambos os padrões (MVP e MVVM), superando significativamente os resultados anteriores, que, por exemplo, no trabalho "Coach", foram de 56% para MVP e 67% para MVVM[cite: 3090, 3105].

## 3. Fichamento de Citações

* [cite_start]_"This paper presents an ML-based approach for software architecture detection, namely, MVP (Model-View-Presenter) and MVVM (Model-View-ViewModel)."_ [cite: 2757]
* [cite_start]_"Firstly, we present a labeled dataset that consists of 5973 data points retrieved from GitHub."_ [cite: 2758]
* [cite_start]_"Using precision, recall, accuracy, and F1 score, the outstanding ML model performance is 83%, 83%, 83%, and 83%, respectively."_ [cite: 2760]
* [cite_start]_"Our approach outperforms when compared with the state-of-the-art."_ [cite: 2761]
* [cite_start]_"Based on the results presented in Table 2, it is evident that the number of class default Methods (class_defMethodsQty) and number of returns in method (method_returnsQty) are the most important metrics."_ [cite: 3052]
* [cite_start]_"This work shows the feasibility of using a machine-learning-based approach for detecting architectural design patterns starting from source code metrics."_ [cite: 3064]
