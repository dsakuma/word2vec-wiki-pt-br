### Files

| Files | Description |
|--------|-------------|
|process_wiki.py| Process the xml format wikipedia to text format |
|train_word2vec_model.py| Train the pt-br wikipedia word2vec model |
|WikipediaWord2Vec.ipynb| Sample notebook |

### Instructions

1. Build Docker image
```console
docker-compose build
```

1. Download Wikipedia pt-br dump
```console
curl https://dumps.wikimedia.org/ptwiki/latest/ptwiki-latest-pages-articles.xml.bz2 --create-dirs -o data/ptwiki-latest-pages-articles.xml.bz2
```

1. Process Wikipedia dump
```console
docker-compose run jupyter python src/process_wiki.py data/ptwiki-latest-pages-articles.xml.bz2 data/wiki.pt-br.text
```
1. Train Model
```console
docker-compose run jupyter python src/train_word2vec_model.py data/wiki.pt-br.text data/wiki.pt-br.word2vec.model
```

1. Run notebook
```console
docker-compose up -d
```

Access notebook: [localhost:8888](http://localhost:8888)


### Reference:
http://textminingonline.com/training-word2vec-model-on-english-wikipedia-by-gensim
