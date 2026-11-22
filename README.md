# Sudoku Metaheuristics

Este repositório reúne as implementações e os resultados experimentais do Trabalho de Conclusão de Curso (TCC) sobre a comparação de três meta-heurísticas na resolução de instâncias de Sudoku 9×9.

## Algoritmos

- **IPSO** (*Integer-valued Particle Swarm Optimization*)
- **ACO** (*Ant Colony Optimization*)
- **GA** (*Genetic Algorithm*)

## Protocolo experimental

Foram avaliadas 15 instâncias coletadas no [Sudoku.com](https://sudoku.com/br), com cinco tabuleiros em cada nível de dificuldade — fácil, médio e difícil — conforme a classificação da plataforma.

Cada algoritmo foi executado dez vezes por instância, com sementes de 0 a 9, totalizando 450 execuções. Os três algoritmos utilizaram a mesma função de aptidão, baseada na contagem de pares conflitantes nas linhas, nas colunas e nos blocos 3×3. Uma aptidão igual a zero indica uma solução válida.

Cada execução teve um orçamento máximo de 400.000 avaliações da função objetivo. O contador registra as chamadas à função de aptidão sobre tabuleiros completos. No ACO, os cálculos de conflitos locais orientam a construção dos tabuleiros e entram no tempo de execução, ficando fora desse contador.

A comparação considera a taxa de sucesso, a média e o desvio-padrão da aptidão final e as medianas do número de avaliações e do tempo de execução.

## Resultados

O ACO foi o único algoritmo a encontrar soluções válidas. A taxa de sucesso foi de 66% no nível fácil (33 de 50 execuções), 66% no médio (33 de 50) e 6% no difícil (3 de 50). O ACO obteve a menor aptidão média nas 15 instâncias e apresentou tempos medianos superiores aos do IPSO e do GA em todas as instâncias médias e difíceis.

## Implementação

Os algoritmos foram implementados em Python e executados no Google Colab. O código utiliza NumPy e os módulos `random`, `copy` e `time` da biblioteca padrão do Python.

## Estrutura do repositório

- `IPSO_Sudoku.ipynb` — implementação e execução do IPSO
- `ACO_Sudoku.ipynb` — implementação e execução do ACO
- `GA_Sudoku.ipynb` — implementação e execução do GA

## Autor

Gabriel Marques — Trabalho de Conclusão de Curso, IFMG Campus Sabará.
