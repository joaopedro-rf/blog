---
title: "Big O"
date: "2024-08-27"
---

A notação Big O é uma forma de medir como o tempo de execução de um algoritmo cresce à medida que o tamanho do seu input aumenta. Diferentes algoritmos possuem tempos de execução distintos, e a notação Big O nos ajuda a generalizar esses tempos para podermos aplicá-los a diferentes situações.

Mas como podemos generalizar o tempo de execução de um algoritmo? Quais são as variáveis que interferem nesse problema?

A notação Big O não mede diretamente o tempo de execução em si, o tempo de execução real de um algoritmo depende de fatores como o clock do processador e a arquitetura da máquina, tornando difícil fazer uma generalização exata. No entanto, podemos comparar algoritmos observando como o tempo de execução deles cresce à medida que o número de elementos aumenta.
Por exemplo, como vimos no caso dos algoritmos de busca simples e busca binária, o tempo de execução de ambos cresce de maneira diferente. Mas o que isso significa?

### COMPLEXIDADE CONSTANTE O(1)

O menor tempo de execução que um algoritmo pode ter é O(1), também chamado de complexidade constante. Isso significa que o algoritmo sempre levará o mesmo tempo para ser executado, independentemente do tamanho do input. Um exemplo clássico de operação O(1) é acessar um elemento específico em um array, pois essa operação não depende do tamanho do array.

### COMPLEXIDADE LINEAR O(n)

A busca linear, por outro lado, tem complexidade O(n), o que significa que o tempo de execução cresce linearmente com o tamanho do input. Em uma lista de 10 elementos, serão necessárias até 10 iterações no pior caso para encontrar o elemento desejado. Em uma lista de 100 elementos, serão necessárias até 100 iterações, e assim por diante.

### COMPLEXIDADE LOGARÍTMICA O(log n)

Já a busca binária, que discutimos anteriormente, tem complexidade O(log n). Isso significa que o tempo de execução cresce de forma muito mais lenta em comparação com O(n), pois o algoritmo reduz o tamanho do problema pela metade a cada iteração.
Considere o seguinte exemplo:
Em uma lista com 10 elementos, a busca linear requer até 10 iterações, enquanto a busca binária requer apenas 3.
Em uma lista com 100 elementos, a busca linear requer até 100 iterações, enquanto a busca binária ainda requer apenas 7.
Em uma lista com 1000 elementos, a busca linear requer até 1000 iterações, enquanto a busca binária requer apenas 10.
Em uma lista com 10.000 elementos, a busca linear requer até 10.000 iterações, enquanto a busca binária requer apenas 14.

### COMPLEXIDADE O(n log n)

A complexidade O(nlogn) é comum em algoritmos de ordenação eficientes, como o Merge Sort e o Quick Sort. Esses algoritmos utilizam uma abordagem que divide o problema em partes menores, resolve cada uma delas separadamente e depois combina as soluções.

No caso do Merge Sort, o algoritmo divide o array pela metade até que cada parte tenha apenas um elemento, e então começa a combinar essas partes ordenadamente. Esse processo de divisão ocorre em log n passos, porque a cada passo, o array é dividido pela metade. Já o processo de combinação requer O(n) operações para cada nível de divisão, resultando em uma complexidade total de O(n log n).
A maioria das linguagens possuem implementações de algoritmos de sort nativamente, é preciso consultar a documentação para saber como é feita, mas no geral, a complexidade é O(n log n).

### COMPLEXIDADE O(n^2)

Algoritmos de complexidade O(n^2) como o Bubble Sort, Insertion Sort, e Selection Sort, são menos eficientes para grandes conjuntos de dados. Nesses algoritmos, o tempo de execução aumenta quadraticamente com o tamanho do input, porque cada elemento do array é comparado com todos os outros elementos. Este tipo de complexidade é considerado ineficiente para grandes inputs, porque o número de operações aumenta rapidamente à medida que o tamanho do input cresce.

### IDENTIFICANDO A COMPLEXIDADE

Pode ser um exercício complexo no início e requer um pouco de prática, as dicas e cortes de caminho são: procure por loops e investigue quantas vezes eles serão executados, constantes e complexidades menores são ignoradas, se seu código tiver um algoritmo que passa por um array com n posições, 2 vezes, não terá complexidade O(2 x n), apenas de O(n), e se nesse mesmo código houver algo mais complexo como um Quick Sort, será ignorado a complexidade de O(n) e passa a valer apenas o O(n log n) por ser mais custoso.

### CONCLUSÃO

Como você pode ver, o crescimento do tempo de execução de um algoritmo depende da forma como ele processa os dados. O gráfico que representa o número de operações em função do tamanho do input mostra claramente que algoritmos com complexidade O(log n) crescem muito mais lentamente do que aqueles com complexidade O(n).

![Gráfico das curvas de complexidade do Big O](https://web.stanford.edu/class/archive/cs/cs106b/cs106b.1244/lectures/08-bigo/resources/big-o-compare.png)
[Fonte do Gráfico](https://web.stanford.edu/class/archive/cs/cs106b/cs106b.1244/lectures/08-bigo/)

Dessa forma, a notação Big O nos permite comparar a eficiência de diferentes algoritmos em termos de como seu tempo de execução aumenta à medida que o tamanho dos dados cresce, ajudando a escolher a melhor solução para um problema específico. Irei falar mais sobre complexidade de execução durante a série de artigos relacionados a algoritmos e estrutura de dados, essa foi apenas uma introdução para que faça ao menos algum sentido quando citar a notação Big O nos próximos capítulos.
