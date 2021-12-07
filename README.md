## Introduction 
If we treat agriculture as a system, we can think about inputs and outputs. 
![System](https://user-images.githubusercontent.com/86243647/144939640-b4072840-6061-48b5-9755-18b5b321523e.PNG)
Even within the scope of crop production, there can be several outputs, but in this case, we will focus on yield. The input side can be summarized in 3 major categories: seed genetics, machinery interaction, and environmental factors. Depending on these inputs and how they interact, it can result in different yields. To optimize the system, we can manage macro-level practices that can affect the overall performance of a crop. For example, by implementing the right irrigation system for a specific crop in a set environment, we can positively shift the yield and, as a result, optimize the system. However, even then, there are still plant-to-plant variations that affect the overall performance of the crop.
![Corn_variation](https://user-images.githubusercontent.com/86243647/144939652-ead6a9a3-9725-4403-a3f2-9b2823cd69d4.PNG)

By studying and understanding these variations, we could precisely tweak each plant's inputs and increase the yield by moving those low-yielding plants to a higher yield.  

In order to start an understanding of plant to plant variability, we have collected three datasets. First, we collected imagery at planting (Furrow Vision). Then the plant was tracked through aerial imagery (Sentera). Lastly, each plant was hand-harvested, and the yield was recorded.
![puzzle](https://user-images.githubusercontent.com/86243647/144940532-b494e216-4bb9-4032-a97b-cecd5fde2593.PNG)

I look at this dataset as three puzzle parts that help us build the big picture of what is causing plant variability.  

For this project, three different landscapes were selected. Each landscape represents a different topography and soil conditions. Then, each landscape has three replicas that contain 24 rows, representing 10 different planting treatments. 
![image](https://user-images.githubusercontent.com/86243647/144941013-21f55d68-0504-459d-b8d5-d394e251c98f.png)


## Problem Statement
Two main questions drive the analysis of the data. How is the performance of the plant affected by planting treatment? What drives plant to plant variability even when all the inputs (genetics, environment, and machinery settings) remain the same? Although these seem straightforward questions, many data processes need to happen before the data can be used. First, the datasets need to be joined. Then before comparing treatments or conditions, the data has to be normalized to account for spatial variability. In order to approach this task, I created a workflow that indicates the steps needed to answer these questions. 
[Workflow.pdf](https://github.com/lizbethp/516X-Digital_Acre/files/7664293/Workflow.pdf)

There are three main challenges that I faced when analyzing the data. First, joining the data is a time-consuming process that has to be made every time I fix a mistake in the original data or more yield data was updated into the SQL database. Second, there is a lot of spatial variability that needs to be accounted for. Lastly, it is hard to view the effect of one factor at a time. 

For this project, I dedicated my time to creating a pipeline that will update new data, normalize it and create visuals to guide further analysis. Below is a diagram that summarizes the steps of this pipeline. 

<p align="center">
  <img src="https://user-images.githubusercontent.com/86243647/144943104-c56ffc62-86b0-4206-b947-431fa0ca4146.PNG">
</p>
## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/lizbethp/516X-Digital_Acre/edit/main/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/lizbethp/516X-Digital_Acre/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
