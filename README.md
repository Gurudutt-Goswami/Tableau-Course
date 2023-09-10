# Tableau-Course

### What is Tableau ?
Tableau is business & analytics software tool that helps people to understand, visualise & make data driven decisions in real time with extreme agility & accuracy.In simple words to extract information from a huge data sets we use tableau which in turn write SQL queries by itself based on visualisations selected by developer & make it interative to give meaningful insights.

### Versions of Tableau 
1) Tableau Desktop: Data viz application that facitilates user to examine virtually all types of structured data & generate interactive graphs, dashboards & reports quickly.
2) Tableau Server: BI application that offers browser based analytics, its an alternative to slow paced tableau desktop which is online & thus can be shared online, best for distributing & collaborating.
3) Tableau Online: Same as server its also a BI application that offers browser based analytics, its an alternative to slow paced tableau desktop, its a secure cloud based solutions used for sharing & collaborating on tableau views & dashboards.
4) Tableau Public: Free software to connect to a spreadsheet/file and create interative data visualisations for the web.
5) Tableau Reader: free desktop application that you can use to open & interact with data visualisations built in Tableau Desktop.  

### Tableau Features
1) Robust Security
  a) Provides proper Authentication for user access & data connections.
  b) Also provide you to integrate with other security protocols like active directory, kerberos etc.
  c) Practices low level filtering which helps to secure data.
2) Collaboration & Sharing
   Just like any other BI tool you can easily share reports/sheets/dashboards created in Tableau with other users via on-premise, cloud, hybrid etc.
3) Easy to do Time series & forecasting or drawing trend lines.
4) Provides both Live & in memory data connections.
5) Facitilates wide range of charts some unique ones are ghantt, motion chart etc.
6) Capable to show mobile view as well.
7) Wide range of Data sources.

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

### Hands on with Tableau
1) First perform all the necessary joins based on your requirement

### How to extract data sets in Tableau?
You can extract any report (in .hyper format) by going to Data tab -> Report Name -> Extract Data and now either you can extract everything in one table or to multiple tables & also you can select how to identify new rows by checking increamental refresh & then selecing the column name with which you want to identify them.


### Connecting to Tableau Server
From the starting screen click on Tableau Server & enter your server url -> Connect. After that enter credentials & you are done.
![Connect to Tableau Server](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/f660001e-72bf-4cf2-8157-3c08fa738398)
![Steps to follow once connection has been established to tableau server](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/d8a87d32-e572-4070-a15b-cabfd46f9fc4)


### Supported Data sources types
This can be determined by the license purchased. The professional edition supports over 40+ data connections including connections available in personal edition.
![connections](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/dcc2a819-91f1-411d-9b54-140e54410d66)


### Joining & Blending
##### Joins
To perform any type of join just drag the tables in data source section & then select the type of join along with column names with which you want to perform join.  
By default tableau performs inner join, though you can do left,right & full outer joins as well.  
In case sometimes right & full outer join is disabled then what you can do is write your own New Custom SQL but this options generally appears once you established connection from a database that is legacy connection though earlier it was also available for excel files. (Where while importing the excel files you not open it normally but select 'open with legacy connection' to get New Custom SQL option.(Note legacy connection uses microsoft jet data engine driver)
Joins are particularly useful when almost all the dimensions are coming from the same data source. (For exmaple considering our sample superstore data set if sales manager wants to get details regarding how many order have been returned from a region then we need to perform between orders & return tables based on region column)
![Joins](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/cf512042-857c-480f-82ed-9311641feb4a)

To read more about how to write custom sql : https://help.tableau.com/current/pro/desktop/en-us/customsql.htm
##### Blending
When your data is coming from multiple sources then after pulling those sources in Tableau you can directly use in columns from those different data sources & by default Tableau tags those sources as primary & secondary & just after the secondary source it puts an infinity symbol which basically tells developer to not use columns as linking fields. In this case you will not be able to perform joins as Tableau by default is doing blending your data. This is very useful when you have heterogenous data sources.
1) It requires a common dimension to establish a link between data sources.
2) It does not create row level joins.
3) It should be used when you have related data accross multiple data source that you want to analyze together in a single view.
4) Note if a field name is exactly same in multiple sources then Tableau identifies the common dimension automatically else it requires you to explicitly establish a link between those data sets on common dimension. (Just click on </> available near primary data source)
![Blended data](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/ab8f7b26-7c15-4f2c-b84d-9c78ecca329e)
![difference](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/2b2c53fb-eb6f-4429-9d29-da9455b429ca)


### Connection Type (Live & Extract)
#### Live : Any change in the data source will directly reflect in Tableau sheets.
#### Extract : It imports data first into Tableau Data Engine so any change in data source will not directly reflect in sheets but the speed of operation performed on this data will be much faster.
While selecting extract option you can add filters as well, also you can add incremental refresh based on certain fields. (More or less you can refer this type of connection as offline)
1) Extracts are subset of data source created & saved locally in your hard drive disk with .tde (tableau data extract) or .hyper extension.
2) Enable faster data retrival as it eliminate quering data source.
3) Can you filters & limits to only get focused data.
4) can be refreshed fully/incrementally to add recent data.
5) You can extract data even from live connections.
![extract data](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/b801ee2d-b44d-4cc9-af3f-e8acb6ffe384)



### Tableau Authentication
If kerberos is enabled then you don't need to provide server & other authentication details while publishing workbooks.
Tableau server supports kerberos based single sign on (SS0).
Users active directory accounts in a kerberos enabled environment can use single sign on to connect to tableau server from tableau desktop and web browsers.
![Kerberos](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/42d4cb2c-902b-4ce1-ac79-5dc0f1b2a159)
![kerberos setup](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/e065c4e4-102f-4b88-888a-8152d27e59ee)



### How to create calculated fields in Tableau?
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
![box_description](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/cced1c25-2624-4ed6-a96b-7844b088b4b7)

#### Combination Charts
Combined Axes are view which uses measures sharing single axis so that all the marks are displayed in a single pane. It uses 2 or more measures that share a single axes.
Combination charts are views that use multiple mark types in the same sheet. It can be customised to show the distinct mark type for each distinct measures which can be displayed in individual axis, blended axis or dual axis.
![combination chart](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/ee2f39c1-c63f-40c0-a73e-6f59769cffc7)

#### Map Plots
Tableau automatically assigns geographical roles to fields with common geographical names such as country,state, city & so on. It also automatically adds the lattitude & longitude to the fields added to rows & columns.

#### Scatter Plots
Used to visualise relationship between two numeric fields. Its uses one measure in column & atleast one measure in row.
![matrix scatter plot](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/b9c8e7ca-dc09-4f70-9e8b-7a3f38bb28d1)


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
![measure level filter](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/c09f1625-9e91-470a-a526-b34dd8cc6bd4)

#### Filter Types 
![Filter Options](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/0e8ea0fd-e10c-4ffc-9f3d-ad2e07ee32df)


#### How to remove null values?
Add that measure into the filter section & then select the aggregation you want to perform after that select the type of filter 
1) Range of values
2) at least
3) at most
4) special (here you can select to remove the null values)

#### How to last month/weeks etc data?
You can add the date field into the filter section & then select the relative date, after that you will 5 options 
1) Relative dates (here you can select the period that x month/week)
2) range of dates
3) starting date
4) ending date
5) special
![Filters details](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/585543c8-d159-47e8-a5fb-baa63dfdd5e7)


### Sorting of Data
![sorting](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/9d90c8c4-69ff-4895-aec4-973bf1588f04)


### Combined Fields
These are used to create cross product of members from different dimensions. The view will include all combinations of each members of the dimensions.
To create this select 2 fields from different dimensions & right click -> create -> combined fields.
![combined fields](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/cbd940f6-7f1a-4a7a-9e4a-9ee86d0e6104)

### Groups & Defining Aliases
![groups](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/e2ba1c46-8788-4686-bae4-110efb282381)
![aliases](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/3c4ea906-4c93-4e7a-b88a-a9b9a4480e1e)
![aliases characterstics](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/1aae7ddd-fc7a-4fff-9f63-73d586d12111)

### Sets & computed sets
1) Sets are custom fields that define a subset of dimension members.
2) It can be created for specific dimension members in the view or it can be based on a condition.
3) Computed sets are dynamic as the number of members in the set can vary at run time based on the condition.
4) You can also combine two sets to make a new set.

![sets](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/efeb7801-62b0-4299-8e10-34d2b557edcf)
![combined sets](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/82cc7180-35d9-4cfa-970c-e65dfe66647e)


### Hierarchy
A hierarchy is a grouping of related dimensions depicting direct parent-child relationships between them.
![hierarchy](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/b9d768ad-eb9a-400e-b8e8-a2691755aafd)



### Tips 
Quick table calculation, click on the field after adding that too rows & select quick table calculation. Using this you can see Running total(cummulative), difference, percent difference, percent of total, percentile, rank etc.


### Optimizing Performance
![performance](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/eda7ee1c-52ed-492f-8232-833c2bfa8ee8)
#### Shadow Extracts
Note: The folder which contains this will only be visible on licensed copy.
![tableau shadow extracts](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/5617ba05-fbb6-447f-be16-8463f29ba557)


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


#### Business Scenario
![scenario](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/df4efa9e-0ff8-463e-9cbb-369f44cae9e6)

Sol: 
1) Line chart - sales by order- yearly level
2) Drill quarterly
3) create a table calculation - difference

![scenario sol](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/3c27a663-8a41-4105-9fd3-229e88cab85c)


#### Business Scenario 2
![scenario 2](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/e4766aa9-dc9c-4296-b0c0-ddea1d1493db)
Sol:
1) Sales by state
2) Blended Axis - Profit and Sales
3) Filter - Phones
4) Scatter plot
![scenario 2 sol](https://github.com/Gurudutt-Goswami/Tableau-Course/assets/86184439/b4c2b6ce-5bfb-4a15-8c64-1f3b83a62d7f)
