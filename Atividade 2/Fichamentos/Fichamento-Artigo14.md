# Design pattern recognition: a study of large language models

Pandey, Sushant Kumar; Chand, Sivajeet; Horkoff, Jennifer; Staron, Miroslaw; Ochodek, Miroslaw; Durisic, Darko. "Design pattern recognition: a study of large language models," in Empirical Software Engineering, vol. 30, no. 69, 2025. doi: [10.1007/s10664-025-10625-1](https://doi.org/10.1007/s10664-025-10625-1)

## 1. Fichamento de Conteúdo

Este artigo apresenta um estudo aprofundado sobre a capacidade de Modelos de Linguagem de Grande Porte (LLMs) para realizar o Reconhecimento de Padrões de Projeto (DPR) em código-fonte Java. O objetivo principal é avaliar a eficácia de diferentes LLMs na captura de informações semânticas e sintáticas para identificar padrões, visando facilitar a criação de ferramentas de DPR mais eficientes. A metodologia envolveu o uso de cinco LLMs de última geração (Code2Vec, CodeBERT, CodeGPT, CodeT5 e RoBERTa) para gerar *embeddings* (representações vetoriais) de projetos Java do repositório P-MARt. Esses *embeddings* foram então utilizados por um classificador k-NN (k-Nearest Neighbors) para prever a presença de cinco padrões de projeto criacionais do "Gang of Four" (GoF). Os resultados mostraram que o **RoBERTa** foi o modelo com melhor desempenho, alcançando um F1-score médio de 0.91, seguido pelo CodeGPT (0.79) e CodeBERT (0.77). O estudo conclui que a performance dos LLMs é comparável aos métodos estado-da-arte, mas com a vantagem significativa de exigir menos esforço, como a criação de regras específicas para cada padrão ou pré-treinamento extensivo. Fatores como tamanho do arquivo, complexidade da implementação e uso de palavras-chave foram identificados como influenciadores da precisão das previsões, destacando o potencial dos LLMs para avançar as práticas de engenharia de software.

## 2. Fichamento Bibliográfico

* **Reconhecimento de Padrões de Projeto (DPR)**: É a tarefa de identificar automaticamente a implementação de padrões de projeto (soluções recorrentes para problemas comuns de design, como Singleton, Factory, etc.) no código-fonte. A automação do DPR é crucial para a compreensão, manutenção e melhoria da qualidade de sistemas de software complexos. Métodos tradicionais frequentemente dependem de regras manuais, análise estática que exige compilação (para gerar ASTs) ou técnicas de Machine Learning que necessitam de grandes volumes de dados rotulados.

* **Abordagem Proposta (LLM + k-NN)**: A metodologia central do estudo utiliza LLMs para extrair a essência semântica e estrutural do código e, em seguida, um classificador simples para a predição. O processo consiste em:
    1.  **Geração de Embeddings**: Um trecho de código Java é fornecido a um LLM, que o converte em um vetor numérico de alta dimensão (*embedding*). Esse vetor captura o "significado" do código.
    2.  **Classificação k-NN**: O *embedding* gerado é classificado usando o algoritmo **k-Nearest Neighbors (k-NN)**. O k-NN prevê o padrão de um novo programa medindo a distância Euclidiana entre seu *embedding* e os *embeddings* de exemplos já conhecidos (rotulados). Se os vizinhos mais próximos forem majoritariamente do padrão "Singleton", por exemplo, o novo programa é classificado como tal. Essa abordagem dispensa a necessidade de regras complexas e pré-treinamento específico para a tarefa.

* **Modelos de Linguagem (LLMs) Avaliados**: O estudo comparou o desempenho de cinco LLMs proeminentes:
    * **Code2Vec**: Um modelo que representa o código com base em caminhos extraídos da Árvore de Sintaxe Abstrata (AST). Foi o único modelo que exigiu pré-treinamento específico.
    * **CodeBERT, CodeGPT, CodeT5**: Modelos baseados na arquitetura Transformer, pré-treinados em grandes volumes de código e texto, projetados para tarefas de engenharia de software.
    * **RoBERTa**: Uma versão otimizada do BERT, treinada em uma vasta quantidade de texto em linguagem natural. Surpreendentemente, foi o modelo com o melhor desempenho, mesmo não sendo explicitamente projetado para código.

* **Dataset e Padrões Selecionados**: A pesquisa utilizou projetos do repositório **P-MARt**, uma coleção de projetos Java curados e amplamente aceita como benchmark para estudos de DPR. O foco foi em cinco **padrões de projeto criacionais**: Singleton, Builder, Prototype, Abstract Factory e Factory Method. Esses padrões foram escolhidos por sua popularidade, diversidade de complexidade e impacto positivo na qualidade do software.

* **Fatores de Influência na Classificação**: A análise dos resultados corretos e incorretos revelou fatores que impactam a precisão do DPR com LLMs:
    * **Implementação Padrão**: Programas que seguiam de perto a estrutura canônica de um padrão eram mais facilmente classificados.
    * **Uso de Palavras-chave**: A presença de termos explícitos (como "Singleton" no nome da classe ou "clone" em um método) facilitava a identificação.
    * **Tamanho e Complexidade do Arquivo**: Arquivos menores e menos complexos tendiam a ser classificados com mais precisão, pois a geração de um *embedding* médio para arquivos grandes pode resultar em perda de informação contextual.
    * **Convenções de Nomenclatura**: O uso de nomes de métodos e classes que seguem as convenções do padrão (ex: `createDefaultResponder()` em um Factory Method) contribuía para uma classificação correta.

## 3. Fichamento de Citações

* _"This study aims to evaluate the abilities of Large Language Models (LLMs) in identifying DPs in source code, which can facilitate the development of better Design Pattern Recognition (DPR) tools."_
* _"ROBERTa is the top performer, followed by CodeGPT and CodeBERT, which showed mean F1 Scores of 0.91, 0.79, and 0.77, respectively."_
* _"The performance of LLMs in DPR is comparable to existing state-of-the-art methods but with less effort in identifying pattern-specific rules and pre-training."_
* _"This is as ROBERTa is not explicitly intended to understand source code, but language in general."_
* _"We found a few factors affecting the prediction of DPs: file size, how the patterns are implemented (i.e., whether they use common conventions), the size of the files, use of keywords, and file complexity."_
* _"Overall, based on our results, we recommend ROBERTa and CodeGPT as the first choices for pre-training for domain-specific DPR tasks."_
