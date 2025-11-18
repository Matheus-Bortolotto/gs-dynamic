# Global Solution — Motor de Orientação de Habilidades (MOH)

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/)

**Projeto:** Programação Dinâmica Aplicada ao Planejamento de Carreira  
**Instituição:** FIAP — Faculdade de Informática e Administração Paulista  
**Disciplina:** Engenharia de Software  
**Professor:** André Marques  
**Semestre:** 2º/2025

---

## Equipe OptiMind

| Nome | RM | Função |
|------|-----|--------|
| **Luan Ramos** | 558537 | Desenvolvimento & Análise |
| **Matheus Bortolotto** | 555189 | Implementação & Testes |
| **Matheus Ricciotti** | 556930 | Documentação & Visualização |

---

## Visão Geral

O **Motor de Orientação de Habilidades (MOH)** é um sistema de otimização que utiliza **Programação Dinâmica** para planejar trajetórias ótimas de aprendizado profissional. O sistema considera:

- ✅ **Dependências entre habilidades** (pré-requisitos)
- ✅ **Restrições de tempo e complexidade**
- ✅ **Incerteza de valores futuros** (simulação Monte Carlo)
- ✅ **Cenários de mercado** (probabilidades de valorização)
- ✅ **Múltiplos objetivos** (valor, custo, adaptabilidade)

**Demonstração:**
```
Entrada: 12 habilidades com dependências
Objetivo: Alcançar S6 (IA Generativa Ética)
Restrições: Tempo ≤ 350h, Complexidade ≤ 30
Saída: Caminho ótimo com valor 45, tempo 340h
```

---

## Estrutura do Projeto

```
global-solution-moh/
├── gs_dynamic_2semestre.ipynb           # Notebook principal (Colab)
├── Relatorio_GS_DynamicProgramming.pdf  # Relatório técnico
├── README.md                            # Este arquivo
├── habilidades_base.json                # Dataset de habilidades
├── resultados_completos.txt             # Resultados dos 5 desafios
├── resultados_visualizacoes.png         # Gráficos gerados
└── grafo_dependencias.png               # Visualização do grafo
```

---

## Instalação e Uso

### Google Colab (Recomendado)

1. Acesse o notebook no Google Colab
2. Execute: `Executar → Executar tudo`
3. Aguarde ~30 segundos para conclusão

### Ambiente Local

```bash
# Clone o repositório
git clone https://github.com/equipe-optimind/global-solution-moh.git
cd global-solution-moh

# Instale dependências
pip install matplotlib numpy jupyter

# Execute o notebook
jupyter notebook gs_dynamic_2semestre.ipynb
```

---

## Desafios Implementados

### Desafio 1: Caminho de Valor Máximo
- **Técnica:** Programação Dinâmica (knapsack multidimensional)
- **Complexidade:** O(2^n · n) com n=12
- **Resultados:** Valor=45, Tempo=340h, Complexidade=28
- **Monte Carlo:** E[V] = 48.7 ± 2.5 (1000 simulações)

### Desafio 2: Verificação Crítica
- **Técnica:** Enumeração de 120 permutações
- **Complexidade:** O(n! · n²)
- **Resultados:** Top 3 ordens com custo 550h

### Desafio 3: Pivô Mais Rápido
- **Técnicas:** Guloso O(n log n) vs Ótimo O(2^n · n)
- **Resultados:** Guloso=Ótimo no dataset real
- **Contraexemplo:** Demonstração de falha do guloso

### Desafio 4: Trilhas Paralelas
- **Técnica:** Merge Sort implementado
- **Complexidade:** O(n log n) em todos os casos
- **Resultados:** Sprint A (6 básicas) + Sprint B (6 avançadas)

### Desafio 5: Recomendações
- **Técnica:** DP com horizonte temporal (5 anos)
- **Complexidade:** O(T · 2^n · n) com memoização
- **Top 3:** H12 (IoT), H10 (Segurança), S2 (SQL)

---

## Tecnologias

- **Python 3.10** — Linguagem principal
- **Google Colab** — Ambiente de execução
- **Bibliotecas:** itertools, collections, random, statistics, matplotlib

**Algoritmos:**
- DFS (Detecção de Ciclos) — O(V + E)
- Kahn (Ordenação Topológica) — O(V + E)
- DP (Knapsack Multidimensional) — O(2^n · n)
- Monte Carlo — O(k · 2^n · n)
- Merge Sort — O(n log n)

---

## Resultados

| Desafio | Algoritmo | Tempo | Otimalidade |
|---------|-----------|-------|-------------|
| D1 - Determinístico | DP | 0.016s | ✓ Ótimo |
| D1 - Monte Carlo | Simulação | 18.42s | ✓ Robusto |
| D2 - Permutações | Força Bruta | 0.005s | ✓ Completo |
| D3 - Guloso | Heurística | 0.0001s | ⚠ Depende |
| D4 - Merge Sort | Div. & Conquista | 0.00004s | ✓ Estável |
| D5 - Recomendações | DP Temporal | 0.032s | ✓ Ótimo |

---

## Referências

1. Cormen et al. (2022). *Introduction to Algorithms* (4th ed.). MIT Press.
2. Winston (2021). *Operations Research: Applications and Algorithms*. Cengage.
3. Bellman, R. (1957). *Dynamic Programming*. Princeton University Press.
4. Kahn, A. B. (1962). "Topological sorting of large networks". *CACM*.

---

## Licença

Este projeto está licenciado sob a **MIT License**.

---


*FIAP — Engenharia de Software — 2º Semestre/2025*