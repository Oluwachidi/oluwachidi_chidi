---
layout: post
title: "House Price Prediction"
background: '/img/posts/house price image.jpeg'
---

<p>Github link <a href="https://github.com/Oluwachidi/Houses-Price-Prediction">house price prediction</a>.</p>





<h2 class="section-heading">Introduction</h2>
<p>With 79 explanatory variables describing (almost) every aspect of residential homes, this project is aimed to predicting the final price of each home using Advanced regression techniques (like random forest and gradient boosting) and Creeative feature engineering</p>
<p>The dataset was compiled by Dean De Cock </p>



<h2 class="section-heading">Dataset</h2>
<p>The dataset contains about 1460 rows(homes) and 80 columns(feautures) including the target; SalePrice</p>
<img src="https://load data.jpg" width="800" alt="load data" border="0">

<p>This 80 columns are a combination of Categorical and numeric feature with lots of missing values(NaN). Features that bring too little esplanation to the model is removed. Then a basic preprocessing pipeline is designed as follows:</p>

<p>For categorical features</p>
<ul>
  <li>Simple-Impute with most frequent values</li>
  <li>One-Hot-Encode features that have less than 7 unique values to start with</li>
  <li>Drop all others features</li>
</ul>

<p>As for numerical features</p>
<ul>
  <li>Simple-Impute with strategy 'mean'</li>
  <li>Min-Max Scale</li>
</ul>
<img src="https://preproc_baseline.jpg" width="800" alt="preproc_baseline" border="0">



<h2 class="section-heading">Models</h2>
<p>First let's pipeline a baseline model for predicting a baseline score</p>





<h2 class="section-heading">App and Model Deployment</h2>
<ul>
  <li>Build a predictive API with FastAPI</li>
</ul>

<p>app_link <a href="https://wasteassist.herokuapp.com/">waste-assist-app</a>.</p>

  
  
  

<h2 class="section-heading">Performance</h2>
<p>The software can now... </p>

