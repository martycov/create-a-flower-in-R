# create-a-flower-in-R
this program create a spiral that seem like a flower. from DataCamp
library(ggplot2)

# Define t using correct syntax
points <- 500
angle <- pi * (3 - sqrt(5))
t <- (1:points) * angle
x <- t * sin(t)
y <- t * cos(t)
df <- data.frame(t, x, y)

df <- data.frame(t, x, y)
spiral_flower <- ggplot(df, aes(x, y)) +
  geom_point()
spiral_flower

tidy_flower <- ggplot(df, aes(x, y)) + 
  geom_point(size = 8, alpha = 0.5, color = "darkgreen") + 
  theme(
    panel.background = element_blank(),
    panel.grid = element_blank(),
    axis.ticks = element_blank(),
    axis.title = element_blank(),
    axis.text = element_blank()
  )

tidy_flower

dandelion_flower <- ggplot(df, aes(x, y)) + 
  geom_point(aes(size = t), alpha = 0.5, color = "black", shape = 8) +
  theme(
    panel.background = element_blank(),
    panel.grid = element_blank(),
    axis.ticks = element_blank(),
    axis.title = element_blank(),
    axis.text = element_blank(),
    legend.position = "none"
  )

dandelion_flower

# imaginary flower
points <- 1000
angle <- pi * (5 - sqrt(8))
t <- (1:points) * angle
x <- t * sin(t)
y <- t * cos(t)
df <- data.frame(t, x, y)

imaginary_flower <- ggplot(df, aes(x, y)) +
  geom_point(size = 8, alpha = 0.5, color = "darkgreen") +
  geom_point(aes(size = t), alpha = 0.8, color = "pink", shape = 8) + 
  theme(
    panel.background = element_rect(fill = "midnightblue", color = NA),
    panel.grid = element_blank(),
    axis.ticks = element_blank(),
    axis.title = element_blank(),
    axis.text = element_blank(),
    legend.position = "none"
  )
imaginary_flower
