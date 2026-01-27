---
title: "[Blog] Sea Urchin Movement Model (Lévy Walk + Chemical Cue Targeting)"
date: 2025-11-27
categories: [Blog]
---

*This post documents an R simulation for sea urchin foraging: a Lévy-walk–style search that switches to directed movement when the animal enters a chemical-cue detection radius around food sources. The output is an animated GIF that tracks the path and the cue “rings”.*

---

## Overview

The core idea is:

- The urchin explores with **random steps** drawn from a heavy-tailed step-length distribution (a Lévy-like rule).
- When it approaches a food source (within a **detection radius**), it **moves toward the food**.
- Once it reaches food, it **stops** (in this implementation).

In this demo:

- Four food sources are placed at the corners of the arena.
- Each food source has a dashed circle showing its detection radius.
- When the urchin path intersects a detection circle, the model transitions into cue-following.

![Demo animation](output.gif)

---

## R code (complete)

### Libraries

```r
# Load necessary libraries
library(ggplot2)
library(ggforce)
library(ggimage)
library(gganimate)
library(scales)
```

---

## Helper functions

### Distance calculation

```r
# Function to calculate distance between two points
calculate_distance <- function(x1, y1, x2, y2) {
  sqrt((x2 - x1)^2 + (y2 - y1)^2)
}
```

### Line–circle intersection (cue detection)

This checks whether a movement segment crosses a food-source detection circle.

```r
# Function to check if a line segment intersects with a circle
line_circle_intersection <- function(x1, y1, x2, y2, cx, cy, r) {

  dx <- x2 - x1
  dy <- y2 - y1
  fx <- x1 - cx
  fy <- y1 - cy

  a <- dx^2 + dy^2
  b <- 2 * (fx * dx + fy * dy)
  c <- fx^2 + fy^2 - r^2

  discriminant <- b^2 - 4 * a * c

  if (discriminant >= 0) {
    t1 <- (-b + sqrt(discriminant)) / (2 * a)
    t2 <- (-b - sqrt(discriminant)) / (2 * a)

    if ((t1 >= 0 && t1 <= 1) || (t2 >= 0 && t2 <= 1)) {
      return(TRUE)
    }
  }

  return(FALSE)
}
```

---

## Lévy-walk movement with cue-following + stopping

Mechanism:

1. Find the closest food source.
2. If distance is larger than the detection threshold:
   - take a Lévy-like random step (heavy-tailed step length + random angle).
3. If within detection radius:
   - move directly toward the food.
   - if the path intersects the cue circle, snap to the food and stop.

```r
simulate_urchin_movement_towards_food_stopping <- function(
  num_steps,
  alpha,
  food_points,
  start_x = 0,
  start_y = 0,
  distance_thresholds = 5
) {

  x <- numeric(num_steps + 1)
  y <- numeric(num_steps + 1)

  x[1] <- start_x
  y[1] <- start_y

  reached_food <- FALSE

  for (i in 2:(num_steps + 1)) {

    if (!reached_food) {

      closest_distance_to_food <- Inf
      closest_food_index <- 0

      # find closest food
      for (j in 1:nrow(food_points)) {

        food_x <- food_points[j, "x"]
        food_y <- food_points[j, "y"]

        direction_x <- food_x - x[i - 1]
        direction_y <- food_y - y[i - 1]
        distance_to_food <- sqrt(direction_x^2 + direction_y^2)

        if (distance_to_food < closest_distance_to_food) {
          closest_distance_to_food <- distance_to_food
          closest_food_index <- j
        }
      }

      # far from food -> Lévy-like random step
      if (closest_distance_to_food > distance_thresholds) {

        step_length <- abs(rnorm(1, mean = 0, sd = 1))^(-1 / alpha)
        step_angle  <- runif(1, 0, 2 * pi)

        new_x <- x[i - 1] + step_length * cos(step_angle)
        new_y <- y[i - 1] + step_length * sin(step_angle)

        # keep inside arena bounds
        x[i] <- pmin(300, pmax(-300, new_x))
        y[i] <- pmin(300, pmax(-300, new_y))

      } else {

        # within cue radius -> move toward food
        food_x <- food_points[closest_food_index, "x"]
        food_y <- food_points[closest_food_index, "y"]

        # if the segment intersects the cue circle, snap to food and stop
        if (line_circle_intersection(
              x[i - 1], y[i - 1],
              food_x, food_y,
              food_x, food_y,
              distance_thresholds
            )) {

          x[i] <- food_x
          y[i] <- food_y
          reached_food <- TRUE

        } else {

          unit_direction_x <- (food_x - x[i - 1]) / closest_distance_to_food
          unit_direction_y <- (food_y - y[i - 1]) / closest_distance_to_food

          new_x <- x[i - 1] + unit_direction_x
          new_y <- y[i - 1] + unit_direction_y

          x[i] <- pmin(300, pmax(-300, new_x))
          y[i] <- pmin(300, pmax(-300, new_y))
        }
      }

    } else {
      # already reached food -> stop
      x[i] <- x[i - 1]
      y[i] <- y[i - 1]
    }
  }

  return(data.frame(x = x, y = y, step = 1:(num_steps + 1)))
}
```

---

## Parameters and run

```r
# Parameters for simulation
num_steps <- 3000  # Number of steps for the simulation
alpha <- 1.5       # Levy distribution parameter (alpha > 1 for heavy-tailed distribution)

food_locations <- data.frame(
  x = c(-200, -200, 200, 200),  # X-coordinates of the food points
  y = c(-200, 200, 200, -200)   # Y-coordinates of the food points
)

distance_thresholds <- 100

# Simulate sea urchin movement with stopping condition
urchin_movement_stopping <- simulate_urchin_movement_towards_food_stopping(
  num_steps,
  alpha,
  food_locations,
  distance_thresholds = distance_thresholds
)
```

---

## Plot + animate (gganimate)

**Notes**
- Put your urchin PNG (e.g., `sea_urchin2.png`) in the working directory, or provide a full path.
- The output GIF is saved as `output.gif`.

```r
# Create ggplot object for initial plot with food points and sea urchin movement
sea_urchin_image <- "sea_urchin2.png"  # Replace with your image file path

p <- ggplot() +
  geom_rect(
    data = food_locations,
    aes(xmin = x - 0.25, xmax = x + 0.25, ymin = y - 0.25, ymax = y + 0.25),
    fill = "blue"
  ) +
  geom_line(
    data = urchin_movement_stopping,
    aes(x = x, y = y),
    color = "blue",
    alpha = 0.3
  ) +
  geom_point(
    data = food_locations,
    aes(x = x, y = y),
    shape = 17,
    size = 5,
    color = "green"
  ) +
  geom_image(
    data = urchin_movement_stopping,
    aes(x = x, y = y, image = sea_urchin_image),
    size = 0.15
  ) +
  lapply(distance_thresholds, function(threshold) {
    geom_circle(
      data = food_locations,
      aes(x0 = x, y0 = y, r = threshold),
      inherit.aes = FALSE,
      color = "black",
      linetype = "dashed",
      alpha = 0.5
    )
  }) +
  labs(
    x = "X-axis",
    y = "Y-axis",
    title = "Sea Urchin Searching for Chemical Cue and Food"
  ) +
  transition_reveal(step) +
  theme_bw() +
  xlim(-300, 300) +
  ylim(-300, 300) +
  coord_fixed()

p

# Render and save animation
animation <- gganimate::animate(
  p,
  renderer = gganimate::gifski_renderer(),
  width = 800,
  height = 600
)

gganimate::anim_save("output.gif", animation)
```

---

## Limitations (current implementation)

1. **Fixed duration**: the simulation runs for a fixed `num_steps` and then ends, even if no food is reached.
2. **Idealized behavior**: cue-following is simplified; real urchin movement can be affected by currents, substrate complexity, and multiple sensory cues.
3. **Single stopping rule**: once food is reached, the urchin stops. You could extend this to allow continued foraging among multiple patches.

---

## Further reading

- Lévy walks: <https://en.wikipedia.org/wiki/L%C3%A9vy_flight>
