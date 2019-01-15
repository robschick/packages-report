01\_write-installed-packages.R
================
rob
Tue Jan 15 17:01:23 2019

``` r
## deja vu from earlier!

## create a data frame of your installed packages
## hint: installed.packages() is the function you need
library(tidyverse)
```

    ## -- Attaching packages ----------------------------------------------------- tidyverse 1.2.1 --

    ## v ggplot2 3.1.0     v purrr   0.2.5
    ## v tibble  1.4.2     v dplyr   0.7.8
    ## v tidyr   0.8.2     v stringr 1.3.1
    ## v readr   1.3.1     v forcats 0.3.0

    ## -- Conflicts -------------------------------------------------------- tidyverse_conflicts() --
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

``` r
library(here)
```

    ## here() starts at E:/rob/Documents/research/projects/happygitwithr/packages-report

``` r
ipt <- installed.packages() %>%
  as_tibble()
ipt
```

    ## # A tibble: 292 x 16
    ##    Package LibPath Version Priority Depends Imports LinkingTo Suggests
    ##    <chr>   <chr>   <chr>   <chr>    <chr>   <chr>   <chr>     <chr>   
    ##  1 abind   C:/Use~ 1.4-5   <NA>     R (>= ~ method~ <NA>      <NA>    
    ##  2 acepack C:/Use~ 1.4.1   <NA>     <NA>    <NA>    <NA>      testthat
    ##  3 akima   C:/Use~ 0.6-2   <NA>     R (>= ~ sp      <NA>      <NA>    
    ##  4 assert~ C:/Use~ 0.2.0   <NA>     <NA>    tools   <NA>      testthat
    ##  5 babyna~ C:/Use~ 0.3.0   <NA>     R (>= ~ tibble  <NA>      <NA>    
    ##  6 backpo~ C:/Use~ 1.1.2   <NA>     R (>= ~ utils   <NA>      <NA>    
    ##  7 base64~ C:/Use~ 0.1-3   <NA>     R (>= ~ <NA>    <NA>      <NA>    
    ##  8 BB      C:/Use~ 2014.1~ <NA>     R (>= ~ stats,~ <NA>      setRNG,~
    ##  9 BH      C:/Use~ 1.66.0~ <NA>     <NA>    <NA>    <NA>      <NA>    
    ## 10 bindr   C:/Use~ 0.1.1   <NA>     <NA>    <NA>    <NA>      testthat
    ## # ... with 282 more rows, and 8 more variables: Enhances <chr>,
    ## #   License <chr>, License_is_FOSS <chr>, License_restricts_use <chr>,
    ## #   OS_type <chr>, MD5sum <chr>, NeedsCompilation <chr>, Built <chr>

``` r
## optional: select just some of the variables, such as
##   * Package
##   * LibPath
##   * Version
##   * Priority
##   * Built

## write this data frame to data/installed-packages.csv
## hint: readr::write_csv() or write.table()
## idea: try using here::here() to create the file path
readr::write_csv(ipt, here('data', 'installed-packages.csv'))

## YES overwrite the file that is there now (or delete it first)
## that's a old result from me (Jenny)
## it an example of what yours should look like and where it should go
```
