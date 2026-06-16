# Resolvedor do Jogo 'Queens' do LinkedIn com IA

Projeto desenvolvido para a disciplina de **Sistemas Inteligentes (2026/1)**. O objetivo é criar um sistema capaz de ler capturas de tela (prints) do jogo "Queens" do LinkedIn, mapear o tabuleiro e encontrar a solução ideal utilizando algoritmos de busca e otimização.

## 🛠️ Tecnologias e Algoritmos Utilizados
- **Python 3**
- **OpenCV & Scikit-Learn (K-Means):** Para segmentação de imagem e agrupamento das 8 regiões de cores do tabuleiro.
- **Busca Heurística (Algoritmo A*):** Para exploração de estados e resolução lógica do problema.
- **Algoritmo Genético:** Para otimização evolucionária e busca da combinação de rainhas com zero conflitos.

## 📂 Estrutura do Repositório
- `/imagens_tabuleiro`: Contém os prints dos tabuleiros do LinkedIn utilizados para testes.
- `main.ipynb`: Código principal de processamento (notebook).
