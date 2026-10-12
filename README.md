# r-programming-assignments


data("mtcars")

# Show first few rows
head(mtcars)

# Describe structure
str(mtcars)




# Generic function: print()
print(mtcars)

# Generic function: summary()
summary(mtcars)

# Generic function: plot()
plot(mtcars$wt, mtcars$mpg)

# Generic function applied to an object derived from the dataset
model <- lm(mpg ~ wt + hp, data = mtcars)

summary(model)

# Check methods used by summary()
methods("summary")


s3_obj <- list(name = "may", age = 19, GPA = 3.8)

class(s3_obj) <- "student_s3"

# S3 print method
print.student_s3 <- function(x, ...) {
  cat("Student (S3)\n")
  cat("Name:", x$name, "\n")
  cat("Age:", x$age, "\n")
  cat("GPA:", x$GPA, "\n")
}

# Generic dispatch
print(s3_obj)


setClass(
  "student_s4",
  slots = c(
    name = "character",
    age = "numeric",
    GPA = "numeric"
  )
)

s4_obj <- new(
  "student_s4",
  name = "Myself",
  age = 29,
  GPA = 3.5
)

# S4 method
setMethod(
  "show",
  "student_s4",
  function(object) {
    cat("Student (S4)\n")
    cat("Name:", object@name, "\n")
    cat("Age:", object@age, "\n")
    cat("GPA:", object@GPA, "\n")
  }
)

# Generic dispatch
s4_obj


class(s3_obj)
isS4(s3_obj)

class(s4_obj)
isS4(s4_obj)

# Underlying types
typeof(s3_obj)
typeof(mtcars)
