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

  If $m$ isn't a power of 2, letting $k = log{_2}{m}$ rounded down the character lengths are either $k$ or $k + 1$, and the average length by counting the leaves at those 2 depths is $k + 2 - \frac{2^{k + 1}}{m}$,  which gives a total cost of $n(k + 2 - \frac{2^{k + 1}}{m})$

**2: Making Change**

- **2a. (5 pts)** Given a $N$ dollars, state a greedy algorithm for producing
as few coins as possible that sum to $N$.

Let $L$ be the amound of dollars not yet made change for from $N$

Let $k = log{_2}{L}$ rounded down to the nearest integer

repeatedly select coins worth $2^{k}$ dollars after finding $k$ with the new $L$ until $L = 0$


- **2b. (5 pts)** Prove that this algorithm is optimal by proving the greedy
  choice and optimal substructure properties.

Base Case: $N = 0$; no coins will be given, which is clearly optimal

Inductive Hypothesis: assume the algorithm holds for all $m < N$

For $N > 0$; $k = log{_2}{N}$; $2^{k} <= N < 2^{k+1}$, so the first coin selected is worth $2^{k}$

For the algorithm to be optimal, there can be no duplicate coins because for any $x >= 0$, $2^{x} + 2^{x} = 2^{x+1}$, so the two duplicate coins could be replaced by one single higher denomination coin

The first selection of a coin worth $2^{k}$ must be optimal because $2^{0} + 2^{1}... + 2^{k-1} = 2^{k} - 1 < N$

Then the algorithm must find the optimal $L$ for $L = N - 2^{k}$ which it does by treating $L$ as a new $N$ and repeating the step already proved to be optimal

Therefore, the algorithm holds for all $N$

- **2c. (4 pts)** What is the work and span of your algorithm?

Note: Worst case (most coins) is $N = 2^{k} - 1$ for some $k$

Span: for the worst case, the algorithm finds coins worth $2^{x}$ for $x = 0, 1,... k-1$, which is $k$ coins

The whole chain is dependent, and $k = log{_2}{N}$, so $S(n) = O(log{_2}{n}) = O(logn)$

Work is the total number of operations performed, which is the total number of coins found (already found above)

Therefore, $W(n) = O(logn)$

