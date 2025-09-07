# Prevalence and severity of design anti-patterns in open source programs — A large-scale study

Liu, A.; Lefever, J.; Xiao, L.; Cai, Y.; Kazman, R. *Prevalence and severity of design anti-patterns in open source programs — A large-scale study*. Information and Software Technology, 170 (2024) 107429. [https://doi.org/10.1016/j.infsof.2024.107429](https://doi.org/10.1016/j.infsof.2024.107429)

## 1. Fichamento de Conteúdo

Este estudo de larga escala mede **prevalência** e **severidade** de anti-padrões de design em 1.717 projetos de diferentes linguagens, integrando dependências e histórico de co-mudanças via DV8. Os autores mostram que **99,55%** dos projetos contêm anti-padrões, com destaque para **Modularity Violation**, que é o mais prevalente e o mais custoso em manutenção. O trabalho aponta que dependências implícitas/explícitas são particularmente caras, que a tipagem dinâmica (Python) pode intensificar anti-padrões e que remover casos triviais não altera o quadro geral. Como implicação, sugerem priorizar refatorações orientadas por **severidade** (impacto) e não apenas por contagem bruta. Para Clean Architecture, os resultados sustentam monitoramento contínuo de violações de modularidade entre camadas e de interfaces instáveis, conectando essas métricas à capacidade de evolução do sistema.

## 2. Fichamento Bibliográfico

* Achado global: 99,55% dos projetos contêm anti-padrões (Abstract/Results).
* Prevalência/custo: **Modularity Violation** é o mais prevalente e custoso (Abstract/Results).
* Método: integração de dependências (explícitas e dinâmicas em Python) e remoção de anti-padrões triviais (Methods/Results).

## 3. Fichamento de Citações

* _“The results reveal that 99.55% of these projects contain anti-patterns.”_
* _“Modularity Violation … is most prevalent and costly.”_
* _“For the 288 Python projects, we extracted both explicit and dynamic dependencies… and removed anti-patterns involving five or fewer files to assess the impact of trivial anti-patterns.”_
