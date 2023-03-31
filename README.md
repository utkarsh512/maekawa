# Maekawa's algorithm: Generating request sets

### EC60012 - Advanced Operating Systems Design - Assignment 3

#### Utkarsh Patel

## Maekawa's algorithm

Maekawa's algorithm is an algorithm for mutual exclusion on a distributed system. The basis of this algorithm is a quorum like approach where any one site needs only to seek permissions from a subset of other sites.

Quorum set (or request set) <img src="https://latex.codecogs.com/svg.latex?R_i" /> for each site <img src="https://latex.codecogs.com/svg.latex?S_i" /> must abide by the following rules:
- <img src="https://latex.codecogs.com/svg.latex?\forall i \forall j, R_i \cap R_j = \O " />
- <img src="https://latex.codecogs.com/svg.latex?\forall i, S_i \in R_i " />
- <img src="https://latex.codecogs.com/svg.latex?\forall i, | R_i | = K" />
- Site <img src="https://latex.codecogs.com/svg.latex?S_i" /> is contained in exactly <img src="https://latex.codecogs.com/svg.latex?K" /> request sets

Therefore, <img src="https://latex.codecogs.com/svg.latex?\forall i, | R_i | \geq \sqrt{N - 1}" />

## Generating request sets

If the number of site can be represented as <img src="https://latex.codecogs.com/svg.latex?N = K(K - 1) + 1" />, then the problem translates to generating a **projective plane** of order <img src="https://latex.codecogs.com/svg.latex?K - 1"/>. Solution exist if <img src="https://latex.codecogs.com/svg.latex?K - 1"/> is a power of prime, <img src="https://latex.codecogs.com/svg.latex?p ^ m"/>, for some prime <img src="https://latex.codecogs.com/svg.latex?p"/>. For other cases, we can relax the last two conditions to create degenerate request sets.

## Build and run
```shell
$ cd maekawa
$ make
$ ./maekawa
```

## References
- [Math Games: The Fano Plane](http://www.mathpuzzle.com/MAA/47-Fano/mathgames_05_30_06.html)