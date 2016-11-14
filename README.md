
<!-- README.md is generated from README.Rmd. Please edit that file -->
rtdda
=====

[![Project Status: WIP - Initial development is in progress, but there has not yet been a stable, usable release suitable for the public.](http://www.repostatus.org/badges/latest/wip.svg)](http://www.repostatus.org/#wip) [![MIT Licensed - Copyright 2016 EcoHealth Alliance](https://img.shields.io/badge/license-MIT-blue.svg)](https://badges.mit-license.org/) [![Travis-CI Build Status](https://travis-ci.org/noamross/rtdda.svg?branch=master)](https://travis-ci.org/noamross/rtdda) [![AppVeyor Build Status](https://ci.appveyor.com/api/projects/status/github/noamross/rtdda?branch=master&svg=true)](https://ci.appveyor.com/project/noamross/rtdda) [![codecov](https://codecov.io/gh/noamross/rtdda/branch/master/graph/badge.svg)](https://codecov.io/gh/noamross/rtdda)

This package wraps the [tdda python module](https://github.com/tdda/tdda), which generates automatic *constraints* on data sets given examples. More info can be found on [the TDDA blog](http://www.tdda.info/introducing-rexpy-automatic-discovery-of-regular-expressions).

This is an extremely alpha package wrapping some pretty beta code, so use with caution! It does not currently work on Windows.

Installation
------------

You can install rtdda from github with:

``` r
# install.packages("devtools")
devtools::install_github("noamross/rtdda")
```

Since rtdda calls python code via the [**SnakeCharmR**](https://github.com/asieira/SnakeCharmR) package, you need Python &gt;= 2.7 and a build environment to install it.

Usage
-----

Currently only one function, `rex_extract()` is implemented, for regular expression generation from a character vector:

``` r
library(rtdda)
rex_extract(c("EH1", "7JQ", "WC1", "4AA", "G2", "3PQ"))
#> [1] "^[A-Za-z0-9]{2,3}$"
rex_extract(c("123-AA-971", "12-DQ-802", "198-AA-045", "1-BA-834"))
#> [1] "^\\d{1,3}\\-[A-Z]{2}\\-\\d{3}$"
```
