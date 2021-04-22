# Excel-Analysis

## Background

Over $2 billion has been raised using the massively successful crowdfunding service, Kickstarter, but not every project has found success. Of the more than 300,000 projects launched on Kickstarter, only a third have made it through the funding process with a positive outcome.

Getting funded on Kickstarter requires meeting or exceeding the project's initial goal, so many organizations spend months looking through past projects in an attempt to discover some trick for finding success. For this project, I will organize and analyze a database of 4,000 past projects in order to uncover any hidden trends.

All of the below described analysis can be seen in my [Workbook](Workbook.xlsx).

### Outline of Analysis

Using the Excel table provided, I modified and analyzed the data of 4,000 past Kickstarter projects as I attempted to uncover some market trends.

* I used conditional formatting to fill each cell in the `state` column with a different color, depending on whether the associated campaign was successful, failed, or canceled, or is currently live.

* I created a new column O called `Percent Funded` that used a formula to uncover how much money a campaign made to reach its initial goal.

* I used conditional formatting to fill each cell in the `Percent Funded` column using a three-color scale. The scale starts at 0 and is a dark shade of red, transitioning to green at 100, and blue at 200.

* I created a new column P called `Average Donation` that used a formula to uncover how much each backer for the project paid on average.

* I created two new columns, one called `Category` at Q and another called `Sub-Category` at R, which used formulas to split the `Category and Sub-Category` column into two parts.

* I created a new sheet with a pivot table that analyzed the initial worksheet to count how many campaigns were successful, failed, canceled, or are currently live per **category**.

    * I used this to create a stacked column pivot chart that can be filtered by country based on the table you have created.

* I created a new sheet with a pivot table that analyzed the initial sheet to count how many campaigns were successful, failed, or canceled, or are currently live per **sub-category**.

    * I used this to create a stacked column pivot chart that can be filtered by country and parent-category based on the table you have created.

* The dates stored within the `deadline` and `launched_at` columns use Unix timestamps. I did the following to make these dates more user friendly.

  * I created a new column named `Date Created Conversion` that used [this formula](https://www.extendoffice.com/documents/excel/2473-excel-timestamp-to-date.html) to convert the data contained within `launched_at` into Excel's date format.

  * I created a new column named `Date Ended Conversion` that used [this formula](https://www.extendoffice.com/documents/excel/2473-excel-timestamp-to-date.html) to convert the data contained within `deadline` into Excel's date format.

* Finally, I created a new sheet with a pivot table with a column of `state`, rows of `Date Created Conversion`, values based on the count of `state`, and filters based on `parent category` and `Years`.

  * Then, I created a pivot chart line graph that visualizes this new table.

### Bonus Analysis

* I created a new sheet with 8 columns:

  * `Goal`
  * `Number Successful`
  * `Number Failed`
  * `Number Canceled`
  * `Total Projects`
  * `Percentage Successful`
  * `Percentage Failed`
  * `Percentage Canceled`

* In the `Goal` column, I created 12 rows with the following headers:

  * Less than 1000
  * 1000 to 4999
  * 5000 to 9999
  * 10000 to 14999
  * 15000 to 19999
  * 20000 to 24999
  * 25000 to 29999
  * 30000 to 34999
  * 35000 to 39999
  * 40000 to 44999
  * 45000 to 49999
  * Greater than or equal to 50000

* I used the `COUNTIFS()` formula tocount how many successful, failed, and canceled projects were created with goals within the ranges listed above. I populated the `Number Successful`, `Number Failed`, and `Number Canceled` columns with this data.

* I added up each of the values in the `Number Successful`, `Number Failed`, and `Number Canceled` columns to populate the `Total Projects` column. Then, using a mathematical formula, I found the percentage of projects that were successful, failed, or canceled per goal range.

* Last, I created a line chart that graphs the relationship between a goal's amount and its chances at success, failure, or cancellation.

### Bonus Statistical Analysis

If one were to describe a successful crowdfunding campaign, most people would use the number of campaign backers as a metric of success. One of the most efficient ways that data scientists characterize a quantitative metric, such as the number of campaign backers, is by creating a summary statistics table.

In this final section, I evaluated the number of backers of successful and unsuccessful campaigns by creating **my own** summary statistics table.

* I created a new worksheet in my workbook, and created a column each for the number of backers of successful campaigns and unsuccessful campaigns.

* I used Excel to evaluate the following for successful campaigns, and then for unsuccessful campaigns:

  * The mean number of backers.

  * The median number of backers.

  * The minimum number of backers.

  * The maximum number of backers.

  * The variance of the number of backers.

  * The standard deviation of the number of backers.

* I then used my data to determine whether the mean or the median summarizes the data more meaningfully.

* Lastly, I used my data to determine if there is more variability with successful or unsuccessful campaigns. Does this make sense? Why or why not?

## Written Analysis
* Finally, I created a report in Microsoft Word and answer the following questions. Answers to these can be seen [here](Analysis.md) or [here](Analysis.docx).

    1. Given the provided data, what are three conclusions we can draw about Kickstarter campaigns?
    2. What are some limitations of this dataset?
    3. What are some other possible tables and/or graphs that we could create?
    4. Does the mean or the median summarize the data more meaningfully?
    5. Is there more variability with successful or unsuccessful campaigns? Does this make sense? Why or why not?
