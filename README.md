The [HistWords](https://nlp.stanford.edu/projects/histwords/) project by William L. Hamilton, Jure Leskovec, and Dan Jurafsky produced a series of historical Word2Vec embeddings. This repository includes a converted version of the "All English (1800s-1990s)" trained on [Google N-Grams eng-all](http://storage.googleapis.com/books/ngrams/books/datasetsv2.html). The versions included are in the Google Word2Vec C format, which can be loaded into [gensim](https://radimrehurek.com/gensim/).


Usage:
```
from gensim.models import KeyedVectors

model = KeyedVectors.load_word2vec_format('KeyedVectors/1970-sm.bin', binary=True)
model.most_similar('gay')
```
The [HistWords KeyedVectors example](https://github.com/nealcaren/histwords2vec/blob/main/HistWords%20KeyedVectors%20example.ipynb) notebook includes a few more examples.

I have included my conversion script as a [Jupyter Notebook](https://github.com/nealcaren/histwords2vec/blob/main/Translate%20HistWords%20to%20Word2Vec.ipynb). In addition to changing the file format, I also remove words without vectors in a given decade. Each of the original files has 100,000 words, although the number of words with vectors varies from 13,045  in 1800 to 71,097. Removing the rows filled with 0s shrinks the keyed vector files enough to be redistributed on GitHub.
