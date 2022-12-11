# Canadian-household-spending-2010-2019
This project explores patterns of Canadian household spendings from 2010 to 2019. Throughout the analysis, I kept a few questions in mind. Which province is the most expensive to live in? Do people spend most money on rent, food, or something else? Are things getting a lot more expensive over the years?
## The Data
I analyzed a public dataset named “Household spending, Canada, regions and provinces” published by the Canadian government. The dataset can be downloaded from https://open.canada.ca/.<br>
The [dataset](household_spending.csv), which comes in an excel format, aggregates information about spending patterns of Canadian households across different provinces over the years from 2010 to 2019 through public survey. A [metadata file](11100222_MetaData.csv) of the dataset is also provided. <br>


## Summaries of Findings


<img width="722" alt="image" src="https://user-images.githubusercontent.com/64732803/206878017-fb292780-6515-4d50-8a9d-6eab0adf6201.png">
As of 2019, provinces with highest cost of living in Canada include Alberta, Prairie Region, and British Columbia. In these states, households spent more than CAD 100,000 per year. <br>
<img width="694" alt="image" src="https://user-images.githubusercontent.com/64732803/206878306-c30a0244-c237-4811-bc06-dc3e7caa3eab.png">
Households in Canada typical spend between CAD 56,000 and 80,000 on total current consumption, which includes items such as shelter, food, and transportation, among others. Annual income taxes range between CAD 11,800 and 23,400 (provincial tax rates vary from province to province). Insurance payments cost around CAD 4,600 up to 6,000. Most household gifted between CAD 2,000 and 3,000 in 2019.<br>

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
<img width="722" alt="image" src="https://user-images.githubusercontent.com/64732803/206878017-fb292780-6515-4d50-8a9d-6eab0adf6201.png">
As of 2019, provinces with highest cost of living in Canada include Alberta, Prairie Region, and British Columbia. In these states, households spent more than CAD 100,000 per year. Cost of living is lowest in Prince Edward Island, calculated at CAD 75,249 per year.

### Where has cost of living been rising the fastest?
All provinces experienced general increase in cost of living between 2010 and 2019.
<img width="662" alt="image" src="https://user-images.githubusercontent.com/64732803/206878043-08f562a4-010c-466d-a03d-ead498634bbd.png">
<br>During this period, provinces that experiences most significant increase in household spending are British Columbia (36.41%), Saskatchewan (36.21%), and Manitoba (33.44%). All provinces recorded at least a 25% increase in household spending.
<img width="653" alt="image" src="https://user-images.githubusercontent.com/64732803/206878060-6125a24b-f11b-4ea1-9f68-cbb112300470.png">


### What is the most significant expense for households?
<img width="694" alt="image" src="https://user-images.githubusercontent.com/64732803/206878306-c30a0244-c237-4811-bc06-dc3e7caa3eab.png">
Households in Canada typical spend between CAD 56,000 and 80,000 on total current consumption, which includes items such as shelter, food, and transportation, among others. Annual income taxes range between CAD 11,800 and 23,400 (provincial tax rates vary from province to province). Insurance payments cost around CAD 4,600 up to 6,000. Most household gifted between CAD 2,000 and 3,000 in 2019.

### What are the types of spending under total current consumption?
<img width="912" alt="image" src="https://user-images.githubusercontent.com/64732803/206878313-ef127dbd-0754-4b9c-a315-2cc840dcadca.png">
A breakdown of major type of spending under total current consumption is summarized below:
* Transportation (18%-22%)
* Shelter (24%-32%)
* Food (14%-17%)
* Healthcare (4%-5%). The relative low spending on healthcare can be attributed to a free public healthcare system for Canadian residents.
* Education (1.5%-3.5%). Similar to healthcare, public schools up to high school level provide free education for Canadian citizens.


## Dataset Limitation and Usage

The metadata file noted that in 2019, the survey questionnaire was restructured to reduce respondent burden. Thus, 2019 expenditures may no longer be directly comparable to previous years.<br>
The dataset covers data from 2010 to 2019. The COVID-19 pandemic and the war in Ukraine may have significant impact on cost of goods and household spending patterns. An inflation calculator tool provided on Bank of Canada website estimate that a bucket of goods and services that cost CAD 100 in 2019 would be priced at CAD 112 in 2022.<br>
As a result, the dataset may not be highly relevant when projecting current level of household spending in 2022. However, in the long run, when macroeconomic factors stabilize, the trend shown by this dataset is likely to continue in the future.<br>

