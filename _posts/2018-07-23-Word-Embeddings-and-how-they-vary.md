---
layout: post
title: Word embeddings and how they vary
author: Laura Wendlandt
author_link: https://wendlandt.github.io
comments: true
tags: natural-language-processing word-embeddings language machine-learning
---


Consider for a moment the complexity of human language. Humans can effortlessly process nuanced expressions such as simile (“cool as a cucumber”), sarcasm (“Just great! I failed that test”), and allusion (“don’t be such a Scrooge”). Our vocabulary is also changing -- in March 2018, 850 new words were added to the Merriam-Webster Dictionary, including “cryptocurrency” and “chiweenie” (a cross between a Chihuahua and a dachshund). 

{% include figure.html url="/assets/2018-07-23/chiweenie.png" description="New vocabulary word of the day: chiweenie photo credit: thehappypuppysite.com" %}

Even the same word can mean different things in different contexts. Consider the word bar:

<ul>
<li>After work, the man went to go get a drink at the <b>bar</b>.</li>
<li>This is a really tasty chocolate <b>bar</b>!</li>
<li>The recent law school graduate just passed his <b>bar</b> exam.</li>
<li>The beginning ballet students held onto the <b>bar</b> for balance.</li>
</ul>

<figure align="center"><img src="/assets/2018-07-23/chocolate_bar.png"><figcaption align="center"><small><i>A <b>bar</b> that serves chocolate <b>bars</b>? Oh, the ambiguity!</i> (photo credit: <a href="http://web.eecs.umich.edu/~mazab/">Mahmoud Azab</a>)</small></figcaption></figure>

Given all of this complexity, how is a computer system supposed to understand words and language? Answering this question is a major goal within the field of natural language processing (NLP). When we input a word into a computer, we would ideally like the computer to understand the meaning of that word, as well as its common usage and properties. For example, given the word “cat,” we want a computer to understand that a cat is an animal, that it has fur and four legs, that it’s commonly kept as a household pet, etc. We also want it to understand how each word interacts with other words -- cats like to sunbathe and catch mice and boss around their personal servants (er, owners). We also want to know that a cat is more similar to a dog, for instance, than it is to a car. A dictionary provides some of this information, but it also omits many practical details, due to its brevity.

How else can we get information about a word? One way is to look at the context of the word (the surrounding words). As an example, let’s suppose that we’ve come across a word we’ve never seen before: <b>theraw</b>. Here are a few sentences for this new word:
<ul>
<li>What delicious <b>theraw</b>!</li>
<li>I wish that I could make <b>theraw</b> the way that she makes it.</li>
<li><b>theraw</b> was the perfect ending to a satisfying meal.</li>
</ul>

After seeing these sentences, we have a pretty good guess about what the word <b>theraw</b> means - it’s probably some kind of special dessert. We know this because <b>theraw</b> is described as “delicious”, a word typically associated with food. We also see <b>theraw</b> discussed in the context of a meal (specifically the end of a meal), and we see an example of someone making <b>theraw</b>, again an action that can be associated with food. Furthermore, we have seen other words that we know appear in very similar sentences (e.g., “What delicious pie!”), so we can deduce that <b>theraw</b> is probably related to these other words.

In short, if we want to gather meaningful information about a particular word, the words surrounding that word are a very good place to start. This context-based approach is a key concept behind word embeddings, a popular idea in computer science right now. Essentially, a word embedding is a group of numbers that represents a word. There are different ways to generate word embeddings, but almost all of them use context to extract meaningful information about a word. We can think about a word embedding as a single point somewhere in space. When you look at many of these individual “points” together, you can see how they interact. For example, consider this famous illustration

{% include figure.html url="/assets/2018-07-23/king-queen.png" description="[photo credit: Jaron Collis on Quora]" %}

Here, we can see four points in space, representing king, queen, man, and woman. The location of each point (the word embedding) is determined by the particular group of numbers associated with that word. We can also see that the relationship between king and queen is almost identical to the relationship between man and woman! This tells us that the word embeddings are capturing some analogy information from the words -- king is to queen as man is to woman. Here’s another example:

{% include figure.html url="/assets/2018-07-23/capital.png" description="[photo credit: Jaron Collis on Quora]" %}

Here, we see word embeddings of countries and capital cities. Lines are drawn between each country and its capital city, and we can see that the relationship between countries and their capitals is very similar across multiple countries. This is exciting because it shows us that word embeddings are capturing meaningful information about the words.

So what are the applications of word embeddings? For any word, researchers have at their disposal a word embedding that captures meaningful information drawn from the context of the words. This gives a computer system the ability to better understand word meanings, which is useful in lots of other tasks. For example, word embeddings can be used to perform more precise translations between languages or to more accurately summarize long documents. Researchers use embeddings to predict the sentiment (happy or sad) of a piece of writing and to classify articles into certain categories (e.g., news or sports or entertainment).

To create such word embeddings, we generally use very large collections of texts, which capture how different words occur in different contexts. Of course, this raises the question whether the embeddings that we create depend in any way on the collection being used. Are we getting the same embeddings from a large collection versus a small collection? Or from a collection of texts on sports, versus a collection of texts on arts?

To answer these questions about different text sources, I, along with my collaborators Rada Mihalcea and Jonathan Kummerfeld, have recently been analyzing word embeddings. One of the things we found is that word embeddings change if you use different collections of text as input. This is because words tend to have different contexts when they are used to discuss different topics. For example, consider the following two sentences using the word <b>power</b>, one from the Arts section of the NYT and one from the Sports section of the NYT:

Arts: Eric Owens, a bass, offered a fine balance of gentleness and <b>power</b> in Raphael's music in parts 1 and 3, and as Adam in part 5.

Sports: What has never been in doubt is that Clarett is a special athlete, a thrilling combination of <b>power</b> and speed.

Though the same word, <b>power</b>, is being used in both sentences, it is being used in different ways. In the first sentence, power denotes strength of voice, while in the second sentence, power denotes strength of body. Many words have different connotations when used to talk about different topics. Because of this, changing the collection of text changes the word embeddings produced. This has implications for how word embeddings are used - if a researcher is using embeddings to summarize documents about art, then it will be more effective to use embeddings trained on a collection of texts about art, rather than a collection of texts about sports. For more details, as well as results from other embedding experiments, take a look at our paper (in references below).

Word embeddings are a powerful tool to help computers understand language better. Having a better understanding of how these embeddings work will help us create more effective embeddings, and handle more complex language in a computer system!

If you’re interested in learning more about word embeddings, check out the following resources:

<i><b>Blog Posts</b></i><br/>
“On Word Embeddings - Part 1” by Sebastian Ruder [<a href="http://ruder.io/word-embeddings-1/">link</a>]<br/>
“Deep Learning, NLP, and Representations” by Christopher Olah [<a href="http://colah.github.io/posts/2014-07-NLP-RNNs-Representations/">link</a>]<br/>

<i><b>Textbooks</b></i><br/>
<u>Speech and Language Processing (3rd ed. draft)</u> by Dan Jurafsky and James H. Martin - Chapter 15, “Vector Semantics”; Chapter 16, “Semantics with Dense Vectors” [[link](https://web.stanford.edu/~jurafsky/slp3/)] <br/>
<u>Natural Language Processing</u> by Jacob Eisenstein - Chapter 14, “Distributional and Distributed Semantics” [[link](https://github.com/jacobeisenstein/gt-nlp-class/blob/master/notes/eisenstein-nlp-notes.pdf)]<br/>
<u>Neural Network Methods for Natural Language Processing</u> by Yoav Goldberg - Chapter 10, “Pre-trained Word Representations”; Chapter 11, “Using Word Embeddings” [[link](https://www.morganclaypool.com/doi/abs/10.2200/S00762ED1V01Y201703HLT037)] <br/>

<i><b>Code for Word Embeddings</b></i><br/>
“Word2vec Tutorial” by Radim Řehůřek [[link](https://rare-technologies.com/word2vec-tutorial/)]<br/>
“GloVe: Global Vectors for Word Representation” by Jeffrey Pennington, Richard Socher, and Christopher D. Manning [[link](https://nlp.stanford.edu/projects/glove/")]<br/>
“Quora: Where can I find some pre-trained word vectors for natural language processing/understanding?” [[link](https://www.quora.com/Where-can-I-find-some-pre-trained-word-vectors-for-natural-language-processing-understanding)]<br/>

<i><b>Research Papers</b></i><br/>
<i>[our paper]</i> Wendlandt, Laura, Jonathan K. Kummerfeld, and Rada Mihalcea. "Factors Influencing the Surprising Instability of Word Embeddings." NAACL-HLT (2018). [[link](http://wendlandt.github.io/papers/naacl18embeddings.pdf)]<br/>
Camacho-Collados, Jose, and Taher Pilehvar. "From Word to Sense Embeddings: A Survey on Vector Representations of Meaning." arXiv preprint arXiv:1805.04032 (2018). [[link](https://arxiv.org/abs/1805.04032)]<br/>
