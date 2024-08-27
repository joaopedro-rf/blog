---
title: "Busca Binária (Binary Search)"
date: "2024-08-26"
---

Neste artigo, abordaremos o algoritmo de busca binária, que é fundamental para buscar elementos de forma eficiente em estruturas de dados ordenadas. Para melhor compreensão, começaremos com o conceito de busca linear.

### BUSCA LINEAR

A busca linear é o método mais simples: percorremos todos os elementos de um array até encontrar o valor desejado. Por exemplo, ao procurar a palavra "Jogador" em um dicionário, folheamos de página em página até encontrá-la. Embora funcional, esse método é ineficiente para grandes conjuntos de dados, pois pode exigir muitas comparações.

### BUSCA BINÁRIA

A busca binária, por outro lado, é mais eficiente, mas só funciona em arrays ordenados. O algoritmo divide o array ao meio repetidamente, eliminando metade dos elementos a cada iteração até encontrar o valor desejado.

## Exemplo de Busca Binária:#

Considere o array ordenado:
[1, 3, 4, 5, 6, 7, 8, 9, 10]  
Para encontrar o número 9:

- **Primeira divisão:** O elemento no meio é 5, que é menor que 9. Portanto, descartamos a metade inferior do array. O novo array é
  [6, 7, 8, 9, 10]
- **Segunda divisão:** O elemento no meio é 8, que é menor que 9. Portanto, descartamos a metade inferior do novo array. O novo array é
  [9, 10]
- **Terceira divisão:** O elemento no meio é 9, que é igual ao alvo. Encontramos o valor desejado.

Assim, a busca binária localiza o número em apenas 3 passos, em vez das 8 iterações necessárias na busca linear, demonstrando sua eficiência.

### COMPARAÇÃO COM A BUSCA LINEAR

Na busca linear, o pior caso ocorre quando o alvo é o último item da lista, exigindo a verificação de todos os elementos. Por exemplo, em um array de 100 elementos, seriam necessárias até 100 verificações.

Na busca binária, o número de etapas necessárias é determinado pelo logaritmo base 2 do tamanho do array. Isso porque, a cada etapa, o array é reduzido pela metade. Vamos ilustrar isso:

- Para um array de 100 elementos:
100 -> 50 -> 25 -> 12 -> 6 -> 3 -> 1 
6 etapas

Portanto, no pior caso, a busca binária encontra o alvo em apenas 6 etapas, comparado às 100 etapas da busca linear.

### GENERALIZAÇÃO E NOTAÇÃO BIG O

Para generalizar, o número de tentativas na busca linear é proporcional ao número de elementos nnn do array, ou seja, O(n). Já na busca binária, o número de tentativas pode ser calculado usando o logaritmo base 2 de nnn, resultando em O(log n). O cálculo do número de etapas na busca binária é uma consequência da divisão repetida do array.

## Por que usamos o logaritmo base 2?

O logaritmo base 2 responde à pergunta: "Quantas vezes podemos dividir o número nnn por 2 até restar apenas 1 elemento?" Isso reflete a maneira como a busca binária reduz o tamanho do problema pela metade em cada iteração.

### Código Java para Busca Binária

Aqui está uma implementação em Java do algoritmo de busca binária:
```
public static Integer binarySearch(int\[\] arr, int alvo) {
  int esquerda = 0;
  int direita = arr.length - 1;

  while (esquerda <= direita) {
  int pivo = esquerda + (direita - esquerda) / 2;

  if (arr\[pivo\] == alvo) {
    return pivo; // Encontrou o alvo
  } else if (arr\[pivo\] > alvo) {
    direita = pivo - 1; // Procura na metade inferior
  } else {
  esquerda = pivo + 1; // Procura na metade superior
    }
  }
return -1; // Alvo não encontrado
}

```
### CONCLUSÃO

A notação Big O permite comparar a eficiência de diferentes algoritmos. A busca binária, com complexidade O(log n), é muito mais eficiente para arrays grandes do que a busca linear, com complexidade O(n). No próximo artigo, exploraremos mais sobre a notação Big O e como ela se aplica a diferentes algoritmos.
