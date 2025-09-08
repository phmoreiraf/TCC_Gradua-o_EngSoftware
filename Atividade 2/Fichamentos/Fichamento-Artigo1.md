# Design pattern recognition: a study of large language models

## Referência
Pandey, S. K.; Chand, S.; Horkoff, J.; Staron, M.; Ochodek, M.; Durisic, D. *Design pattern recognition: a study of large language models*. Empirical Software Engineering, 30:69, 2025. [https://doi.org/10.1007/s10664-025-10625-1](https://doi.org/10.1007/s10664-025-10625-1)

## 1. Fichamento de Conteúdo

O artigo investiga a capacidade de Modelos de Linguagem Grandes (LLMs) em reconhecer padrões de projeto (GoF) diretamente do código-fonte, propondo uma abordagem que dispensa a criação manual de regras específicas por padrão ou a análise de Árvores de Sintaxe Abstrata (AST). Os autores comparam cinco LLMs proeminentes (Code2Vec, CodeBERT, CodeGPT, CodeT5 e RoBERTa) para a tarefa de Reconhecimento de Padrões de Projeto (DPR). A metodologia consiste em gerar representações vetoriais (*embeddings*) do código Java e, em seguida, utilizar um classificador k-Nearest Neighbors (k-NN) para prever a presença de cinco padrões criacionais. A avaliação, realizada sobre o repositório P-MARt, demonstra que a abordagem atinge um desempenho competitivo com métodos estado-da-arte, mas com um esforço significativamente menor em pré-processamento e engenharia de características. Os resultados destacam **RoBERTa** como o modelo de melhor desempenho, com um F1-score médio de 0.91, e revelam que os LLMs são capazes de capturar informações semânticas e sintáticas relevantes para a tarefa. O estudo conclui que LLMs são uma via promissora para a criação de ferramentas DPR mais eficientes e flexíveis, embora analise fatores que ainda influenciam a consistência das predições, como a complexidade da implementação do padrão e o tamanho do arquivo.

## 2. Fichamento Bibliográfico

* **Principais Conceitos:**
    * **Reconhecimento de Padrões de Projeto (Design Pattern Recognition - DPR):** É o processo de identificar automaticamente instâncias de padrões de projeto (ex: Singleton, Factory Method) em um código-fonte existente. O DPR é útil para acelerar a compreensão do código, facilitar a manutenção e melhorar a qualidade geral do software.
    * **Embeddings de Código:** São representações vetoriais de trechos de código geradas por LLMs. Cada vetor captura informações semânticas, sintáticas e contextuais do código, permitindo que algoritmos de machine learning comparem e classifiquem programas com base em sua similaridade funcional e estrutural.
    * **Fine-tuning (Ajuste Fino):** Processo de treinar um LLM pré-treinado em um conjunto de dados específico para uma tarefa particular. Neste estudo, o ajuste fino é realizado de forma implícita, usando os *embeddings* gerados pelo LLM como entrada para um modelo específico da tarefa (k-NN), adaptando o conhecimento geral do LLM para a tarefa de DPR.

* **Ferramentas, Bibliotecas e Pacotes:**
    * **Modelos de Linguagem Grandes (LLMs):** O estudo avalia cinco modelos de última geração, todos baseados em arquitetura Transformer, com exceção do Code2Vec:
        * **Code2Vec:** Captura a estrutura do código representando caminhos na Árvore de Sintaxe Abstrata (AST).
        * **CodeBERT:** Desenvolvido pela Microsoft, é um modelo BERT pré-treinado em código e linguagem natural.
        * **CodeGPT:** Um modelo generativo baseado na arquitetura GPT, treinado para tarefas de código.
        * **CodeT5:** Um modelo encoder-decoder que trata todas as tarefas como "texto-para-texto", treinado em dados multimodais (código e texto).
        * **RoBERTa:** Uma versão otimizada do BERT, conhecida por sua robustez, embora não seja específica para código.
    * **Repositório P-MARt:** Um repositório curado e amplamente utilizado na comunidade de pesquisa, contendo projetos Java com anotações de instâncias de padrões de projeto GoF. Serviu como a "verdade fundamental" (*ground truth*) para treinar e avaliar os modelos.

* **Teorias e Métodos:**
    * **Classificação baseada em Embeddings e k-NN:** A metodologia central do estudo é um processo de duas etapas:
        1.  **Extração de Embeddings:** O código-fonte de um arquivo Java é fornecido a um LLM, que o converte em um vetor numérico de alta dimensão (*embedding*).
        2.  **Classificação com k-NN:** O vetor de *embedding* é então passado para um classificador **k-Nearest Neighbors (k-NN)**. Este algoritmo classifica um novo exemplo com base na classe majoritária de seus 'k' vizinhos mais próximos no espaço vetorial. A proximidade é medida usando a **distância euclidiana**. A escolha do k-NN é justificada por sua simplicidade e bom desempenho em espaços de alta dimensão.
    * **Avaliação Empírica:** O desempenho dos modelos foi avaliado usando métricas padrão de classificação: **Precisão (Precision)**, **Revocação (Recall)** e **F1-Score**. Os resultados foram comparados com cinco métodos de DPR estado-da-arte que utilizam técnicas baseadas em regras ou grafos (ex: SparT, DPD, GEML). Para verificar a significância estatística das diferenças de desempenho, foi realizado o **teste t pareado (paired t-test)**.

## 3. Fichamento de Citações

* _"This study aims to evaluate the abilities of Large Language Models (LLMs) in identifying DPs in source code, which can facilitate the development of better Design Pattern Recognition (DPR) tools."_
* _"We compare the effectiveness of different LLMs in capturing semantic information relevant to the DPR task."_
* _"State-of-the-art language models, including Code2Vec, CodeBERT, CodeGPT, CodeT5, and RoBERTa, are used to generate embeddings from source code. These embeddings are then used for DPR via a k-nearest neighbors prediction."_
* _"RoBERTa is the top performer, followed by CodeGPT and CodeBERT, which showed mean F1 Scores of 0.91, 0.79, and 0.77, respectively."_
* _"The performance of LLMs in DPR is comparable to existing state-of-the-art methods but with less effort in identifying pattern-specific rules and pre-training."_
* _"The study found that along with semantics, syntactic information, the context of implementation, keywords, and implementation style are the factors contributing to DPR by LLMs."_
