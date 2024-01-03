# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 4: The Snack-o-Meter: A tool to inform public on consumption of biscuits​

### Problem Statement

The National Health Population Survey highlighted various actions to improve Singaporean health. The focus of our project will be on eating healthier.

Several measures have been implemented to promote healthy eating. This includes the Nutri-Grade labeling for beverages, which focuses on sugar and saturated fat, and has shifted consumption and led to reduction in sugar intake. More recently, Singapore has also shared that it is studying possible regulatory measures to reduce sodium content in food dishes. However, the nutritional values in snacks has not been widely discussed and this is the gap we are targeting to cover.

While all snacks should be considered, biscuit is used as the initial proof-of-concept due to its popularity. The objective of the project is to build a tool that can inform if a biscuit is healthy or not, helping consumers make healthier choices.

---

### Data Used

[`NTUC Fairprice`](https://www.fairprice.com.sg/category/biscuits): Data is scraped from NTUC Fairprice website, under category of Biscuits.
<br>Biscuit Subcategory: 
1) Creamed and Filled
2) Crackers
3) Wafers
4) Chocolate Cookies

---

### Data Dictionary

|Feature|Type|Description|
|---|---|---|
|**type**|*string*|Subcategory of Biscuit<br>cookie: chocolate cookie<br>cracker<br>cream: creamed & filled biscuit<br>wafers|
|**product**|*string*|Name of product|
|**per_serving_g**|*int64*|Size of serving per one gram (gram)|
|**total_fat_g_per_gram_of_serving**|*int64*|Total fats per gram of serving (gram)|
|**sugars_g_per_gram_of_serving**|*int64*|Sugars per gram of serving (gram)|
|**sodium_g_per_gram_of_serving**|*int64*|Sodium per gram of serving (gram)|
|**class**|*string*|Healthy<br>Unhealthy|
---

### Notebook description

* [`01_webscraping`](/code/01_webscraping.ipynb): Scrape nutritional value data from NTUC Fairprice website
* [`02_cleaning`](/code/02_cleaning.ipynb): Cleaning of data
* [`03_EDA`](/code/03_eda.ipynb): Exploratory data analysis
* [`04_modelling`](/code/04_modelling.ipynb): Modelling of the data

---

### Conclusion

- Our decision tree model yields train and test accuracy greater than 0.9, and the train cross validation score also shows that the model is reliable to be deployed for classification.
- With this model, we developed an user-friendly tool (https://snack-o-meter.streamlit.app/) to help consumers identify if the biscuit of their choice is healthy or not, and recommend healthier alternatives.

---

### Recommendations

#### 1 - Increase Public Awareness
- Through marketing campaigns (offline and online campaigns)​
#### 2 - Expand the model to include other snack types​
- For example: Nuts and chips
#### 3 - Integrate tool into HPB’s existing Health 365 app 
- Intergration is beneficial as it makes Health 365 as “one stop app”​

---

### Cost-Benefit Analysis

#### Estimated Cost (per year): $500,000

**1. Marketing Campaign for "Snack-O-Meter": $400,000**
   
The Nutri-Grade mark was officially launched on 30 Dec 2022. In FY2022, HPB spent $400,000 on programme, supplies & marketing.
Using this as a reference, it is expected that the marketing campaign for "Snack-O-Meter" will cost about the same.

_Sources:_ 
- _HPB Annual Report 2021/2022: https://www.hpb.gov.sg/docs/default-source/pdf/hpb-2022_2023-annual-report.pdf?sfvrsn=bec1a971_2_
- _MOH News Highlight: https://www.moh.gov.sg/news-highlights/details/rollout-of-nutri-grade-mark-on-30-december-2022_

**2. Application Development and Maintenance: $100,000**
   
The intention is for the "Snack-O-Meter" to be incorporated into HPB's existing application, the Health 365.
The advantage of integration (as opposed to building a standalone app) is that it would save cost on app development.
In addition, it also uses the Health 365 as a "one-stop" app for the public with regards to health matters.
Lastly, there would be no additional server cost required.

_Source:_ 
- _How Much Does It Cost to Develop an App in Singapore in 2022?: https://neetable.com/blog/app-development-cost-in-singapore_



#### Estimated Benefit (per year): $12,840,000​

**3. Healthcare cost of metabolic risk: $642,000,000**
   
Research conducted in 2023 calculated that the healthcare cost arising from metabolic risks would amounted to S$642 million.
Metabolic risk in this study is defined by high systolic blood pressure, high fasting plasma glucose, high LDL cholesterol.
Consumption of sodium, sugar, and fat are positively correlated to the above metabolic risk.

From FY2017 to FY2019, the median sugar level of beverages decreased from 8.5 to 6.3 grams per 100 ml (25%).
This was attributed to the Nutri-Grade campaign which led to suppliers reducing sugar in their beverages.

According to Etiqa's Nutrition Survey conducted in 2022, most snackers would snack more than 3 times in a week.
Assuming a person consumed a serving of Hello Panda Chocolate a day, that would constitute about 8% of the daily average fats, sodium and sugar intake overall in Singapore.
If the sucess of the Nutri-Grade campaign (25% reduction) can be applied to "Snack-O-Meter", a 2% (25% * 8%) reduction in daily intake of fats, sodium, and sugar intake is expected.
Lastly, assuming that reduction in consumption of those nutrients of concern can directly impact metabolic risk by the same %, then a reduction of healthcare cost of $12,840,000 is expected.

_Sources:_
- _The societal cost of modifiable risk factors in Singapore: https://bmcpublichealth.biomedcentral.com/articles/10.1186/s12889-023-16198-2_
- _Ministry of Health’s (MOH) National Population Health Survey (NPHS) 2022 and Health Promotion Board’s (HPB) National Nutrition Survey (NNS) 2022: https://www.moh.gov.sg/news-highlights/details/national-health-surveys-highlight-need-to-focus-on-healthy-diets-and-lifestyles_
- _Nutrition Survey Report: https://www.etiqa.com.sg/wp-content/uploads/2022/07/Nutrition-Survey-Report_20-Jul.pdf_
