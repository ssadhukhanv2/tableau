
# Dashboarding and Story Telling

* Dashboarding and Story telling
* Interactive
* Efficiency
* Capstone


## Concepts
* to avoid duplication-create smaller tables
  * use small independant table for each question

### Dashboarding
* User input
* Interaction
* Good interface
* Storyline
* High Granularity


* Horizonatal Containers: Rows
* Vertical Containers: Columns

* Tableu remembers state, so if we make any chages on the sheet apart from aprt from data changes, it will not reflect on the existing dashboards.


* Tableau Actions: This controls if something happens on one chart what will happen to the others. (Things to do if a change happens on a sheet)
    * Filter Actions: On the dashboard, if you select anything on the sheet, all other fields gett filtered on the data.

    Other actions may also be defined.

* Floating Option for object: 
  * Tiled: Fixed place
  * Floating: Can go on top of any place

* Data Story: A data story is used to tell a story. It can have the following:
  * Story point
  * All sheets and dashboard
  * Text Option
    
    Mostly used by folks who don't understand the dashboard.
    * You can have multiple storypoints in a data story. 
    * A datastory may even contain dashboard. 
    * It's a way of highlighting specific stories to the user.



### Performace tips
* Reduce data to a minimum.
  * Reduce columns: If there are columns that you are not using in your chart don't even bring them into your dataset.
  * Reduce rows: Reduce the no of rews.
  * Extract should be optimized: You should not be doing joins within tableu. Joins should be done outside table then imported into tableau.
* Reduce data points on the chart: as low as possible. don't make charts cluttered with too many data.
* Visualization should not have too many filters or parameters. 
* Try keeping LOD expressions to a minimum.
* Keep joins as low as possible.



## Assignments
* from the case study
    * Find out which stores are the most popular
    * which products are most popular etc.



## Project Idea
* Find 50 dashboard in tableau public.
* Downaload a dashboard with data
* See 10-12 dashboard with data of similar theme
* Find list of 15-20 metrics/charts
* Divide this into 5-6 metric combinations.
* Individually create dashboard for each of these combination
* **One dashboard a month**


## Data Visualizition Interview Questions

* Theory
  * LOD
  * Type of Filters and how to change those
  * Increase effciency of dashboard
* Practical
  * What chart type to use
  * Given a question which is the best chart to use(axes, color and sizes)
    * which chart
    * what type of charts to use
  * when to use parameter, filters and actions.