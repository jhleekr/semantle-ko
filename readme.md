# 꼬오맨틀 — 단어 유사도 추측 게임

이 레포지터리는 Johannes Gätjen의 [Semantlich](http://semantlich.johannesgaetjen.de/)
([소스코드](https://github.com/gaetjen/semantle-de))를 포크하여,
한국어로 플레이할 수 있도록 수정한 버전인 [꼬맨틀](https://semantle-ko.newsjel.ly/) ([소스코드](https://github.com/NewsJelly/semantle-ko))을
원하는 만큼 플레이할 수 있도록 만든 버전입니다.

### Setup

Download Word2Vec and dictionary data:
```bash
cd data
wget https://dl.fbaipublicfiles.com/fasttext/vectors-crawl/cc.ko.300.vec.gz
gzip -d cc.ko.300.vec.gz
wget https://github.com/spellcheck-ko/hunspell-dict-ko/releases/download/0.7.92/ko-aff-dic-0.7.92.zip
unzip ko-aff-dic-0.7.92.zip
```

Filter and save word2vec in DB
```bash
python filter_words.py
python process_vecs.py
```

Start server
```bash
gunicorn main:app
```