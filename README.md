# r-programming-assignments

Sydney Hardin

LIS4370

# Create vectors
Name <- c("Jeb", "Donald", "Ted", "Marco", "Carly", "Hillary", "Bernie")

ABC_poll <- c(4, 62, 51, 21, 2, 14, 15)

CBS_poll <- c(12, 75, 43, 19, 1, 21, 19)

# Create data frame
df_polls <- data.frame(Name, ABC_poll, CBS_poll)

# Inspect data
str(df_polls)
head(df_polls)

# Summary statistics
mean_ABC <- mean(df_polls$ABC_poll)
median_ABC <- median(df_polls$ABC_poll)
range_ABC <- range(df_polls$ABC_poll)

mean_CBS <- mean(df_polls$CBS_poll)
median_CBS <- median(df_polls$CBS_poll)
range_CBS <- range(df_polls$CBS_poll)

print(mean_ABC)
print(median_ABC)
print(range_ABC)

print(mean_CBS)
print(median_CBS)
print(range_CBS)

# Add difference column
# Note: assignment contains a typo. Use ABC_poll, not ABC_pol.
df_polls$Diff <- df_polls$CBS_poll - df_polls$ABC_poll

print(df_polls)

# Load ggplot2
library(ggplot2)

# Convert data to long format
library(tidyr)

polls_long <- pivot_longer(
df_polls,
cols = c(ABC_poll, CBS_poll),
names_to = "Poll",
values_to = "Support"
)

# Create bar chart
ggplot(polls_long,
aes(x = Name, y = Support, fill = Poll)) +
geom_bar(stat = "identity", position = "dodge") +
labs(
title = "Candidate Support by Poll Source",
x = "Candidate",
y = "Poll Value"
) +
theme_minimal()

# Save plot
ggsave("poll_bar_chart.png", width = 8, height = 5)
