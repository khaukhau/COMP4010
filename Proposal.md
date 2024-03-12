# Project Proposal 1

## 1. Dataset Description
The dataset under consideration is a comprehensive collection of tornado occurrences in the United States from 1950 to 2022. It includes various attributes such as the date and time of each tornado, its geographical coordinates, magnitude, length, width, as well as the resulting injuries, fatalities, and property loss. This dataset, compiled from the National Weather Service and other meteorological sources, serves as a rich historical record of tornado activities and their impacts.

Github Link: https://github.com/rfordatascience/tidytuesday/blob/master/data/2023/2023-05-16/readme.md	

## 2. Reason for Dataset Selection
We chose this dataset due to its detailed recording of natural disasters, specifically tornadoes, which are frequent and impactful weather events in the United States. Understanding the patterns and effects of tornadoes is crucial for improving safety measures, emergency responses, and public awareness. Additionally, this dataset offers a unique opportunity to explore geographical, temporal, and physical aspects of tornadoes, which can lead to valuable insights for science and society.

## 3. Question for Analysis
**Question 1:** What are the overall characteristics of US tornadoes over times?

**Question 2:** Tornado severity and its impact on the economic loss: What are the impacts of the tornadoes?



## 4. Plan for Analysis
**For Question 1:** What are the overall characteristics of US tornadoes over times?

* *Mini Question 1:* How frequent do the tornadoes occur by geographical location, by month and by year? (What monthly and seasonal trends in tornado activity can be inferred from the historical data, and how pronounced are these trends?)

    * Variables: st, mo, om, yr
    * Approach:
        * To visualize tornado frequency by location, generate a heatmap overlay on a US map. This will involve mapping each state (variable 'st') with the number of occurrences ('om') to illustrate geographical distribution. Tools like GIS (Geographical Information Systems) or libraries in Python (e.g., Matplotlib, Basemap) or R (e.g., ggplot2, sf) can be used for this. (ref:  tidytues/scripts/2023/week-20-tornados/tornados.png at 33a01066e4ae8538085c9d37e19ac30593a7c469 · doehm/tidytues (github.com))
        * For monthly and yearly trends, use line or bar graphs to represent the frequency of tornado occurrences over time, with 'mo' on the x-axis for monthly trends and 'yr' for annual trends. This helps identify specific times of the year or patterns over the years where tornado activity spikes.
        * The heatmap should highlight the regions with higher frequencies, and the line or bar graphs should clearly show seasonal and annual trends, enabling the inference of patterns and anomalies in tornado occurrences.

* *Mini Question 2:* How has the distribution of the magnitude, width and length of tornadoes changed annually? 
    * Variable: yr, mag, wid, len, fc
    * Approach:  
        * To analyze changes in tornado characteristics over time, first create a new data table summarizing yearly data. Aggregate the data by year ('yr'), calculating the most common magnitude ('mag'), average width ('wid'), and average length ('len') for each year. This can be done using data aggregation and summarization functions in Python (Pandas) or R (dplyr).
        * Create a "spaghetti graph" where each line represents a different attribute (most common magnitude, average width, and average length) across years. This type of graph will allow you to track changes in tornado characteristics over time and visually assess any trends or shifts.
        * Ensure the graph has clear labels, a legend, and differentiated line styles or colors for each attribute to aid interpretation and comparison.

**For Question 2:** Tornado severity and its impact on the economic loss: What are the impacts of the tornadoes?
* *Mini Question 1:* How is each state affected by the tornadoes? (number of tornadoes + fatalities in each state) ~ take top 10 states
    * Variable: st, om, fal
    * Approach:
        * Utilize a stacked bar chart to display the number of tornadoes and fatalities for the top 10 most affected states. Each bar represents a state ('st'), with one segment for the number of tornadoes ('om') and another for fatalities ('fat'). This can be achieved using visualization libraries such as Matplotlib, Seaborn, or ggplot2.
        * The chart should allow for easy comparison between states regarding both tornado frequency and resultant fatalities, highlighting states that are disproportionately affected by tornadoes.
        * Ensure the chart includes clear labeling, a coherent color scheme distinguishing tornadoes from fatalities, and a legend explaining the segments.
* *Mini Question 2:* What are the economic consequences of tornadoes in terms of property loss, and how do these losses relate to tornado magnitude and path dimensions?
    * Variables: mag, loss, len, wid, yr (maybe take 10 recent years, hoặc gr lại theo range)
    * Approach:
        * Employ a bubble chart to illustrate the relationship between tornado magnitude ('mag'), property loss ('loss'), and path dimensions ('len', 'wid'). Place tornado magnitude on one axis and property loss on another, with the size of each bubble representing either the length or width of the tornado's path.
        * Could create two separate bubble charts: one with bubble size based on 'len' and the other on 'wid', to discern which dimension correlates more strongly with economic loss.
        * The chart should be constructed to enable clear visual correlation between the magnitude of tornadoes and the extent of property damage, using color coding or bubble size to differentiate between tornado dimensions. Consider using logarithmic scales if the range of losses is vast to improve readability.
        * Include annotations or a supplementary legend to aid understanding of the bubble sizes, ensuring the graph is as informative as possible about the relationship between tornado characteristics and economic impacts.

