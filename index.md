---
layout: page
title: Content
---

# What, When, Where, Who?

This tutorial will present a **practical** introduction to
the most important succinct data structures, tools, and applications
with the intent of providing the researchers with a jump-start into
this domain. The focus of this tutorial will be efficient text processing 
utilising space efficient representations of suffix arrays,
suffix trees and searchable integer compression schemes with
specific applications of succinct data structures to
common NLP tasks such as n-gram language modelling.

It will be held on **Monday 9am-12pm, the 12th of December 2016**, in **Osaka, Japan** in conjunction with [COLING 2016](http://coling2016.anlp.jp/).

The tutorial will be presented by [Matthias Petri](http://github.com/mpetri/) and [Trevor Cohn](http://people.eng.unimelb.edu.au/tcohn/) of 
the [University of Melbourne](http://unimelb.edu.au).

# Prerequisites

The practical, "hands-on" parts of this tutorial will be based on the popular [Succinct Data Structure Library (SDSL)](http://github.com/simongog/sdsl-lite/). The library contains highly optimised implementations of most practical succinct structures. You can
install the library on Mac and Linux operating systems using the following commands:

{% gist mpetri/f076fbcc59612787dbfe216228364930 %}


The library requires the following software packages:

* git version control
* make and cmake build systems
* a recent C++ compiler with C++11 support (clang++ or g++)

After installing the library you can test if your setup works correctly buy compiling on of the sample programs included in the library:

{% gist mpetri/8502a79ab731d8911aa1bd683b9485ce %}


# Schedule

The three tutorial is organised as follows:

### 1. Introduction and Motivation (15 Minutes)

In the first session we motivate the need for succinct structures. We discuss existing applications and examples in IR and NLP, and benefits of succinct structures when facing terabyte scale text processing problems.

### 2. Basic Technologies (20 Minutes)

In the second session we give a brief introduction into the theoretical foundation of succinct data structures. We discuss the concept of bitvectors, data compression and basic RANK and SELECT on bitvectors which are at the core of most succinct data structures. Next we introduce several
simple succinct structures such as a succinct tree representation (LOUDS) and
variable size, constant access time, integer representations (DAC).


### 3. Index based Pattern Matching (20 Minutes)

In the next session we start the tutorial by briefly revisiting several classical search indexes such as Suffix Arrays and Suffix Trees which can provide search functionality used in many NLP applications. We then introduce the notation of a Compressed Suffix Array (CSA), which substantially reduces the space requirement of a Suffix Array while providing the same functionality.

###  <span style="color:blue"> 4. Break (20 Minutes)</span>

### 5. Compressed Suffix Arrays/Tree Internals: How does it all work (40 Minutes)

This session covers the underlying technical principals of compressed suffix arrays. This includes concepts such as the Burrows-Wheeler Transform, backward search and wavelet trees. We further extend the concept of compressed suffix arrays to compressed suffix trees (CST). This includes additional structures to represent the shape of the tree as well as additional operations supported by the CST which are important for several NLP applications.

### 6. Utilising CSA and CST in the context of Language Models (20 Minutes)

This session will cover our line of research on unlimited order language modelling with modified Kneser-Ney smoothing. Efficient methods for storing and querying language models are critical for scaling to large corpora and high Markov orders.  At its core, our approach uses a compressed suffix tree of text which provides near optimal compression while supporting efficient search. We present algorithms for on-the-fly computation of probabilities under a Kneser-Ney and Modified Kneser-Ney language models. Our approach is exact and on par with  leading language modelling toolkits in terms of speed while being several order of magnitudes smaller.


### 7. Other applications of Succinct Structures in NLP (10 Minutes)

The last session briefly touch on advanced succinct structures consisting of Range Minimum / Maximum Queries, Succinct Tries, Treaps and 2D-range query structures.


# Practical Exercises

## Exercise 1: Direct-Accessible Variable-Length Codes (DAC)

## Exercise 2: Building a CSA and CST over words

## Exercise 3: Fancy counts


# Resources and References

* Gonzalo Navarro. Compact Data Structures -- A practical approach. Cambridge University Press, 570 pages, 2016 ([website](https://www.dcc.uchile.cl/~gnavarro/CDSbook/))

* Giuseppe Ottaviano. Succinct -- Alternative Succinct Data structure library ([website](https://github.com/ot/succinct))

* Ehsan Shareghi, Matthias Petri, Gholamreza Haffari and Trevor Cohn -- [Fast, Small and Exact: Infinite-order Language Modelling with Compressed Suffix Trees](http://aclweb.org/anthology/Q/Q16/Q16-1034.pdf) TACL 2016

* Ehsan Shareghi, Matthias Petri, Gholamreza Haffari and Trevor Cohn -- [Compact, Efficient and Unlimited Capacity: Language Modeling with Compressed Suffix Trees](http://aclweb.org/anthology/D/D15/D15-1288.pdf) EMNLP 2015
