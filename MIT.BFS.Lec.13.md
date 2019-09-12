# [MIT.Breadth First Search ⤇ ⭆ ⇛ ➟ ➠](https://youtu.be/s-CYnVz-uh4?list=PLUl4u3cNGP61Oq3tWYp6V_F-5jb5L2iHb)

## Graph Search

- Explore a Graph
- Find a Path from a node `S` to node `T`

### What is a Graph

- `V` = `set of vertices`
- `E` = `set of Edges` `≈` `e = {v,w} ∈ E` where `{v,w}` could be
  - _un-ordered - `un-directed graph`_
    - _`A ⎻ B ⎻ C ⎻ A` un-directed graph `V = {A, B, C, D}, E = {(A,B), (B,C), (C,A)}`_
  - _ordered - `directed graph`_
    - _`A ➟ B ➟ C ➟ B` - directed graph `V = {A, B, C, D}, E = {(A,B),(B,C),(C,B)}`_

### Applications (BFS mainly)

- Web Crawling
- Social Networking
- Network Broadcast
- Garbage Collection
- Model Checking
- Checking Mathematical Conjectures
- Solving Puzzles  / Games

> Rubic cube's possible states (Vertices) = `8!.3ˆ8` = `264,539,520`
> Every move can be represented as un-directed graph as you can move back from a move to the previous one

### Diameter of a Graph

- _It is the greatest distance between any pair of vertices_
- _To find the diameter of a graph, first find the shortest path between each pair of vertices_
  - _The greatest length of any of these paths is the diameter of the graph_

## Graph Representation

### Adjacency List

- _Array `Adj` of size `|V|`. Where `V` - is the set of ALL the vertices_
- _As element in the `Array` is a `pointer` to a `Linked-List`_
- _This `Array` is indexed by a `vertex`, `u ∈ V` ➠ `Adj[u]`_
- _For every vertex we store it's neighbors in the corresponding LinkedList_

> `Neighbors` are mainly the vertices that can be reached in one step_

- _`Adj[u]` `≈` `{v ∈ V | (u,v) ∈ E}`_

#### Example

- _`A ➟ B ➟ C ➟ B ➟ A` - directed graph_
  - _`Adj[B] = {C,A}`_
- __
