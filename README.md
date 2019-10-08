# SimulPynk

/!\ still a work in progress ! wear a helmet ... /!\

SimulPynk is a package designed to allow the user to create compute graphs python.
Modulo an understanding of how steps are handelled, it can also allow you to make simulation like [Simulink]
Its name is by the way greately inspired by its big brother.
It comes with a graph execution engine, opperators and very soon multiprocessing.
You can see it as a way to create declaratively series of transformations over data in python (like excel's formulae).

(https://en.wikipedia.org/wiki/Simulink) and even translate your blocks diagrams in python.
Must of all it was designed for robotics and implementation of control loops but you can use it for whatever you want  ^_^.

## what is a compute graph ?

### waT THe HeLL iS A GRapH ???
The short anwser is [here](https://en.wikipedia.org/wiki/Graph_(discrete_mathematics)).
(I would probably direct my attention to [directed acyclic graphs (DAG)](https://en.wikipedia.org/wiki/Directed_acyclic_graph). (<-you see what I did there ^_^))
### DAG + Operators = Compute Graph !
[Data processing graphs](https://en.wikipedia.org/wiki/Directed_acyclic_graph#Data_processing_networks)

## What's included
### the graph class
A graph object represent a dataflow graph. It's created then filled declaratively :

```python
g = ComputeGraph(),
import math
def B(t,c,d):
  return math.cos(t)+c-(d*t)
g.add(Operators.add("A B"))
g.add("B",B)
g.add(lambda A,B: A+B, "addAB")
g.add(lambda t: math.cos(t),"A")
```
