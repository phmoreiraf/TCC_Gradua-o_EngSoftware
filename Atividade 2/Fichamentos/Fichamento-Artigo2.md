# An empirical investigation of the relationship between pattern grime and code smells

Alharbi, M.; Alshayeb, M. *An empirical investigation of the relationship between pattern grime and code smells*. Journal of Software: Evolution and Process, 2024; 36:e2666. [https://doi.org/10.1002/smr.2666](https://doi.org/10.1002/smr.2666)

## 1. Fichamento de Conteúdo

Este artigo apresenta um estudo empírico que investiga a relação entre *pattern grime* — a degradação de instâncias de padrões de projeto pela acumulação de artefatos não relacionados — e a presença de *code smells*. Partindo da hipótese de que ambos são indicadores de má qualidade de código, os autores analisam cinco projetos Java de código aberto para quantificar essa coocorrência. Utilizando uma metodologia robusta com seis métricas para *grime* e a detecção de dez tipos de *code smells*, o estudo emprega múltiplos testes estatísticos, incluindo a correlação de Spearman, o Odds Ratio e o algoritmo Apriori para mineração de regras de associação. Os resultados confirmam uma correlação positiva geral: instâncias de padrões com *grime* são significativamente mais propensas a conter *code smells* do que instâncias "limpas". De forma mais específica, a análise revela uma forte associação entre o *grime* no nível de classe (acúmulo de atributos e métodos "estranhos") e o *smell* **Shotgun Surgery**. O trabalho conclui que a presença de *grime* pode ser um indicador útil para aprimorar ferramentas de detecção de *smells* e para guiar os desenvolvedores na priorização de atividades de refatoração, focando em padrões degradados.

## 2. Fichamento Bibliográfico

* **Principais Conceitos:**
    * **Pattern Grime:** Definido como a "degradação de uma instância de padrão de projeto devido à acumulação de artefatos não relacionados à instância". O *grime* enfraquece os benefícios do padrão, como a manutenibilidade. É classificado em três categorias:
        * **Class Grime:** Acúmulo de elementos (métodos, atributos) não relacionados às responsabilidades das classes do padrão.
        * **Modular Grime:** Acúmulo de relacionamentos (acoplamentos) desnecessários entre as classes do padrão.
        * **Organizational Grime:** Distribuição inadequada de classes do padrão em pacotes ou módulos.
    * **Code Smell:** Um sintoma no código-fonte que indica um problema de design mais profundo. Embora nem sempre seja um erro, é um sinal de que o código pode ser difícil de manter ou evoluir. O estudo investiga 10 *smells*, incluindo God Class, Feature Envy e Shotgun Surgery.
    * **Instância de Padrão de Projeto:** Refere-se aos elementos de código (classes, interfaces, métodos) que implementam concretamente um padrão de projeto em um sistema. O *grime* se acumula dentro dos limites dessas instâncias.

* **Ferramentas e Bibliotecas:**
    * **DPD (Design Pattern Detector) e SSA+:** Ferramentas usadas em conjunto para detectar instâncias de padrões de projeto no código-fonte. O DPD é destacado por sua alta precisão, e o SSA+ o complementa ao identificar classes concretas que participam dos padrões, fornecendo uma visão mais completa.
    * **Spoon-pttgrime:** A primeira ferramenta automatizada projetada especificamente para detectar e quantificar *pattern grime* estrutural. Ela utiliza o código-fonte e um arquivo XML com as instâncias de padrões para calcular seis métricas de *grime*.
    * **iPlasma:** Ferramenta de análise de código utilizada para detectar os 10 tipos de *code smells* investigados no estudo. Foi escolhida por sua ampla cobertura de *smells* e por ter sido validada em estudos anteriores.
    * **Weka:** Uma suíte de software de *machine learning* que foi utilizada para aplicar o algoritmo Apriori e extrair as regras de associação entre *grime* e *smells*.

* **Teorias e Métodos:**
    * **Estudo Empírico Quantitativo:** A pesquisa segue um design experimental para analisar dados de cinco projetos Java de código aberto do repositório **P-Mart**.
    * **Análise de Correlação (Spearman's Rank Correlation):** Usado para avaliar a força e a direção da associação entre a quantidade de *grime* (medida pelas seis métricas) e a contagem de *code smells* em cada instância de padrão. Foi escolhido porque os dados não seguiam uma distribuição normal.
    * **Odds Ratio (OR):** Teste estatístico empregado para confirmar os resultados da correlação. Ele calcula a probabilidade de uma instância de padrão ser "smelly" quando ela contém *grime*, em comparação com a probabilidade quando ela não contém *grime*. Um valor de OR > 1 indica que a presença de *grime* aumenta as chances da presença de *smells*.
    * **Mineração de Regras de Associação (Apriori Algorithm):** Utilizado para descobrir relações de coocorrência mais específicas, como "se o *grime* do tipo X está presente, então o *smell* do tipo Y também tende a estar". A força das regras foi avaliada pela métrica de **Conviction**, que é mais confiável que Suporte e Confiança para datasets menores, indicando a força da implicação (um valor > 1 sugere uma associação positiva).

## 3. Fichamento de Citações

* _"Our statistical results indicate that, in general, the growth of grime is more likely to co-occur with code smells using Spearman’s correlation and Odd Ratio test."_
* _"Specifically, there is a strong positive association between the growth of pattern grime at the class level and the presence of Shotgun Surgery smell according to the result of applying the Apriori algorithm, which gives conviction values equal to 1.66."_
* _"As the presence of both code smells and pattern grime raises a flag at code segments that need more careful examinations, a potential connection between them may exist."_
* _"The findings in this paper are helpful for developers and researchers as the presence of pattern grime could be considered a factor in improving the performance of existing smell detection methods."_
* _"The rationale of design patterns could be seen as the opposite of code smells as the former imposes good design practices in the system, whereas the latter represents signs of code flaws."_
* _"Even though many studies discussed the impact of design patterns, code smells, and pattern grime on software quality attributes, as mentioned above, no study has yet explored the relationship between pattern grime and code smells..."_
