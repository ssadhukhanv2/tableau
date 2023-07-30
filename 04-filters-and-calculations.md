# **Filters and Calculations**

## Agenda
* Charts and Visualizations
  * Hierarchy
  * Stacked Bar Chart, Scatterplot
  * Combined Axis/Dual Axis
  * Treemap
* Filters
* Calculated Fields


## Concepts

* **Tree Map**:
    * Sales vs Region vs Subcategory chart
      * 2 measures - subcategory, region
      * 1 dimensions -sales
      * color -> region
      * blocks -> sub category
      * size -> sum of sales
    * Sales vs Region vs Subcategory vs Profit
      * 2 measures - subcategory, region
      * 2 dimensions -sales
      * color -> profit
      * blocks -> sub category, region
      * size -> sum of sales

    * Not all charts can answer all questions. Foe example with Treemap we can't answer cross dimensions questions. For example we will be able to answer which maxiumum sub category within a region but we will not be able to answer which is the maximum subcategory across all regions
    * Size and color are the most distinctive feature so always use them
      * if we bring an attribute to color, existing color attribute is removed

* [**Treemap vs HeatMap**](https://discuss.boardinfinity.com/t/what-is-the-difference-between-a-tree-and-heat-map/11518) In heat map focus is on color, in tree map the focus is the size. 


* **Combined Axis Chart**: Two charts in a single ewindow with the same x axis 
  * Compare sales and profit across years
  * Use consistent colors across sheets and categories
  * Chart type as well as characteristics can be individuallly changed
  * use this when order of axis is not similar

* **Dual Axis Chart:** 
  * Create Combined Axis Chart and then change one of the chart to "Dual Axis".
  * Synchronize one of the axis to avoid confusion
  * single x axis and two y axis.
  * use this when order of axis is similar
    * magnitute is same
    * main focus is on 1 chart, other is of lower priority.

* 2 different measure in the same chart

* **Hierarchy of fields**: we can create custom hierarchies for fields in tableau. Some fields like dates have hierarchy automatically created.


* **Filters**: Filters within tableau may be used to exludes data irrelevant data and include only meaningful data
  * clarity. priority
  * reduce runtime/speed up
  * keeping meaningfuldata in a single chart.
* **Types of filters in tableau**:
  * **Extract Filter**: only read a subset of data from the database. rows are removed only at the datasource level. 
    * Not available in tableau public. 
    * only reads the subset of filtered data.
    * opposite of live.
    * only fetch and download the relevant rows from the database.

  * **Datasource Filter**: apply filtering on the extracted datasource. Apply filtering on the extracted data so that data will be filtered at every place where this datasource is used. (on the main datasource page we apply filter, it's this one)
    * For example we connect to the world co2 datasource, then pivot the data, then we might use a datasource filter to filter out null values.
    * csv is not modified
  * **Context Filter**: Context filter is applied before a quick filter. 
    * Filters to be applied before anything else. Add to context, this adds a context filter which will be applied before quick filter.
    * Example- we can use context filters with maps to find top 10 subcategories in terms of profits for the central region.
    * *Set, TopN, BottomN, Fixed LoD is applied after ExtractFilter, Datasource filter and ContextFilter*
  * **Quick Filter**: 
    * **Dimension Filter**: Drag a dimension field to filter and select the values 
      * *Include/Exclude LOD, Blending is applied after dimension filter*
    * **Measure Filter**: Drag a measure and select the range of values.
      * Forecast,Analytics is applied after measure filters
    *Measure filters are similar to sql having and dimension is where, so Dimension Filters are applied first then Measure Filter is applied*
  * **Table Calculation Filter**: Subqueries(will be covered in later classes)
    * *Trendline filters*
* **Order of Execution of Filters**: Important Interview Questions
  1. Extract Filters 
  2. Datasource  Filters 
  3. Context Filters 
  4. Dimension Filters
  5. Measure Filters
  6. Table Calculation Filters

* To allow users to view filters, click on filters and clieck on show filters.



* Calculated Fields: crete a new field out of existing fields