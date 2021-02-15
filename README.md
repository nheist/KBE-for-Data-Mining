# Evaluation of Knowledge Graph Embeddings on Data Mining Tasks

This code is part of a larger work that compares typical knowledge graph embeddings for Data Mining (e.g. RDF2vec) with those for Link Prediction (e.g. TransE). A link to the preprint will be provided here as soon as it is available.

Here, we compare RDF2vec with several Link Prediction approaches (TransE, TransR, RotatE, DistMult, RESCAL, ComplEx) on the following Data Mining tasks:

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

The provided notebook shows how to generate the embedding vectors for the Link Prediction approaches using DGL-KE (alternatively, you can download the trained embedding vectors [here](http://data.dws.informatik.uni-mannheim.de/KBE-for-Data-Mining/)). The generated vectors then simply have to be run in GEval to produce the final evaluation results.