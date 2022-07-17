# ngramcollector

This code was written to analyze text and look for frequent words / ngrams. As written, you'll need to use a CSV file for the input, so this is best suited for text collected via scraping websites. You can edit the helper function ```textbuilder``` to accomodate different kinds of files, but once your corpus makes its way to ```WordsAndPhrases```, it should be one continuous text in the form of a string.

When we run the script, we have the choice of specifying a threshold, named ```cutoff```. If the frequency of the word/phrase is below this cutoff, then it won't be saved to the output CSV. At line 61, there's a bit of arithmetic going on; the purpose of this is to include longer phrases in the output CSV. We do this because longer phrases have less frequency in texts. If we select a high cutoff to filter out more trivial 1-grams, then without this arithmetic, we'd lose n-grams of length 2 or more.
