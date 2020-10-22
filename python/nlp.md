I've been working with linguistic analysis a lot lately. It turns out that this is not super easy

## Word Tokenization

Word tokenization is a surprisingly difficult problem. For example, what is the tokenization of "it's"?
90% of the functionality is implemented in `nltk.tokenize.word_tokenize` [link](https://www.nltk.org/api/nltk.tokenize.html#nltk.tokenize.punkt.PunktLanguageVars.word_tokenize).

I also learned that `string.punctuation` does not actually contain all punctuation, and misses many common unicode punctuation marks such as fancy quotes.

## Word Cloud

I love word clouds! There is a nice python package that can generate them, and even computes bigrams! [link](https://github.com/amueller/word_cloud)
