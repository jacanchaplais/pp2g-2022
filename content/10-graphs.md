# Why graphs? {
data-background-image='img/bg/pawel-czerwinski_7.jpg'
data-background-opacity=0.5
}

Introduction to graph structured data and analysis.

## Graph definition {
data-background-image='img/bg/pawel-czerwinski_7.jpg'
data-background-opacity=0.5
}

Graphs are minimally comprised of two pieces of information:

1. Set of data points, known as _nodes_ or _vertices_ $V$
2. Set of relations between points, known as _links_ or _edges_ $E$

$$
G = \left( V, E, u \right) \text{ or } G\left( V, E, u \right)
$$
{#eq:graph_def}

Edges between nodes can be described by an adjacency matrix,
$$
A_{ij} = \begin{cases}
1 & \exists \; v_j \in \mathcal{N}(v_i)
\\
0 & \text{else}
\end{cases}
$$
{#eq:adj_def}
where $\mathcal{N}(v_i)$  is the neighbourhood of
node $v_i$. The adjacency matrix is therefore a sparse binary matrix of
order $|V| \times |V|$.

## Images are graphs {
data-background-image='img/bg/pawel-czerwinski_7.jpg'
data-background-opacity=0.5
}


:::::::::::::: {.columns}
::: {.column width="55%"}

<iframe width="500px" height="500px" src="img/fig/img-graph.html" frameborder="0" allowfullscreen=""></iframe>

:::
::: {.column width="45%"}

![Image convolution operation.](img/fig/conv-anim.gif)

:::
::::::::::::::


## Generalising the update {
data-background-image='img/bg/pawel-czerwinski_7.jpg'
data-background-opacity=0.5
}


:::::::::::::: {.columns}
::: {.column width="55%"}

<iframe width="500px" height="500px" src="img/fig/graph.html" frameborder="0" allowfullscreen=""></iframe>

:::
::: {.column width="45%"}

![
Each node has bespoke computation.
Applies order invariant `agg` func over neighbours,
then embeds with `update` func.
](img/fig/comp_graph.svg)

:::
::::::::::::::


## Edges are powerful {
data-background-image='img/bg/pawel-czerwinski_7.jpg'
data-background-opacity=0.5
}

Edges can do more than just hold parametrised weights: they can model
pairwise relations.
These can be embedded, just like the nodes.

$$
\mathbf{e}^{(l)}_{s r} = \operatorname{ACT}(\mathbf{W}_e^{(l)} \cdot [
\mathbf{v}_r^{(l - 1)}
|| \mathbf{v}_s^{(l - 1)}
|| \mathbf{e}_{s r}^{(l - 1)}
])
$$
{#eq:edge_embed}

The learned edge features can then be aggregated to form _messages_, to
update the nodes.

$$
\mathbf{v}_r^{(l)} = \operatorname{ACT}(\mathbf{W}_v^{(l)} \cdot
[ \mathbf{v}_r^{(l - 1)}
|| \operatorname{AGG}(
\{\mathbf{e}_{s r}^{(l)}, \forall v_s \in \mathcal{N}(v_r)\})
])
$$
{#eq:node_embed}
