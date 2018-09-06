---
title: "538 Collab"
author: "Thomas Mock"
date: "9/6/2018"
output: html_document
---

# New datasets

Core fivethirtyeight [datasets](https://github.com/fivethirtyeight/data)

[Congress Resignations](https://github.com/fivethirtyeight/data/tree/master/congress-resignations)
[Lebron](https://github.com/fivethirtyeight/data/tree/master/lebron)
[masculinity-survey](https://github.com/fivethirtyeight/data/tree/master/masculinity-survey)
[next bechdel tests](https://github.com/fivethirtyeight/data/tree/master/next-bechdel)
[poll quiz guns](https://github.com/fivethirtyeight/data/tree/master/poll-quiz-guns)
[primary candidates 2018](https://github.com/fivethirtyeight/data/tree/master/primary-candidates-2018)
[rare pepes](https://github.com/fivethirtyeight/data/tree/master/rare-pepeshttps://github.com/fivethirtyeight/data/tree/master/rare-pepes)
[reluctant trump](https://github.com/fivethirtyeight/data/tree/master/reluctant-trump)
[special elections(https://github.com/fivethirtyeight/data/tree/master/special-elections)

# Modified  datasets
[pollster ratings](https://github.com/fivethirtyeight/data/tree/master/pollster-ratings)
[Reluctant Trump](https://github.com/fivethirtyeight/data/tree/master/reluctant-trump)
[Thanksgiving](https://github.com/fivethirtyeight/data/tree/master/thanksgiving-2015)

# Goals for Users

We think the following 4-tier model for assigning projects might work:

## Tier 1

1. **Beginner-level**: tidying/taming of data. **Deliverables**: A `.R` script that takes the raw .csv and "tames" it, as described in [Section 3](http://rpubs.com/rudeboybert/fivethirtyeight_tamedata) of `538_tamedata`. [Ex](https://github.com/rudeboybert/fivethirtyeight/blob/master/data-raw/process_data_sets_albert.R)  

### What is `tame data`? 

`Tame data` can be seen in [Section 3](http://rpubs.com/rudeboybert/fivethirtyeight_tamedata) of Albert Kim's fivethirtyeight - Tame Data document.

#### Naming conventions for data frame and variable names:

**1. Whenever possible, all names should be no more than 20 characters long.**  
        1. Exceptions to this rule exist when shortening the names to less than 20 characters would lead to a loss of information.  
        2. Use only lower case characters and replace all spaces with underscores. This format is known as `snake_case` and is an alternative to `camelCase`, where successive words are delineated with upper case characters.  
        3. In the case of variable (column) names within a data frame, use underscores instead of spaces.  
  
**2. Variables identifying observational units:**
        1. Any variables uniquely identifying each observational unit should be in the left-hand columns.

**3. Dates:**
        1. If only a year variable exists, then it should be represented as a numerical variable.
        2. If there are year and month variables, then convert them to Date objects as year-month-01. In other words, associate all observations from the same month to have a day of 01 so that a correct Date object can be assigned.
        3. If there are year, month, and day variables, then convert them to Date objects as year-month-day.

**4. Ordered Factors, Factors, Characters, and Logicals:**
        1. Ordinal categorical variables are represented as ordered factors.
        2. Categorical variables with a fixed and known set of levels are represented as regular factors.
        3. Categorical variables whose possible levels are either unknown or of a very large number are represented as characters.
        4. Any “yes/no” character encoding of binary variables is converted to TRUE/FALSE logical variables.

**5. Tidy data format:**
        1. Whenever possible, save all data frames in “tidy” data format as defined by Wickham (2014):
                - Each variable forms a column.
                - Each observation forms a row.
                - Each type of observational unit forms a table.
        2. If converting the raw data to “tidy” data format alters the dataset too much, then make the code to convert to tidy format easily accessible.

## Tier 2

2. *Intermediate-level*: Also including the roxygen code that generates a correctly formatted help file, necessitating a little reading of Hadley's R Packages book. The help files are rather standardized across datasets.  *Deliverables*: A `.R` file with the roxygen code. [Ex](https://github.com/rudeboybert/fivethirtyeight/blob/master/R/data_albert.R)  

## Tier 3

3. *Advanced-level*: CRAN checking the package locally (as described in R Packages) and then making a pull request. *Deliverables*: A PR with just the above two files, with Travis CI build checks passing. [Ex](https://github.com/rudeboybert/fivethirtyeight/pull/27)  

## Tier 4

4. *Meta-level*: Build some alpha-version of a "quickstart" manual to the above. *Deliverables*: I ultimately would like to use "adding new 538 datasets to the R package via pull request" as a starter project into the world of open-source/R development for my ugrad students at Smith College. What I like is that the end deliverable is very clear (Does the dataset load in the console? Is the help file correctly formatted?), but there are many ways about achieving these so things are still partially open-ended. Making this an exhaustive guide is probably overkill, but some sort of "quickstart" guide, like when you get a new phone/computer, would be wonderful!  
