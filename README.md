# Evaluation of Knowledge Graph Embeddings on Data Mining Tasks

This code is part of a larger work that compares typical knowledge graph embeddings for Data Mining (e.g. RDF2vec) with those for Link Prediction (e.g. TransE). A version of the paper that is currently being reviewed is available [here](http://www.semantic-web-journal.net/system/files/swj2892.pdf).

Here, we compare embedding approaches that are orignally designed for Data Mining (RDF2vec, Node2vec, DeepWalk) with Link Prediction approaches (TransE, TransR, RotatE, DistMult, RESCAL, ComplEx) on the following Data Mining tasks:

- Classification
- Clustering
- Regression
- Semantic Analogies
- Document Similarity
- Entity Relatedness

All these tasks are based on entities of the [DBpedia 2016-10](https://wiki.dbpedia.org/downloads-2016-10) dataset. Consequently, we use this dataset to create our embedding vectors.

To produce the embedding vectors and evaluate them on the mentioned Data Mining tasks, we use the following frameworks:

- [KGvec2go](http://kgvec2go.org) to retrieve embedding vectors for RDF2vec
- [DGL-KE](https://github.com/awslabs/dgl-ke) to train embedding vectors for Link Prediction approaches
- [GEval](https://github.com/mariaangelapellegrino/Evaluation-Framework) to evaluate the generated embedding vectors on Data Mining tasks

## Preparations

### Software Prerequisites
- Clone the GEval repository: `git clone git@github.com:mariaangelapellegrino/Evaluation-Framework.git evaluation_framework`
- Install the requirements: `pip install -r evaluation_framework/requirements.txt` (you may want to use a virtual environment)

### Retrieving the Data
Download the embedding vectors for all approaches (RDF2vec, Node2vec, DeepWalk, KGlove, RDF2vec<sub>oa</sub> TransE, TransR, RotatE, DistMult, RESCAL, ComplEx) [here](http://data.dws.informatik.uni-mannheim.de/KBE-for-Data-Mining/) and put them into the `data` folder.

Alternatively, you can use [this notebook](embedding-vector-generation.ipynb) to train the embedding vectors of the link prediction approaches on your own. But note that it takes multiple hours on a GPU to train embedding vectors of a single approach due to the large size of the DBpedia dataset. So you have to plan 3-4 days for the generation of all embedding vectors.

## Running the Evaluation
To run the evaluation framework with the embedding approaches, use [this notebook](run-embedding-evaluation.ipynb). If you are using virtual environments, make sure that the notebook runs in the same environment where the dependencies of GEval are installed.