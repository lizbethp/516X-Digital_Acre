[Website URL](https://lizbethp.github.io/516X-Digital_Acre/)
https://lizbethp.github.io/516X-Digital_Acre/

## Introduction 
If we treat agriculture as a system, we can think about inputs and outputs. 
![System](https://user-images.githubusercontent.com/86243647/144939640-b4072840-6061-48b5-9755-18b5b321523e.PNG)
Even within the scope of crop production, there can be several outputs, but in this case, we will focus on yield. The input side can be summarized in 3 major categories: seed genetics, machinery interaction, and environmental factors. Depending on these inputs and how they interact, it can result in different yields. To optimize the system, we can manage macro-level practices that can affect the overall performance of a crop. For example, by implementing the right irrigation system for a specific crop in a set environment, we can positively shift the yield and, as a result, optimize the system. However, even then, there are still plant-to-plant variations that affect the overall performance of the crop.
![Corn_variation](https://user-images.githubusercontent.com/86243647/144939652-ead6a9a3-9725-4403-a3f2-9b2823cd69d4.PNG)

By studying and understanding these variations, we could precisely tweak each plant's inputs and increase the yield by moving those low-yielding plants to a higher yield.  

In order to start an understanding of plant to plant variability, we have collected three datasets. First, we collected imagery at planting (Furrow Vision). Then the plant was tracked through aerial imagery (Sentera). Lastly, each plant was hand-harvested, and the yield was recorded.
![puzzle](https://user-images.githubusercontent.com/86243647/144940532-b494e216-4bb9-4032-a97b-cecd5fde2593.PNG)

I look at this dataset as three puzzle parts that help us build the big picture of what is causing plant variability.  

The table below show part of the data that each dataset countains.
| Furrow Vision | Sentera| Yield
| ----------- | ----------- | ----------- |
| Residue Level | Emergence Day | Weight
| Residue Occusion | Area of plant (Day 1 - Day 18) | Kernel Count
| Trench Quality | Angle |
| Seed Orientation | Leaf Count |
| Effective Depth | Location |


For this project, three different landscapes were selected. Each landscape represents a different topography and soil conditions. Then, each landscape has three replicas that contain 24 rows, representing 10 different planting treatments. 
![image](https://user-images.githubusercontent.com/86243647/144941013-21f55d68-0504-459d-b8d5-d394e251c98f.png)


## Problem Statement
Two main questions drive the analysis of the data. How is the performance of the plant affected by planting treatment? What drives plant to plant variability even when all the inputs (genetics, environment, and machinery settings) remain the same? Although these seem straightforward questions, many data processes need to happen before the data can be used. First, the datasets need to be joined. Then before comparing treatments or conditions, the data has to be normalized to account for spatial variability. In order to approach this task, I created a workflow that indicates the steps needed to answer these questions. 

<p align="center">
  <img src="https://user-images.githubusercontent.com/86243647/144981392-7236cacc-0d74-4566-9947-e9697f3f0c1d.PNG">
</p>


[Workflow.pdf](https://github.com/lizbethp/516X-Digital_Acre/files/7664293/Workflow.pdf)

There are three main challenges that I faced when analyzing the data. First, joining the data is a time-consuming process that has to be made every time I fix a mistake in the original data or more yield data was updated into the SQL database. Second, there is a lot of spatial variability that needs to be accounted for. Lastly, it is hard to view the effect of one factor at a time. 

For this project, I dedicated my time to creating a pipeline that will update new data, spatially normalize it and create visuals to guide further analysis. Below is a diagram that summarizes the steps of this pipeline. 

<p align="center">
  <img src="https://user-images.githubusercontent.com/86243647/144943104-c56ffc62-86b0-4206-b947-431fa0ca4146.PNG">
</p>

### FAIR Principles and Motivation
I have performed that workflow using other tools such as Excel and Minitab, but I felt motivated to create a script because of several advantages. A simple one is that a scrip (if made correctly) keeps up with changes in data. This is really necessary for this project since data is still being generated. When analyzing the data in python, intermediate steps are saved and open the possibility of using these values for other analysis/ approaches. By saving this analysis and recording how they were produced, the approaches are being recorded, and if a different approach is chosen, the previous one will not be forgotten. Lastly, it facilitates the reproducibility of the analysis. This project will be repeated next year, and it is essential to generate the same data and analysis as this year. 

The data of this project cannot be updated into GitHub due to NDA agreements. For now, this analysis cannot be reproducible by individuals outside my research group. The way I made my scripts facilitated our group analysis. When a document is updated, the pipeline will account for these changes.


## Code 
There are 2 scripts that work with one another. I developed the first script in ArcGIS Pro using spatial packages such as arcpy. This script does all the spatial joins. The second script uses the output of the ArcGIS one and adds more data, and then normalizes it by plot and by row. After it normalized the data it generetes graphs to visualize the reuslts. 

### ArcGIS (Spatial Join) Script 
[ArcGIS Script](https://github.com/lizbethp/516X-Digital_Acre/blob/c9be245431c299c8919b9be1d3b2b5aad1676173/ArcGIS_Joins.py)


### Data Normalization and Visualization
[Data Normalization and Visualization Notebook](https://github.com/lizbethp/516X-Digital_Acre/blob/c9be245431c299c8919b9be1d3b2b5aad1676173/Normalized%20Data.ipynb)

### Assignment 
[Assignment Notebook](https://github.com/lizbethp/516X-Digital_Acre/blob/06abf38efeee583a374be3749434395c37b02a63/Digital_Acre_Assignment.ipynb)

## Conclusion
Although none of my research questions were answered, I consider this project a success. I was able to create the base of my research analysis and to generate intermediate steps in an automized way. In the class, I learned how to wrangle through data, summarize and visualize it, and I successfully applied these learnings to my research. This project has given me the advantage of having all my analysis in a version control environment and using updated files without even opening them. The side back of only using a script is that some of the explorations of the data can be hard to perform through python and might be faster in other platforms. 


