# Finding Frames in Parliament: Computational Framing Analysis of UK House of Commons Speech

_Abstract_ – Media framing analysis is an important tool for political communication researchers, providing an insight into how issues are being talked about and how this varies over time. Computational framing analysis seeks to automate a traditionally manual task, facilitating the identification of frames at scale. This report proposes a novel approach to this task, with the primary aim of identifying frames in a corpus of UK parliamentary speech (Hansard). The approach builds on previous attempts and utilises cutting-edge transformer methods to embed and cluster texts from the corpus. From these clusters, candidate frames are extracted in the form of 'sub-clusters' of texts and associated descriptions (consisting of statistically distinctive and semantically meaningful words contained in the texts). This flexible, modular approach is shown to extract meaningful intra-topic linguistic variation, some examples of which can be identified as frames, while others appear to be sub-topics. This successful computational frame analysis of Hansard–a broad and varied corpus–represents an improvement on the state of the art.

Code is available online at https://github.com/bendennes/hansard-nlp

## Code Execution Guidance

* Please run the notebooks in numbered order
* All code (in the form of Jupyter notebook files) is self-contained; all data required is downloaded from a web server by the first notebook (1_hansard_get_speeches.ipynb)
* Due to the size of the dataset and the computational complexity of certain operations, running the entire pipeline (all six notebooks) can take many hours. The slowest step is notebook 4 (4_lda.ipynb) which creates 44 LDA models and the 44 corresponding coherence models, and then calculates the C_V coherence (an accurate but computationally intensive coherence metric). For this reason, cell outputs have been included to give the marker a guide to the general expected outputs at each stage, 
* Please run notebooks 1 to 3 with [version 4.0.0](https://radimrehurek.com/gensim/) of the gensim package, and [version 3.8.3](https://radimrehurek.com/gensim_3.8.3/) for notebooks 4 to 6. This is due to v4.0.0's superior performance when generating n-grams in notebook 3, but the requirement for a gensim wrapper for the MALLET implementation of LDA in steps 4 to 6 (this functionality was deprecated in v4.0.0 due to lack of maintenance, but is functional in v.3.8.3).

## Required non-standard packages

Please use most up-to-date version as of 1 June 2021 (except gensim, as outlined above)

Python packages:
* [spacy](https://spacy.io/usage)
* [gensim](https://pypi.org/project/gensim/)
* [umap-learn](https://umap-learn.readthedocs.io/en/latest/)
* [sentence-transformers](https://pypi.org/project/sentence-transformers/), requires:
	* PyTorch 1.6.0 or higher
	* transformers 4.6.0 or higher
* [hdbscan](https://pypi.org/project/hdbscan/)

The Java-based package [MALLET](http://mallet.cs.umass.edu/) is also required 