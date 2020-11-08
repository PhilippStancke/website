---
abstract: Este articulo se enfoca en buscar una explicación por el comportamiento de la población estadounidense por Estado en las elecciones del presidente. Nosotros analizamos factores de género que pueden haber influenciado este comportamiento.
authors:
- admin
#- Robert Ford
date: "2019-11-30T00:00:00Z"
doi: ""
featured: true
image:
  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/KHxxCc8XMNE)'
  focal_point: ""
  preview_only: false
# links:
# - name: Custom Link
#   url: http://example.org
projects:
# - internal-project
# publication: In *Source Themes Conference*
# publication_short: #n *STC*
publication_types:
- "4"
publishDate: "2019-11-30T00:00:00Z"
#slides: example
summary: Diese Arbeit wurde im Rahmen des Moduls "Economía Política de Género", an der Universidad de los Andes (Bogotá, Kolumbien) geschrieben.
tags:
- Women's March
- USA
- Donald Trump
- Elections
- 2017
- Politics
title: El ambiente político y los resultados de las elecciones estadounidenses
#url_code: '#'
#url_dataset: '#'
url_pdf: 
#url_poster: '#'
#url_project: ""
#url_slides: ""
#url_source: '#'
#url_video: '#'
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(collapse = TRUE)
```

# R Markdown

This is an R Markdown document. Markdown is a simple formatting syntax for authoring HTML, PDF, and MS Word documents. For more details on using R Markdown see <http://rmarkdown.rstudio.com>.

You can embed an R code chunk like this:

```{r cars}
summary(cars)
fit <- lm(dist ~ speed, data = cars)
fit
```

# Including Plots

You can also embed plots. See Figure \@ref(fig:pie) for example:

```{r pie, fig.cap='A fancy pie chart.', tidy=FALSE}
par(mar = c(0, 1, 0, 1))
pie(
  c(280, 60, 20),
  c('Sky', 'Sunny side of pyramid', 'Shady side of pyramid'),
  col = c('#0292D8', '#F7EA39', '#C4B632'),
  init.angle = -50, border = NA
)
```