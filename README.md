# Resolvedor do Jogo 'Queens' do LinkedIn com IA

Projeto acadêmico desenvolvido para a disciplina de **Sistemas Inteligentes (2026/1)**. O objetivo é construir um pipeline completo que converte capturas de tela (*printscreens*) do jogo *Queens* do LinkedIn em matrizes digitais e resolve o enigma utilizando algoritmos de busca determinística e meta-heurísticas estocásticas.

## 📐 O Problema e a Justificativa
Diferente do problema clássico das 8-Rainhas, a variação do LinkedIn introduz restrições dinâmicas de adjacência diagonal e agrupamentos de cores de formatos arbitrários que mudam a cada tabuleiro. Este projeto serve como um ambiente de testes ideal para analisar o impacto dessas condições de contorno na complexidade do espaço de estados e avaliar a eficiência de convergência de diferentes classes de algoritmos.

## 🔄 Fluxo de Processamento (Pipeline)
O sistema opera em 5 etapas sequenciais:
1. **Aquisição de Imagens:** Carga das 14 imagens brutas capturadas do jogo.
2. **Pré-processamento e Recorte:** Isolamento automatizado da Região de Interesse (ROI) do tabuleiro $8 \times 8$ usando filtros de escala de cinza, binarização (*threshold*) e detecção de contornos via **OpenCV**.
3. **Mapeamento do Tabuleiro:** Extração dos pixels centrais das 64 células e aplicação do algoritmo **K-Means (Scikit-Learn)** para segmentar as 8 cores e gerar a matriz estática de adjacências.
4. **Execução dos Modelos:** Modelagem do espaço de estados em um vetor compacto de 8 elementos para o processamento das restrições pelos algoritmos de busca.
5. **Resultados:** Extração quantitativa de métricas de desempenho.

## 🛠️ Algoritmos Implementados
Para fins de análise comparativa, o problema é submetido a duas naturezas de abordagens:

* **Métodos Determinísticos:**
    * Busca em Largura (BFS)
    * Busca em Profundidade (DFS)
    * Busca Gulosa (*Greedy Best-First Search*)
    * Busca Heurística ($A^*$)
* **Meta-heurísticas Não-Determinísticas (Estocásticas):**
    * Algoritmo Genético (AG)
    * Recozimento Simulado (*Simulated Annealing* - SA)

## 📊 Métricas de Avaliação
O desempenho de cada modelo é validado a partir de três critérios principais:
- Geração de curvas de convergência da função de custo ao longo do tempo.
- Contagem exata do número de iterações necessárias para encontrar a solução (zero conflitos).
- Aplicação de métricas estatísticas descritivas (média simples e desvio padrão) sobre os resultados obtidos.

## 📂 Estrutura do Repositório
- `/imagens_tabuleiro`: Amostra com os 14 prints dos tabuleiros reais do LinkedIn utilizados nos testes.
- `main.ipynb`: Notebook principal contendo as funções de visão computacional, modelagem matemática da função de custo, implementação dos 6 algoritmos e plotagem dos gráficos de desempenho.
