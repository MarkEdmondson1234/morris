## Morris

This is an experimental R package that provides the [Morris](http://morrisjs.github.io/morris.js/) visualization library as a html widget for R. The implementation in this package borrows heavily from some utility functions in [rCharts](http://github.com/ramnathv/rCharts), but uses the `htmlwidgets` package to deliver the widget.

### Installation

You can install it from github

```r
library(devtools)
install_github('rstudio/htmltools')
install_github('ramnathv/htmlwidgets')
install_github('ramnathv/morris')
```

### Usage

Here are some simple examples that you can play with.

__Line Chart__

```r
dat = data.frame(
  year = as.character(2008:2012),
  value = c(20, 10, 5, 5, 20)
)
morris(value ~ year, data = dat, type = 'Line')
```

![morris1](http://i.imgur.com/Vo5DLOq.png)

__Bar Chart__

```r
haireye = as.data.frame(HairEyeColor)
dat <- subset(haireye, Sex == "Female" & Eye == "Blue")
morris(Freq ~ Hair, data = dat, type = 'Bar', labels = list("Count"))
```

![morris2](http://i.imgur.com/1l3LnrE.png)

__MultiBar Chart__


```r
haireye = as.data.frame(HairEyeColor)
dat = subset(haireye, Sex == "Female")

morris(Freq ~ Eye, 
  group = "Hair", 
  data = dat, 
  type = "Bar", 
  labels = levels(dat$Hair),
  barColors = c('black', 'brown', 'red', '#FAF0BE')  
)
```

![morris3](http://i.imgur.com/aBgtzbU.png)

