# Notebooks

Worked, runnable notebooks. Each one renders directly on this site (code, markdown, and saved
outputs), and can also be downloaded and run locally or in Colab.

All notebooks here build the same running example: separating a Higgs boson signal
(&rarr; two leptons) from a top-quark-pair background, using 26 physics-motivated features per
event.

<div class="card-grid" markdown>

<div markdown>
### DNN for HEP: PyTorch Lightning
Rebuilds the classifier with a `LightningModule`, a `LightningDataModule`, and a `Trainer` —
covering how each piece of a manual PyTorch training loop maps onto Lightning's structure.

[Open notebook &rarr;](DNN4HEP_lightning.ipynb)
</div>

<div markdown>
### DNN for HEP: Improved
The same classifier, with the ML-workflow basics filled in: fixed seeds, device handling, a
baseline, a small hyperparameter search, a confusion matrix, threshold/significance analysis, and
model saving.

[Open notebook &rarr;](DNN4HEP_improved.ipynb)
</div>

</div>

## Adding a new notebook

1. Drop the `.ipynb` file into `docs/notebooks/`.
2. Add it to the `nav` section of `mkdocs.yml` under **Notebooks**.
3. (Optional) Add a card for it on this page.

Notebooks are rendered as-is via the [`mkdocs-jupyter`](https://github.com/danielfrg/mkdocs-jupyter)
plugin, including any saved outputs (plots, tables, printed metrics) &mdash; they are **not**
re-executed at build time (`execute: false` in `mkdocs.yml`), so make sure a notebook has been run
and saved with the outputs you want to show before adding it here.
