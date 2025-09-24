A matrix that behaves "nicely", specifically it means that it is a matrix that, when multiplying a vector, makes the vectors scale by a consistent number and point in a consistent direction.
- This is relevant for optimization problems and dynamic systems because it means the matrix represents something "well behaved and stable"

Mathematically, a matrix $A$ is positive definite if 
$$
\forall v:v^TAv>0
$$
