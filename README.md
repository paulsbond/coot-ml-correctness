# coot-ml-correctness

Coot ML Correctness script that uses machine learning to predict the correctness of protein residues

From the menu, go to `Calculate -> Run Script` and select
[correctness.py](https://raw.githubusercontent.com/paulsbond/coot-ml-correctness/master/correctness.py).

This will create two new menu items under `ML Correctness`.
The `GUI` item opens a new window that lists all chains, residues and side chains along with their correctnesss scores.
The `Prune` item automatically prunes the model using the default options of the prune function.

The prune function is also available via scripting with the following signature:
```python
prune(
    imol,
    imap,
    imap_diff,
    chains=True,
    chain_threshold="auto",
    max_chain_fraction=0.2,
    max_chain_length=20,
    residues=True,
    residue_threshold="auto",
    max_residue_fraction=0.2,
    remove_isolated_residues=True,
    sidechains=True,
    sidechain_threshold="auto",
    max_sidechain_fraction=0.2,
)
```
The `chains`, `residues`, and `sidechains` arguments control whether whole chains, residues and side chains are deleted.
The `max_*_fraction` arguments specify the maximum proportion of residues or sidechains to delete.
The `*_threshold` arguments specify the maximum correctness score to delete.
`*_threshold="auto"` defaults to 0.2 times the median for chains and 0.5 times the median for residues and side chains.

The script has been tested using Coot 0.8.9.2.  
