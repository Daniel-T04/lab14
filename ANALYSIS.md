# Analysis

Run `./build/analysis_main` and copy the counts here. "Ascending" input is the reverse of the order the sorts want (they sort with `score_descending`); "descending" input is already in order.

## 1. Measured comparisons (27 numbers)

| Input | n | Selection | Insertion | Merge |
| --- | --- | --- | --- | --- |
| random | 10 | 45 | 34 | 22 |
| random | 100 | 4950 | 2508 | 539 |
| random | 1000 | 499500 | 251218 | 8736 |
| ascending | 10 | 45 | 45 | 19 |
| ascending | 100 | 4950 | 4950 | 356 |
| ascending | 1000 | 499500 | 499500 | 5044 |
| descending | 10 | 45 | 9 | 15 |, 
| descending | 100 | 4950 | 99 | 316 |
| descending | 1000 | 499500 | 999 | 4932 |

## 2. Predicted comparisons

Selection: n(n-1)/2. Insertion: best case and worst case. Merge: n log₂ n.

| Input | n | Selection | Insertion | Merge |
| --- | --- | --- | --- | --- |
| random | 10 |  45 | ~25 | ~33 |
| random | 100 | 4950 | ~2500 | ~644 |
| random | 1000 | 499500 | ~250000 | ~9966 |
| ascending | 10 | 45 | 100 | ~33 |
| ascending | 100 | 4950 | 10000 | ~664 |
| ascending | 1000 | 499500 | 1000000 | ~9966 |
| descending | 10 | 45 | 9 | ~33 |
| descending | 100 | 4950 | 99 | ~664 |
| descending | 1000 | 499500 | 999 | ~9966 |

Where the prediction and the measurement differ, say why:

For Selection sort. The measured and predicted numbers match completely because selection sort always checks every remaining element regardless of the input order.

In Insertion sort. on descending already sorted input, the count matches the n - 1 formula exactly because the loop stops after one check per element. On ascending which is reverse input, it measures counts like 45,4950, 499500 are half of the n power of 2 predications like 100, 10,000, 1,000,000 because the n power of 2 is just a rough Big-O  upper bound, whereas the exact worst-case forumla is n(n-1)/2.

And Merge Sort: it's measured counts are always  lower than the n log n formula especially in already sorted or reverse inputs because once one half finishes during a merge, the rest of the other half gets copied over without needing ant more comparisons.


## 3. When n grows tenfold

Selection sort: Comparison counts grows by a factor of 100 example (10(2)) every time n multiples by 10 45 to 4,950 to 499,500, regardless of the order.

Insertion sort: On descending, which is already sorted input, counts grow linearly  by its factor of 10
 9 to 99 and 99 to 999.

 in the random and ascending end, the inputs , counts grow quadratically by a factor of 100.
 34 to 2,508, to 251,218, and 45 to 4,4950 to 499,500.

Merge sort: It's comparisons counts grow by slightly more than a factor 10 which around 15 or 24 times by tenfold increse in the follow example 22 to 539 to 8,736 onto random input, which is scaling at O or the (n log2 n)instead of O (n(2)).

## 4. Which algorithm?

A leaderboard of 100 entries, and one of one million entries. Say why.

For a leaderboard of 100 entries, I would use insertion sort, which n as 100 even worst case is insertion sort takes only 4,950 comparisons, it requires zero extra axiality memory the (O(1) space) it could run near its O(n)best case of this scenario is we get 99 comparisons when new scores  are added to an already sorted leaderboard. However for a leaderboard of one million entries  to work, we need to use the merge sort, so we would assign n as 1,000,000 quadratic algorithms like selections or insertion sort would need up to 5 * 10(11) comparisons which can take minutes or hours to do , where merge sort's O (n log n) scaling finishes in under the 2 * 10(7) comparisons, keeping performance fast and predictable regardless of input order. 
