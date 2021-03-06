# README: welcome to the workshop
Elise Gould  
03/02/2017  

# About the structure of this workshop

We will be drawing on the core packages in Hadley Wickhams "tidyverse".
You can install the required packages onto your computer using the following: 


```r
install.packages("tidyverse")
```

```r
library(tidyverse) # load libraries
```

```
## Loading tidyverse: ggplot2
## Loading tidyverse: tibble
## Loading tidyverse: tidyr
## Loading tidyverse: readr
## Loading tidyverse: purrr
## Loading tidyverse: dplyr
```

```
## Conflicts with tidy packages ----------------------------------------------
```

```
## filter(): dplyr, stats
## lag():    dplyr, stats
```

**Challenge** Open RStudio and type the above into your console.

### If you need help

We will have a post-it note system in use: If you are having difficulty please stick a red post-it note on your computer so we can come over and get you up to speed if you fall behind or need help completing a challenge task.

### Mixed bag of skills

Initially, the content favours less experienced R-users. We ask that more advanced or experienced R users focus on the broader workflows and data-management skills as well as the rationale behind the example under consideration, rather than on the function or code at hand. You will certainly still gain useful information from the earlier modules.

As we progress the code will become a bit more complex, favouring more experienced R-users, who will probably pick up the use and application of these functions more quickly and complete the challenges with more ease. To the R-users with little or no experience: do not fret, you can return to the workshop materials hosted here on GitHub at a later stage to re-read the content in more detail and to work through the examples and challenges at your own pace.

### A note on the code syntax adopted throughout workshop materials:

In case you want to install individual packages from the tidyverse, rather than the whole suite of packages, I have specified the package that each function comes from using the `::` symbol. For example, if I wish to use the `filter` function from `dplyr`, I simply write: `dplyr::filter()`. The double-colon between the package name and the function ensures that the function is called from the specified package. This has two purposes, (1) in the context of this workshop, a pedagogical one, being that you can learn which functions ship with which package (and for your own project install only the relevent package), and (2), a practical one. For example, the filter function also belongs to the `stats` package. By calling a function direclty and explicitly from the intended package (in this case dplyr), you can ensure that you are calling the intended function. R will use the same-named function from the package that was loaded first, which might not be the one you intend to use.

We will run through the materials in the "./walkthrough" folder. Each "chapter" of the course is written in an 'Rmarkdown' document. Throughout and at the end of each document there are one or more challenges to complete. Each challenge will ask you to implement some of the functions using a real ecological data set. The aim is to work through a series of analysis questions that build on one another to iteratively generate knowledge and understanding about this dataset. We hope to show you how to do this by simultaneously using best-practice workflows for robust, portable and reproducible data analysis. At the end of the workshop you will have a toolbox and a generalisable roadmap for navigating data analysis for your own datasets.


# About the format ofthe materials

Lots more information included in here than we will cover on the day, with links to additional resources or extra tips on best-practice RStudio use / data management. The point is that you can go back over these materials into the future.

## About the dataset we will be working with:

We will be working with the two datasets:
1. Iris, shipped with R
2. data from the paper: Straka, T. M., Lentini, P. E., Lumsden, L. F., Wintle, B. A., & Ree, R. (2016). Urban bat communities are affected by wetland size, quality, and pollution levels. Ecology and Evolution, 6(14), 4761-4774.

Pia can tell us a little bit about how this dataset was colected.

