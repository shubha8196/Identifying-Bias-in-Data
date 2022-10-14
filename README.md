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

data-512-homework_2/
  |- README.md
  |- LICENSE
  |- DATA 512-HW1-Jupyter Notebook.ipynb
  |- JSON data files/
    |- dino_monthly_mobile_201507-202209.json
    |- dino_monthly_desktop_201507-202209.json
    |- dino_monthly_cumulative_201507-202209.json
  |- Analysis Graphs/
    |- Plot1- article_maxmin_avg_views.jpg
    |- Plot2- article_peak_page_views.jpg
    |- Plot3- article_fewest_months.jpg
  |- Data
    |- dinosaur_genera.cleaned.SEPT.2022.xlsx
