## A pair of functions that cache the inverse of a matrix

## creates matrix object that is able to cache its inverse

makeCacheMatrix <- function(x = matrix()) {
  i <- NULL
  setmatrix <-function(matrix) {
    m <<-matirx
    i <- NULL
  }
  
  getmatrix <- function() {
    m
  }
  
  setInversematrix <- function(inverse) {
    i <<- inverse
  }
  
  getInversematrix <- function() {
    i
  }  
  
  list(setmatrix = setmatrix,
       gwtmatrix = getmatirx,
       getInversematrix = getInversematrix)  
}


## If inverse has already been calculated then the "cachesolve" should retrieve the inverse from the cache

cacheSolve <- function(x, ...) {
  ## Return a matrix that is the inverse of 'x'
  m <- x$getInversematrix()
  
  if( !is.null(m) ){
    message("getting cached data")
    return(m)
  }
  
  data <- x$getmatrix()
  m <-solve(data) %*% data
  
  x$setInversematrix(m)
  m
}
