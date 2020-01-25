# POS-tagging

We implemented the POS tagging in which we were supposed to mark every word in a sentence with its correct part of speech. We had a dataset of Brown Corpus and we had to implement Bayesian Nets, Viterbi and MCMC using Gibbs Sampling. 
We calculated first the prior probability which is the probabilty of a label occuring at the start of the sentence. We maintained a lookup which had all the frequency of the words with respect to its labels. We made a list of all the labels which exist and also kept the track of transitions. We defined the transition probability as the probability of transition from one POS label to another. We calculated all the possible combinations of transitions and we calculated the probability for it. We defined the emission probability as the probability of the word for a particular label. 

Bayesian Nets: 
We had to implement Bayes net to find the all part of speech for each word in the given sentence. We considered each word and probability of each word for all 12 possibilities of part of speech. We considered the max value of the probability and selected that label as the final label for respective word. It was just a baseline model which worked and performed average.

Viterbi:
The second part of the problem is to use viterbi algorithm to optimize the previous setting and helping us calculate the suitable probability.  Viterbi helps us find the most likely sequence of states. Viterbi considers three probabilities, start, emission and transition and combines all these probabilities to give best label sequence. Since the probabilities depended on the previous states, unlike in Bayes Net and gave us a much better result. 

MCMC using Gibbs Sampling:
First we considered random labels for all the words of the sentence. Then we performed 1000 iterations on each word of a sentence. We calculated cumulative emission probability of each label for that word. We decided a particular label for that word by tossing a coin.

Problems:
when any new word came which is not present in the training corpus, we have set their probability to a very small value 1e-20. While calculating emission probability of such words we are assigning its value as 0. In Viterbi we have assigned emission value and probability value of states as 1e-20 if it is zero.
