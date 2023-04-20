# Feature Extraction for RYSe 

RYSe is strategy that was designed to identidy a young (7-11 year old) searchs given their search queries


The code in this folder is designed to extract the features from our data sets (search query). The following notebooks can be run in any order:

1. ExtractLexicalFeatures.ipynb
2. ExtractSearchFeatures.ipynb
3. ExtractSpellingAndPunctuation.ipynb
4. ExtractSyntaticalFeatures.ipynb
5. ExtractVocabFeatures.ipynb

but all must be run before running:

FeatureExtractionMain.ipynb

which aggregates the output from all the Extract[featureType].ipynb notebooks.
