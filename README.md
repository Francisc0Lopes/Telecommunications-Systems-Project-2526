# Simulador de Tráfego e Dimensionamento de Call Center

![Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellow)
![Ferramenta](https://img.shields.io/badge/ferramenta-C++-blue)
![Relatório](https://img.shields.io/badge/relatório-Overleaf_(LaTeX)-green)
![Tipo](https://img.shields.io/badge/tipo-Simulação_Estocástica-orange)

---

## Sumário
1. [Descrição Geral](#descrição-geral)
2. [Arquitetura e Requisitos](#arquitetura-e-requisitos)
3. [Equipa e Responsabilidades](#equipa-e-responsabilidades)
4. [Estrutura do Relatório Técnico](#estrutura-do-relatório-técnico)
5. [Plano de Trabalho](#plano-de-trabalho)
6. [Metas de Dimensionamento](#metas-de-dimensionamento)

---

## Descrição Geral

Este projeto visa o dimensionamento de uma **Rede de Circuitos Comutados** e de um **Call Center**, desenvolvido no âmbito da unidade curricular de **Sistemas de Telecomunicações (2025/2026)**.

O núcleo do trabalho é o desenvolvimento de um **simulador dinâmico, estocástico e de eventos discretos** que modele o tráfego de voz e filas de espera. O objetivo é comparar os resultados da simulação com modelos matemáticos teóricos (Erlang B e Erlang C) para determinar o número ideal de circuitos e operadores.

---

## Arquitetura e Requisitos

O sistema modelado obedece à topologia descrita no enunciado:
- **Rede:** 3 comutadores de trânsito e 4 de acesso.
- **Fluxo:** Tráfego originado em A, B, C com destino a F (Call Center).
- **Encaminhamento:** Rotas diretas prioritárias; rotas alternativas apenas em caso de bloqueio.
- **Call Center:** Sistema de espera FIFO ideal (capacidade infinita, sem desistências).

### Ferramentas de Desenvolvimento
- **Simulação:** MATLAB (Implementação de lógica de eventos discretos e geração de variáveis aleatórias).
- **Controlo de Versão:** GitHub.
- **Documentação:** Overleaf (LaTeX) para o relatório técnico.

---

## Equipa e Responsabilidades

| Membro              | Responsabilidades Principais                                                                 |
|---------------------|---------------------------------------------------------------------------------------------|
| **Francisco Lopes** | Modelação Teórica (Erlang B/C); Definição da topologia e rotas; Introdução e Estado da Arte.|
| **João Dragovíc** | Implementação do motor de simulação (Gestão de eventos e listas); Validação estatística.    |
| **Sérgio Matias** | Análise de Resultados (KPIs); Dimensionamento final (Circuitos/Operadores); Conclusão.      |

---

## Estrutura do Relatório Técnico

O relatório (limite de 25 páginas) seguirá a seguinte estrutura lógica:

- **Introdução:** Contextualização do problema de Engenharia de Tráfego.
- **Modelo Teórico:** Cálculos analíticos para probabilidade de bloqueio e tempos de espera.
- **Arquitetura do Simulador:** - Descrição da abordagem de eventos discretos.
  - Geração de tráfego (Interchegadas e Duração de chamadas).
  - Lógica de encaminhamento e gestão de recursos.
- **Análise de Resultados e Dimensionamento:**
  - Comparação Teoria vs. Simulação.
  - Determinação do número de linhas e operadores para cumprir os requisitos.
  - Gráficos de validação (Bloqueio Global/Local, Ocupação, Espera).
- **Conclusão:** Síntese das opções tomadas e viabilidade da solução proposta.

---

## Plano de Trabalho

1. **Fase 1 (Modelagem):** Definição das matrizes de tráfego e cálculo teórico inicial.
2. **Fase 2 (Core do Simulador):** Implementação do loop de eventos e gestão de filas FIFO.
3. **Fase 3 (Validação):** Testes preliminares para garantir coerência estocástica.
4. **Fase 4 (Dimensionamento):** Execução iterativa para encontrar o número mínimo de recursos que satisfaz os requisitos de QoS.
5. **Fase 5 (Relatório):** Redação final e análise crítica dos dados.

---

## Metas de Dimensionamento

O sistema final deve garantir estritamente os seguintes Requisitos de Qualidade de Serviço (QoS):

| Parâmetro | Meta / Restrição |
|-----------|------------------|
| **Probabilidade de Bloqueio** | $\le 1.5\%$ (Global) |
| **Nível de Serviço** | $50\%$ das chamadas atendidas em $< 6$ min |
| **Equilíbrio de Rede** | Diferença de bloqueio entre nós D, E, F $\le 0.5\%$ |
| **Fila de Espera** | FIFO Ideal (sem desistências) |

---
*ISEL - Licenciatura em Engenharia Informática, Redes e Telecomunicações*