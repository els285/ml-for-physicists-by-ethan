# Introduction 

Notebooks I have put together over the years. 


## How to use

The notebooks render directly on this site but you can't run them interactively here.
The recommended way to run the notebooks is through Google Colab: each notebook has a link which will open the notebook in Google Colab.
Alternatively, click the link at the top of each notebook to download it. You can then run locally e.g. in VSCode provided you have a suitable iPython kernel and the necesasry Python modules installed. [Every module is pip-installable anyway but I will soon make some instructions on modern ways to set up Python environments.]



<div class="card-grid" markdown>

<div markdown>
### Tensors
Introduces PyTorch tensors &mdash; what they are and how to create, index, and manipulate them &mdash;
as the foundation for everything that follows.

[Open notebook &rarr;](Tensors.ipynb)
</div>

<div markdown>
### Linear Regression with Scikit-Learn
1D and multi-input linear regression on the penguins dataset, then a first step into logistic
regression, using `scikit-learn`.

[Open notebook &rarr;](Regression_Penguins_SKlearn.ipynb)
</div>

<div markdown>
### Linear Regression with PyTorch
Repeats the same regression problem in PyTorch instead of `scikit-learn`, as a stepping stone
towards building neural networks.

[Open notebook &rarr;](Regression_Penguins_PyTorch.ipynb)
</div>

<div markdown>
### Classifying Penguins
A quick classification problem on the penguins dataset &mdash; a precursor to the main DNN exercise
below.

[Open notebook &rarr;](Classification_Penguins.ipynb)
</div>

<div markdown>
### DNN for HEP: PyTorch
Builds a PyTorch binary classifier DNN to separate a Higgs boson signal (&rarr; two leptons) from a
top-quark-pair background, using 26 physics-motivated features per event.

[Open notebook &rarr;](DNN4HEP_exercise.ipynb)
</div>

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
