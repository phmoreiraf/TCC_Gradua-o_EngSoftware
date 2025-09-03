# Towards Predicting Architectural Design Patterns: A Machine Learning Approach

Komolov, Sirojiddin; Dlamini, Gcinizwe; Megha, Swati; Mazzara, Manuel. "Towards Predicting Architectural Design Patterns: A Machine Learning Approach," in Computers, vol. 11, no. 10, p. 151, Oct. 2022. doi: [10.3390/computers11100151](https://doi.org/10.3390/computers11100151)

## 1. Fichamento de Conteúdo

Este artigo apresenta uma abordagem baseada em Machine Learning (ML) para prever padrões de projeto arquiteturais, especificamente **Model-View-Presenter (MVP)** e **Model-View-ViewModel (MVVM)**, a partir de métricas de código-fonte. O estudo foi motivado pela falta de datasets de benchmark e de abordagens de ML mais precisas para a detecção de arquitetura de software. Para resolver isso, os autores criaram e disponibilizaram um novo e robusto dataset, contendo **5.973 projetos Java de código aberto** recuperados do GitHub, todos rotulados como MVP ou MVVM. Utilizando a ferramenta CK para extrair métricas de código, eles treinaram nove algoritmos de ML populares, incluindo Regressão Logística, SVM, Redes Neurais e CatBoost. Os resultados foram muito positivos, com os modelos de melhor desempenho (SVM e Redes Neurais) alcançando **83% de precisão, recall, acurácia e F1-score**. A abordagem proposta superou significativamente os trabalhos estado-da-arte existentes. Além disso, o estudo utilizou modelos de ML interpretáveis para identificar as métricas de código mais importantes para a predição, destacando o "número de métodos default em uma classe" e o "número de retornos em um método" como os indicadores mais fortes.

---

## 2. Fichamento Bibliográfico

* **Padrões Arquiteturais (MVP e MVVM)**: O estudo foca em dois padrões arquiteturais comuns no desenvolvimento de aplicações com interface de usuário, especialmente em Android.
    * **MVP (Model-View-Presenter)**: Derivado do padrão MVC, o MVP separa as responsabilidades em três componentes. O **Model** contém os dados e a lógica de negócios. A **View** é uma interface passiva que exibe os dados e delega os eventos do usuário ao Presenter. O **Presenter** atua como um intermediário, buscando dados do Model e atualizando a View.
    * **MVVM (Model-View-ViewModel)**: Semelhante ao MVP, mas com um acoplamento ainda menor entre a View e a lógica de apresentação. O **ViewModel** expõe os dados do **Model** para a **View** através de *data bindings*, que atualizam a UI automaticamente quando o estado dos dados muda.

* **Metodologia (Extração de Métricas + Classificação ML)**: A abordagem do artigo segue um pipeline bem definido para a predição de padrões:
    1.  **Criação do Dataset**: Extração de 5.973 repositórios Java do GitHub usando a API de busca com as palavras-chave "Android MVP" e "Android MVVM". Este dataset é uma das principais contribuições do trabalho.
    2.  **Extração de Features**: Uso da ferramenta de código aberto **CK** para calcular um conjunto de métricas de código estático para cada projeto, como métricas de coesão, acoplamento, complexidade e contagem de elementos (métodos, classes, etc.).
    3.  **Treinamento e Avaliação**: Aplicação de **nove algoritmos de ML** sobre o dataset de métricas para treinar modelos capazes de classificar um projeto como MVP ou MVVM. O desempenho foi medido com precisão, recall, F1-score, acurácia e validado com validação cruzada (k-fold com k=5).

* **Métricas de Código Mais Relevantes**: Utilizando modelos interpretáveis como Random Forest e CatBoost, o estudo identificou as métricas de código que mais contribuem para a distinção entre MVP e MVVM. As duas mais importantes foram:
    * **`class_defaultMethodsQty`**: O número de métodos com modificador de acesso *default* (nível de pacote) em uma classe.
    * **`method_returnsQty`**: O número de declarações de retorno (`return`) em um método.
    Essas métricas servem como fortes indicadores da estrutura implementada, alinhando-se com a teoria de implementação de ambos os padrões em Java.

* **Comparação com o Estado-da-Arte**: A performance do método proposto foi comparada com dois trabalhos recentes e proeminentes na área (referidos como "Rimaz" e "Coach"). O modelo dos autores alcançou um **F1-score de 83%** para ambos os padrões (MVP e MVVM), superando significativamente os resultados anteriores, que, por exemplo, no trabalho "Coach", foram de 56% para MVP e 67% para MVVM.

---

## 3. Fichamento de Citações

* _"This paper presents an ML-based approach for software architecture detection, namely, MVP (Model-View-Presenter) and MVVM (Model-View-ViewModel)."_
* _"Firstly, we present a labeled dataset that consists of 5973 data points retrieved from GitHub."_
* _"Using precision, recall, accuracy, and F1 score, the outstanding ML model performance is 83%, 83%, 83%, and 83%, respectively."_
* _"Our approach outperforms when compared with the state-of-the-art."_
* _"Based on the results presented in Table 2, it is evident that the number of class default Methods (class\_defMethodsQty) and number of returns in method (method\_returnsQty) are the most important metrics."_
* _"This work shows the feasibility of using a machine-learning-based approach for detecting architectural design patterns starting from source code metrics."_
