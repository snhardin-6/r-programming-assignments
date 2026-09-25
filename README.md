# r-programming-assignments

Sydney Hardin

LIS4370
# Assignment #4 - Matrix Algebra in R

# Create matrices
A <- matrix(1:100, nrow = 10)
B <- matrix(1:1000, nrow = 10)

# Inspect dimensions
dimA <- dim(A)
dimB <- dim(B)

print(dimA)
print(dimB)

# Compute inverse and determinant with error handling
invA <- tryCatch(
  solve(A),
  error = function(e) e
)

detA <- tryCatch(
  det(A),
  error = function(e) e
)

invB <- tryCatch(
  solve(B),
  error = function(e) e
)

detB <- tryCatch(
  det(B),
  error = function(e) e
)

# Display results
print(invA)
print(detA)
print(invB)
print(detB)
