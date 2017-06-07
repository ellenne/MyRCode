Average RAtio Actual Premium - Processed Premium by working day and month
-------------------------------------------------------------------------

The chart below shows the percentage of premium processed in a given
working day.

    premium %>% 
      subset(WorkDayNoWE > 0) %>% 
      group_by(Month, WorkDayNoWE) %>% 
      summarise(avg_perc = mean(PercPremium)) %>% 
      ggplot(aes(x = Month, y = WorkDayNoWE, fill = avg_perc)) +
      geom_tile(alpha = 0.8, color = "white") + 
      scale_x_continuous(name="Month", 
                         breaks = c(1:12),
                         labels = factor(1:12)) +
      scale_y_continuous(name="Working day of the month", 
                         breaks = seq(1, 23, 1),
                         labels = factor(1:23),
                         minor_breaks = seq(1, 23, 1)) +
      scale_fill_gradientn(colours = c(palette_light()[[1]], palette_light()[[2]])) +
      theme_tq() + 
      theme(legend.position = "bottom") +
      labs(title = "Average Ratio Actual Premium - Processed Premium by month and workday",
           fill = "Average Ratio")

![Alt text](/img_001.png?raw=true "Optional Title")
