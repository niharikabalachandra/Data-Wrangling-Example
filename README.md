# Data-Wrangling-Example
Example working with large string dataset

## Problem Statement
“You are given a dictionary (dictionary.txt), containing a list of words, one per line. Imagine you
have seven tiles. Each tile is either blank or contains a single lowercase letter (a-z).Please list all
the words from the dictionary that can be produced by using some or all of the seven tiles, in any
order. A blank tile is a wildcard, and can be used in place of any letter.
  1.Find all of the words that can be formed if you don’t have to deal with blank tiles.
  2.Find all of the words that can be formed, including those where blank tiles are used as
wildcards.
  3.Please bear in mind you will need to process several hundred of 7-tile sets with the same
dictionary.

## Solution
Consider the 7 tiles, each tile can either be a blank or contains a single lowercase letter from a to
z. We have the option of using some or all of the given 7 tiles. Therefore, each tile can be ﬁlled in
27 ways (a-z or blank). The word that we generate can either be a 1, 2, 3, 4, 5, 6, or 7 letter word.
The sample space for all the possible tile combinations as per the above requirements will have
10862674479 (27ˆ1 + 27ˆ2 + 27ˆ3 + 27ˆ4 + 27ˆ5 + 27ˆ6 +27ˆ7) words.
However, since we only have to worry about the tile combinations (of characters a-z or blank)
that form words which match with the ones in the dictionary, our new sample space is all the
words in the given dictionary.

Since we can only form words that are 7 letter or smaller, we eliminated all word that have
more than 7 letter from the given dictionary. This would also be all of the words that can be
formed if you don’t have to deal with blank tiles. In this code, ‘valid_words’ stores this list. You
can view this list of words in the ‘wordlist.csv’ ﬁle.
To ﬁnd all of the words that can be formed, including those where blank tiles are used as
wildcards we have to realize all the possible combination of words that are formed if the blank is
replaced by any letter. For example, the word ‘b-girl’ represents the following set of combinations:
[‘bagirl’, ‘bbgirl’, ‘bcgirl’, ‘bdgirl’, ‘begirl’, ‘bfgirl’, ‘bggirl’, ‘bhgirl’, ‘bigirl’, ‘bjgirl’, ‘bkgirl’, ‘blgirl’,
‘bmgirl’, ‘bngirl’, ‘bogirl’, ‘bpgirl’, ‘bqgirl’, ‘brgirl’, ‘bsgirl’, ‘btgirl’, ‘bugirl’, ‘bvgirl’, ‘bwgirl’,
‘bxgirl’, ‘bygirl’, ‘bzgirl’]

The function replace() executes this idea and we apply this function to all the words that
contain a blank in the list ‘valid_words’ (‘valid_words’ houses all the words of interest from the
given dictionary). The combination of words that the blank wildcard represents is stored in the
‘new_dictionary’ list.

The ‘new_dictionary’ list is added to the ‘valid_words’ list to form all of the words that
can be formed, including those where blank tiles are used as wildcards. This combined list is
new_dictionary_ﬁnal. You can view this combined list of words in the ‘wordlistforwildcards.csv’
ﬁle.
