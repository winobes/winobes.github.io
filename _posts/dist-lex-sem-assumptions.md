

So I'm going to write about some common assumptions made in distributional lexical semantics that are particularly relevant to my topic of research.

[Distributional lexical semantics](https://en.wikipedia.org/wiki/Distributional_semantics) is a family of methods for estimating the meaning of words based on their distribution (in relation to other words) in actual usage.
Often this means you're using a large corpus of text to learn some geometric or vector representation of meaning. 

Word2Vec is probably the best know distributional model for lexical semantics.
I'm not trying to write a big criticism of Word2vec here, but I'll use it as a bit of foil to make some of the assumptions I'm highlighting more concrete, so it's worth saying a few words about what it is.

For each word in its vocabulary, the Word2vec learns a real-valued vector of (typcially) a couple hundred dimensions.
If you're not familiar with word vectors, you'd be right to wonder how a _numerical vector_ could possibly represent the _meaning of a word_.
Suffice it to say that Word2vec vectors have some very nice properties that suggest they capture _at least some_ aspects of meaning.
Perhaps most significantly, words similar in meaning map to similar (in terms of Euclidean distance) vectors.
And famously, Word2vec vectors in particular have some [very nice](https://www.technologyreview.com/s/541356/king-man-woman-queen-the-marvelous-mathematics-of-computational-linguistics/) and sometimes [not so nice](https://arxiv.org/abs/1607.06520) results when it comes to completing analogies.

There are a couple different learning algorithms for Word2vec, but the gist of it is that the model computes these vectors by learning to predict words based on their context (i.e., the other words they appear with).

### Historic semantic change

To train a Word2vec model, you give it a big old corpus of text written in the language you want it to learn meanings for. 
But as we know, language changes over time. The meanings of words change. 
So the vectors you get out estimate not so much the meaning of words at a given time, as some _average_ meaning over whatever time period the corpus is from.
And a corpus might span years or decades. 
Word2vec is commonly trained text from Wikipedia articles, which often contain text written at many different times, and where it's non-trivial to track what was written when.

In a [previous post]({% post_url 2018-03-18-word-embeddings-semantic-shift %}) I wrote about some work that uses this to its advantage to track changes in meaning over time by training Word2vec (and other distributonal semantic models) on texts from different time periods.

### Semantic adaptation 

Not only do the meaing of words change over time, they can also change _during a dialogue_. 
This can happen either _explicitly_ (you and I agree we're going to use a certain word to mean a certain this we need to talk about) or _implicitly_ (the way we use a word reenforces a certain interpretation).

### Speech community 

This is one of my favorites.

We usually think of _a language_ as something like _Spanish_, _Arabic_, or _Italian_, but of course each of those languages has many dialects where some words may have different meanings and there may be some words that don't exist at all in other dialects.
Beyond dialects, you can find even more fine grained differences in word meaning.
Electricians have their own special lexicon, as do people who live in London, and (probably) your group of friends or immediate family.

All these different nested and overlapping speech communities use words in subtly (and sometimes significantly) different ways. 
And that social context has an effect on meaning.

### Linguistic style

### Homonymy / Polysemy
