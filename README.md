[![license](https://img.shields.io/github/license/DAVFoundation/captain-n3m0.svg?style=flat-square)](https://github.com/DAVFoundation/captain-n3m0/blob/master/LICENSE)
![contributors](https://img.shields.io/github/contributors/shubha8196/data-512-homework_1.svg) ![codesize](https://img.shields.io/github/languages/code-size/shubha8196/data-512-homework_1.svg)

# Considering Bias in Data
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


# Research Implication

Reflectiion:
Understanding the biases in the source data can help you spot any biases in the model and prevent incorrect interpretation of the results. We are aware that when dealing with material obtained from the internet, there is always some type of bias. Several queries regarding the articles per capita were raised during the post-hoc analysis, including whether it was a trustworthy measure of coverage and whether it was related to ORES scores. In the course of the post-hoc study, few biases in the data are visible. The per capita values of the articles seem to be very dependent on the population of the nation/region. For instance, the majority of the nations/regions with the highest coverage also have the lowest populations, and vice versa. Non-native English speakers had less high-quality articles than native speakers, which suggests a linguistic and cultural prejudice.All of these observations, together with a few other data discrepancies, led me to overall doubt the accuracy of the per capita computation carried out


What biases did you expect to find in the data (before you started working with it), and why?

I had initially anticipated a strong bias in favor of wealthy nations in high-quality papers, but this was not the case. This exercise involves selection bias because many nations, including important industrialized nations like the United States, Canada, etc., have missing data. I also anticipated that Southern Asia would have a lower article per capita value because to its vast population. The idea that articles in their native languages would be more numerous led me to believe that the quantity of articles in Asian and African countries would be lower per capita.

What might your results suggest about (English) Wikipedia as a data source?

Multiple runs of data show dynamic changes, which could cause analysis to be inconsistent. The ORES scores might not be reliable because they were generated by an AI model that might be prejudiced on the basis of ideology, race, gender, or culture. I learned from the ORES Wiki that the ORES model appears to be biased toward the article's structure rather than the content when assessing the quality of the article itself.


Can you think of a realistic data science research situation where using these data (to train a model, perform hypothesis-driven research, or make business decisions) might create biased or misleading results, due to the inherent gaps and limitations of the data?

During the second week of class in DATA-512, one of the texts made available for a reading assignment showed us how gender, demographic, and cultural biases could lead to the models producing predictions that might not be correct. The article on Islamophobia is another example of how GPT-3 is against the particular religion. These limitations are caused by the data that is sent to these AI systems, which follow the principle of "Garbage In, Garbage Out."


How might a researcher supplement or transform this dataset to potentially correct for the limitations/biases you observed?

The dataset is missing information from several areas and nations' Wikipedia articles. Few nations have population figures of 0. The articles-per-capita may not accurately reflect the genuine levels because to the two aforementioned factors. The researcher should therefore take the politicians' Wikipedia entries from those of the absent nations. To acquire a real picture of the high-quality article per capita, it is also necessary to obtain the ORES scores for the articles published in these nations.

## Author
- [Shubha Changappa Palachanda](https://github.com/shubha8196)
