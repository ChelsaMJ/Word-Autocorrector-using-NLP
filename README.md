# Word Autocorrector using NLP in Python

This project implements a simple **word-level autocorrector** using Natural Language Processing (NLP) techniques. It suggests the most probable correct spellings for misspelled words.

## What's New in This Version (WA 1.1)

This updated notebook introduces key improvements over earlier versions:

-  **Replaced regex-only logic with spaCy and NLTK** for better preprocessing and more accurate suggestions.
-  **Integrated NLTK’s English dictionary (`words`)** to expand the vocabulary and suggest real, valid English words.
-  **Used Brown corpus frequencies** from NLTK to rank candidate corrections based on real-world usage.
-  Modular and readable code with a clean suggestion logic (`edits1 + known + word_prob`).

## Features

- Autocorrect suggestions for individual words
- Edit-distance based candidate generation
- Suggestions ranked by corpus-based word frequency
- English dictionary lookup using `nltk.corpus.words`

## Technologies Used

- Python 3
- [NLTK](https://www.nltk.org/)
- [spaCy](https://spacy.io/)
- Brown and Words corpus from NLTK
- Edit-distance based spell correction algorithm

## How It Works
- Preprocessing:
Words are cleaned using regex and lowercased.
Vocabulary is built from nltk.corpus.words.

- Candidate Generation:
Generates all possible words at edit-distance 1.
Filters only valid English words (known()).

- Ranking:
Suggestions are sorted by word frequency (Brown corpus).

- Output:
Top 5 most probable suggestions shown for the user input.

## Problems with the Old Version (Word Autocorrector 1.0.ipynb)
The initial version of the project had basic functionality but lacked accuracy and robustness. It relied heavily on a manually prepared text file (final.txt) as the only source of vocabulary, which limited its ability to suggest valid corrections for common misspellings.

- Key Issues Faced:
  - Limited Vocabulary: Only used words from a custom text file, missing many valid English words like "apple" or "friendship" unless they were explicitly included.
  - Low Suggestion Quality: The correction logic used regex tokenization and pattern matching, which didn’t capture the linguistic nuances of word forms or real-world usage frequency.
  - No Lemmatization: Without tools like spaCy, word forms (e.g., "running", "ran", "run") were treated as unrelated, hurting suggestion accuracy.
  - No Frequency-Based Ranking: Suggestions were not ranked by real usage probability, making them often irrelevant or random.
  - No Robust Error Handling: It lacked fallbacks like edit-distance-2 or advanced matching strategies, failing silently when no known match was found.

## Why I Improved It
- To make the autocorrector more intelligent, accurate, and usable, I moved to a hybrid NLP-based approach using:
  - spaCy for lemmatization,
  - NLTK’s corpora for real vocabulary and word usage frequencies,
  - and better structured, readable logic for generating and ranking corrections.
  - This made the autocorrector not just smarter, but also much more reliable for real-world use.

## File Structure
- Word Autocorrector 1.1.ipynb → ✅ Latest working version
- Word Autocorrector 1.0.ipynb → Older version
- Autocorrector_Feature_Using_NLP_In_Python.ipynb → Initial draft obtained from https://www.geeksforgeeks.org/autocorrector-feature-using-nlp-in-python/
