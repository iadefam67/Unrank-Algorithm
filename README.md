# Unrank-Algorithm
C implementation and Proof of unrank permutation algorithm

An array of n items has n! possible unique permutations, assuming n contains unique elements. Generating random permutations is useful for many applications where a random ordering of a set of items is needed. The following unrank algorithm computes a random permutation in O(n) operations.

I decided to implement this algorithm because I was trying to solve a problem for an unrelated homework assignment, looked up this algorithm in my textbook (Skiena), and felt like the relative simplicity of the implementation was hiding a lot of details. In particular, Myrvold and Ruskey's paper's explaination of the correctness of the unranking algorithm was delightfully maddening: "It should be fairly obvious why this function works". 

In psuedocode, the unranking algorithm presented by Myrvold and Ruskey goes like this:

Problem: Given an array of unique elements, generate a random permutation. Every possible permutation on the elements of the given set must be equally possible. 

Inputs: A set containing n unique elements. A number, rank, where 0 <= rank <= n-1. Variable a is an array of size n. 

  define unrank, with arguments n, rank, a:
      intermediate variables: new_rank, index, new_n
      while n > 0 
          new_rank <- floor(rank / n)
          index <- rank mod n
          new_n <- n -1
          swap a\[index\] with a\[new_n]
          rank <- new_rank
          n <- new_n
      end while   

Sources:
"The Algorithm Design Manual", 2nd Edition, Steven S. Skiena, Springer Press, 2008. Chapter 14.4 "Generating Permutations"

"Ranking and Unranking Permutations in Linear Time", Wendy Myrvold, Frank Ruskey, 2000
