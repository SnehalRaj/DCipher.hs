# DCipher.hs


We have a data comprising of trigram frequency occurring in English language which has been crawled from the web after searching extensively in the web.We first calculate the score  of each trigram by taking the log of probability of occurrence of each trigram.

Using this measure we can calculate score corresponding to any text in English language. A less negative score will denote the correctness of string and thus we try to maximize the score of our trigrams

We first start decoding small letters by using the key which matches ‘a’..’z’ to ‘a’..’z’. We then start doing random swaps in the key and select the swap which increases the score of the text.The swap is made only when the score of the key increases.

This is done till we reach a local maxima and no further swaps increase the score.Thus we have achieved  a local maxima.

To handle the case of capital letters we use a dictionary lookup to get the mapping for the correct letter. As the number of capital characters were very low, solving the problem by only trigram frequencies wouldl not have resulted in a correct score and therefore we employ another heuristic of looking up the dictionary and checking if the word we have found are correct or not.



We have included a script in our submitted zip file using which the user can parse any kind of text in a given format and thus is can be copied and pasted into ghci and used to decrypt the cipher.  We have included five main files for solving keeping in mind the different formats in which the cipher-text was given. In the second cipher given, we were able to get an accuracy of 89% and 90% using two heuristics and the only words which were not matched differed at atmost two letters which was due to the lesser frequency of the capital letters in the text.

