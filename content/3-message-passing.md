# Learning embeddings with message passing {
data-background-image='img/bg/jason-leung_3.jpg'
data-background-opacity=0.35
}

## Message passing {
data-background-image='img/bg/jason-leung_3.jpg'
data-background-opacity=0.35
}

Message passing allows nodes to communicate (update each other) via edges.

1. Data on adjacent nodes, plus edge data, concat'd with each other
2. Run through trainable NN layer $\to$ new edge embedding
3. All edges incident on node concat'd and run through another NN layer
4. Permutation invariant aggregate, _eg._ sum, mean, _etc._, forms message
5. Message concat'd with node data, then run through NN for node embedding

:::notes
- might ask about why I'm using simulation data

- precision is defined as the ratio of true positive predictions against
  the sum of true positive and false positive predictions.
- Recall is defined as the ratio of true positive predictions against
  the total number of positive examples.

:::


## Promising results {
data-background-image='img/bg/jason-leung_3.jpg'
data-background-opacity=0.25
}

- Interaction networks learn relations between particles
  ^[Unusual, as high dimensional edge embeddings learned for this, leading to
  high memory and computational costs]
    - JEDI-Net for jet tagging [@moreno_2019; @duarte_2020]
    - Boosted W-boson clustering [@ju_2020]
- Attention based GNNs improve background rejection [@mikuni_2020]
- Initial work to reproduce results of [@ju_2020], but research now
  pivoting towards attention based techniques, and variational graph
  autoencoders (VGAEs) [@kipf_2016]


## Interaction network clustering results {
data-background-image='img/bg/jason-leung_3.jpg'
data-background-opacity=0.25
}


:::::::::::::: {.columns}
::: {.column width="45%"}

![
Precision and recall for our network.
](img/fig/prec_rec.svg){#fig:my_prec_rec}

:::
::: {.column width="52%"}

|              | Threshold | 0.1     | 0.5     | 0.8     |
| ------------ | --------- | ------: | ------: | ------: |
| This work    | Precision | 0.239   | 0.598   | 0.837   |
|              | Recall    | 0.969   | 0.845   | 0.664   |
| Ju _et al._  | Precision | 0.715   | 0.908   | 0.960   |
|              | Recall    | 0.965   | 0.896   | 0.824   |

: Comparing precision and recall scores {#tbl:prec_rec}

:::
::::::::::::::
