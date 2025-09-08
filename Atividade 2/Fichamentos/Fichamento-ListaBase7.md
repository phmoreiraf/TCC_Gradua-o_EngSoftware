# Completeness of composite refactorings for smell removal

## Referência

Bibiano, A. C. *Completeness of composite refactorings for smell removal*. In: ICSE ’22 Companion, 2022. [https://doi.org/10.1145/3510454.3517060](https://doi.org/10.1145/3510454.3517060)

## 1. Fichamento de Conteúdo

Este artigo de pesquisa de doutorado examina a eficácia de **refatorações compostas** — sequências de múltiplas refatorações inter-relacionadas — na remoção de *code smells*. O trabalho parte da premissa de que uma única refatoração raramente é suficiente para eliminar completamente um *smell*. A pesquisa investiga a **completude** dessas composições, ou seja, se elas de fato removem o *smell* alvo, e analisa os efeitos colaterais da (in)completude na qualidade estrutural geral do software. Utilizando uma abordagem empírica, a autora minerou 618 refatorações compostas em 20 projetos de software. Os resultados preliminares revelam duas questões críticas: primeiro, a maioria (58%) das composições **incompletas** não chega a degradar a qualidade interna, mas também não a melhora; segundo, muitas composições **completas** (cerca de 36%) introduzem novos *smells* como efeito colateral, um risco não alertado pela literatura. O objetivo final da pesquisa é propor um catálogo de recomendações empiricamente fundamentado para ajudar os desenvolvedores a aplicarem refatorações compostas de forma eficaz, evitando a degradação da qualidade do código.

## 2. Fichamento Bibliográfico

* **Principais Conceitos:**
    * **Refatoração Composta (Composite Refactoring):** Uma sequência de duas ou mais refatorações únicas e inter-relacionadas, aplicadas com o objetivo de remover um ou mais *code smells*. São necessárias porque uma única refatoração raramente é suficiente para eliminar um *smell* por completo.
    * **Completude da Composição (Composite Completeness):** Uma característica que descreve se uma refatoração composta atingiu seu objetivo de remover completamente um *smell* alvo.
    * **Composição Completa (Complete Composite):** Uma refatoração composta que remove com sucesso pelo menos um *code smell* alvo. No entanto, o estudo mostra que mesmo as completas podem introduzir outros *smells*.
    * **Composição Incompleta (Incomplete Composite):** Uma refatoração composta que falha em remover o *smell* alvo, deixando-o persistir no código. O estudo descobriu que 58% dessas composições não alteram a qualidade interna das classes afetadas.

* **Ferramentas e Bibliotecas:**
    * **RefactoringMiner 2.0:** Ferramenta utilizada para coletar as operações de refatoração do histórico de commits dos projetos. É destacada por sua alta precisão na detecção. Mais informações: [https://github.com/tsantalis/RefactoringMiner](https://github.com/tsantalis/RefactoringMiner).
    * **Organic:** Ferramenta utilizada para detectar e coletar instâncias de *code smells* nos projetos de software. Também é citada por sua alta precisão. Mais informações: [https://github.com/organic-tool/organic](https://github.com/organic-tool/organic).

* **Teorias e Métodos:**
    * **Estudo Quantitativo (Mineração de Repositórios):** A metodologia central é a mineração de repositórios de software para construir um banco de dados de refatorações compostas. Foram analisados 20 projetos Java de código aberto, selecionados com base em critérios específicos.
    * **Coleta e Classificação de Dados:** O processo envolveu usar o RefactoringMiner para identificar refatorações e o Organic para identificar *smells* antes e depois das refatorações. Um *script* foi desenvolvido para classificar as composições como (in)completas, verificando se um *smell* alvo foi removido após a aplicação da sequência de refatorações.
    * **Análise de Qualidade Interna:** Para avaliar o impacto das refatorações compostas, foram utilizadas 10 métricas de código para medir quatro atributos de qualidade interna: **coesão, acoplamento, tamanho e complexidade**. Esta análise permitiu verificar se as composições melhoravam, degradavam ou mantinham a qualidade estrutural das classes afetadas.

## 3. Fichamento de Citações

* _"Code smells are problems in the internal structural quality. Refactoring is a technique commonly used to remove code smells."_
* _"A single refactoring rarely suffices to assist developers in achieving a full removal of a code smell."_
* _"This doctoral research investigates the effect of composite (in)completeness on structural quality and proposes a catalog with composite recommendations."_
* _"We found that 58% of incomplete composites did not change the internal structural quality, and 64% of complete composites are formed by refactoring types that were not actually previously recommended in the literature or elsewhere."_
* _"Our results present that about 36% of complete composites formed by Extract Methods introduced Feature Envies and Intensive Couplings."_
* _"This lack of empirical knowledge makes it difficult to assist developers with recommendations of how to successfully apply a composite without introducing any harm."_
