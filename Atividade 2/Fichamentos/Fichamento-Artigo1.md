# Design pattern recognition: a study of large language models

## Referência
Pandey, S. K.; Chand, S.; Horkoff, J.; Staron, M.; Ochodek, M.; Durisic, D. *Design pattern recognition: a study of large language models*. Empirical Software Engineering, 30:69, 2025. [https://doi.org/10.1007/s10664-025-10625-1](https://doi.org/10.1007/s10664-025-10625-1)

## 1. Fichamento de Conteúdo

O artigo investiga se modelos de linguagem (LLMs) conseguem reconhecer padrões de projeto diretamente do código, sem regras artesanais por padrão. Os autores comparam Code2Vec, CodeBERT, CodeGPT, CodeT5 e RoBERTa, gerando embeddings e usando k-NN para prever a presença de padrões em projetos Java do P-MARt. A avaliação usa precisão, revocação e F1, mostrando desempenho competitivo com abordagens de estado-da-arte baseadas em regras/AST, porém com menos engenharia. Os resultados indicam que LLMs capturam pistas sintáticas e semânticas úteis para DPR, e que RoBERTa apresenta o melhor F1 médio entre os avaliados. O estudo também discute fatores que afetam a predição no nível de arquivo e programa, além de limitações de generalização para outros domínios/linguagens. No contexto do seu TCC, o trabalho é um excelente baseline para detecção automática de Factory, Strategy, Observer e Decorator em projetos com Clean Architecture, permitindo medir prevalência dos padrões e relacioná-la com métricas de clareza/evolução. Em suma, o artigo demonstra viabilidade prática de usar LLMs para apoiar compreensão e auditoria de design em bases reais.

## 2. Fichamento Bibliográfico

* Objetivo: avaliar a capacidade de LLMs em DPR e comparar modelos quanto à efetividade para capturar informação semântica relevante (Abstract).
* Método: embeddings com LLMs (Code2Vec, CodeBERT, CodeGPT, CodeT5, RoBERTa) + k-NN; métricas: Precisão/Revocação/F1 (Methods/Abstract).
* Base: repositório P-MARt com projetos Java anotados com padrões GoF (Methods/Abstract).
* Achado: desempenho comparável ao SOTA e menor esforço por evitar regras específicas por padrão (Conclusion).

## 3. Fichamento de Citações

* [cite\_start]*"This study aims to evaluate the abilities of Large Language Models (LLMs) in identifying DPs in source code, which can facilitate the development of better Design Pattern Recognition (DPR) tools."* [cite: 585]
  * [cite\_start]*"We compare the effectiveness of different LLMs in capturing semantic information relevant to the DPR task."* [cite: 586]
  * [cite\_start]*"State-of-the-art language models, including Code2Vec, CodeBERT, CodeGPT, CodeT5, and RoBERTa, are used to generate embeddings from source code. These embeddings are then used for DPR via a k-nearest neighbors prediction."* [cite: 588, 589]
  * [cite\_start]*"RoBERTa is the top performer, followed by CodeGPT and CodeBERT, which showed mean F1 Scores of 0.91, 0.79, and 0.77, respectively."* [cite: 591]
  * [cite\_start]*"The performance of LLMs in DPR is comparable to existing state-of-the-art methods but with less effort in identifying pattern-specific rules and pre-training."* [cite: 593]
  * [cite\_start]*"The study found that along with semantics, syntactic information, the context of implementation, keywords, and implementation style are the factors contributing to DPR by LLMs."* [cite: 670]
