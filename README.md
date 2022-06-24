# Translating Text Across Time

### Introduction

This is the software archive for the code for my Individual Project at Imperial College. In order to work, this software needs to be used in parallel with the files proviced separately, which consist of the parallel corpus, the historical embedding representation and some saved models.

Each of the following files have the following function
- NeuralMachineTranslator.ipynb: Provides a Neural Machine Translator that can be trained if it is given a parallel translation corpus. In the latest cells of the file, the translation attempts to perform translation across time if it is given the path to the embeddings for the source language and the ones for the target language. 
- AnalyzeData.ipynb: Able to get a set of words and plot them in a two-dimensional plan according to their embeddings. The closer the words are in the space, the closer they are in context 
- Word2WordTranslator.ipynb: Word-level translator, which trains the master function _translate_ where the input word is translated to from an input language and an input year to another language of another year. This file also provides a function for the volatility of the word (how much a word is susceptible to change over time). More details about these can be found in the thesis

### Assembling the project

In order for the files to identify the paths correctly, this repository needs to be cloned to a folder of which the "ProjectSoftwareArchiveFiles" folder belongs. In other words, the directory structure should be the following:

HistoricalMachineTranslation/
  NeuralMachineTranslator.ipynb
  AnalyzeData.ipynb
  Word2WordTranslator.ipynb
  ProjectSoftwareArchiveFiles/
    TranslationModelFiles/
    TranslationTrainingFiles/
    en-embs/
    fr-embs/
    de-embs/
    chi-embs/
    Wordlists/
    
If this does not work, or you want to modify the paths manually, then here are the indications for where you can do that:
- in NeuralMachineTranslator.ipynb:
  - write the path to the parallel corpus in the "Providing Information for the Translation" cell
  - write the path to the encoder and the decoder in the "Loading a Saved Model" cell
  - write the path to the source vocabulary, source embeddings, target vocabulary, target embeddings in the "Loading embeddings cell"
- in AnalyzeData.ipynb:
  - please check the simple indications in the text snippets within the file
- in Word2WordTranslator.ipynb:
  - write the paths where all the historical embedding files in the _path_ variable situated in "Getting the Translation Files".

The input for the translation or the tools can be accessed in the following way
- to execute Encoder-Decoder Seq2Seq Neural Machine Translation, write the sentence you wish to translate in the first line of the "Creating Translation" cell, which is the very last cell of the file NeuralMachineTranslator.ipynb
- to use the word-to-word translator: write the necessary parameters in the call to the translate function, which is on line 78 of the cell "Training and obtaining results from the Word-level translator"
- to calculate the volatility of a word: write the word in the call to the volatility function in the last line of the cell "Volatility of a Word" from Word2WordTranslator.ipynb
