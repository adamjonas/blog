---
layout: post
title: "Preparing Data for Machine Learning"
date: 2017-03-10 10:02
comments: true
categories: machine-learning
---

## Why machine learning - you can predict the future
  - Explosion of data, more available than ever
  - sheer processing power available at a reasonable price point

## Data Preparation Tools
  - Rstudio -> data prep and execute the machine learning
  - jupyter notebooks -> python in the cloud
  - excel -> stick with the tools you know
  - azure machine learning studio
  - scikit learn (competitor to r studio) for python
  - relational database tools (SQL queries)
  - sed / awk
  - python, r, sql most common languages to clean up data

## Data Cleaning
  - missing values in data or repeating values in data (blanks, null,
  n/a, unknown, 999999)
  - what's your business goal?
    - SPCA - can you help us predict what animals won't get adopted?
    - got enough data to be significant, you can delete rows -> not
    always an option
  - can substitute a specific value (can go with a worst case
  scenario)
  - fill forward and fill backwards based on the last value we read ->
  going to have to write code
  - R is.na()
  - python pandas.fillna(), pandas.isnull()

  - excel tips ->
    - select individual columns, go to special, select blanks (will
    select every blank cell) and you can enter a value

  - repeated values
    - causes a bias in the data
    - duplicate row vs duplicate IDs
    - r duplicated()
    - python dataframe.drop_duplicates
    - SQL DISTINCT or correctlated queries
    - correlated subquery -> if the rows are the same but the IDs are different when you find
      two identitical records and delete the one with the lower ID
      number

## Data Transformation
  - Decomposition
    - the more you know about the data, the better
    - one column represents two or more values (like addresses lumped
    together and finding the city and state)
    - return a 1 or 0 to represented spayed and nuetered
  - Aggregation
    - how many copies of different books to keep in stock?
    - don't want the day it was sold, want total number of books sold
    per wk/mon x date
    - select count(*) from sales group by (books sold per period)

  - Scaling
    - predict how long a patient admitted the flu will need to stay in
    the hospital
    - because the age has a wider varience in age you don't see the
    lower differences like temperatute
      - create ranges -> normalizing, standardizing

## Concolusion
  - Training data versus test data
    - subject matter experts become important as they need to undetr
    - tumors -> which do you want, one with more false positives and one
    with more false negatives

  - slides at `aka.ms/confooml`
  - data science and machine learning essentials
  - cleaning data with python
  - building your first machine learning experiment

