## Recap
* Parameters
* Calculated Fields
* Data Structure
* Filters
* LOD
* Charts

## Concepts
* Elements of good visualization
  * Insightful
  * Interactive
  * Easy to read: Uncomplicated, Labels etc.

* Given a visulation task, below are the steps to be followed
    * What chart you need?
      * Axes: Dimension, Measure
      * example- Sales vs Month
    * Find the chart Type 
      * Bar, Line, Pie etc
    * Chart Operations
      * User Input: Parameter
      * Figure out if additional field is required: Calculated field
    * Limiting Data
      * Filtering: Mostly done on Dimension
      * Grouping or Sets
    * Calculated Field
      * Same granularity: Normal 
      * Multi granular: use LOD
        * Compare two level
        * Calculate share of/percentage of
    * Beautification of Chart
      * Color
      * Label
      * Tool tip

* Find states which are performing poorly interms of profit
  * Bar or Map
  * Limit Bottom 10: use set to filter


* LOD
  * Fixed: Independant of chart granularity
  * Include
  * Exclude
* Compare Profit for a sub category against it's parent category for the last 12 month

* Table Calculation: This is a tableau concept.
  * This is done after creating the table chart.
  * This can only be used after table has been created.
  * INDEX() -> returns index of current rowin the partition.
  * BI tools defines total till the end of the index.
  * Indexing May be changed. Click on Calculated Field created with Index> Compute using> selctthe type of indexing you want
    
* Tableau Table Indexing
  * Scope in Tableu Table
    * Table: The entire table
    * Pane: section in table that corresponds to an entire dimension.
      * Smallest unit is called pan
      * Either col or row should have more than 1 field. For Pane either more than 1 column or row field should be there. 3 or more dimensions are required 
    * Cell
  * Direction in Table Table:
    * Across: Horizontal
    * Down: Vertically down
  * Indexing is done based on scope and direction. This is also reflected in "Compute using



* **Table Calculation**: when we need to to compare values
  * Example:
    * Percentage contri of subcategory to parent category
    * % conrti of 2014 yearly subcategory level sales
    * Percentage contri of a specific month in the entire year for a subcategory to parent category
    * ranking
    * Compare statewise sales over years
  * Steps to use table calculation
    * craete basic table using required fields
    * change aggregation to sum to whatever you want to do.
    * change the compute using


* Difference Table Calculation and Calculated Field
* Table Calculation: Chart Level/sheet level
* Calculated Field: Available across sheets

* Table calculations are also available in non table view like map. But if it's not in table view, we will not be able to confirm which value it's using to calculate.


* Tool Tip Visulatization
  * **Changing Tool Tip** double click on tooltip within marks and modify.
    * We can also add chart to tool tip using "Insert". Any changes to the chart will impact the tool tip.
    * Generally adding a chart to tool tip will add a filter to the chart, if we remove this filter, all tool tip will have the same chart


* Analytics Tabs in Tableau
  * AVG
  * Forecast
  * Trendline(Use exponential or polynomial trendline for live data)
 