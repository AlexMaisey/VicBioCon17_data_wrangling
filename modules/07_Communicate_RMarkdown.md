# Rmarkdown Documents
Elise Gould  
25/01/2017  




# What are RMarkdown documents?

An RMarkdown file is a record of your research. It can act as a lab-notebook where you can perform exploratory data analyses or other experiments before proceeding with your main analysis (e.g. deciding what covariates to include in a model). It mixes code and text so that others can fully reproduce your analysis and that readers can understand your analysis story and code.

*Challenge 12 (1-minute)*

- Create an RMarkdown document inside the `./doc/` folder called `bat_data_exploration.Rmd`

> File > New File > Enter title and author, select OK.

- Save, commit, and push to github
- We will examine this document and step through each of the different components together

## Basic components of an RMarkdown document

*YAML header*

At the top of every RMarkdown file is a YAML header or template, which gives instructions to R as to how your RMarkdown document should be turned into a report.

When you create a new RMarkdown document, this will be automatically filled out for you. You can customise this to your liking.

There are many different formats, including journal articles for those submitted to elsevier journals - see the [rmarkdown rstudio website](rmarkdown.rstudio.com/) for list of formats.

*Code chunks versus text*

- Code chunks are demarcated by three an upper line of code: ` ```{r} `
- and a lower line of code: ` ``` `
- Any R code is written between those upper and lower lines.
- You can hit the 'insert-chunk' button inside the RMarkdown editor to automatically insert a new chunk.

Any text you use to annotate your code, occurring outside of these chunks, is displayed.

Text can be written with MarkDown syntax, to provide formatting options such as italics, bold, different heading styles, links and so on.

*Chunk options*

Options telling knitr how to process and display each each chunk of code are written inside the upper fence of the chunk, inside the curly braces.

Inside the template example, the option `echo=FALSE` is provided. This tells knitr to prevent printing of the R code that generated the plot.

# Reproducible Research: turning your RMarkdown document into a report

An RMarkdown document is converted into a report by a series of intermediate steps, using the knitr engine.

When you knit the document, it is first converted to markdown `MD` and then to `HTML`. Or in the case of PDF output, is first converted to `LaTeX`.

Your code is evaluated by R, and the results displayed at the same time as your text is rendered to display.

## Filepaths and working directory madness

When you knit RMarkdown documents, your R code is evaluated inside a separate environment. Any objects available in your workspace or global environment that you created interactively are not accessible to it. You must:
- load and create all necessary objects and functions within the document itself.
- source required functions you have written
- Load all required libraries

Working directories also behave differently. when you work inside the console or source code within a script, your root directory is taken to be the directory where the rproject file is located.

However, when you knit an RMarkdown document, it is taken to be the location of the RMarkdown document, unless you specify otherwise.

This means that when importing data into an Rmarkdown document, you must load data *relative to the position of the RMarkdown file*, otherwise the knitting will fail.

*Challenge 13: Modify your Rmarkdown file and load data (2-minute)*

1. Edit the heading to change the title of the document to whatever you like
2. Delete everything below the YAML header / template
3. Add a new R chunk a few lines below the template
4. give it a name `load-data`.
5. import the processed bat data inside `./output/` into the RMarkdown file, assigning it to an object name of your choice.
tip: Hit the tab button to bring up a list of directories as you are writing the character string containing the filepath. Start by typing: `"./` and then hit tab.
6. Print the object, and knit the document to see what happens
7. Save, commit, push

*Challenge 14: 10-minute challenge*

- In your first chunk, source the function we created called `se.R` within the `./R/` directory. This loads the function into the Rmarkdown environment.
- Create another new chunk called `bat-summary-vars`
-  Subset the bat variables (subset for the first three fixed variable columns, and for the variable `BatSpecies`)
-  For each combination of Habitat and Season, compute using summarise:

1. mean_richness
2. se_richess using the function you sourced `se`
3. Assign the output to the object `richness_by_season`
4. Knit, commit, push

At each combination of Habitat and Season, take the mean 



Next we will create a plot!

**When to use Rmarkdown docs or R scripts?**

Genearlly anything that results in an any output should be written in a script.

Rmarkdown documents are great for sucking up the outputs of your scripts, and then presenting them with text, but should never result in any outputs, other than those automatically created during knitting.


# References and other Resources:

[http://rmarkdown.rstudio.com](http://rmarkdown.rstudio.com)
RMarkdown cheatsheet: `Help > Cheatsheets > RMarkdown Cheatsheet`
RMarkdown Reference Guide: `Help > Cheatsheets > RMarkdown Reference Guide`
