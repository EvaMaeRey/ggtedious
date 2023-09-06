
<!-- README.md is generated from README.Rmd. Please edit that file -->

# ggtedious

<!-- badges: start -->

<!-- badges: end -->

Quoting the testthat package:

> ‘Testing your code can be painful and tedious, but it greatly
> increases the quality of your code. testthat tries to make testing as
> fun as possible, so that you get a visceral satisfaction from writing
> tests. Testing should be addictive, so you do it all the time.’

I still feel like it’s essentially not fun, but maybe in good company it
can be better.

Building a simple, straightforward extension provide a fun occasion to
build out testing muscles.

geom\_post and geom\_lollipop might work well. After building those
functions, we can add tests, error messages, etc.

Meeting objectives:

0.  My prestep: Figure out what best practices for ggplot2 extension
    packages are; figure out some experts to ask for help.

At meeting:

1.  Write ggplot2 extension functions geom\_post() geom\_lollipop().
2.  Put them in a package using best practices.
3.  meet like minded stats educators\!

# Part 1. Work on functionality

## Step 0. Do it with base ggplot2 (can become problem statement later)

``` r
prize_wheel <- data.frame(probs = c(.7, .2, .1), payout = c(0, 1, 5))

library(ggplot2)
ggplot(prize_wheel) + 
  aes(x = payout, y = probs) + 
  geom_point() + 
  aes(xend = payout, yend = 0) + 
  geom_segment()
```

![](README_files/figure-gfm/use_base_ggplot2-1.png)<!-- -->

## Step 1. Write compute group function and test

reference:
<https://evamaerey.github.io/mytidytuesday/2022-01-03-easy-geom-recipes/easy_geom_recipes.html>

## Step 2. Pass to ggproto object

## Step 3. Write geom\_\*() functions

## Step 4. Test it out enjoy\! (possibly basis of examples and tests)

## Step 5. Formalize tests, write messages.

``` r
testthat::test_that("multiplication works", {
  testthat::expect_equal(2*2, 4)
})
#> Test passed 🌈
```

# Part 2. Build out package

## 1\. devtools::create

## 2\. Send functions to .R folder and Tests to test\_that folder (or copy and paste).

``` r
library(readme2pkg)
chunk_to_r("geom_lollipop")
chunk_to_tests_testthat("test1")
```

## 3\. devtools::check

## 4\. Install and restart

## Done\!

# Appendix. list of code chunks in this doc.

``` r
knitr::knit_code$get() |> names()
#>  [1] "unnamed-chunk-1"     "use_base_ggplot2"    "compute_group"      
#>  [4] "test_compute_group"  "ggproto"             "geom_post"          
#>  [7] "geom_lollipop"       "unnamed-chunk-2"     "test_multiplication"
#> [10] "unnamed-chunk-3"     "unnamed-chunk-4"
```
