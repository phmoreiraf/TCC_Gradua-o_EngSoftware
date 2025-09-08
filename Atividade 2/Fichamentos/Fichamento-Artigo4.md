# Prevalence and severity of design anti-patterns in open source programs — A large-scale study

## Referência
Liu, A.; Lefever, J.; Xiao, L.; Cai, Y.; Kazman, R. *Prevalence and severity of design anti-patterns in open source programs — A large-scale study*. Information and Software Technology, 170 (2024) 107429. [https://doi.org/10.1016/j.infsof.2024.107429](https://doi.org/10.1016/j.infsof.2024.107429)

## 1. Fichamento de Conteúdo

Este artigo apresenta um estudo empírico de larga escala sobre a **prevalência** (quão comuns são) e a **severidade** (quão custosos são em termos de manutenção) de seis tipos de anti-padrões de design. Analisando 1.717 projetos de código aberto em Java, C/C++ e Python, os autores utilizam a ferramenta DV8 para detectar anti-padrões, considerando não apenas dependências estruturais, mas também o histórico de co-mudanças dos arquivos. Os resultados são contundentes: **99,55%** dos projetos contêm algum tipo de anti-padrão. O anti-padrão **Modularity Violation** (violação de modularidade) destaca-se como o mais prevalente e o mais caro, sendo responsável por mais de 60% do esforço de manutenção (medido em churn). O estudo também revela que a tipagem dinâmica em Python tende a ocultar e exacerbar problemas de dependência, tornando os projetos Python, em média, mais caros de manter. Ao filtrar anti-padrões "triviais" (que afetam cinco ou menos arquivos), os autores mostram que muitas violações comuns de princípios de design, como ciclos, têm escopo limitado e baixo impacto, sugerindo que as equipes devem priorizar a correção de anti-padrões com base na severidade, e não apenas na frequência.

## 2. Fichamento Bibliográfico

* **Principais Conceitos:**
    * **Anti-padrão de Design (Design Anti-pattern):** Estruturas ou relações sub-ótimas no código-fonte que, embora não causem erros imediatos, podem degradar a qualidade e dificultar a manutenção a longo prazo, sendo uma forma de dívida técnica.
    * **Prevalência (Prevalence):** Mede a frequência com que um anti-padrão é detectado em uma população de projetos. Neste estudo, é expressa como a porcentagem de projetos que contêm pelo menos uma instância de um determinado anti-padrão.
    * **Severidade (Severity):** Mede o impacto negativo de um anti-padrão, quantificado neste estudo principalmente pelo esforço de manutenção. A principal métrica utilizada é o **Churn**, que representa o total de linhas de código adicionadas e deletadas em arquivos envolvidos no anti-padrão durante um período de um ano.
    * **Modularity Violation Group (MVG):** Um anti-padrão que ocorre quando um grupo de arquivos que não possui dependências estruturais explícitas entre si muda frequentemente em conjunto (*co-change*). Isso indica a existência de dependências implícitas ou ocultas, que são custosas de manter.
    * **Unstable Interface (UIF) e Crossing (CRS):** Anti-padrões relacionados a arquivos que são ao mesmo tempo muito influentes (muitos outros arquivos dependem deles) e instáveis (mudam com frequência). Tais arquivos se tornam pontos centrais de dívida técnica, propagando instabilidade para outras partes do sistema.

* **Ferramentas e Bibliotecas:**
    * **DV8:** A principal suíte de ferramentas utilizada para a análise de arquitetura automatizada. O DV8 detecta os anti-padrões combinando informações de dependências estruturais com o histórico de evolução (co-mudanças) extraído de sistemas de controle de versão como o Git. Ele também relata os custos de manutenção de cada instância de anti-padrão.
    * **Depends:** Uma ferramenta de extração de dependências de código-fonte multilinguagem, usada pelo DV8 como pré-processador. É capaz de extrair dependências explícitas (em linguagens como Java e C/C++) e também **dependências possíveis** (inferidas estaticamente em linguagens de tipagem dinâmica como Python).

* **Teorias e Métodos:**
    * **Estudo Empírico de Larga Escala:** A pesquisa foi conduzida em uma grande amostra de 1.717 projetos de código aberto do GitHub, selecionados com base em popularidade e filtrados para incluir apenas projetos não triviais (mais de 100 arquivos) e com histórico de evolução de mais de um ano.
    * **Análise Combinada (Estrutura + Histórico):** Diferente de muitas ferramentas que se baseiam apenas em métricas estáticas, a abordagem deste estudo incorpora o histórico de co-mudanças para identificar anti-padrões como MVG, UIF e UIH. A lógica é que problemas de design reais tendem a se manifestar como alto custo de manutenção ao longo do tempo.
    * **Análise de Impacto de Tipagem Dinâmica:** Para os projetos Python, a análise foi realizada duas vezes: uma considerando apenas dependências explícitas e outra incluindo as "dependências possíveis" inferidas pela ferramenta Depends. Isso permitiu quantificar como a tipagem dinâmica afeta a prevalência e a severidade dos anti-padrões detectados.
    * **Filtragem de Instâncias Triviais:** Para avaliar se anti-padrões prevalentes são sempre prejudiciais, os autores removeram da análise as instâncias que envolviam cinco ou menos arquivos. Essa abordagem foi baseada em estudos de psicologia cognitiva sobre a capacidade humana de processar "pedaços" de informação, sugerindo que violações de pequena escala podem não ser um problema significativo.

## 3. Fichamento de Citações

* _"The results reveal that 99.55% of these projects contain anti-patterns."_
* _"Modularity Violation - frequent co-changes among seemingly unrelated files is most prevalent (detected in 83.54% of all projects) and costly (incurred 61.55% of maintenance effort on average)."_
* _"Duck typing in Python incurs more anti-patterns, and the churn spent on Python files multiplies that of C/C++ and Java files."_
* _"For the 288 Python projects, we extracted both explicit and dynamic dependencies and compared how the detected anti-patterns and maintenance costs changed."_
* _"To the best of our knowledge, this is the first large-scale, multiple-language prevalence and severity study of design-level anti-patterns."_
* _"Implicit and visible dependencies are the most expensive to maintain, and dynamic typing in Python exacerbates the issue."_
