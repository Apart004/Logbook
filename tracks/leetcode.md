# July 21, 2026
Focus: Array Processing & Hash Table Lookups — LeetCode #1: Two Sum

-What I did: Kickstarted the dedicated LeetCode track by solving "1. Two Sum" (Easy). Evaluated index-tracking mechanisms to identify two integer elements within an array matching a target sum, optimizing complementary value checks ($\text{target} - \text{nums}[i]$) using hash map lookups to drop execution bounds from $\mathcal{O}(n^2)$ to $\mathcal{O}(n)$ time complexity.
-Takeaway: Storing complements in a key-value hash map provides instantaneous $\mathcal{O}(1)$ lookup performance, transforming nested-loop brute force problems into single-pass linear operations.