# Tableau-Course

## Topics
1) [What is Tableau](#What-is-Tableau), [Versions of Tableau](#Versions-of-Tableau), [Tableau Features](#Tableau-Features)
2) [Advantages of Tableau](#Advantages-of-Tableau), [Disadvantages of Tableau](#Disadvantages-of-Tableau)
3) [How to extract data sets in Tableau](#How-to-extract-data-sets-in-Tableau)
4) [Connecting to Tableau Server](#Connecting-to-Tableau-Server)
5) [Supported Data sources types](#Supported-Data-sources-types)
6) [Joining & Blending](#Joining-n-Blending)
7) [Blending Limitations](#Blending-Limitations)
8) [Connection Type (Live & Extract)](#Connection-Type-Live-n-Extract)
9) [Tableau Authentication](#Tableau-Authentication)
10) [How to create calculated fields in Tableau](#How-to-create-calculated-fields-in-Tableau)
11) [Charts](#Charts)
12) [Formatting](#Formatting), [Filtering](#Filtering), [Sorting of Data](#Sorting-of-Data)
13) [How to remove null values](#How-to-remove-null-values), [How to last month/weeks etc data](#How-to-last-month-or-weeks-etc-data)
14) [Combined Fields](#Combined-Fields)
15) [Groups & Defining Aliases](#Groups-n-Defining-Aliases)
16) [Sets & computed sets](#Sets-n-computed-sets)
17) [Hierarchy](#Hierarchy),[Parameters](#Parameters), [Difference between Parameters n Filters](#Difference-between-Parameters-n-Filters)
18) [LOD Expressions](#LOD-Level-of-Details-Expressions), [Limitation of LOD](#Limitations-of-LOD-Expressions-in-Tableau), [Tables VS LOD Expressions](#Difference-Tables-Vs-LOD-Expressions)
19) [Reference-Lines](#Reference-Lines)
20) [Grand-Total-&-Sub-Totals](#Grand-Total-n-Sub-Totals)
21) [Bins](#Bins), [Mapping](#Mapping)
22) [Changing-aggregation-function](#Changing-aggregation-function)
23) [Optimizing-Performance](#Optimizing-Performance), [Shadow-Extracts](#Shadow-Extracts)
24) [Practice-Sets](#Practice-Sets), [Scenarios](#Scenarios), [Interview-Questions](#Interview-Questions)
25) [Row Level Security](#Row-Level-Security)


### What is Tableau
Tableau is business & analytics software tool that helps people to understand, visualise & make data driven decisions in real time with extreme agility & accuracy.In simple words to extract information from a huge data sets we use tableau which in turn write SQL queries by itself based on visualisations selected by developer & make it interative to give meaningful insights.

### Versions of Tableau 
1) Tableau Desktop: Data viz application that facitilates user to examine virtually all types of structured data & generate interactive graphs, dashboards & reports quickly.
2) Tableau Server: BI application that offers browser based analytics, its an alternative to slow paced tableau desktop which is online & thus can be shared online, best for distributing & collaborating.
3) Tableau Online: Same as server its also a BI application that offers browser based analytics, its an alternative to slow paced tableau desktop, its a secure cloud based solutions used for sharing & collaborating on tableau views & dashboards.
4) Tableau Public: Free software to connect to a spreadsheet/file and create interative data visualisations for the web.
5) Tableau Reader: free desktop application that you can use to open & interact with data visualisations built in Tableau Desktop.  

### Tableau Features
Robust Security
1) Provides proper Authentication for user access & data connections.
2) Also provide you to integrate with other security protocols like active directory, kerberos etc.
3) Practices low level filtering which helps to secure data.
4) Collaboration & Sharing
   Just like any other BI tool you can easily share reports/sheets/dashboards created in Tableau with other users via on-premise, cloud, hybrid etc.
5) Easy to do Time series & forecasting or drawing trend lines.
6) Provides both Live & in memory data connections.
7) Facitilates wide range of charts some unique ones are ghantt, motion chart etc.
8) Capable to show mobile view as well.
9) Wide range of Data sources.

### Advantages of Tableau
1) Remarkable visualisation
2) Ease of use
3) High Performance
4) Mobile friendly
5) Rich community

### Disadvantages of Tableau
1) High Cost
2) Inflexible pricing (pricing is independent of customer requirement)
3) Poor after sales support
4) Poor BI capabilities
5) Poor Version control

### Tableau File Types and Folders
You can save your work using several different Tableau specific file types: 
1) workbooks : .twb
2) bookmarks : .tbm
3) packaged data files : .twbx
4) data extracts : .hyper
5) data connection files : .tds & .tdsx
For more details: https://help.tableau.com/current/pro/desktop/en-us/environ_filesandfolders.htm

### How to extract data sets in Tableau
You can extract any report (in .hyper format) by going to Data tab -> Report Name -> Extract Data and now either you can extract everything in one table or to multiple tables & also you can select how to identify new rows by checking increamental refresh & then selecing the column name with which you want to identify them.


### Connecting to Tableau Server
From the starting screen click on Tableau Server & enter your server url -> Connect. After that enter credentials & you are done.
![Connect to Tableau Server](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/1f2b8e95-7e31-455a-9506-ae4db32e16bc)
![Steps to follow once connection has been established to tableau server](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/ec3ba12e-5d69-449e-a8e9-bfdc232d5274)



### Supported Data sources types
This can be determined by the license purchased. The professional edition supports over 40+ data connections including connections available in personal edition.
![connections](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/7409b78f-1830-4285-8ba4-db4ffdce660f)



### Joining n Blending
##### Joins
To perform any type of join just drag the tables in data source section & then select the type of join along with column names with which you want to perform join.  
By default tableau performs inner join, though you can do left,right & full outer joins as well.  
In case sometimes right & full outer join is disabled then what you can do is write your own New Custom SQL but this options generally appears once you established connection from a database that is legacy connection though earlier it was also available for excel files. (Where while importing the excel files you not open it normally but select 'open with legacy connection' to get New Custom SQL option.(Note legacy connection uses microsoft jet data engine driver)
Joins are particularly useful when almost all the dimensions are coming from the same data source. (For exmaple considering our sample superstore data set if sales manager wants to get details regarding how many order have been returned from a region then we need to perform between orders & return tables based on region column)
![4 Joins](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/6ca0c0b0-0baf-493b-bd17-661943a60326)


To read more about how to write custom sql : https://help.tableau.com/current/pro/desktop/en-us/customsql.htm
##### Blending
1) Blending is a method for combining data from multiple sources. It brings additional information from secondary source & display it with primary source direcly in the view.
2) Blends unlike joins never truly combines data, instead it queries each data source independently the results are then aggregated to appropriate level where they presented visually together in the view.
3) When your data is coming from multiple sources then after pulling those sources in Tableau you can directly use in columns from those different data sources & by default Tableau tags those sources as primary & secondary & just after the secondary source it puts an infinity symbol which basically tells developer to not use columns as linking fields. In this case you will not be able to perform joins as Tableau by default is doing blending your data. This is very useful when you have heterogenous data sources.
4) It requires a common dimension to establish a link between data sources.
5) It does not create row level joins.
6) It should be used when you have related data accross multiple data source that you want to analyze together in a single view.
7) Note if a field name is exactly same in multiple sources then Tableau identifies the common dimension automatically else it requires you to explicitly establish a link between those data sets on common dimension. (Just click on </> available near primary data source)

Example: Lets suppose we have a car & a bike data. In car data we have a column called Region & in bike we have a column called Zone. Apart from these two columns we have many other common columns. After bringing these two data sources in Tableau we go to Data -> Edit Blend Relationship. Tableau by default will show certain columns which can be matched but since we want to explicitly define blend relationship we can add Region & zone as matched column for blend. After this if we use fields from car data then it will treat car data as primary source & vice versa. Now suppose we want to see Sum of annual sales of both car & bike in a single chart then we need to make a blend calculated field, something like below which we can use in our chart. (Note: data source name has been added for car, also we need ZN to replace null values with 0)

![data blend calculation](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/bbbfc608-d26b-43e2-b3d5-f666ff902b7c)


### Blending Limitations
![6 blending limitations](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/cc6e6e09-abf3-4bf1-b17a-35ef806c78b8)



![7 Blended data](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/4bd9eef2-af9f-4291-baa8-e4da5b8480af)
![8 difference](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/a1399d93-3c5d-45f6-97d5-327b012e6302)
![9 difference new](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/c08a9cc7-7aaa-41fc-ab7c-b4ace6f6e745)





### Connection Type Live n Extract
#### Live : Any change in the data source will directly reflect in Tableau sheets.
#### Extract : It imports data first into Tableau Data Engine so any change in data source will not directly reflect in sheets but the speed of operation performed on this data will be much faster.
While selecting extract option you can add filters as well, also you can add incremental refresh based on certain fields. (More or less you can refer this type of connection as offline)
1) Extracts are subset of data source created & saved locally in your hard drive disk with .tde (tableau data extract) or .hyper extension.
2) Enable faster data retrival as it eliminate quering data source.
3) Can you filters & limits to only get focused data.
4) can be refreshed fully/incrementally to add recent data.
5) You can extract data even from live connections.
![extract data](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/93831f58-3c5b-4083-9532-d79bd816f92b)




### Tableau Authentication
If kerberos is enabled then you don't need to provide server & other authentication details while publishing workbooks.
Tableau server supports kerberos based single sign on (SS0).
Users active directory accounts in a kerberos enabled environment can use single sign on to connect to tableau server from tableau desktop and web browsers.
![11 Kerberos](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/8ebab794-9499-48b8-b18a-4c21fde1e6d9)
![12 kerberos setup](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/33af134e-76aa-47f0-9406-4ce404a8880f)



### How to create calculated fields in Tableau
1) Right click on any columan name -> create -> create calculated field
2) Go to analysis from menu tab -> create calculated field
3) You can also create from drop down just near the Dimensions section.

You can perform following types of calculations in Tableau
1) Arithematic Calculation:
eg) Sales per Item : SUM([Sales])/COUNTD([Product Name])
Note: You can change the default aggregation for measure by right click -> Default properties -> Aggregation -> select agg function
2) String Calculation: Contains([Customer Name], 'S*')
eg) Customer with S : STARTSWITH([Customer Name],"S")
3) Date Calculation : 
eg) Days to ship : Datediff('day', [order date], [ship date])
Note : the 'day' should be in lower case else it will throw an error
4) Logical Calculation :
eg) sales KPI :
IF SUM([Sales]) >= 100000
then 'High' 
ELSE 'Low'
END


### Charts
#### Box Plots
![13 box_description](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/37f09db8-8df2-4b1d-8cb4-197699db45ea)


#### Combination Charts
Combined Axes are view which uses measures sharing single axis so that all the marks are displayed in a single pane. It uses 2 or more measures that share a single axes.
Combination charts are views that use multiple mark types in the same sheet. It can be customised to show the distinct mark type for each distinct measures which can be displayed in individual axis, blended axis or dual axis.
![14 combination chart](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/f2100e1f-b3d3-4644-97ab-b8bb24f4d167)


#### Map Plots
Tableau automatically assigns geographical roles to fields with common geographical names such as country,state, city & so on. It also automatically adds the lattitude & longitude to the fields added to rows & columns.

#### Scatter Plots
Used to visualise relationship between two numeric fields. Its uses one measure in column & atleast one measure in row.
![15 matrix scatter plot](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/36428d12-b186-439b-999b-8f5feb36bf5a)


### Formatting
In the data source you can see a globe symbol for the column which can be used to represent in maps, also you can set what it represent that is country,state , city etc. or you can keep it by default to let Tableau decide. To format anything (Font, alignment, shading, border, lines) just go to format menu & click on a specific property which you want to modify, now it will add a seperate panel in the left hand side to adjust any property for sheets, rows & columns.

### Filtering
Condition that can be applied to dimensions, measures or fields to narrow down the data displayed in a view.
A) After adding a field to the filter section you get 4 options: (Dimension Level)
1) general(specific value(/s) to include/exclude
2) Wildcard (contains,starts with, endswith, exactly matches etc)
3) Condition (A logical condition mostly >,<,>=,<= etc.)
4) Top (top/bottom n rows by any specific field condition)

#### When filtering on a measure, you can either select filter row level data or an aggregated value of data.
![measure level filter](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/9e7d98de-22ef-4c43-9f31-e1286c69265d)

#### Extract Filters 
https://www.javatpoint.com/tableau-extract-filters#:~:text=Click%20on%20the%20%22Edit%22%20option,option%20present%20in%20the%20Window.

#### Filter Types 
![17 Filter Options](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/8c7db441-0548-491f-b219-dcd09e4c75e7)


#### How to remove null values
Add that measure into the filter section & then select the aggregation you want to perform after that select the type of filter 
1) Range of values
2) at least
3) at most
4) special (here you can select to remove the null values)

#### How to last month or weeks etc data
You can add the date field into the filter section & then select the relative date, after that you will 5 options 
1) Relative dates (here you can select the period that x month/week)
2) range of dates
3) starting date
4) ending date
5) special
![18 Filters details](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/420b9369-dde4-4ad4-bb1a-252083f1f3a9)


### Sorting of Data
![19 sorting](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/2a28cfd8-49da-45a4-ac21-c39bf07fe50d)



### Combined Fields
These are used to create cross product of members from different dimensions. The view will include all combinations of each members of the dimensions.
To create this select 2 fields from different dimensions & right click -> create -> combined fields.
![20 combined fields](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/cfb499e4-7857-4fe4-999b-c4ce6efff605)

### Groups n Defining Aliases
![21 groups](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/8345a1f5-63da-43e6-a0e7-d96d68470d74)
![22 aliases](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/9210aef9-82ba-4854-9aa9-237ffce2c194)
![23 aliases characterstics](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/dbe32707-8afd-4693-a1d4-c4d6d7f2fc74)

### Sets n computed sets
1) Sets are custom fields that define a subset of dimension members.
2) It can be created for specific dimension members in the view or it can be based on a condition.
3) Computed sets are dynamic as the number of members in the set can vary at run time based on the condition.
4) You can also combine two sets to make a new set.
![24 sets](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/fa4387ad-93c9-4139-8d5e-44c88125e4d8)
![25 Combined sets new](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/34ac7d69-b176-4cdf-b1c9-64dee64efcb4)

### Hierarchy
A hierarchy is a grouping of related dimensions depicting direct parent-child relationships between them.
To create a hierarchy just drag a field on to another & name it according. In case you want to add a new field into just drag that field to a specific level with in a hierarchy & you are done.

![26 hierarchy](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/12dc5e4c-6003-4554-82b5-face71cc418b)
![27 date hierarchy](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/3f5b288d-96c0-4226-b98a-e0ae913a0b32)


![28 scenario 4](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/e72a6610-5675-4221-94b6-5db40e19e9da)
You can also add filters for specific quaters & also quick table calculation like running total to see actual growth year by year
![29 scenario 4 sol](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/cafe21e4-6e00-4845-9285-eacdeeff02f7)
Pivotting date parts to view it in better way
![30 scenario 4 better sol](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/5ea22534-f522-43d1-b6bb-69d5663d5acc)


### Parameters
1) Top N parameters: Just add the filter & while selecting top n select create a parameter & then you can select list with certain values & how those values should appears & after creating you can show parameter in your sheet.
![31 top n parameters](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/48836087-3a99-4d75-b5e6-d375cbb6f410)


3) Date Field Parameter : Create a string parameter which will contains the string values (year,quarter,month,week & day) & based on this we will then create calculated field which will take this parameter values.
![32 date field parameter](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/49950b3d-8a26-48b1-8579-b43fefbaad65)
After creating this create following calculated field
Note that `2 Date Field Parameter` is the name of the date parameter
```
Case [2 Date Field Parameter]
when "Year" THEN STR(YEAR([Order Date]))
when "Quarter" THEN STR(YEAR([Order Date])) + "/Q" + DATENAME('quarter',[Order Date])
when "Month" THEN DATENAME('month',[Order Date]) + "" + STR(YEAR([Order Date]))
when "Week" THEN "Week" + STR(DATEPART('week',[Order Date]))
when "Day" THEN STR(DATE([Order Date]))
END
```
Once its created you can use this calculated values in your visualisations.

3) Dynamic Dimension Parameter
Create a string parameter which will contain (Category, ship mode & Segment) & based on this we will then create a calculate field which will take this parameter values as case conditions.

![33 dynamic dimensions parameter](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/28084bc1-cb68-476f-a981-72efb7d1818c)
After this create following calculated field
Note that `3 Dynamic Dimensions Parameter` is the name dynamic parameter.
```
CASE [3 Dynamic Dimensions Parameter]
when "Category" then [Category]
when "Ship Mode" then [Ship Mode]
when "Segment" then [Segment]
END
```
Once its created you can use this calculated values in your visualisations.

4) Dynamic Measures Parameter
Create a string parameter which will contain (Sales, profit & Quantity) & based on this we will then create a calculated field which will take this parameter values as case conditions.
![34 dynamic measure parameter](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/8ad7a8f1-7f59-4e81-bace-cd38c34c6f33)

After this create following calculated field
Note that `4 Dynamic Measure Parameter` is the name dynamic parameter.
```
CASE [4 Dynamic Measure Parameter]
when "Sales" then [Sales]
when "Profit" then [Profit]
When "Quantity" then [Quantity]
END
```
Once its created you can use this calculated values in your visualisations.


5) Both Dynamic Dimensions & Dyanamic Measures
Directly use calculated fields which we have created in 3) & 4) & put them in columns & rows respectively. Now you visualisation should change according to the parameters selection.



### Difference between Parameters n Filters
![35 difference parameter   filters](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/d244b9a7-2fc4-4ff5-b4ba-1139e09ef72d)



### LOD Level of Details Expressions
LOD expressions are employed to execute complex queries at data source level instead of bringing them to tableau interface.
1) Row level LOD expressions (expressions referencing unaggregated data source columns are computed for each row in the underlying table)
2) View level LOD expressions (expressions referencing aggregated data source columns are computed at the dimensionality defined by the dimensions in the view)
```<Dimension Declaration> : <aggregate expression>```
Types of LOD expressions
1) Include (Row level)
```
a) {INCLUDE [Customer ID] : SUM([Sales])} 
b) Avg({INCLUDE [State] : SUM([Sales])}) => Sum of sales per state
```
2) Exclude (View level)
```{EXCLUDE [Region] : sum([Sales])}```
3) Fixed
```{FIXED [Region] : SUM([Sales])}```


### Limitations of LOD Expressions in Tableau 
1) Behave unreliable view when floating values are involved.
2) LOD expression will not be shown in data source.
3) With data blending, the linking field from the primary data source must be in the view before you can use a LOD expression from the secondary data source.

### Difference Tables Vs LOD Expressions






### Reference Lines
1) Create a date parameter first with date data type.
2) Now go to analytics tabs & drag reference lines to the visualisation section & drop it on table.
3) Now here you can use that date parameter which you create in step 1 & can also modify the line type & color.
![36 reference line](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/1970f7d7-f687-4f6d-801c-28b91383bd86)


### Grand Total n Sub Totals
1) Totals facitilates the aggregation of data in a View.
2) It can only be applied to grid type visualisations.
3) Sub totals & grand totals are computed as a seperate calculation of the measure at a coarser level of granularity.
4) To apply this go to the analytics panel & drag totals to the visualisations.


### Bins
1) Custom bandings of values of a measure based on a specific size.
2) Can be thought of as bucket of values.
3) Two Types : Fixed sized & variable sized.
4) Note : To create variable sized bins you need to first create a calculated field out of those columns & then you can use this newly generated column to create bins of your own sized.
#### Fixed sized Bins
![37 bins](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/680667f9-22f1-4fac-a298-d61e6d0cbf97)


#### Variable sized Bins
Note in the following there are 3 bins of different sizes 
![38 variable sized bins](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/5f3cf934-8d63-4e39-ba1a-751080e6dfaa)


### Mapping
Difference between symbol map & normal map is that in symbol map one can use 0 to 2 measure while in normal map one can only use 0 to 1 measure.
![38 scenario 3](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/563890ba-0f99-443a-9c6e-587ff7027e95)


Note : Before proceeding if your data has any such values which Tableau doesn't able to understand then it will throw an error at the bottom right & on click you will see a pop up to correct the same.
1) Double click on state this will generate longitude & lattitude.
2) Put sales in color by. (This means darker the color higher the sales & vice versa)
3) Put profit into the size. (This means larger the size greater the profit & vice versa)
4) Show the labels.

In case tableau is not able to detect geographic roles you can do following
Note: In case you are providing your custom geocoding then keep in mind that the longitude & lattitude should be real numbers & that up to 1 decimal places at least.
![39 map problem](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/ad3a57ab-0189-44c7-86a2-bc0880d3f51a)

Custom geocoding
![41 german postal code](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/5188133d-2ae1-4ea0-9812-41469de75ba8)



you can also explicitly tell tableau geographical role if you think its not correct by default
![42 geographical roles change](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/b8b8eb8d-b826-4f9f-b046-809b7f07e709)





### Changing aggregation function
![43 changing aggregation function](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/bdb89ac7-2ad7-4522-a458-311096474ca5)



### Tips 
Quick table calculation, click on the field after adding that too rows & select quick table calculation. Using this you can see Running total(cummulative), difference, percent difference, percent of total, percentile, rank etc.


### Optimizing Performance
![44 performance](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/686b2586-bab9-4e10-b2ea-dd8ff1c04a29)

#### Shadow Extracts
Note: The folder which contains this will only be visible on licensed copy.
![45 tableau shadow extracts](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/ce0934b1-2e05-4d69-9bcf-8b6ee29857a4)



### Practice Sets

#### Q1: Reviewing profit per state in decending order & also seeing which orders have been returned per state per customer ?

Steps to perform
1) Import Sample superstore data set 
2) Inner join between orders & People based on Region
3) Left join between order & returns based on Order Id
4) Go to sheet 1 & add state & person in rows 
5) Add distinct count of order id (returns) & sum(profit) to columns
6) sort based on profit

#### Q2: Create a set to show states with 100 or more customers ?
Sol: Right click on any column name -> Create -> Set -> Give set Name -> go to condition -> By field > Count(Customer Name) >= 100

#### Q3: Create calculated fields to show the average sales per customer?
Col Name : Avg sales per customer
Sol: AVG({INCLUDE [Customer Name]:SUM([Sales])})

#### Q4: Calculated fields to show sales goals?
Col Name : Sales Goal
Sol: 
if MIN([States with 100+ Customers])= TRUE
THEN SUM([Sales]) *1.3
ELSE [Avg sales per customer]*100
END

#### Q5: Calculated fields to show emerging & developing states?
Col Name: Emerging or Developing State
Sol:
if COUNTD([Customer Name]) >= 100
then "Developing State"
else "Emerging State"
END

#### Q6: Use Q3, Q4 & Q5 and show avg(sales goal) & sum(sales) & distinct(customer count) per state?
Sol: 
1) Add Agg(sales goal) in columns
2) Add State in Rows 
Now you should be able to see Sales goal per state 
3) Now add customer name in columns & make it distinct
4) Make it(Customer Name) discrete if its continous as its discreate entity.
4) Add Sum(sales) in Column
5) Go to Show me & select bullet graph
6) Now since only one thing can be in columns you can right click on the x-axis & select swap reference line fields
Add on
7) Now put Emerging or Developing State in color & rename the sheet as well to the same.
8) You can sort based on distinct customer count or sales goal

### Scenarios
#### Business Scenario
![46 scenario](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/9a531b68-1026-4a6c-bf40-c42e60303f86)


Sol: 
1) Line chart - sales by order- yearly level
2) Drill quarterly
3) create a table calculation - difference
![47 scenario sol](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/9a328ebb-9c21-4b07-817b-fc44f5c42d44)




#### Business Scenario 2
![48 scenario 2](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/988826b4-94bf-4eae-8a4c-c71bb730a624)

Sol:
1) Sales by state
2) Blended Axis - Profit and Sales
3) Filter - Phones
4) Scatter plot
![49 scenario 2 sol](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/9cbebb1c-6f0e-4d38-98fb-c1c1dd51d10e)




### Interview Questions
(https://www.youtube.com/watch?v=Kkg27cnLc1I)

#### Q. Data types supported in tableau?
1) String (Text Values)
2) Date
3) Date & Time
4) Numerical/float
5) Boolean Values (True/False)
6) Geographical Values (Used with Maps)
Note: We can also change the data type of any field in the data source

#### Q. What are dimensions & Measures?
1) Dimensions are Qualitative fields/Categorical Fields
2) Measure are numberical/Quantitative fields.  
![50 Dimensions](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/7c44a9e0-8903-41c7-a8e2-c918c6d2d1ec)
 | ![51 measures](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/4f7ce0d9-b5a4-450c-9b41-7a5f1542211b)

Note : Tableau automatically detects data type for each column & also by default aggregation type for measure is Sum but you can change it.

#### Q. Discrete(Blue) & Continuos(Green)? 
1) Discrete : Observations are recorded on specific date.
2) Continous : Observations are recorded for all dates.
Note: Both dimensions & measures can be discrete or continous.
Example:
Discrete Dimension : Product Name
Continous Dimension : Year(Order Date)
Discrete Measures : Sum(Profit)
![52 sum of profit](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/2b5dc5e3-4e00-440e-802e-7070c9e6240b)
Continous Measures : Sum(Profit)

#### Q. Filter & their types?
Filters are way to restrict data that allows you to only see the data you want to see.
![53 Order of operations](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/79fc2f99-1a1a-4691-9ce4-84c1ebe03e90)


#### Q. There are 3 customer segments in superstore data set. What % of profits is associated with the corporate segment ?
1) Add segment in rows.
2) Double click on profits.
3) add table calculation to Percent of total.

#### Q. Different join in tableau?
Sol : Inner, left, right & full outer.
Note : To get product of two fields select those field right click & create computed fields. This will contain product of those two column. (mxn rows).
You can also do union which is basically to add rows of 2 or more tables into one.

#### Q. Joining & Blending?
Joining : Combining the data between 2 or more tables or sheets within the same data source is data joining.  
Blending : Combining data from 2 or more different/heterogenous sources.  
Note: In blending we actually dont combine data but query different sources independently & the field the visual uses define the primary & secondary sources.

#### Q. Live & Extract?
1) live connection offer convenience of real time updates, with any changes in the data source reflected in tableau.
2) Extract are snapshots of data optimized for aggregation & loaded into system memory to be quickly recalled for visulization.
Note: In Tableau server you can add schedule to refresh extract data to be updated.

#### Q. Calculated Field? (=#)
You can create new field by adding certains conditions & functions on your existing fields that is called calculated fields.

#### Q. How to display top 5 & bottom 5 in same view?
Create two sets, one for top 5 & other for bottom 5 & then combine those two sets, then use this set in filter condition.
![Combined sets new](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/9ab02936-afba-4a5c-8435-3c7517449135)

#### Q. Groups & Sets?
1) Group : 1 dimensional, used to create High level category.
2) Set : Multi dimensional & can contain conditions as well.
Note : We can't use group in calculated fields but can use sets.
![54 grouping](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/7cb7f0c0-e991-4858-a898-3afbd37f23af)


#### Q. Parameter? Example? ( ~Document Properties in Spotfire)
Parameters are dynamic values that can replace constant values in calculations, filters & reference lines.
Lets suppose we want to give an option to user to select top & bottom 5,10,15 & 20 customers based on profits, then we can make a parameter with range values values (PFB the image) from 5 to 20 with a step size of 5 & then can use this parameter in those two sets which represents top & bottom n customers.
![55 paramter new](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/cd96093a-c93e-490e-b02d-57e440511ad4)

#### Q. Tree Map & Heat Map?
1) Heat Map : Used to compare categories using color & size. For example extreme high/low the profit darker the color & vice versa.
2) Tree Map : Used to represent hierarchiral data. The space in view is divided into rectangles that are sized & ordered by a measure.
Note: Main difference is the hierarchy.
![56 heat map](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/dbbf331c-c301-4100-bf8f-9582ea399e3c) | ![57 Tree Map](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/65d27d61-6b9b-4a75-ab57-a3fa1528f199)


#### Q. .twbx & .twb?
1) .twbx : Tableau packages workbook, contains all the information necessary to work in tableau along with the data source.
2) .twb : xml document, contains only the instructions to interact with the data source, thus data source needs to be attached seperately.

#### Q. worksheet, dashboard, story & workbook?
![58 all](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/c77e4a14-60d6-4064-a73d-b667bc9a5499)

Note: Story is more or less a ppt kind off mode where we want to convey something in a sequential & more meaningful manner, basically it directs the person on focused area.
Points to remember: 
1) We can only access dimensions, measures & custom fields in a worksheet.
2) From dashboard we can access sheets but not dimensions & measures directly.
3) From story we can access the dashboard & worksheet but not the dimensions & measures directly.


#### Q. Blended Axis?
Blended Axis is used to blend two measures to share an axis when they have same scale.
![59 blended axis](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/ad1ab0be-5e35-4714-83e9-2e873c05d482)


#### Q. Dual Axis? How to Create?
Dual axis allows you to compare measures with different scales.
Note: You can convert dual axis to blend axis by right click -> synchronise axis.
![60 dual axis](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/99699512-9daf-4126-86ad-510cf7c4f94f)


#### Q. Difference dual & blend axis?
dual axis has two marks cards where as blend has only one & ofcourse dual axis has two axis where as blend has only one. Dual axis is particularly useful when we have measures of different scales.
Also in dual axis we change chart types for each measure which is not the case with the blend axis.

#### Q. Left(3,'Tableau')?
It will throw syntax error. Left('Tableau',3) => Tab

#### Q. Null Values & other special values?
Filter values -> Special values -> Non null values. You can do this manually or just click on the right bottom where you see null values & click on filter values. In case you think for these values the values should be 0 then you can select the 2nd option.
![61 null values](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/51127927-b3a5-45ad-8c7b-211eab9f21f4)


#### Q. 2nd Top product by subcategory by sales for first class ship mode?
Columns -> sub-category rows -> Sum(sales) filter-> ship mode(first class) sol: chairs
![62 sol](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/00b5db99-67bf-4176-bbc6-09a507ab8606)

#### Q. Customer name with lowest profit & what's his/her profit ratio?
Make a new calculated field ```Profit Ratio -> Sum(Profit)/Sum(Sales)``` & plot Sum(sales) by customer name & sort it by decending order & put this profit ratio on labels.


#### Q. Rank, Rank_Modified, Rank_Dense, Rank_Unique?
Note: All Rank function by default works descending
Also Rank_Unique though gives unique ranking but prefers according to ascii.
![63 all ranks](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/5c22fc25-0709-4872-a1b9-60988ed73f11)


#### Q. Embed webpage in dashboard?
1) First double click on country & filter it by US.
2) Add sum of sales in color by & show sum(sales) & state in labels.
3) After this make a dashboard & add this map sheet along with a webpage from object section.
4) Now go to dashboard -> action -> add action -> go to url -> add ```https://en.wikipedia.org/wiki/``` url & at last apend state to it ```<state>``` & select ```select```.
5) Now whichever state from above chart you will click you will be able to its wikipedia page.
![64 dynamic web page](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/f08c3b7d-9e26-44ba-bc1a-15d09771df8c)


### Q. Design a view to show region wise profit & sales?
This question demands how much efficient you can portray these details.
1) Double click on states since Region is not a map type
2) Convert chart type from automatic to Map
3) Drop Region to color by
4) Drop state, sum(sales), sum(profit) on labels
![detailed](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/201461a8-6316-47eb-b089-d6091c353944)


### Q. Optimize performance of a dashboard?
![65 performance new](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/cd9d3cd4-7d46-434b-b26c-766021012a70)


### Q. Viz according to scenario?
![66 type of viz](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/3af94c29-2e35-4690-bae6-1a3819b630fe)


### Q. What will you do if some countries/province (any grohraphical entity) is missing & displaying a null when you use map view?
![67 map issue solution](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/5eb6da5b-8de0-4a99-bc38-e6c33f96a6ad)
![68 options map issue solution](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/fd898c4a-45be-457f-96b4-f95cbc5c33bc)


### Q. LOD expressions?
Level of details expression are used to Run complex queries involving many dimensions at the source level instead of bringing them to tableau interface.
1) Include (includes dimension & view level dimensions) (performs like measures)
2) Exclude (excludes that dimension)
3) Fixed (only include the mentioned dimension) (performs like boolean)
![69 exclude LOD](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/712fcc0d-1189-475c-86b7-e8d32217753e)

### Q. Compute daily profit using LOD?
LOD 1 
![70 LOD Exp 1](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/ecb104bb-7f89-4a17-8786-c016a38a3643)

LOD 2
![71 LOD Exp 2](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/0d8b9ff1-35cb-45db-95a0-8da2116b43fd)

![72 profits by LOD](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/5b8a4966-1753-43f3-aabf-3877841b57d4)


### Q. How can you schedule a workbook after publishing it?
![schedule](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/1458874b-873e-487d-b541-d5bd42fef167)
![73 schedule](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/ec0a9aab-c16c-4c3f-8c14-5282cecafb51)
![74 schedule 2](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/5a87cd22-2505-4d43-bf0d-2cda13221c37)

### Row Level Security
https://help.tableau.com/current/server-linux/en-us/rls_options_overview.htm#:~:text=The%20simplest%20way%20to%20achieve,%E2%80%9D%20column%20is%20%E2%80%9CEast%E2%80%9D.
