# An empirical investigation of the relationship between pattern grime and code smells

Alharbi, M.; Alshayeb, M. *An empirical investigation of the relationship between pattern grime and code smells*. Journal of Software: Evolution and Process, 2024. [https://doi.org/10.1002/smr.2666](https://doi.org/10.1002/smr.2666)

## 1. Fichamento de Conteúdo

Este artgio apresenta um estudo quantifica a relação entre *pattern grime* — degradações acumuladas dentro de instâncias de padrões — e *code smells*. Em cinco projetos Java de código aberto, os autores medem grime com múltiplas métricas e cruzam com dez smells, usando correlação de Spearman, *odds ratio* e regras de associação (Apriori). Os resultados indicam que classes com padrões “envelhecidos” tendem a ser mais suscetíveis a *smells* do que instâncias sem grime. Em particular, há associação positiva forte entre o crescimento de grime no nível de classe e o smell **Shotgun Surgery**; nos níveis modular e organizacional, a associação não se confirma. O trabalho sugere que a qualidade de aplicação do padrão — e não sua mera presença — explica parte relevante da manutenibilidade. Para seu TCC, isso orienta medições de “uso saudável” de Factory, Strategy, Observer e Decorator (ex.: papéis/roles e grime por papel), conectando-as a *smells* e à facilidade de evolução em Clean Architecture.

## 2. Fichamento Bibliográfico

* Escopo: 5 projetos Java; 6 métricas de grime e 10 *code smells*; análise com Spearman, OR e Apriori (Methods/Results).
* Achado central: crescimento de grime co-ocorre com *smells*; destaque para associação com **Shotgun Surgery** no nível de classe (Results/Conclusion).
* Amostra: cinco projetos OSS com centenas de classes por projeto (Methods).

## 3. Fichamento de Citações

* _“Our statistical results indicate that, in general, the growth of grime is more likely to co-occur with code smells using Spearman’s correlation and Odd Ratio test.”_
* _“There is a significant positive association between the growth of pattern grime at the class level and the presence of Shotgun Surgery smell.”_
* _“Six-grime metrics and 10 code smells on five Java open-source projects ranging from 217 to 563 classes.”_
