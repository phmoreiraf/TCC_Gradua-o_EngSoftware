# An Empirical Study Assessing Software Modeling in Alloy

## Referência
Cirilo, Edson; Garcia, Alessandro; Whittle, Jon. "An Empirical Study Assessing Software Modeling in Alloy," in *Proceedings of the 45th International Conference on Software Engineering (ICSE 2023)*, pp. 145–156, May 2023. doi: [10.1109/ICSE.2023.10164717](https://ieeexplore.ieee.org/document/10164717)

## 1. Fichamento de Conteúdo
O artigo apresenta um estudo empírico detalhado que investiga a usabilidade da linguagem de modelagem formal Alloy, com foco em como a experiência do usuário afeta o desempenho em tarefas práticas. A pesquisa envolveu 30 participantes, divididos em "novatos" e "não-novatos", que realizaram tarefas de correção de bugs (sintáticos e semânticos) e de construção de um modelo a partir de uma especificação em linguagem natural. Além disso, o estudo avaliou a correlação entre o desempenho nessas tarefas e as habilidades cognitivas dos participantes, especificamente a memória de trabalho e a cognição espacial (rotação mental). Os resultados indicam diferenças significativas entre os grupos: os não-novatos foram 54% mais precisos e, em média, 32 minutos mais rápidos nas tarefas de correção de bugs. A construção de modelos a partir do zero provou ser uma tarefa difícil para todos os participantes, independentemente do nível de experiência. O estudo também revelou que a habilidade de cognição espacial está positivamente correlacionada com o sucesso na correção de bugs em Alloy, sugerindo que essa capacidade é importante para a compreensão de seus conceitos. O artigo conclui que há uma necessidade clara de melhorar a usabilidade e, principalmente, as visualizações do Alloy Analyzer para melhor apoiar tanto novatos quanto usuários experientes.

## 2. Fichamento Bibliográfico
* **Linguagem Alloy e Alloy Analyzer:** Alloy é uma linguagem de modelagem formal declarativa, com uma sintaxe que combina notações de design orientado a objetos e lógica relacional de primeira ordem. Ela é utilizada para construir modelos de software e verificar propriedades do sistema. O Alloy Analyzer é a ferramenta de back-end que realiza análises automatizadas, verifica asserções e, crucialmente, gera contraexemplos visuais quando uma propriedade é violada, auxiliando no processo de depuração.

* **Divisão de Participantes (Novatos vs. Não-Novatos):** O estudo classificou os 30 participantes em dois grupos para medir o impacto da experiência. Os novatos (N=17) eram iniciantes na linguagem. Os não-novatos (N=13) foram definidos como usuários com mais de um ano de experiência ou com menos de um ano, mas que utilizavam Alloy para pesquisa e classificaram seu nível de conforto com a sintaxe como igual ou superior a 3 (em uma escala de 5). Essa distinção foi fundamental para analisar as diferenças de desempenho e comportamento.

* **Tipos de Tarefas do Estudo:** Os participantes realizaram duas categorias principais de tarefas:

* **Correção de Bugs (Bug Fixing):** Os participantes receberam modelos Alloy com erros e uma especificação em linguagem natural, com o objetivo de corrigir os problemas. Os bugs foram divididos em sintáticos (erros que o analisador detecta formalmente) e semânticos (erros lógicos que alteram o comportamento do modelo, levando a instâncias incorretas ou contraexemplos).

* **Construção de Modelo (Model Building):** Uma tarefa na qual os participantes recebiam uma especificação para uma lista encadeada e um "esqueleto" de modelo Alloy, que eles precisavam completar. Esta tarefa se mostrou extremamente desafiadora para ambos os grupos.

* **Avaliação de Habilidades Cognitivas:** O estudo investigou a relação entre habilidades cognitivas e o desempenho em Alloy. Foram utilizados dois testes:

* **Operation Span Task:** Para medir a capacidade da memória de trabalho.
* 
* **3D Mental Rotation Task:** Para medir a habilidade de cognição espacial.
O resultado mais significativo foi a correlação positiva e estatisticamente significante entre o desempenho no teste de rotação mental e a precisão na correção de bugs, sugerindo que a habilidade espacial é um fator importante para o uso eficaz de Alloy. Nenhuma correlação significativa foi encontrada com a memória de trabalho.

* **Padrões de Comportamento e Uso da Ferramenta:** A análise dos logs de uso do Alloy Analyzer revelou padrões de comportamento distintos. O estudo observou que os participantes, especialmente os novatos, trabalhavam de forma incremental, fazendo pequenas alterações no modelo e executando o analisador repetidamente. A ação "Execute" foi a mais utilizada por todos. Em média, novatos realizaram mais edições e mais ações no analisador do que os não-novatos. Para o grupo de novatos, um maior número de ações e edições correlacionou-se positivamente com uma maior pontuação final, indicando que eles dependiam mais da ferramenta para chegar à solução correta.

## 3. Fichamento de Citações
* _"Traditionally, working with formal specification languages has required in-depth mathematical knowledge due to their complexity, and the learning curve is very steep for non-mathematicians".
* _"Results indicate that overall, non-novices completed the tasks with significantly higher accuracy (54% more accurate) than novices".
* _"We found that participants of all levels had much difficulty writing a model from scratch, and they did not utilize the analyzer to improve their models".
* _"Non-novices who performed better on the Alloy tasks had higher mental rotation scores, which indicates the importance of spatial cognition ability in solving Alloy tasks".
* _"RQ2 results show that despite the differences in experience, all participants found it difficult to build an Alloy model from scratch by looking at the natural language specification".
* _"Overall, we find that there is a definite need to improve the usability of the visualizations in the Alloy Analyzer".
