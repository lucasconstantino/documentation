---
title: geom_quantile in ggplot2 | Examples | Plotly
name: geom_quantile
permalink: ggplot2/geom_quantile/
description: How to use geom_quantile with Plotly.
layout: base
thumbnail: thumbnail/geom_quantile.jpg
language: ggplot2
page_type: example_index
has_thumbnail: true
display_as: statistical
order: 4
output:
  html_document:
    keep_md: true
---



### New to Plotly?

Plotly's R library is free and open source!<br>
[Get started](https://plot.ly/r/getting-started/) by downloading the client and [reading the primer](https://plot.ly/r/getting-started/).<br>
You can set up Plotly to work in [online](https://plot.ly/r/getting-started/#hosting-graphs-in-your-online-plotly-account) or [offline](https://plot.ly/r/offline/) mode.<br>
We also have a quick-reference [cheatsheet](https://images.plot.ly/plotly-documentation/images/r_cheat_sheet.pdf) (new!) to help you get started!

### Version Check

Version 4 of Plotly's R package is now [available](https://plot.ly/r/getting-started/#installation)!<br>
Check out [this post](http://moderndata.plot.ly/upgrading-to-plotly-4-0-and-above/) for more information on breaking changes and new features available in this version.


```r
library(plotly)
packageVersion('plotly')
```

```
## [1] '4.9.0'
```

### Basic Example


```r
library(plotly)
library(MASS)

df <- MASS::birthwt

df <- with(df, {
  race <- factor(race, labels = c("white", "black", "other"))
  ptd <- factor(ptl > 0)
  ftv <- factor(ftv)
  levels(ftv)[-(1:2)] <- "2+"
  data.frame(low = factor(low), age, lwt, race, smoke = (smoke > 0),
             ptd, ht = (ht > 0), ui = (ui > 0), ftv, bwt)
})

p <- ggplot(df, aes(lwt, bwt, colour = smoke)) +
  geom_point(size = 1) +
  geom_quantile(quantiles = 0.5, size = 0.5, alpha = 0.5)

p <- ggplotly(p)

# Create a shareable link to your chart
# Set up API credentials: https://plot.ly/r/getting-started
chart_link = api_create(p, filename="geom_quantile/basic")
chart_link
```

<iframe src="https://plot.ly/~RPlotBot/4422.embed" width="800" height="600" id="igraph" scrolling="no" seamless="seamless" frameBorder="0"> </iframe>
Reference: [ggplot2 docs](http://ggplot2.tidyverse.org/reference/geom_quantile.html#examples)

### Reference

See [https://plot.ly/r/reference](https://plot.ly/r/reference) for more information and options!
