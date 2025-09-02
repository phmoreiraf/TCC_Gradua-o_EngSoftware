# An Exploratory Study on the Occurrence of Self-Admitted Technical Debt in Android Apps

## Referência
Wilder II, Gregory; Miyamoto, Riley; Watson, Samuel; Kazman, Rick; Peruma, Anthony. "An Exploratory Study on the Occurrence of Self-Admitted Technical Debt in Android Apps," in *Proceedings of the 6th International Conference on Technical Debt (TechDebt 2023)*, pp. 11–20, May 2023. doi: [10.1109/TechDebt2023.10207081](https://ieeexplore.ieee.org/document/10207081)

## 1. Fichamento de Conteúdo

Este artigo realiza um estudo exploratório em larga escala para investigar a ocorrência e as características da Dívida Técnica Auto-Admitida (SATD) em aplicações Android de código aberto. A pesquisa aborda uma lacuna significativa, pois estudos anteriores sobre SATD focaram majoritariamente em sistemas não-móveis, que possuem características e restrições distintas das aplicações móveis. Analisando mais de 15.000 apps Android, os autores descobriram que, embora a SATD esteja presente, seu volume é consideravelmente menor do que em sistemas tradicionais, com uma mediana de apenas quatro comentários de SATD por aplicativo, provavelmente devido ao menor tamanho dos projetos. A análise qualitativa de uma amostra estatisticamente significativa revelou que a categoria mais comum de dívida é a **Dívida de Código** (35,23%), principalmente na forma de "workarounds" para lidar com bugs de APIs, do SDK do Android ou de dispositivos específicos. Em seguida, vêm a **Dívida de Design** (23,58%) e a **Dívida de Requisito** (19,95%). O estudo também identificou os elementos de código mais suscetíveis à dívida, que incluem APIs do SDK do Android (como `Activity`, `Fragment` e `View`), componentes gerais de UI, conceitos de programação (armazenamento, segurança, tratamento de erros) e hardware (câmera, suporte a dispositivos específicos). O trabalho fornece um panorama inicial, porém fundamental, sobre como os desenvolvedores de Android lidam e documentam conscientemente suas decisões de implementação subótimas.

## 2. Fichamento Bibliográfico

* **Dívida Técnica Auto-Admitida (SATD)**: Refere-se à prática dos desenvolvedores de documentar intencionalmente, por meio de comentários no código-fonte (usando palavras-chave como `TODO`, `FIXME`, `XXX`), decisões de implementação que são subótimas ou incompletas. Essas anotações são feitas para atender a prazos ou contornar problemas imediatos, com a intenção de resolver a "dívida" no futuro. A SATD serve como um registro explícito de compromissos de qualidade e é o foco principal da análise do estudo.

* **Metodologia de Análise**: O estudo empregou uma metodologia mista em várias etapas:
    1.  **Coleta de Dados**: Foram clonados 37.342 repositórios de aplicativos Android de código aberto do dataset AndroZooOpen.
    2.  **Detecção de SATD**: Utilizou-se a ferramenta `SATD Detector Core`, baseada em processamento de linguagem natural e machine learning, para identificar comentários de SATD em 1.386.942 arquivos Java.
    3.  **Análise Quantitativa**: Foi calculada a frequência e a distribuição da SATD nos aplicativos e arquivos, além de correlações com o tamanho dos arquivos.
    4.  **Categorização Manual**: Uma amostra estatisticamente significativa de 386 comentários de SATD foi analisada manualmente por todos os autores e classificada em sete tipos de dívida pré-definidos (Código, Design, Requisito, Defeito, Documentação, Teste e Inclassificável).
    5.  **Análise de N-Grams**: Foram extraídos os unigramas, bigramas e trigramas mais frequentes de todos os comentários de SATD para identificar os elementos de código e conceitos mais comumente associados à dívida.

* **Tipos de Dívida Técnica Identificados**: A classificação manual revelou a seguinte distribuição, destacando as principais preocupações dos desenvolvedores de Android:
    * **Dívida de Código (35,23%)**: A categoria mais prevalente, abrangendo workarounds, código de baixa legibilidade e soluções temporárias, muitas vezes para contornar bugs em APIs ou dar suporte a dispositivos específicos.
    * **Dívida de Design (23,58%)**: Relacionada a problemas estruturais, violações de princípios de design e necessidade de refatoração para mover código para locais mais apropriados.
    * **Dívida de Requisito (19,95%)**: Documenta funcionalidades ausentes ou incompletas, tanto na camada de apresentação quanto na lógica de negócios, incluindo a necessidade de suportar futuras versões do Android.
    * **Dívida de Teste (1,30%)**: Foi a categoria menos frequente, o que é consistente com estudos anteriores que apontam que apps Android são, em geral, mal testados.

* **Elementos de Código Propensos à Dívida**: A análise de n-grams revelou quatro áreas principais onde a SATD é mais comum em apps Android:
    1.  **API do SDK do Android**: A área mais crítica, envolvendo componentes de UI (`Activity`, `View`, `Fragment`), APIs não-UI (`Context`, `ContentProvider`) e gerenciamento de versões da API (`deprecated_api`, `api_level`).
    2.  **UI Geral**: Termos genéricos de interface do usuário, como `button`, `color`, `margin`, geralmente relacionados à implementação de novas funcionalidades.
    3.  **Programação Geral**: Abrange refatoração, manipulação de data/hora, armazenamento (banco de dados, JSON), comunicação com recursos externos (URLs, servidores), tratamento de erros e segurança.
    4.  **Hardware**: Dívidas relacionadas à integração com componentes específicos do dispositivo, como `camera` e a necessidade de criar soluções alternativas para diferentes modelos de `device`.

## 3. Fichamento de Citações

* _"While prior research has investigated the occurrence and characteristics of SATD, this research has primarily focused on non-mobile systems"_.
* _"Our findings show that even though such apps contain occurrences of SATD, the volume per app (a median of 4) is lower than in non-mobile systems, with most debt categorized as Code Debt"_.
* _"This comparatively low occurrence of SATD is likely due to the fact that apps contain fewer source files"_.
* _"Code debt contributes the greatest number of SATD instances that Android developers injected into their apps, implying that developers frequently compromise their code quality via workarounds to achieve a desired result"_.
* _"This is consistent with the low occurrence of Test Debt in our dataset"_.
* _"We also show that technical debt is not only related to general programming or design concepts but also due to shortcomings developers take when implementing code that utilizes Android APIs"_.
