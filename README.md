# Maekawa's algorithm: Generating request sets

### EC60012 - Advanced Operating Systems Design - Assignment 3

#### Utkarsh Patel

## Maekawa's algorithm

Maekawa's algorithm is an algorithm for mutual exclusion on a distributed system. The basis of this algorithm is a quorum like approach where any one site needs only to seek permissions from a subset of other sites.

Quorum set (or request set) $R_i$ for each site $S_i$ must abide by the following rules:
- $\forall i \forall j, R_i \cap R_j \ne \phi$
- $\forall i, S_i \in R_i$
- $\forall i, | R_i | = K$
- Site $S_i$ is contained in exactly $K$ request sets

Therefore, $\forall i, | R_i | \geq \sqrt{N - 1}$

## Generating request sets

If the number of site can be represented as $N = K(K - 1) + 1$, then the problem translates to generating a **projective plane** of order $K-1$. Solution exist if $K-1$ is a power of prime, $p^m$, for some prime $p$. For other cases, we can relax the last two conditions to create degenerate request sets.

## Build and run
```shell
$ git clone https://github.com/utkarsh512/maekawa.git
$ cd maekawa
$ make
$ ./maekawa
```

## References
- [algorithm - What are the mathematical/computational principles behind this game? - Stack Overflow](https://stackoverflow.com/questions/6240113/what-are-the-mathematical-computational-principles-behind-this-game)
- [Math Games: The Fano Plane](http://www.mathpuzzle.com/MAA/47-Fano/mathgames_05_30_06.html)
