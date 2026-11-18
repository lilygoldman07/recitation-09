# CMPS 2200 Recitation 09

## Answers

**Name:** Lily Goldman


Place all written answers from `recitation-09.md` here for easier grading.



- **2) (2 pts)** What is the worst-case work of your algorithm, assuming $G$ has $k$ connected components?

  The `visited` set is shared, so each node is visited once and each edge is pushed onto a heap at most twice (once from each end), no matter how many components there are. Each heap push or pop costs $O(\log m)$, which is $O(\log n)$ because $m \le n^2$. Looping over all $n$ nodes to find new starting points adds $O(n)$.

  So the work is $O(n + m \log n)$. This is the same as normal Prim's, and it does not depend on $k$: the $k$ runs together still touch each node and edge only once.

- **4) (2 pts)** What is the work of your full algorithm in the previous answer?

  Building the graph: every pair of $n$ points gets an edge, so there are $m = \frac{n(n-1)}{2} \in O(n^2)$ edges, each with an $O(1)$ distance calculation. That is $O(n^2)$ work.

  Running Prim's: $O(m \log n) = O(n^2 \log n)$.

  Total: $O(n^2) + O(n^2 \log n) = O(n^2 \log n)$.