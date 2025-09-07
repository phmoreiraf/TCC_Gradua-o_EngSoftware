# Evaluating Atoms of Confusion in the Context of Code Reviews

## Referência
Bogachenkova, V.; Nguyen, L.; Ebert, F.; Serebrenik, A.; Castor, F. *Evaluating Atoms of Confusion in the Context of Code Reviews*. In: 2022 IEEE International Conference on Software Maintenance and Evolution (ICSME), pp. 404–408. [https://doi.org/10.1109/ICSME55016.2022.00048](https://doi.org/10.1109/ICSME55016.2022.00048)

## 1. Fichamento de Conteúdo

O artigo, de resultados emergentes, investiga se **átomos de confusão** — pequenos padrões sintáticos conhecidos por induzir confusão — estão associados à confusão relatada em *code reviews*, e como esses átomos evoluem ao longo de *pull requests*. Por meio de um **estudo de caso exploratório**, os autores combinam detecção automática de átomos e análise manual de comentários. Contrariando expectativas, a análise estatística **não** encontra relação entre presença de átomos e comentários de confusão em *reviews*. Além disso, os átomos tendem a **não** ser removidos nos PRs, sugerindo persistência desses micro-padrões. O trabalho encerra com hipóteses para estudos futuros e reforça que compreender clareza em *reviews* requer olhar além de micro-padrões, considerando desenho e arquitetura. Para seu TCC, funciona como alerta metodológico: métricas de clareza devem combinar diversos sinais (padrões GoF, *smells*, *grime* e *feedback* de *reviews*).

## 2. Fichamento Bibliográfico

* Contexto: *code review* é prática central; “success of code reviews can be threatened by confusion experienced by code reviewers” (Abstract).
* Perguntas: relação entre átomos e confusão em *reviews*; persistência dos átomos ao longo de PRs (Abstract).
* Achados: “statistical analysis did not show any relationship … \[and] atoms of confusion are mostly not being removed in pull requests” (Abstract).

## 3. Fichamento de Citações

* _“In this emerging results paper, we report an exploratory case study to provide a deeper understanding of atoms of confusion…”_
* _“…statistical analysis did not show any relationship between atoms of confusion and presence of confusion comments in code reviews.”_
* _“Additionally, we found evidence that atoms of confusion are mostly not being removed in pull requests.”_
* _“Based on the results, we formulate hypotheses … that should be confirmed or rejected by future studies.”_
