# Kaggle dataset - Store Sales - Time Series Forecasting
<p align='justify'>In this dataset containt a thousands of product families sold at Favorita stores located in Ecuador. There are several explanations:
<h3> train.csv</h3>
<ul>
  <li>The training data, comprising time series of features store_nbr, family, and onpromotion as well as the target sales.</li>
  <li>store_nbr identifies the store at which the products are sold.</li>
  <li>sales gives the total sales for a product family at a particular store at a given date. Fractional values are possible since products can be sold in fractional units (1.5 kg of cheese, for instance, as opposed to 1 bag of chips).</li>
  <li>onpromotion gives the total number of items in a product family that were being promoted at a store at a given date.</li>
</ul>
<h3>test.csv</h3>
<ul>
  <li>The test data, having the same features as the training data. You will predict the target sales for the dates in this file.</li>
  <li>The dates in the test data are for the 15 days after the last date in the training data.</li>
</ul>
<h3>sample_submission.csv</h3>
<ul>
  <li>A sample submission file in the correct format.</li>
</ul>
<h3>stores.csv</h3>
<ul>
  <li>Store metadata, including city, state, type, and cluster.</li>
  <li>cluster is a grouping of similar stores.</li>
</ul>
<h3>oil.csv</h3>
<ul>
  <li>Daily oil price. Includes values during both the train and test data timeframes. (Ecuador is an oil-dependent country and it's economical health is highly vulnerable to shocks in oil prices.)</li>
</ul>
<h3>holidays_events.csv</h3>
<ul>
  <li>Holidays and Events, with metadata</li>
  <li>NOTE: Pay special attention to the transferred column. A holiday that is transferred officially falls on that calendar day, but was moved to another date by the government. A transferred day is more like a normal day than a holiday. To find the day that it was actually celebrated, look for the corresponding row where type is Transfer. For example, the holiday Independencia de Guayaquil was transferred from 2012-10-09 to 2012-10-12, which means it was celebrated on 2012-10-12. Days that are type Bridge are extra days that are added to a holiday (e.g., to extend the break across a long weekend). These are frequently made up by the type Work Day which is a day not normally scheduled for work (e.g., Saturday) that is meant to payback the Bridge.</li>
<li>Additional holidays are days added a regular calendar holiday, for example, as typically happens around Christmas (making Christmas Eve a holiday).</li>
</ul>
<h2> Preparation Data </h2>
<p>First step is load all data of stores.csv, train.csv, and transaction.csv. In this data, we dont have missing value or data with a large range. So, it can be to process and analyze.</p>
<img src="https://github.com/MrNoTaiL/kaggle-Store-Sales-Time-Series-Forecasting/blob/main/img/1.jpg"></img>

<h2>Exploratory Data</h2>
<p align='justify'>Import attribut for analyze data. First we can see transaction data. The transaction data contain information about date, store_nbr, and transaction. We can analyze average sales per year by grouping transactions from 2013 to 2017.</p>

<img src="https://github.com/MrNoTaiL/kaggle-Store-Sales-Time-Series-Forecasting/blob/main/img/2.jpg"></img>
  
<p align='justify'>We can see that the average transactions per year has been decreased. It happen from 2014 to 2016. The transactions decreased may be due to lack of people buying goods from family. Also, it happens on average transactions per week. For example, in January 6,2013 average transactions amount 1641.09. it means transactions made during the week starting the day after january 6,2013.</p>
  
<img src="https://github.com/MrNoTaiL/kaggle-Store-Sales-Time-Series-Forecasting/blob/main/img/3.jpg"></img>
<img src="https://github.com/MrNoTaiL/kaggle-Store-Sales-Time-Series-Forecasting/blob/main/img/4.jpg"></img>

<p align='justify'>The transactions made by store can be seen in this part. For largest transactions occur in number 44,47,46,3. The store_nbr data identifies the store at which the products are sold. The store with the number 44 is in the city Quito, Pinchincha, type A, cluster 5.</p>

<img src="https://github.com/MrNoTaiL/kaggle-Store-Sales-Time-Series-Forecasting/blob/main/img/5.jpg"></img>
<img src="https://github.com/MrNoTaiL/kaggle-Store-Sales-Time-Series-Forecasting/blob/main/img/6.jpg"></img>

<p align='justify'>The train dataset contain id,date,store_nbr,family,sales,and onpromotion. The highest sales occur on family Grocery I at Quito, Pichincha, type D, cluster 13. So, it can be conclude that this area has the highest sales on May 2,2016.</p> 

<img src="https://github.com/MrNoTaiL/kaggle-Store-Sales-Time-Series-Forecasting/blob/main/img/7.jpg"></img> 
  
<p><b>ANOVA</b></p>
<p align='justify'>Anova is a statistic analytic method. it can use test for difference between more groups. The groups mean treatment type. So, in this section, import attribute for analyze (i.e:  f_oneway). The groups there are AUTOMOTIVE,BABY CARE, BEAUTY, BEVERAGES, BOOKS, BREAD/BAKERY, CELEBRATION,CLEANING, DAIRY, DELI, EGGS,  FROZEN FOODS, GROCERY I, GROCERY II, HARDWARE, HOME AND KITCHEN I, HOME AND KITCHEN II, HOME APPLIANCES	, HOME CARE, LADIESWEAR, LAWN AND GARDEN, LINGERIE, LIQUOR, WINE, BEER, MAGAZINES, MEATS, PERSONAL CARE, PET SUPPLIES, PLAYERS AND ELECTRONICS, POULTRY, PREPARED FOODS, PRODUCE, SCHOOL AND OFFICE SUPPLIES, SEAFOOD. So, first we can group it by family.</p>
    
<img src="https://github.com/MrNoTaiL/kaggle-Store-Sales-Time-Series-Forecasting/blob/main/img/8.jpg"></img>

 <p align='justify'>The result of oneway f test 92057,93 and p value 0. This result imply each category in family not significantly different based on sales. </p>
  
<img src="https://github.com/MrNoTaiL/kaggle-Store-Sales-Time-Series-Forecasting/blob/main/img/9.jpg"></img>

