# Evolution patterns of software-architecture smells: An empirical study of intra- and inter-version smells

## Referência
Gnoyke, P.; Schulze, S.; Krüger, J. *Evolution patterns of software-architecture smells: An empirical study of intra- and inter-version smells*. Journal of Systems and Software, 217 (2024) 112170. [https://doi.org/10.1016/j.jss.2024.112170](https://doi.org/10.1016/j.jss.2024.112170)

## 1. Fichamento de Conteúdo

Este artigo apresenta um estudo empírico aprofundado sobre como **architecture smells** (sintomas de degradação arquitetural) evoluem ao longo do tempo em software. Analisando 485 *releases* de 14 sistemas de código aberto, os autores introduzem uma distinção crucial entre smells **intra-versão** (dentro de uma única versão) e **inter-versão** (a trajetória de um *smell* através de múltiplas versões). O estudo propõe técnicas avançadas para rastrear a evolução dos *smells*, incluindo novas visualizações como "grafos de evolução de dependências cíclicas", que capturam eventos de fusão (*merging*) e divisão (*splitting*) de *smells*. Os resultados indicam padrões evolutivos distintos para diferentes tipos de *smells*: **dependências cíclicas** em nível de classe são propensas a se tornarem extremamente complexas, frequentemente através da fusão com outros *smells*, formando "tangled multi-hubs". Em contraste, **dependências instáveis** tendem a crescer lentamente, enquanto **dependências do tipo hub** permanecem relativamente estáveis. O trabalho fornece insights valiosos para que desenvolvedores e arquitetos possam identificar e intervir em pontos de degeneração arquitetural de forma proativa.

## 2. Fichamento Bibliográfico

* **Principais Conceitos:**
    * **Architecture Smell:** Um sintoma de violação de princípios de design no nível da arquitetura de software, indicando possíveis problemas de qualidade interna, como baixa manutenibilidade. O estudo foca em três tipos:
        * **Dependência Cíclica (Cyclic Dependency):** Ocorre quando um conjunto de componentes depende mutuamente uns dos outros, direta ou indiretamente, violando o princípio da dependência acíclica.
        * **Dependência do tipo Hub (Hub-Like Dependency):** Um componente com um número excessivamente alto de dependências de entrada (fan-in) e de saída (fan-out), atuando como um gargalo no sistema.
        * **Dependência Instável (Unstable Dependency):** Um componente que depende de outros componentes que são menos estáveis (mais propensos a mudanças) do que ele próprio.
    * **Intra-versão vs. Inter-versão Smells:** Uma distinção conceitual proposta pelos autores. Um **smell intra-versão** é uma instância de um *smell* detectada em uma única versão do sistema. Um **smell inter-versão** é a evolução de um *smell* ao longo de múltiplas versões consecutivas, rastreado como uma sequência (ou família) de *smells* intra-versão relacionados.
    * **Fusão e Divisão (Merging and Splitting):** Eventos evolutivos de *smells* cíclicos. A **fusão** ocorre quando a adição de uma dependência une dois ou mais *smells* cíclicos em um só, maior e mais complexo. A **divisão** é o processo inverso, onde a remoção de dependências quebra um *smell* grande em múltiplos menores.

* **Ferramentas e Bibliotecas:**
    * **Arcan:** Uma ferramenta de código aberto para detecção de *architecture smells* em sistemas Java. Foi a ferramenta base para a análise deste estudo. Os autores modificaram o Arcan para detectar superciclos, quantificar dívida técnica e otimizar seu desempenho. Link para a versão pública: [https://gitlab.com/essere.lab.public/arcan](https://gitlab.com/essere.lab.public/arcan).
    * **AsTdEA (Architecture Smell and Technical Debt Evolution Analyzer):** Uma ferramenta desenvolvida pelos próprios autores para controlar a execução do Arcan em múltiplas versões de um sistema e para implementar a lógica de rastreamento de *smells* inter-versão, incluindo a detecção de fusões e divisões.
    * **Qualitas Corpus:** Um conhecido conjunto de dados de sistemas Java de código aberto, utilizado como fonte para os 14 projetos analisados. É um recurso padrão para estudos empíricos em engenharia de software.

* **Teorias e Métodos:**
    * **Estudo de Caso Múltiplo (Multi-case Study):** A pesquisa foi desenhada como um estudo de caso múltiplo, analisando a evolução de 14 sistemas de software para aumentar a validade externa e a generalização dos resultados.
    * **Rastreamento de Smells (Smell Tracking):** A metodologia central para analisar a evolução inter-versão. Para *hubs* e dependências instáveis, o rastreamento se baseia na similaridade dos componentes afetados entre versões adjacentes (usando a similaridade de Jaccard). Para dependências cíclicas, o rastreamento é mais complexo e se baseia na sobreposição de componentes em **superciclos** (componentes fortemente conectados), o que permite lidar com fusões e divisões.
    * **Grafos de Evolução de Dependências Cíclicas:** Uma visualização inovadora proposta no artigo para representar a vida de um *smell* cíclico. Cada nó no grafo é um *smell* intra-versão, e as arestas representam transições entre versões, tornando fusões (múltiplas arestas de entrada) e divisões (múltiplas arestas de saída) explícitas.
    * **Análise de Propriedades dos Smells:** Foram medidas diversas métricas quantitativas para cada *smell* intra-versão (ex: `order` - nº de componentes, `size` - nº de dependências, `centrality`) e inter-versão (ex: `lifespan`, `family width`) para analisar seus padrões evolutivos.

## 3. Fichamento de Citações

* _"An empirical study of how architecture smells evolve and what typical patterns they exhibit in 485 releases of 14 open-source systems."_
* _"Building on our previous work in this direction, we present extended techniques for measuring architecture smells, novel visualizations, as well as an empirical study of how architecture smells themselves evolve."_
* _"The results of our study indicate that especially cyclic dependencies on the class-level are prone to becoming highly complex over time, with one of the reasons being the continued merging of smells, most often resulting in tangled multi-hubs."_
* _"We (Gnoyke et al., 2021) have established a distinction between intra-version and inter-version architecture smells, referring to intra-version smells if we consider the architecture smells that exist in a single version of a system, and inter-version smells if we consider a set of intra-version smells that are related and occur through multiple consecutive versions of a system."_
* _"Adding one or more dependencies among system components can lead to the merging of two or more intra-version cyclic dependencies. Similarly, removing one or more dependencies can cause the splitting of an intra-version cyclic dependency into multiple ones."_
* _"We cannot confirm that there is a general compound interest effect on architectural issues in software systems."_
