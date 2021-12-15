<p align="center">
    <h1 align="center">Analysis of Song Lyrics</h1>
</p>

<div id="top"></div>

<details>
  <summary>Table of Contents</summary>
  <ol>
<li><a href="#problem-statement">Problem Statement</a></li>
      <li><a href="#executive-summary">Executive Summary</a></li>
    <li><a href="#Data">Data</a></li>
      <li><a href="#getting-started">Getting Started</a></li>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>


## Problem Statement

Can the lyrics of our most popular songs be used to determine which decade they were released?

<hr style="border:0.2px light gray"> </hr>

## Executive Summary

This project involves analyzing the lyrics of Billboard Top 100 songs from 1960 to 2009 in order to predict which decade the song was released. The song and artist names were scraped from billboardtop100of.com. Once scraped, this data was used in conjunction with the Lyric Genius API in order to pull the lyrics for each song. The songs are genre agnostic and based solely on the top 100 most popular songs for each year.

Data cleaning largely involved correcting issues with the lyric pull from Genius. After inspection around 10% of songs had pulled erroneous text (classic novels, screenplays, poems, news articles, etc.) rather than lyics. These songs were identified and removed by capping the word count at 1,100 and removing all duplicate values from the dataset (erroneous lyrics tended to pull in for multiple songs). After removal we were left with 4,396 songs. Feature engineerint included adding a word count, sentiment score, average word length and an identifier of whether the song contained dirty or suggestive lyrics.

After EDA and prior to vectorization the most important features identified were word count and whether the song contained dirty lyrics. Average word count has more than doubled from the 1960s to the 2000s. 
<br>

<img src="./assets/word_count.png" alt="Drawing" style="width: 500px;"/>



There has been a similar rise in dirty / suggestive lyrics over this time period, with the number of suggestive songs rising from ~10% in the 1960s to over 50% in the 2000s.
<br>

<img src="./assets/suggestive.png" alt="Drawing" style="width: 500px;"/>

The model with the highest accuracy was a boosted gradient classifier with a max depth of 3 and 200 estimators. Count vectorization was performed with an ngram range of (1,1) and 5,000 words. The model performed with 43.2% accuracy vs. a baseline model of 21.7%. The most important features were requested ship speed, customer location, order hour of day, whether order was submitted before noon, order week and order profit ratio.



### Process

### Models Used

* Boosted Gradient Classifier
* Logistic Regression
* Multinomial Naive Bayes

### Findings
Top performing features:

<img src="./assets/coefs.png" alt="Drawing" style="width: 700px;"/>

### Model Performance

The final model (Extra Tree Classifier) achieved a 92.55% score when predicting whether a product would be shipped on time. This is compared to a baseline model of 57.27%.

<hr style="border:0.2px light gray"> </hr>

## Recommendations

* Don’t offer Same Day delivery after midday
* Reallocate freed resources from Same Day to First Class
* Sites with lower ship volume struggle
* Prioritize at-risk shipments

<hr style="border:0.2px light gray"> </hr>

### Data

The data was obtained from kaggle and contains 180,000 transactions with 60 different columns about Product, Customer and Order information:

* [Kaggle DataCo Smart Supply Chain for Big Data](https://www.kaggle.com/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis)

A link to the data dictionary can be found [here](https://www.kaggle.com/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis?select=DescriptionDataCoSupplyChain.csv).

<hr style="border:0.2px light gray"> </hr>

### Getting Started

No installations are needed to use this project. Please refer to the [requirements.txt](https:) file to see python packages used in this project
## License

Distributed under the MIT License. See `LICENSE.txt` for more information.





<!-- CONTACT -->
## Contributors
[Cynthia Owens](https://www.linkedin.com/in/cynthiakowens/)<br>
[Chad Richter](https://www.linkedin.com/in/chad-richter/)<br>
[Sean McNamara](https://www.linkedin.com/in/sean123mcnamara/)<br>

<p align="right">(<a href="#top">back to top</a>)</p>
