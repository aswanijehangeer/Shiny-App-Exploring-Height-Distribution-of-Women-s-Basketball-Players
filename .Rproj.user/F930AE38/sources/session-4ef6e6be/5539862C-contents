# install.packages("tidyverse")
# install.packages("janitor")


library(tidyverse)
library(janitor)



# theme set
theme_set(theme_minimal(base_size = 12, base_family = "Open Sans"))

# theme update
theme_update(
  axis.ticks = element_line(color = "grey9"),
  axis.ticks.length = unit(0.5, "lines"),
  panel.grid.minor = element_blank(),
  legend.title = element_text(size = 12),
  legend.text = element_text(color = "grey9"),
  plot.title = element_text(size = 18, face = "bold"),
  plot.subtitle = element_text(size = 12, color = "grey9"),
  plot.caption = element_text(size = 9, margin = margin(t = 15))
)

# Importing data set
wbb_data <- read_csv("wbb_rosters_cleaned_2022_23.csv") |> 
  clean_names()

# Data set Structure
wbb_data |>
  glimpse()

# Dimension
dim(wbb_data)


# Bar plot
wbb_data |> 
  ggplot(aes(total_inches)) +
  geom_bar(fill = "black") +
  labs(title = "Exploring the Height of Women's Basketball Players",
       x = "Height (Inches)",
       y = "Total Players", 
       caption = "Data Source: Merril College created by: aswanijehangeer") +
  theme(plot.caption = element_text(face = "bold", hjust = 0.5))




