[![license](https://img.shields.io/github/license/DAVFoundation/captain-n3m0.svg?style=flat-square)](https://github.com/DAVFoundation/captain-n3m0/blob/master/LICENSE)
![contributors](https://img.shields.io/github/contributors/shubha8196/data-512-homework_1.svg) ![codesize](https://img.shields.io/github/languages/code-size/shubha8196/data-512-homework_1.svg)

# data-512-homework_2: HW2- Considering Bias in Data
This repository contains all the required materials for Homework 2 of DATA 512- Human Centered Data Science course (Autumn 2022) offered by the MSDS program at the University of Washington.

# Goal
The goal of this assignment is to explore the concept of bias in data using Wikipedia articles. This assignment will consider articles on political figures from different countries. For this assignment, the a dataset of Wikipedia articles is combined with a dataset of country populations, and a machine learning service called ORES is used to estimate the quality of each article.

# Data Utilized

1. [Politicians by nationality](https://en.wikipedia.org/wiki/Category:Politicians_by_nationality)
2. [World Population](https://www.prb.org/international/indicator/population/table)
3. [ORES Rest API](https://www.mediawiki.org/wiki/ORES)
4. [Wikimedia Foundation REST API terms of use](https://www.mediawiki.org/wiki/Wikimedia_REST_API#Terms_and_conditions)

The input data for this project is extracted from the below wikipedia (politicians wikipedia pages) and prb (population) web pages. Additionally, two more endpoints are used for page information and ORES scores. The datasource endpoints are licensed under the [CC-BY-SA 3.0]( CC-BY-SA 3.0 and GFDL licenses) and [GFDL licenses](CC-BY-SA 3.0 and GFDL licenses). ORES is a machine learning tool that can provide estimates of Wikipedia article quality. The ORES API endpoint provides the article quality estimates from best to worst:

FA - Featured article
GA - Good article
B - B-class article
C - C-class article
Start - Start-class article
Stub - Stub-class article

# Repository Distribution

```
data-512-homework_2/
  |- README.md
  |- LICENSE
  |- HCDS-HW2-Shubha.ipynb
  |- data/
    |- politicians_by_country_SEPT.2022.csv
    |- population_by_country_2022.csv
  |- logs/
    |- articles_missing_score.txt
    |- no_page_info_articles.txt
  |- output
    |- wp_countries-no_match.txt
    |- wp_politicians_by_country.csv
```

# Jupyter Notebook
HCDS-HW2-Shubha.ipynb : Contains the code used for the analysis

# Input files (data folder)
politicians_by_country_SEPT.2022.csv : The Wikipedia Category Politicians by nationality was crawled to generate a list of Wikipedia article pages about politicians from a wide range of countries.
population_by_country_2022.csv : This dataset is drawn from the world population data sheet published by the Population Reference Bureau.

# Output files (output folder)
wp_countries-no_match.txt : all countries for which there are no matches and output a list of those countries, with each country on a separate line
wp_politicians_by_country.csv : Consolidating the remaining data as instructed into a single CSV file

# Intermediate files (log folder)

no_page_info_articles.txt: This log maintains the list of article titles for whom the page info was not available.
articles_missing_score : The log maintains the articles for which ORES scores was not retreivable


# Issues/ Special considerations

1. The input data file for politicians contains few duplicates. All absolute duplicates are removed from the data, however for per-capita estimates, duplicates at the article name level are taken into consideration.
2. Countries are mapped to the areas that are nearest to them and lower on the hierarchy of regions after regions with cumulative population numbers are excluded.
3. There are not many nations with a population of 0. This may be because the figure is rounded to the nearest decimal place and expressed in millions. These nations are excluded from Step 4's calculation of the article-per-capita because their denominator 3 values of 0 result in infinity.




## Author
- [Shubha Changappa Palachanda](https://github.com/shubha8196)
