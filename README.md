# R introduction for data visualization

This is a repository with Scripts for data analyses, visualization and statistics
using R.

I recommend installing Rstudio and then we can have a look at how to sync with 
the repository. If not you can just use it as reference.

## All I know starts with some data

Thats why we need to get our data in the right format for R.
It looks something like this:

| Time    | Reactor | pH | Temp | TOC | TN | TP |
|---------|---------|----|------|-----|----|----|
| Monday  | 1       | 5  | 20   | 24  | 2  | 65 |
| Tuesday | 1       | 8  | 20   | 10  | 2  | 21 |
| Monday  | 2       | 5  | 20   | 10  | 2  | 40 |
| Tuesday | 2       | 7  | 20   | 6   | 1  | 30 |

So, we can order it in excel for example or we could import it into R and order
it inside R. However, you probably will be more comfortable with excel.

Important is to save as .csv or .txt files as this allows R to import it.

## Import .csv to R

First we need to know where we are with Rstudio

```R
getwd()
```
It is convenient to have a folder structure (Project1) to analyse all the data
The folder structure will have a folder inside called Scripts, another folder 
called data, another called plots.

```R
getwd()
project_path<- "c:/.../Project1"
setwd(project_path)
getwd()
```
Now we supposedly have our R studio session set at the same folder that our 
project.

Now we also have the table so we need to import it into our R session.

```R
mydata <- read.table("./mydata.csv", header=TRUE,
        sep=",")
View(mydata)
```
From now on... we will keep going in project specific rmarkdown scripts.
rmarkdown helps keep track of the changes and produce reports with all the data
and the plots from our analyses.

