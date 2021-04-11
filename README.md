# makeCacheMatrix.R
makeCacheMatrix <- function(x = matrix()) {
+   inv <- NULL
+   set <- function(y) {
+     x <<- y
+     inv <<- NULL
+   }
+   get <- function() x
+   setInverse <- function(inverse) inv <<- inverse
+   getInverse <- function() inv
+   list(set = set,
+        get = get,
+        setInverse = setInverse,
+        getInverse = getInverse)
+ }
> makeCacheMatrix <- function(x = matrix()) {
+   
+   inv <- NULL
+   set <- function(y) {
+     x <<- y
+     inv <<- NULL
+   }
+   get <- function() x
+   setinv <- function(inverse) inv <<- inverse
+   getinv <- function() inv
+   list(set = set, get = get, setinv = setinv, getinv = getinv)
+ }
> m <- matrix(rnorm(16),4,4)
> m1<- makeCacheMatrix(m)
> cacheSolve(m1)
           [,1]        [,2]       [,3]       [,4]
[1,] -1.1796798 -0.79290406  0.8155790  0.9022940
[2,]  0.4505484 -0.13267812  0.1725633 -2.3738965
[3,] -0.3019759 -0.25612362 -0.1189929 -0.6600356
[4,] -0.3448059 -0.03779414  0.4988447 -0.7536763
