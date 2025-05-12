# Otimização do Problema da Mochila com PSO Binário

## Integrantes da Equipe

* Larissa Hoffmann
* Lukas Thiago
* Mateus Akira
* Matheus Gabriel

## Objetivo

Implementar e testar o algoritmo bio-inspirado PSO Binário (Particle Swarm Optimization) para resolver o Problema da Mochila 0/1, considerando diferentes tamanhos de instâncias, e realizar uma avaliação do desempenho.

## 🧠 Algoritmo Utilizado

O algoritmo utilizado é o **PSO Binário**, uma variação do Particle Swarm Optimization, adaptada para problemas com variáveis discretas (0 ou 1). Cada partícula representa uma possível seleção de itens para a mochila e "voa" pelo espaço de soluções, ajustando suas escolhas com base nas melhores soluções já encontradas por ela e pelo grupo.

## Modelagem do Problema

### Lista de Pesos e Valores

* Cada item possui um peso (inteiro aleatório entre 1 e 50) e um valor (entre 10 e 100).

### Capacidade da Mochila

* É definido como 40% da soma total dos pesos.

### Representação das Soluções

* Vetor binário: cada posição indica se o item correspondente foi incluído (1) ou não (0).

---

## Implementação do Algoritmo

### Funções Utilizadas

* `avaliar`: Calcula o valor total dos itens selecionados, penalizando se o peso total exceder a capacidade.
* `sigmoid`: Função de ativação para binarização das soluções.
* `pso_mochila`: Executa o algoritmo PSO Binário, com atualização de velocidade e posições conforme as equações do PSO tradicional.

### Operadores PSO

* Inércia (w), atração cognitiva (c1), atração social (c2).
* Binarização com probabilidade gerada pela função sigmoide.

---

## Avaliação das Soluções

### Penalização

* Soluções com peso total acima da capacidade recebem valor 0.

### Função de Aptidão

* Soma total dos valores dos itens selecionados (se válida).

### Métricas Comparadas

* Valor total (fitness), peso final, tempo de execução, histórico de melhoria.

### Complexidade

* Tempo de execução por iteração: O(n \* p), onde:

  * *n*: quantidade de itens
  * *p*: número de partículas
  * Para *i* iterações: O(n \* p \* i)

---

## Execução e Testes

### Parâmetros Utilizados

* 100 itens (aleatórios), 5 execuções, 50 iterações, 30 partículas.

### Exemplos de Entrada/Saída

* **Entrada:**

  * Lista de pesos: `[10, 22, 17, ...]`
  * Lista de valores: `[50, 80, 45, ...]`
  * Capacidade: `842`
* **Saída:**

  * Valor total obtido: `1378`
  * Peso da mochila: `827`
  * Solução binária: `[1, 0, 1, ...]`

### Resultados

* Melhor valor global: `1410`
* Pior valor obtido: `1284`
* Média das execuções: `1345.6`

### Gráfico

* Apresentado o histórico de melhoria da 1ª execução usando `matplotlib`.

---

## Dificuldades e Aprendizados

### Dificuldades

* Binarização eficiente da velocidade.
* Manter a diversidade das soluções.
* Ajustar penalidades sem eliminar boas soluções por pouco excesso de peso.

### Aprendizados

* PSO é eficaz mesmo com busca estocástica.
* Importância da função de aptidão e dos parâmetros.
* Modularização do código facilita testes e manutenção.

---

## Sugestões para Testes Futuros

* Testar com 1000 e 10.000 itens.
* Implementar outras abordagens bio-inspiradas (GA, ABC, ACO).
* Usar análise estatística para consolidar os resultados.

---

## Execução

```bash
python pso_mochila.py
```

Certifique-se de ter o pacote `matplotlib` instalado:

```bash
pip install matplotlib
```
