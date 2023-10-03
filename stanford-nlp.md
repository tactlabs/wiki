/ [Home](index.md)


# StanfordNLP
## stanford NLP :
- used for building models in other languages
- stanford NLP librabry can support more than 53 human languages
- collection of pre-trained state-of-art models
- models are built on pytorch and can be trained with our own data
- core NLP(official wrapper)

## setup: stanford NPL:

```

conda create -n stanfordnlp python=3.7.1

source activate stanfordnlp

pip install stanfordnlp

import stanfordnlp

stanfordnlp.download('en')

```

- language model size: english: 1.96 GB
## error possibilities:
- older version of pytorch might crash
- check pytorch version:  
    ```
    pip freeze | grep torch
    ```
- non gpu machine will throw a memory error

## pipelines
- sequence of data processing tasks and algorithm(while tokenization)
- processors:
    - tokenization
    - mwt
    - lemma
    - pos
    - depparse

## tokenization

- gives particular tokens to parts of sentences
- contains index,list of words(if multi word token)
- all word objects contains useful info(index,lemma,pos tag, morphological features)

## lemmatization
- lemma property of words(root word of a particular word)
- .lemma method gives the lemma of each word

## pos
- pos(parts of speech) tagger gives the parts of speech property of a word in a sentences
- ex: could: modal verb, for: preposition

## dependency extraction

- gives the grammatical relationship  between words in sentence
- sentence.print_dependencies()

## stanford nlp for hindi language:

```
stanfordnlp.download('hi')
```

## core_nlp
- time tested
- industry grade
- performance 
- accuracy

### setup(core_nlp)
```
    wget http://nlp.stanford.edu/software/stanford-corenlp-full-2018-10-05.zip

    unzip stanford-corenlp-full-2018-10-05.zip

    java -mx4g -cp "*" edu.stanford.nlp.pipeline.StanfordCoreNLPServer -port 9000 -timeout 15000
```
- export $CORENLP_HOME as the location of your folder(to amke sure stanfordnlp knows location of core_nlp):
```
export CORENLP_HOME=stanford-corenlp-full-2018-10-05/
```


## annotators:
- read the text
- locate target entities
- highlight them
- predetermine list of labels
    ('tokenize','ssplit','pos','lemma','ner','depparse','coref'):
        ssplit: sentence split(dividing text into sentences)
        ner: named entity recognition(categorize parts of sentence)
        depparse: dependency parsing(outputs based on dependency extraction)
        coref: coreference resolution(finds mentions of the same entity in text, ex: 'deepika may' and 'she may', refers to the same entity: deepika)

## Dependency Parsing and POS:
- print(dependency_parse)
- print(token.pos)

## Named Entity Recognition and Co-Reference Chains:
- print(token.ner)
- print(ann.corefChain)

## Pros and Cons:

### Pros:
- multiple languages
- goin to be official python interface(improves functionality and easy to use)
- fast
- straightforward setup in python

### cons:
- large language models
- quickly scripting prototype is not possible
- missing visualizing features
