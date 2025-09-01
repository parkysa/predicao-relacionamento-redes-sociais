# Predição de Relacionamento em Redes Sociais

Este projeto é uma implementação em C de algoritmos para predição de relacionamentos em redes sociais, baseado em um exercício-programa da disciplina de Algoritmos e Estruturas de Dados II. A ideia principal é calcular diferentes métricas que mensuram a potencial relação entre os indivíduos de uma rede social, representada por um grafo.

## Estrutura do Grafo

O projeto representa uma rede social como um grafo não direcionado, onde os vértices são pessoas e as arestas indicam uma amizade. Além da estrutura de amizades, cada pessoa (vértice) possui um perfil com 10 características, que são utilizadas para calcular as métricas de predição de relacionamento.

A estrutura de dados utilizada para representar o grafo da rede social em `ep1.c` é a seguinte:

```c
typedef struct {
    int numVertices;
    int numArestas;
    bool** matriz;
    int** caracteristicas;
} Grafo;
```

## Principais Conceitos

As seguintes métricas são implementadas para analisar a probabilidade de um novo relacionamento ser formado a partir de um vértice `v`:

* **Homofilia**: Calcula o número de interesses e características em comum entre duas pessoas. A premissa é que quanto mais semelhanças, maiores as chances de se relacionarem.
* **Raridade**: Pondera as características em comum pela sua raridade na rede. Interesses raros compartilhados têm um peso maior, pois tendem a se destacar.
* **Influência Social**: Mede como as características de um indivíduo são influenciadas pelos seus amigos. Uma característica compartilhada com muitos amigos de uma pessoa pode ser um forte indicador para novos relacionamentos.
* **Amizades em Comum**: Baseia-se no princípio de que quanto mais amigos em comum duas pessoas têm, maior a probabilidade de elas se tornarem amigas.
* **Proximidade Social**: Calcula a distância (menor caminho) entre as pessoas no grafo social. Pessoas mais próximas na rede têm um relacionamento em potencial.
* **Conexão Preferencial**: Pessoas com mais conexões (mais populares) tendem a atrair novos relacionamentos mais facilmente. Esta métrica corresponde ao grau de cada vértice.
