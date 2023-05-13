# StringRush-Parallelized-Rabin-Karp-Algorithm
The Rabin-Karp algorithm, which uses a rolling hash to match patterns in text, is commonly used for exact string matching and plagiarism detection. This work presents a parallel version of the Accelerated Rabin-Karp algorithm, implemented using MPI and Distributed Python disPy.


**The Rabin-Karp algorithm ** is a linear time string matching algorithm that uses hash functions to find occurrences of a pattern within a larger text. 
The parallelized algorithm has two phases which can be performed in parallel to improve performance : 
1. Preprocessing 
2. Matching, 
In the preprocessing phase, the text is divided into smaller blocks and hashed using a hash function.
In the matching phase, the algorithm compares the hash values of the pattern and the blocks to find a match. A rolling hash function and multiple hash functions can be used to further improve the algorithm's performance.

we have compared the serial and parallel execution time for 15 different values of number of processors. The serial execution time(ts) is constant across all whereas the parallel execution time(tp) first decreases then increases after a certain number of processors. To measure the performance improvement achieved by parallel execution, we have calculated the speedup. 
The speedup is a measure of how much faster a program runs on multiple processors compared to a single processor. 
It is calculated as the ratio of the serial execution time (ts) to the parallel execution time (tp) for a given number of processors.

The time complexity of the parallelized Rabin-Karp algorithm depends on the number of parts into which the text is divided. If the text is divided into k parts, then the time complexity of the algorithm will be **O((n/k) + m.k)** As k increases, the time required to search for the pattern in each part decreases, but the overhead associated with dividing the text into parts and merging the results increases. Therefore, there is an optimal value of k that minimizes the overall time complexity of the algorithm.
The optimal value of k may need to be determined empirically by testing the algorithm with different
values of k and measuring the execution time. 
Here we tested the value of k for **15 different number of processors** and by observing we can easily conclude that for **k=8** we have the most optimal value of ** Speedup which is 5.36 **.
