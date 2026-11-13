# CMPS 2200 Assignment 5
## Answers

**Name:**_________________________

Place all written answers from `assignment-05.md` here for easier grading.


**1: Fixed-Length vs. Variable-Length Codes**

- **1d. (5 pts)** What trend do you see?

  Fixed-length cost:  1039367
  Huffman cost:  676374
  Fixed-length cost:  876253
  Huffman cost:  606448
  Fixed-length cost:  1340
  Huffman cost:  826
  Fixed-length cost:  78050
  Huffman cost:  56206
  Fixed-length cost:  26047
  Huffman cost:  17356

  The ratio ranges from 3:5 to 3:4

- **1e. (4 pts)** What is the expected
  cost of a Huffman encoding for the document? Is it consistent across
  documents?

  Let $m = \Sigma$ be the number of unique characters, and $n$ be the number of unique characters

  If $m$ is a power of 2, each character length of $log{_2}{m}$, so the total cost is $nlog{_2}{m}$

  If $m$ isn't a power of 2, letting $k = log{_2}{m}$ rounded down the character lengths are either $k$ or $k + 1$, and the average length by counting the leaves at those 2 depths is $k + 2 - \frac{2^{k + 1}}{m}$,  which gives a total cost of $n(k + 2 - \frac{2^{k + 1}}{m}$

**2: Making Change**

- **2a. (5 pts)** Given a $N$ dollars, state a greedy algorithm for producing
as few coins as possible that sum to $N$.




- **2b. (5 pts)** Prove that this algorithm is optimal by proving the greedy
  choice and optimal substructure properties.




- **2c. (4 pts)** What is the work and span of your algorithm?



