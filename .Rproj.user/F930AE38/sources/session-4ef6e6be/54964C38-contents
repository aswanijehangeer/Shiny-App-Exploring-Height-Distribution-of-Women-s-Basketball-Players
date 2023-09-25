# loading package
library(shiny)

# Sourcing global.R file (In our current working directory)
source("global.R")

# UI Interface
ui <- fluidPage(
  titlePanel("The Height of Womens NCAA Basketball Players"),
  sidebarLayout(
    sidebarPanel(
      selectInput("college_year", "College Year", 
                  choices = c("All", unique(wbb_data$year_clean[!is.na(wbb_data$year_clean)]))),
      selectInput("position", "Position", 
                  choices = c("All", wbb_data$position_clean[!is.na(wbb_data$position_clean)])),
      selectInput("division", "Division", 
                  choices = c("All", unique(wbb_data$division)))
      ),
    mainPanel(
      plotOutput("bar_plot")
    )
  )
)

# Server Side  
server <- function(input, output, session) {
    
    output$bar_plot <- renderPlot({
      
      filtered_data <- wbb_data
      
      # Filter based on selected inputs, excluding "All"
      if (input$college_year != "All") {
        filtered_data <- wbb_data %>% filter(year_clean == input$college_year)
      }
      
      if (input$position != "All") {
        filtered_data <- wbb_data %>% filter(position_clean == input$position)
      }
      if (input$division != "All") {
        filtered_data <- wbb_data %>% filter(division == input$division)
      }
      
      ggplot(filtered_data, aes(total_inches)) +
        geom_bar(fill = "black") +
        labs(
          title = "Analyzing Height Distribution of Women's Basketball Players",
          x = "Height (Inches)",
          y = "Total Players", 
          caption = "Data Source: Merril College created by: aswanijehangeer"
        ) +
        theme(plot.caption = element_text(face = "bold", hjust = 0.5, size = 15))
    })
  }

# ShinyApp  
shinyApp(ui, server)
  