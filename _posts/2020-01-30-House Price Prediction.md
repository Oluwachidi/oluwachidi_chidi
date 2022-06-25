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
<img src="https://i.ibb.co/Ybdp8LC/load-data.jpg" alt="load-data" border="0">

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
<img src="https://i.ibb.co/SymwNGL/preproc-baseline.jpg" alt="preproc-baseline" border="0">



<h2 class="section-heading">Models</h2>
<p>First I pipelined a baseline model to make a baseline prediction. Created a performance metric (rmsle) using make_scorer then perform a 5-fold cross validation to achive a 17% baseline score which is stored for future comparison.</p>
<img src="https://i.ibb.co/G71V2zf/baseline-score.jpg" alt="baseline-score" border="0">

<p>Now is time to optimize the model but first, the features have to preprocessed further by:</p>
<ul>
  <li>Ordinal Encoding of categorical features with a hidden notion of order in their values (e.g. "bad", "average", good")</li>
  <li>Target engineering by transforming our target to directly predict its log (i.e y_log). Normally distributed variables should be easier to predict with linear models. <img src="https://i.ibb.co/QY3yktJ/target-engineering.jpg" alt="target-engineering" border="0"></li>
  <li>Statistical Feature Selection to remove useless features (avoid overfitting and reduce train time). This is done by using Spearman's rank correlation combined with a heatmap to know whether some ordinally encoded and numeric features are almost entirely "ordered" similarily than others or almost entirely explain others respectively. Then, create a "filter" in the pipeline that removes any correlation below a certain threshold. <img src="https://i.ibb.co/RB8mmJt/feature-selection.jpg" alt="feature-selection" border="0"></li>
</ul>
<p>A final preprocessed pipeline is compiled</p>
<img src="https://i.ibb.co/PwR0qqr/final-preproc-pipeline.jpg" alt="final-preproc-pipeline" border="0">

<p>Iterate accross different models(e.g linear models, KNN, SVM, Trees, Random Forest, XGBOOST etc), to discover the model with the best validation score. In this case, XGBOOST</p>
<img src="https://i.ibb.co/j3sY1MT/Best-validation-model.jpg" alt="Best-validation-model" border="0">

<p>The model is further optimised using Neural Networks</p>
<img src="https://i.ibb.co/4gxgh3g/Neural-Networks.jpg" alt="Neural-Networks" border="0">

