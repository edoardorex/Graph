# Graph Algorithms

An educational Python implementation of directed graphs, depth-first search, and
strongly connected components. The project explores how graph size and edge
density affect the number of strongly connected components.

## What is included

- Adjacency lists backed by `collections.defaultdict`.
- Recursive depth-first traversal.
- Graph transposition and a two-pass, Kosaraju-style SCC traversal.
- Random edge generation and Matplotlib experiments.

| File | Purpose |
| --- | --- |
| [graph.py](graph.py) | `Graph`, traversal methods, and a small demonstration function |
| [testSCC.py](testSCC.py) | SCC experiments with fixed and increasing vertex counts |

## Getting started

The original source requires **Python 2.7**; its `print` statements are not
Python 3 syntax. Matplotlib is needed for the plotting script, but not for the
graph class itself. Python 2 is end-of-life: use an isolated legacy environment
for historical experiments rather than a production installation.

From the repository root:

```sh
python2 -c "from graph import provaClasse; provaClasse()"
python2 testSCC.py
```

The second command runs both experiments and opens their plots. Traversal
results are also printed to the terminal.

## Example

```python
from graph import Graph

graph = Graph(5)
graph.addEdge(0, 1)
graph.addEdge(1, 2)
graph.addEdge(2, 0)
graph.addEdge(2, 3)
graph.addEdge(3, 4)
component_count = graph.printSCCs()
```

Vertices are integer indices from `0` to `V - 1`. DFS is recursive, so large
graphs may require attention to the interpreter's recursion limit. The experiment
scripts are exploratory benchmarks, not an automated correctness test suite.

## Project provenance

This repository is a fork of [edoardore/Graph](https://github.com/edoardore/Graph).
The original implementation and history are preserved; this README documents
the code currently included in the fork.
