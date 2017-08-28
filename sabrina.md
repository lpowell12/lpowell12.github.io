# sabrina




```r
# Create Plotly Pie Chart for Agency Personnel Spending

# Add packages
#install.packages("plotly")
library(plotly)
```

```
## Loading required package: ggplot2
```

```
## 
## Attaching package: 'plotly'
```

```
## The following object is masked from 'package:ggplot2':
## 
##     last_plot
```

```
## The following object is masked from 'package:stats':
## 
##     filter
```

```
## The following object is masked from 'package:graphics':
## 
##     layout
```

```r
setwd("C:\\Users\\lpowel06\\Documents\\sabrina for github")

# Read in agency personnel spending data set
agency_data <- readRDS(file="data-agencyspendpiechart.RData")
  #agency_data <- readRDS(file="Output\\data-agencyspendpiechart.RData")

# Create Chart
colors <- c("#00b5db", "#00caec",  "#143e64", "#aae1f4", "#bcbec2",  "#007faa", 
            "#6e747e","#0086c8", "#2869a4", "#0f767f", "#00928f", "#215b69", "#2c2c2c", "#414b57",
            "#024558", "#416878")
textform <- list(
  family="Open Sans", 
  size = 12)
plot_ly(agency_data, labels= ~Group.1, values= ~x, type='pie',
        textposition="outside",
        textinfo = "label",
        insidetextfont=list(color="#2c2c2c", family="Arial"),
        hoverinfo = "text", 
        text= ~paste(Group.1, "\n",
                     percent_c, "%", "\n",
                     "Personnel Obligations: $", obligations, "million"), 
        marker=list(colors=colors, 
                    line=list(color="#e7f5f9", width=1)))  %>%
  layout(title="Personnel Budgets Across Government", font= list(size=12, color="#2c2c2c"),
         xaxis=list(showgrid=FALSE, zeroline=FALSE, showticklabels=FALSE),
         yaxis=list(showgrid=FALSE, zeroline=FALSE, showticklabels=FALSE)) 
```

<!--html_preserve--><div id="9bc664a2e0d" style="width:672px;height:480px;" class="plotly html-widget"></div>
<script type="application/json" data-for="9bc664a2e0d">{"x":{"visdat":{"9bc2ecb5015":["function () ","plotlyVisDat"]},"cur_data":"9bc2ecb5015","attrs":{"9bc2ecb5015":{"labels":{},"values":{},"textposition":"outside","textinfo":"label","insidetextfont":{"color":"#2c2c2c","family":"Arial"},"hoverinfo":"text","text":{},"marker":{"colors":["#00b5db","#00caec","#143e64","#aae1f4","#bcbec2","#007faa","#6e747e","#0086c8","#2869a4","#0f767f","#00928f","#215b69","#2c2c2c","#414b57","#024558","#416878"],"line":{"color":"#e7f5f9","width":1}},"alpha":1,"sizes":[10,100],"type":"pie"}},"layout":{"margin":{"b":40,"l":60,"t":25,"r":10},"title":"Personnel Budgets Across Government","font":{"size":12,"color":"#2c2c2c"},"xaxis":{"showgrid":false,"zeroline":false,"showticklabels":false},"yaxis":{"showgrid":false,"zeroline":false,"showticklabels":false},"hovermode":"closest","showlegend":false},"source":"A","config":{"modeBarButtonsToAdd":[{"name":"Collaborate","icon":{"width":1000,"ascent":500,"descent":-50,"path":"M487 375c7-10 9-23 5-36l-79-259c-3-12-11-23-22-31-11-8-22-12-35-12l-263 0c-15 0-29 5-43 15-13 10-23 23-28 37-5 13-5 25-1 37 0 0 0 3 1 7 1 5 1 8 1 11 0 2 0 4-1 6 0 3-1 5-1 6 1 2 2 4 3 6 1 2 2 4 4 6 2 3 4 5 5 7 5 7 9 16 13 26 4 10 7 19 9 26 0 2 0 5 0 9-1 4-1 6 0 8 0 2 2 5 4 8 3 3 5 5 5 7 4 6 8 15 12 26 4 11 7 19 7 26 1 1 0 4 0 9-1 4-1 7 0 8 1 2 3 5 6 8 4 4 6 6 6 7 4 5 8 13 13 24 4 11 7 20 7 28 1 1 0 4 0 7-1 3-1 6-1 7 0 2 1 4 3 6 1 1 3 4 5 6 2 3 3 5 5 6 1 2 3 5 4 9 2 3 3 7 5 10 1 3 2 6 4 10 2 4 4 7 6 9 2 3 4 5 7 7 3 2 7 3 11 3 3 0 8 0 13-1l0-1c7 2 12 2 14 2l218 0c14 0 25-5 32-16 8-10 10-23 6-37l-79-259c-7-22-13-37-20-43-7-7-19-10-37-10l-248 0c-5 0-9-2-11-5-2-3-2-7 0-12 4-13 18-20 41-20l264 0c5 0 10 2 16 5 5 3 8 6 10 11l85 282c2 5 2 10 2 17 7-3 13-7 17-13z m-304 0c-1-3-1-5 0-7 1-1 3-2 6-2l174 0c2 0 4 1 7 2 2 2 4 4 5 7l6 18c0 3 0 5-1 7-1 1-3 2-6 2l-173 0c-3 0-5-1-8-2-2-2-4-4-4-7z m-24-73c-1-3-1-5 0-7 2-2 3-2 6-2l174 0c2 0 5 0 7 2 3 2 4 4 5 7l6 18c1 2 0 5-1 6-1 2-3 3-5 3l-174 0c-3 0-5-1-7-3-3-1-4-4-5-6z"},"click":"function(gd) { \n        // is this being viewed in RStudio?\n        if (location.search == '?viewer_pane=1') {\n          alert('To learn about plotly for collaboration, visit:\\n https://cpsievert.github.io/plotly_book/plot-ly-for-collaboration.html');\n        } else {\n          window.open('https://cpsievert.github.io/plotly_book/plot-ly-for-collaboration.html', '_blank');\n        }\n      }"}],"cloud":false},"data":[{"labels":["Department of Agriculture","Department of Commerce","Department of Defense","Department of Homeland Security","Department of Justice","Department of State","Department of the Interior","Department of the Treasury","Department of Transportation","Department of Veterans Affairs","Office of Personnel Management","Smallest Agencies by Budget","Social Security Administration"],"values":[37639994076,3286550792.94,202008808922.46,15230997222.56,8849862571.26,3284615066.27,3373059906.48,5405305323.04,4485736115.29,18157356950.08,27084330920.83,7086396593.22,3337121399.98],"textposition":["outside","outside","outside","outside","outside","outside","outside","outside","outside","outside","outside","outside","outside"],"textinfo":"label","insidetextfont":{"color":"#2c2c2c","family":"Arial"},"hoverinfo":["text","text","text","text","text","text","text","text","text","text","text","text","text"],"text":["Department of Agriculture <br /> 11.10 % <br /> Personnel Obligations: $  37,639.99 million","Department of Commerce <br />  0.97 % <br /> Personnel Obligations: $   3,286.55 million","Department of Defense <br /> 59.55 % <br /> Personnel Obligations: $ 202,008.81 million","Department of Homeland Security <br />  4.49 % <br /> Personnel Obligations: $  15,231.00 million","Department of Justice <br />  2.61 % <br /> Personnel Obligations: $   8,849.86 million","Department of State <br />  0.97 % <br /> Personnel Obligations: $   3,284.62 million","Department of the Interior <br />  0.99 % <br /> Personnel Obligations: $   3,373.06 million","Department of the Treasury <br />  1.59 % <br /> Personnel Obligations: $   5,405.31 million","Department of Transportation <br />  1.32 % <br /> Personnel Obligations: $   4,485.74 million","Department of Veterans Affairs <br />  5.35 % <br /> Personnel Obligations: $  18,157.36 million","Office of Personnel Management <br />  7.98 % <br /> Personnel Obligations: $  27,084.33 million","Smallest Agencies by Budget <br />  2.09 % <br /> Personnel Obligations: $   7,086.40 million","Social Security Administration <br />  0.98 % <br /> Personnel Obligations: $   3,337.12 million"],"marker":{"fillcolor":"rgba(31,119,180,1)","color":"rgba(31,119,180,1)","colors":["#00b5db","#00caec","#143e64","#aae1f4","#bcbec2","#007faa","#6e747e","#0086c8","#2869a4","#0f767f","#00928f","#215b69","#2c2c2c","#414b57","#024558","#416878"],"line":{"color":"#e7f5f9","width":1}},"type":"pie","frame":null}],"highlight":{"on":"plotly_click","persistent":false,"dynamic":false,"selectize":false,"opacityDim":0.2,"selected":{"opacity":1}},"base_url":"https://plot.ly"},"evals":["config.modeBarButtonsToAdd.0.click"],"jsHooks":{"render":[{"code":"function(el, x) { var ctConfig = crosstalk.var('plotlyCrosstalkOpts').set({\"on\":\"plotly_click\",\"persistent\":false,\"dynamic\":false,\"selectize\":false,\"opacityDim\":0.2,\"selected\":{\"opacity\":1}}); }","data":null}]}}</script><!--/html_preserve-->

```r
htmlwidgets::saveWidget(as_widget(last_plot()), "agency_pie_chart.html", selfcontained = TRUE)
```

