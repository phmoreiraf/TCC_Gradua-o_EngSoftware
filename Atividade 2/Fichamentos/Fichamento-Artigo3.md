# Evolution patterns of software-architecture smells: An empirical study of intra- and inter-version smells

Gnoyke, P.; Schulze, S.; Krüger, J. *Evolution patterns of software-architecture smells: An empirical study of intra- and inter-version smells*. Journal of Systems & Software, 217 (2024) 112170. [https://doi.org/10.1016/j.jss.2024.112170](https://doi.org/10.1016/j.jss.2024.112170)

## 1. Fichamento de Conteúdo

O artigo analisa como *architecture smells* surgem, persistem e se transformam em 485 *releases* de 14 sistemas OSS, distinguindo padrões **intra-versão** (ao longo de uma *release*) e **inter-versão** (entre *releases*). Os autores expandem técnicas de medição e propõem novas visualizações para acompanhar a evolução. Entre os achados, **dependências cíclicas** em nível de classe tendem a crescer em complexidade ao longo do tempo, por “fusão” de cheiros que formam *tangled multi-hubs*. **Dependências instáveis** crescem mais lentamente, enquanto **hubs** permanecem relativamente estáveis. Esses resultados ajudam a priorizar intervenções e a entender pontos de degradação arquitetural. Para Clean Architecture, a leitura sugere monitorar acoplamentos entre camadas/adapters e antecipar refatorações estruturais antes que ciclos se tornem intratáveis, conectando as métricas à clareza do design e à facilidade de evolução.

## 2. Fichamento Bibliográfico

* Amostra: 485 *releases* de 14 projetos OSS; foco em padrões evolutivos de *architecture smells* (Abstract).
* Contribuição: técnicas estendidas de medição e visualizações novas (Abstract).
* Achados: ciclos tornam-se *tangled multi-hubs*; instáveis crescem devagar; hubs estáveis (Abstract).

## 3. Fichamento de Citações

* _“An empirical study of how architecture smells evolve and what typical patterns they exhibit in 485 releases of 14 open-source systems.”_
* _“We present extended techniques for measuring architecture smells, and novel visualizations…”_
* _“…cyclic dependencies on the class-level are prone to becoming highly complex over time, often resulting in tangled multi-hubs.”_
