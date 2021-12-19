# Kickstarting with Excel

## Overview of Project
Helping a client visualize theater campaign outcomes based on launch dates and funding goals.

### Purpose
The client will have a better understanding of the best months to fund a play and will be able to set realistic goal amounts that will succeed. 

## Analysis and Challenges
I used pivot tables and graphs in Excel to showcase how successful (or unsuccessful) the outcome of a campaign was based on the launch date.

I also used various Excel formulas to manipulate the data in meaningful ways. For example, I had to convert the UNIX data to a readable format. Then I had to use the "YEAR" formula to pull the dates by year. 

```
The formula used to convert the UNIX timestamp:
=(((H84/60)/60)/24)+DATE(1970,1,1)

The formula used to pull Date End by Year:
=YEAR(S2:S4115)

COUNTIFs were used to pull outcomes by goal:
=COUNTIFS('Raw Data'!$E:$E, "successful", 'Raw Data'!$C:$C, "<1000", 'Raw Data'!$Q:$Q, "plays")
```

### Analysis of Outcomes Based on Launch Date
The first chart (linked below) is a line chart that shows the relationship between outcomes and launch date.

![Theater_Outcomes_vs_Launch png](https://github.com/zobisurf/kickstarter-analysis/blob/main/Resources/PNG/Theater_Outcomes_vs_Launch.png)

In the theatre category, Q2 (April-June) had the highest number of successful outcomes (failures were also highest).
About 60% of the total projects were successful this year in the theatre category (failure rate is lower than success rate).

### Analysis of Outcomes Based on Goals
The second chart (linked below) is also a line chart that shows the relationship between outcomes and a range of goals. 

![Outcomes_vs_Goals png](https://github.com/zobisurf/kickstarter-analysis/blob/main/Resources/PNG/Outcomes_vs_Goals.png)

It seems that goals in the "plays" subcategory within the $1,000 to $5,000 range have higher chances of successful outcomes and are more likely to get produced.

### Challenges and Difficulties Encountered
I ran into issues with the COUNTIFs formulas. I accidentally mapped the wrong cells (used pledged amount instead of goals). I also forgot to check against the "plays" subcategory. 

These issues caused the chart to be incorrect. I went back and looked at the original tutorial video and also used YouTube to find some supplemental material. 

After some trial and error, I figured it out. 

## Results
- What are two conclusions you can draw about the Outcomes based on Launch Date?
  - In the theatre category, Q2 (Apr-Jun) had the highest number of successful outcomes (failures were also highest). The slowest time period is during Q4 (Oct-Dec).
  - About 60% of the total projects were successful this year in the theatre category (failure rate is lower than success rate).

- What can you conclude about the Outcomes based on Goals?
  - It seems that goals in the "plays" subcategory within the $1,000 to $5,000 range have higher chances of successful outcomes and are more likely to get produced.

- What are some limitations of this dataset?
  - Although we know which months have more successful outcomes, we don't know what genre is driving this (is there a specific type of play that drives higher results)?

- What are some other possible tables and/or graphs that we could create?
  - I think it would be interesting see what type of "plays" drive more successful outcomes by country. 
