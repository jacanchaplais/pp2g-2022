# Learning flow tracing with GNNs {
data-background-image='img/bg/jason-leung_3.jpg'
data-background-opacity=0.35
}

## Message passing {
data-background-image='img/bg/jason-leung_3.jpg'
data-background-opacity=0.35
}

Feature vectors are made up of 4-momenta and charge,

$$
\mathbf{v}^i = \begin{bmatrix}E^i & p_x^i & p_y^i & p_z^i & Q^i\end{bmatrix}^T
$$
{#eq:node_feats}

and edges are formed within a radius of $\Delta R = R_0$

$$
A_{ij} = \begin{cases}
1 & \Delta R_{i j} < R_0
\\
0 & \text{else}
\end{cases}
$$
{#eq:connectivity}

Message passing is used to create embeddings of nodes based on community
structure, and regression is used to predict flow tracing of particles
from ancestors.

## Results{
data-background-image='img/bg/jason-leung_3.jpg'
data-background-opacity=0.35
}


<div class="tenor-gif-embed" data-postid="15372563" data-share-method="host" data-aspect-ratio="1.77778" data-width="100%"><a href="https://tenor.com/view/tumbleweed-silence-no-answer-anyone-there-echo-gif-15372563">Tumbleweed Silence GIF</a>from <a href="https://tenor.com/search/tumbleweed-gifs">Tumbleweed GIFs</a></div> <script type="text/javascript" async src="https://tenor.com/embed.js"></script>
