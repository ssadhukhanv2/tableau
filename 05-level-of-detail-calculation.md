# Level of Detail Calculation

### Main Agenda
* Interactive Visualization
* Granularity
* LOD - Level of Detail calculation

## Concepts

* **Calculated Fields**: Custom fields that can be created using existing fields and functions within tableau.
  * Whether a calculated is a dimention or a measure is autodetermined by tableau. Integers may be placed in measure even though we might need it in dimension(example -year). so keep an eye out.
  * case when, if else, calculations etc goes into calculated field
  * Find profit share from sales


* Why is tableau used
  * effective and meaningful data visulation

* **Dashboard**: collection of charts. Dashboard should be able to answer all questions asked by the business.
    * Interacting with Dashboards:
        * Filters
        * User Input: Create Parameter
* **Sharing Filters across multiple sheets witihin a dashboard:** Same Filter may be applied to multiple worksheet. This way if we want to use the same filter for multiple sheet within the same dashboard, we can do so. Select the filter > apply to worksheets.
* **Taking User Inputs as parameters in dahsboard:** Create Parameter. Use parameter to create a set, and use the set in filters.
To show params within a dashboard: Analysis> Parameter> select parameter



* **Multiple Charts within a single chart:** Connect User input to chart type. Example Give Sales Breakdown: Here only the dimension changes(Category, SubCategory, Region), measure is still sales.
    * Same chart types for multiple charts
        * sales vs region
        * sales vs category
        * sales vs year
    * essentially this is sales vs some dimension(region or category or year) user chooses this dimension.
    * create a parameter as string list to take the user input, create a calculated field and connect the parameter value using case when, use the calculated field in the column or rows. 
        * Parameter: User chooses an input string value
        * Calculated Fields: Connects it


* Change Chart Title: Use "Insert" to insert user parameters or other fields.


* **Data Granularity:**
  * Measure of level of details in a datastructure.
  * How detailed the data is
  * how much information is there
  * High Granularity: More Detail
  * Low Granularity: Low Detail
  * What granularity would be used in a chart depends on the context
    * Example- Where you are from
        * India (Lowest Granularity) [if you are ousite india]
        * West Bengal, India [if you are within india but ouside state]
        * Kolkata, West Bengal, India [if you are within west bengal but ouside kolkata]
        * 700026, Kolkata, West Bengal, India (Highest Granularity) [swiggy delivery agent]
  * Sales Analysis: 
    * Country Level Analysis: Sales vs State [less granular]
    * State Level Analysis: Sales vs City [more granular]
  * Granularity may only be compared in data against the same dimension, incase different dimension granularity may not be compared. If you still need to compare:
    * More number of rows = High granularity
    * Less number of rows = Low granularity
  * To move from high granularity to low granularity we do aggregation.
  * **Relation between number of dimension & measures with a chart's granularity.**
    * increasing/decresing number of dimension increases or decreases the  granularity of a chart.
    * increasing/decresing number of measures doesn't affect granularity
  * **Always use aggregated functions while doing calculations with measures in "Calculated Fields" when data is not at the highest granularity.** If your data is not at the highest granularity, do not use non-aggregated calculation.

  * When we are talking about granularity we should consider all the dimensions within the chart(be the dimension is in row, column or marks)



* **LOD(Level of Detail Calculation)**:
  * By default all calculations are done at chart granularity.
  * With LOD expression we can define a specific granularity to do the calculation.
  * **Types of LOD**:
    * [**Fixed LOD**](https://www.thedataschool.co.uk/hanna-nykowska/intro-to-tableau-lods-fixed/): Independent of Chart. `{FIXED [Category]:SUM([Sales])}`
    * [**Include LOD**](https://www.thedataschool.co.uk/hanna-nykowska/tableau-lods-include-and-exclude/): Chart Granularity plus whatever is there in include `{INCLUDE [Category]:SUM([Sales])}`
    * [**Exclude LOD**](https://www.thedataschool.co.uk/hanna-nykowska/tableau-lods-include-and-exclude/): Chart Granularity minus whatever in exclude. `{EXCLUDE [Category]:SUM([Sales])}`
  * **Fixed LOD**: Fix the granularity of a calculation.
    * we can use fixed lod fields in our calculation
    * Example
        * Find Category Level Sales. 
        * View Sales by Category and View Sales by Subcategory in the same chart.
        * Find share of each subcategory against it's parent category
    * **Aggregation of LOD doesn't matter** `Share of Subcategory: SUM([Sales])/SUM([Sum at Category])`
    Here `SUM([Sum at Category])` the SUM doesn't matter but tableau forces us to use it but it's redundant.
    * Usage:
        * 99% Fixed
        * 0.99% Exclude
        * rest Include

* Measure Names and Measure Values