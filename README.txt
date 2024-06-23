Task: Find all proper nouns in a text passage.

Methodology:

1. My first point of reference to remove common nouns is the Scrabble dictionary. Since proper nouns are not allowed in Scrabble at all, the words in that dictionary should be proper nouns unless presented as a capitalized pair of words that make a proper noun.

2. Using the pattern CLIP model, I am able to find all nouns using part-of-speech tagging. Using the scrabble dictionary, I identify all nouns in that dictionary to shorten the list of words to check for. I am able to create an updated dictionary so I don't need to run this function every time. This doesn't affect time complexity but it does reduce the amount of space required by the dictionary HashSet. Limiting the size of this dataset will reduce startup time since I will have fewer entries to input to the reference set.

3. Proper nouns are always capitalized, so any capitalized nouns identified by the pattern model in the middle of the sentence should be proper nouns. This unfortunately does not account for the human error of capitalizing regular nouns while writing. The questionable items that require the dictionary would be the nouns identified at the beginning of the sentence, since those could be common nouns capitalized only due to their position in the beginning of the sentence. To account for human error, and due to the low O(1) time complexity of a dictionary check, I check every noun found in the passage to see if it is in the common noun dictionary.