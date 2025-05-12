# Lexical Simplification in Spanish: A Comparative Study of Pre-trained Static and Contextual Embeddings

This repository contains the code and report for an independent, experimental study at attempting steps 2 and 3 of the Lexical Simplification pipeline: Substitution Generation, and Substitution Selection.

## Overview

The goal of the investigation was a performance comparison between pre-trained, static FastText embeddings for the Spanish language, and contextual embeddings provided by a RoBERTa MLM model trained by the Biblioteca Nacional de España on a massive Spanish-language corpus. Two different selection strategies were implemented for each of the models: for the FastText model, and ranking through a context window of the words surrounding the target word and averaged their embeddings to create one context vector, and then used cosine similarity to rank the candidate embeddings based on which is most similar to the context vector. This approach was intended to add a context component to the FastText model, whose embeddings are static and semantic. 

For the MLM model, a prompting strategy with Mistral-Small was employed. The Mistral-Small model was prompted to reorder the candidate words based on how well they would fit in a sentence (in the blank where the original target word is supposed to be), and taking into account the simplicity of the candidate words. 

## Results

Please refer to the report included in this repository to find out all of the detailed strategies that were implemented for each model approach. Summarily however, the FastText model outperformed the RoBERTa MLM model in every metric.
