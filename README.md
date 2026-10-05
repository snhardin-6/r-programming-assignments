# r-programming-assignments

Sydney Hardin

# Assignment 6: Matrix Operations and Construction

# Task 1
A <- matrix(c(2, 0, 1, 3), ncol = 2)
B <- matrix(c(5, 2, 4, -1), ncol = 2)

A + B
A - B

# Task 2
D <- diag(c(4, 1, 2, 3))
D

# Task 3
M <- diag(3, 5)
M[1, ] <- c(3, 1, 1, 1, 1)
M[2:5, 1] <- 2

M
