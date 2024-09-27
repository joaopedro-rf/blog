---
title: "Array"
date: "2024-09-27"
---

Nesta artigo, falaremos sobre Arrays, ou vetores. Um array é uma estrutura de dados usada para armazenar múltiplos valores de maneira que seja fácil acessá-los por um índice.

Pense em uma máquina de vendas automáticas. Ela armazena diversos itens em compartimentos numerados e com uma capacidade fixa. Essa é a essência de um array: uma estrutura que armazena elementos em posições indexadas, de tamanho fixo, definido no momento de sua criação.
```
public class Item {
    public String nome;
    public float preco;

    public Item(String nome, float preco) {
        this.nome = nome;
        this.preco = preco;
    }

    @Override
    public String toString() {
        return this.nome + ", custa " + this.preco;
    }
}

Item[] maquinaDeVendas = new Item[20]; // Criação de um array com 20 posições
```

Aqui criamos uma máquina de vendas que pode armazenar até 20 itens.

```
Item cocaCola = new Item("Coca Cola", 8.50);
maquinaDeVendas[5] = cocaCola; // Adicionando um item na 5ª posição
System.out.println(maquinaDeVendas[5]); // "Coca Cola, custa 8.50"
```

Os arrays têm um tamanho pré-definido, que não pode ser alterado depois de sua criação. Os elementos ocupam posições de 0 a N-1, uma convenção da maioria das linguagens de programação.

# CAPACIDADE DO ARRAY

Quando iniciamos o array, precisamos passar a capacidade, como por exemplo

```
Item[] array = new Item[10];
System.out.println("A capacidade do array é: " + array.length); // Capacidade: 10
```

Não podemos acessar posições fora do intervalo definido, como array[11], o que causaria uma exceção `ArrayIndexOutOfBoundsException`.

# TIPOS DE OPERAÇÕES

Os arrays suportam três operações principais:
- **Inserção** de um novo elemento
- **Leitura** de uma posição específica
- **Deleção** de um elemento específico

# INSERÇÃO

### No final  do array

Inserir no final é simples, desde que haja espaço:

```
int[] array = new int[6];
int tamanho = 0;

for(int i = 0; i < 5; i++) {
    array[tamanho] = i;
    tamanho++;
}
```

![Array de exemplo base](https://raw.githubusercontent.com/joaopedro-rf/blog/refs/heads/main/public/ArtigoArray/Array1.png)

```
array[tamanho] = 5; // Adiciona o 5 na última posição
tamanho++;
```

![Inserção no final do array](https://raw.githubusercontent.com/joaopedro-rf/blog/refs/heads/main/public/ArtigoArray/Array2.png)

> Se tentarmos adicionar mais um elemento, receberemos um erro, pois o array tem tamanho fixo.

### No início do array

Inserir no início exige deslocar todos os elementos uma posição à frente, o que tem custo O(N), já que cada posição precisa ser atualizada.

```
for(int i = 4; i >= 0; i--) {
    array[i + 1] = array[i];
}
array[0] = 5; // Insere 5 no início
```

![Inserção no início do array](https://raw.githubusercontent.com/joaopedro-rf/blog/refs/heads/main/public/ArtigoArray/Array3.png)

### No meio do array

```
for(int i = 5; i > 3; i--) {
    array[i + 1] = array[i];
}
array[3] = 5; // Insere o valor 5 na posição 3
```
![Inserção no meio do array](https://raw.githubusercontent.com/joaopedro-rf/blog/refs/heads/main/public/ArtigoArray/Array4.png)

> Novamente, os elementos à frente precisam ser movidos para liberar espaço.

![Inserção no meio do array](https://raw.githubusercontent.com/joaopedro-rf/blog/refs/heads/main/public/ArtigoArray/Tabela.png)

# CONCLUSÃO

Arrays são estruturas úteis, mas têm limitações devido ao seu tamanho fixo e ao custo de operações de inserção, especialmente quando há necessidade de realocar os elementos. Para usos mais dinâmicos, estruturas como listas podem ser mais adequadas, que será o assunto abordado no próximo artigo.


