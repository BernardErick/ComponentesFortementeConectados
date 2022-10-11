Aplicação em grafos usando SCC

- Um grafo direcionado é fortemente conexo se existe um caminho entre todos os pares de vértices. Um componente fortemente conectado ( SCC ) de um grafo direcionado é um subgrafo maximal fortemente conectado. Por exemplo, existem 3 SCCs no gráfico a seguir.

![alt text](https://media.geeksforgeeks.org/wp-content/cdn-uploads/SCC.png)

- Usa o algoritmo de Kosaraju

1) Crie uma `pilha vazia 'S'` e faça o `percurso DFS` de um grafo. No percurso DFS, depois de chamar o DFS recursivo para vértices adjacentes de um vértice, dê o `push` no vértice para empilhar. No grafo acima, se iniciarmos o DFS a partir do vértice 0, obteremos vértices na pilha como 1, 2, 4, 3, 0.
   
2) `Inverta` as direções de todos os arcos para obter o `gráfico de transposição`.
   
3) De um por um use o `pop` nos vértices de S enquanto o S não for vazio. Deixe o vértice obtido pelo `pop` ser 'v'. Aplique o DFS em 'v' (chame DFSUtil(v) ). O DFS a partir de v imprime o componente fortemente conectado de v. No exemplo acima, processamos os vértices na ordem 0, 3, 4, 2, 1 (um por um retirado da pilha). 

