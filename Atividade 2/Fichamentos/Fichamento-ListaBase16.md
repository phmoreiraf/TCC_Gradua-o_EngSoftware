# Evaluating Atoms of Confusion in the Context of Code Reviews

## Referência
Bogachenkova, V.; Nguyen, L.; Ebert, F.; Serebrenik, A.; Castor, F. *Evaluating Atoms of Confusion in the Context of Code Reviews*. In: 2022 IEEE International Conference on Software Maintenance and Evolution (ICSME), 2022, pp. 404–408. [https://doi.org/10.1109/ICSME55016.2022.00048](https://doi.org/10.1109/ICSME55016.2022.00048)

## 1. Fichamento de Conteúdo

Este artigo de resultados emergentes investiga se **átomos de confusão** pequenos padrões sintáticos de código conhecidos por induzir erros em ambientes de laboratório estão associados à confusão real manifestada por desenvolvedores durante *code reviews*. Além disso, o trabalho explora como esses átomos evoluem ao longo de *pull requests* (PRs), questionando se são removidos como parte do processo de melhoria da qualidade do código. Por meio de um **estudo de caso exploratório** em dois grandes repositórios Java, os autores combinam a detecção automática de átomos com a análise manual de comentários de *review*. Contrariando a expectativa inicial, a análise estatística **não encontrou uma relação significativa** entre a presença de átomos de confusão no código e a ocorrência de comentários que expressam confusão por parte dos revisores. Adicionalmente, o estudo revela que os átomos tendem a **não** ser removidos durante os PRs, sugerindo que eles persistem no código-fonte. O trabalho conclui formulando hipóteses para investigações futuras, como a possibilidade de que desenvolvedores experientes não se confundam com esses micro-padrões, e reforça que a compreensão da clareza do código em revisões pode depender mais de fatores de design e arquitetura do que de padrões sintáticos isolados.

## 2. Fichamento Bibliográfico

* **Principais Conceitos:**
    * **Átomos de Confusão (Atoms of Confusion):** São definidos como pequenos trechos de código que seguem um padrão conhecido por levar à confusão ou a mal-entendidos entre desenvolvedores, mesmo havendo alternativas funcionalmente equivalentes e menos confusas. Um exemplo clássico é o uso de pós-incremento em uma mesma declaração de atribuição, como `V1 = V2++;`, que poderia ser reescrito de forma mais clara em duas linhas: `V1 = V2; V2 = V2 + 1;`. Esses padrões foram originalmente identificados em estudos de laboratório, frequentemente com estudantes.
    * **Confusão em *Code Reviews*:** Refere-se a qualquer situação durante uma revisão de código em que o revisor expressa incerteza ou incapacidade de entender algo sobre o código proposto. Neste estudo, ela é identificada através da análise manual de comentários embutidos (*inline comments*) nos *pull requests*, buscando por expressões de dúvida ou dificuldade de compreensão.

* **Ferramentas e Bibliotecas:**
    * **Detector de Átomos de Confusão:** Para a detecção automática dos átomos de confusão em código Java, o estudo utilizou uma ferramenta baseada no trabalho de Langhout e Aniche. O repositório da ferramenta, desenvolvido pelo SERG-Delft, está disponível no GitHub: [https://github.com/SERG-Delft/atoms-of-confusion-detector](https://github.com/SERG-Delft/atoms-of-confusion-detector).

* **Teorias e Métodos:**
    * **Estudo de Caso Exploratório:** O método de pesquisa empregado foi um estudo de caso exploratório, adequado para investigar fenômenos pouco compreendidos e gerar hipóteses para pesquisas futuras. A pesquisa foi dividida em duas partes, cada uma abordando uma questão de pesquisa (RQ).
    * **Análise para a RQ1 (Relação entre átomos e confusão):** Foi realizada uma análise em uma amostra aleatória de 368 PRs do repositório `openhab-addons`. A presença de átomos foi detectada automaticamente, enquanto a confusão foi identificada por meio de uma análise manual e cruzada de comentários por dois pesquisadores. Para testar a associação entre as duas variáveis categóricas (presença/ausência de átomos vs. presença/ausência de confusão), foram utilizados os testes estatísticos **Qui-quadrado (Chi-squared)** e o **Teste Exato de Fisher**.
    * **Análise para a RQ2 (Evolução dos átomos nos PRs):** Foi analisada a totalidade dos PRs fechados de dois repositórios, `openhab-addons` e `confluentinc-ksql`. A ferramenta de detecção foi aplicada ao código antes e depois de cada PR para verificar se o número de átomos aumentou, diminuiu ou permaneceu o mesmo. Os resultados foram organizados em matrizes de contingência e analisados estatisticamente para identificar tendências.

## 3. Fichamento de Citações

* _"In this emerging results paper, we report an exploratory case study to provide a deeper understanding of atoms of confusion…"_
* _"…statistical analysis did not show any relationship between atoms of confusion and presence of confusion comments in code reviews."_
* _"Additionally, we found evidence that atoms of confusion are mostly not being removed in pull requests."_
* _"The results suggest, contrary to our intuition, there is no relation between atoms of confusion and confusion present in code review discussions."_
* **H1. Atoms of confusion are not perceived as confusing for experienced developers.** _"Future research should try to confirm whether the atoms of confusion, which so far have been confirmed with students, in different contexts, are indeed causing misunderstanding for experienced developers."_
* _"Based on the results, we formulate hypotheses … that should be confirmed or rejected by future studies."_
