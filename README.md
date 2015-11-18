# jointreps
Joint Word Representation Learning using a Corpus and a Semantic Lexicon

This software implements the joint word representation learning method proposed in the AAAI-2016
submission titled "Joint Word Representation Learning using a Corpus and a Semantic Lexicon".

Requirements
============

1. The source code is in ./src/reps.cc and is written in C++. You will need C++0x supported compiler 
    to compile the source.

2. The code uses the Eigen library. (http://eigen.tuxfamily.org/index.php?title=Main_Page)
    If you have your path variables properly configured in the C++
    compiler, it should be able to read the library from the current location, without having to
    install the Eigen library. If you do not wish to install Eigen, then simply copy the source code of
    Eigen into a directory named 'eigen' at the same level as 'src'.

The code is implemented and tested only on Ubtuntu Linux. It might not compile/run on other platforms
without further configurations.

Installation
============
Go to ./src and type 
make

Example
=======

A small co-occurrence matrix containing 100k elements is provided in ./work/edges.sample.
A Makefile is provided that trains word representations using synonym relation. To run this type

make run
which will internall call

./reps --dim=300 --epohs=20 --model=../work/model --alpha=0.01 --lmda=10000 --edges=../work/edges.sample  --pairs=../work/synonyms

Here, 
--dim 
    is the dimensionality of the word vectors,

--epohs
     is the maximum number of iterations,

--alpha 
    is the initial learning rate in AdaGrad,

--lmda 
    is the regularization coefficient in the proposed method,

--edges 
    is the co-occurrence matrix, and

--pairs 
    is the lexicon file (8 relation types provided in ./work)

The learnt word representations will be written to ./work/model, specified by --model.

