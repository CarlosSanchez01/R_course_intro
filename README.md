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

# Setting Git with Rstudio

You need to start a new project
Then you mention, initialize through GIT. You enter the link https://github.com/CarlosSanchez01/R_course_intro.git and the folder where you 
want to keep the local copy of the repository.

It should initialize with this file and all the files that we will set up.

I already populated one folder with each of your names. Inside this folder you will be able to set your own folder structure in a way we can see each others scripts and workflow. Also ask for comments or help.

## Being able to update the repo with your data

To be able to update the repository from Rstudio and thus, being able to share the code with me and between yourself, we need to tell Rstudio who you are and your email address.

For this you have to install git for windows[https://git-scm.com/download/win]

Then in Rstudio you will find a "Terminal"

In the terminal you need to state:

```
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```
Then you can go to "tools" > version control > commit 

Inside the commit menu you will see which changes you have made in relation to the files in the respository, you will need to "stage" them and then commit

Once you commit then you need to push it to the respository branch

# Rmarkdown

R markdown is a special type of formatting in which we can embeed code.
This text here is a markdown. Rmarkdown allows to embeed R code and outputs 
for better tracking of the changes and better reports of the used data
and plots in the analysis.

# Github pages

The idea is to bring rmarkdown files for each analyses into a github pages for this repository (carlossanchez01.github.com/R_course_intro). Following this guide https://bookdown.org/yihui/rmarkdown/rmarkdown-site.html.

For this, all rmarkdown files should include the following:

```{r setup, include=FALSE}
# knit: (function(input_file, encoding) {
#   out_dir <- '../docs/';
#   rmarkdown::render(input_file,
#                     encoding=encoding,
#                     output_file=file.path(dirname(input_file), 
#                                           out_dir, 'index.html'))})
```

Then we just need to compile the rmarkdowns in docs/ with the following:

```
setwd(dir= "docs/")
rmarkdown::render_site()
```
