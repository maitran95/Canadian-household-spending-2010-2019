# Candian-household-spending-2010-2019
This project explores the cost of living in Canada, and British Columbia in particular. Which province is the most expensive to live in? Do people spend most money on rent, food, or something else? Are things getting a lot more expensive over the years?
## The Data
I analyzed a public dataset named “Household spending, Canada, regions and provinces” published by the Canadian government. The dataset can be downloaded from https://open.canada.ca/.<br>
The [dataset](household_spending.csv), which comes in an excel format, aggregates information about spending patterns of Canadian households across different provinces over the years from 2010 to 2019 through public survey. A metadata file of the dataset is also provided. <br>


## Summaries of Findings


## Data Transformation
Let’s start with the raw data and explore how I came to the conclusions above. <br>

Here is a snippet of the raw dataset. <br>
<img width="846" alt="image" src="https://user-images.githubusercontent.com/64732803/206877810-fcd07471-8cca-4f1c-944a-891cf1449622.png">

Before it can be analyzed, the raw data need to undergo some cleaning. I used Python and Jupyter Notebook, heavily making use of pandas package to process the data. While detailed step-by-step commands can be found in a Jupyter Notebook file [here](data-transformation.ipynb), a short summary of the steps that I took is presented below.<br><br>
The process started with: 
*	Keeping relevant columns for analysis: REF_DATE (column A), GEO (column B), Household expenditures, summary-level categories (column E), and value (column L)
*	Give the relevant columns more descriptive names
<img width="533" alt="image" src="https://user-images.githubusercontent.com/64732803/206877781-c0dddf88-ba22-432c-b8fa-c1c9dbb5831f.png">

Now we have a concise data frame with relevant columns. Next, by referring to the metadata file, I know that not all expenses are equal. For example:
*	“total current consumption” is a subset of “total expenditure”
* “food expenditure” is a subset of “total current consumption” 
*	“food purchased from stores” is a subset of “food expenditure”
<br>We need to do further data transformation to correctly classify the type of expenses so that in the future, we will be able to analyze the expense accurately. By referencing to the metadata file, I used python to classify all expenses into their hierarchy.<br>
<img width="782" alt="image" src="https://user-images.githubusercontent.com/64732803/206877866-892cadd1-c38c-4a24-bd06-5f5539b711da.png">

Now the processed file is ready to be passed on to a visualization tool for further analysis. My choice of visualization tool is Tableau.
## Vizualizations and Insights
### Which province has the highest cost of living in Canada?

### Where has cost of living been rising the fastest?

### What is the most significant expense for households?



