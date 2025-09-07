# Completeness of composite refactorings for smell removal

## Referência

Bibiano, A. C. *Completeness of composite refactorings for smell removal*. In: ICSE ’22 Companion, 2022. [https://doi.org/10.1145/3510454.3517060](https://doi.org/10.1145/3510454.3517060)

## 1. Fichamento de Conteúdo

O trabalho examina **refatorações compostas** (sequências coordenadas) para remover *code smells*, perguntando quando tais sequências são **completas** (suficientes) e qual o efeito da (in)completude na qualidade estrutural. A autora minera ocorrências reais com ferramentas como RefactoringMiner/Organic e discute catálogos de recomendações. Os achados indicam que composições **incompletas** são comuns e podem não eliminar o *smell*, enquanto composições completas podem introduzir efeitos colaterais indesejados (p.ex., outros *smells*), recomendando cuidado na orquestração. Na prática, isso implica planejar *playbooks* de refatoração com sequência e escopo adequados, medindo impacto em coesão, acoplamento, tamanho e complexidade. Para Clean Architecture, o estudo é útil para coordenar refatorações em torno de padrões GoF, evitando que a correção pontual piore o desenho global.

## 2. Fichamento Bibliográfico
* Motivação: *code smells* e a necessidade de combinar refatorações em sequências coesas (Abstract/Intro).
* Pergunta: quando uma composição é “completa” para remover um *smell*, e que efeitos tem a (in)completude na qualidade? (Abstract/Conclusion).
* Contribuição: catálogo/recomendações para composições; mineração com ferramentas reconhecidas (Abstract).

## 3. Fichamento de Citações
* _“Code smells are problems in the internal structural quality. Refactoring is a technique commonly used to remove code smells.”_
* _“This doctoral research investigates the effect of composite (in)completeness on structural quality and proposes a catalog with composite recommendations.”_
* _“A single refactoring rarely suffices to assist developers in achieving \[complete] smell removal.”_
