# Kaggle dataset - Store Sales - Time Series Forecasting
<p align='justify'>In this dataset containt a thousands of product families sold at Favorita stores located in Ecuador. So, i have to challange myself to analyze and get insight from dataset store sales. There are several explanations:
<h3> train.csv</h3>
<ul>
  <li align='justify'>The training data, comprising time series of features store_nbr, family, and onpromotion as well as the target sales.</li>
  <li align='justify'>store_nbr identifies the store at which the products are sold.</li>
  <li align='justify'>sales gives the total sales for a product family at a particular store at a given date. Fractional values are possible since products can be sold in fractional units (1.5 kg of cheese, for instance, as opposed to 1 bag of chips).</li>
  <li align='justify'>onpromotion gives the total number of items in a product family that were being promoted at a store at a given date.</li>
</ul>
<h3>test.csv</h3>
<ul>
  <li align='justify'>The test data, having the same features as the training data. You will predict the target sales for the dates in this file.</li>
  <li align='justify'>The dates in the test data are for the 15 days after the last date in the training data.</li>
</ul>
<h3>sample_submission.csv</h3>
<ul>
  <li align='justify'>A sample submission file in the correct format.</li>
</ul>
<h3>stores.csv</h3>
<ul>
  <li align='justify'>Store metadata, including city, state, type, and cluster.</li>
  <li align='justify'>cluster is a grouping of similar stores.</li>
</ul>
