# Automotive-EDA
EDA on Automotive Dataset Scraped from www.theCarConnection.com, ~~www.0-60Specs.com~~, and ~~www.zeroto60times.com~~
![Automotive EDA Header](https://raw.githubusercontent.com/boogiedev/automotive-eda/master/img/automobiles.jpg)

<p align="center">
  <img src="https://img.shields.io/badge/Maintained%3F-Kinda-blue?style=flat-square"></img>
  <img src="https://img.shields.io/github/license/boogiedev/automotive-eda?style=flat-square">
  <img src="https://img.shields.io/github/repo-size/boogiedev/automotive-eda?style=flat-square">
  <img src="https://img.shields.io/github/commit-activity/m/boogiedev/automotive-eda?style=flat-square">
</p>

---
## Sections:
 |  **[Introduction](#introduction)**  |
 **[Data Cleaning](#data-cleaning)**  |
 **[Hypothesis...?](#not-really-a-hypothesis)**  |
 **[Exploration](#exploration)**  |
 **[Hypothesis](#hypothesis)**  |
 **[Focused Exploration](#focused-exploration)**  |
 **[Analysis](#analysis)**  |
 **[Future](#future)**  |<br><br>
 |  **[Takeaways](#takeaways)**  |
 **[Shoutouts](#shoutouts)**  |
 
---
## Introduction
Cars come in all shapes and sizes, each with their own unique features and quirks; as humans, we create and design cars to fit our utility needs. Whether this means dropping your 5 kids off to their soccer matches, or smoking someone in a street-race, cars can do everything. Today we'll be looking at a dataset from theCarConnection.com that was scraped by [Nicolas Gervais](https://github.com/nicolas-gervais/predicting-car-price-from-scraped-data/blob/master/scraping).
This project is mean to be an EDA on the different aspects of Automobiles. What started out with a specific question, has changed numerously throughout the journey of this EDA, so stay tuned to find out!  
> This is by all means a student project (my first eda!), which means the data that is sourced, cleaned, analyzed, etc will not always be perfect. If you see an issue please submit a ticket so I can fix it 
---
## Data-Cleaning
Original Dataset:
![Original Dataset](https://raw.githubusercontent.com/boogiedev/automotive-eda/master/img/orig_dataset.png)
The world is nowhere near perfect, and as for datasets, even much less so. As you can see, the original intake dataset... was all kinds of misshaped (+30000 COLUMNS!), but this is nothing a simple transformation couldn't handle. After cleaning, casting, and adding a some features such as Cylinders, Brand, etc, I was finally able to end up with this.

Cleaned Dataset:
![Cleaned Dataset](https://raw.githubusercontent.com/boogiedev/automotive-eda/master/img/clean_dataset.png)

---
<sub>[  **[Back to Sections](#sections)** ]</sub>

## Not Really a Hypothesis
Going into this EDA originally, I was set on trying to compare common features of cars with 0-60 times on a continuous scale, but I soon realized that I was biting off much more than I could chew. I also found out that some of the sources that I was preparing to scrape (crossed out above) had pieces of data in it that were extremely incorrect. 

> Sub 2.0 seconds to 60? On a MANUAL Combustion Engine Car, that's stock??  Source: [0-60 Specs](https://www.0-60specs.com/0-60-times/)
![weird 0-60 times](https://raw.githubusercontent.com/boogiedev/automotive-eda/master/img/0-60bunk.png)

---
<sub>[  **[Back to Sections](#sections)** ]</sub>

## Exploration
### Graphs/Visualizations:
 |  **[Averge MPG by Manufacturer](#Average-MPG-by-Manufacturer)**  |
 **[Horsepower to MPG](#MPG-to-Horsepower-Scatter-Plot)**  |
 **[Torque to MPG](#MPG-to-Torque-Scatter-Plot)**  |
 **[Weight to MPG](#MPG-to-Weight-Scatter-Plot)**  |
 **[Passenger Door to MPG](#MPG-to-Passenger-Doors-Density-Plot)**  |<br>
<details>
  <summary>
    Show Graphs
  </summary>
<br>

> The rabbit hole of exploration
#### Average MPG by Manufacturer  
<img src="https://raw.githubusercontent.com/boogiedev/automotive-eda/master/img/avgmpgbrand.png" width="80%"></img>
<br>| **[Back](#graphsvisualizations)** |
#### MPG to Horsepower Scatter Plot
<img src="https://raw.githubusercontent.com/boogiedev/automotive-eda/master/img/mpgbyhp.png" width="80%"></img>
<br>| **[Back](#graphsvisualizations)** |
#### MPG to Torque Scatter Plot
<img src="https://raw.githubusercontent.com/boogiedev/automotive-eda/master/img/mpgbytq.png" width="80%"></img>
<br>| **[Back](#graphsvisualizations)** |
#### MPG to Weight Scatter Plot
<img src="https://raw.githubusercontent.com/boogiedev/automotive-eda/master/img/mpgbyweight.png" width="80%"></img>
<br>| **[Back](#graphsvisualizations)** |
#### MPG to Passenger Doors Density Plot
> Getting a little desperate to find something meaningful...
<img src="https://raw.githubusercontent.com/boogiedev/automotive-eda/master/img/mpgbydoorsDensity.png" height="auto" width="80%"></img>
<br>| **[Back](#graphsvisualizations)** |
<br>


</details> 

Ever since the mishap of finding possibly corrupted data, as well as choosing a topic/hypothesis that was unsupportable or unquantifiable at this point (with my skillset), I started to delve deeper into the data. I knew I needed to visualize and compare different specifications against each other in order to find something interesting. 

<br> 

> With a 2020 mindset and considering the trajectory of car specifications over the years, I thought to myself, "*What are some important aspects that come to mind when people pick a car*? 

<br>

That's when it hit me! I started to focus my visualizations and comparisons over a car's MPG (Miles per Gallon). Over 10-20 plots later, and with the help of [Pandas-Profiling](https://github.com/pandas-profiling/pandas-profiling), I was finally able to reformulate a hypothesis.  

---
<sub>[  **[Back to Sections](#sections)** ]</sub>

## Focused Exploration

It was on this plot that I was pointed out that 5 Cylinder engines have a *Bimodal* distribution when it comes to their MPG

> #### MPG-to-n_Cylinders-Density-Plot <img src="https://raw.githubusercontent.com/boogiedev/automotive-eda/master/img/mpgbycyldense.png" width="80%"></img><br>

As you can see, with the graphs, there has been a progression on centering the focus of what exact pieces of data I wanted to further explore 

<details>
  <summary>
    <b> Histogram of MPG of 5-CYL Engines with Dist </b>  
  </summary>
  <img src="https://raw.githubusercontent.com/boogiedev/automotive-eda/master/focused_img/5cylmpgdist.png">
  </img>
</details>

<details>
  <summary>
    <b> MPG Dist of 5-CYL Engines by Manufacturer </b>  
  </summary>
  <img src="https://raw.githubusercontent.com/boogiedev/automotive-eda/master/focused_img/5cylmpgbymodel.png">
  </img>
  <img src="https://raw.githubusercontent.com/boogiedev/automotive-eda/master/focused_img/5cylmpgbymodelgran.png">
  </img>
</details>

<details>
  <summary>
    <b> 5-CYL MPG Averages by Model  </b>  
  </summary>
  <img src="https://raw.githubusercontent.com/boogiedev/automotive-eda/master/focused_img/mpgavg5cylmodel.png">
  </img>
</details>

---

<details>
  <summary>
    <b> 5-CYL Horsepower/Torque Averages by Model  </b>  
  </summary>
  <img src="https://raw.githubusercontent.com/boogiedev/automotive-eda/master/focused_img/hptqavgmodel.png">
  </img>
</details>

<details>
  <summary>
    <b> 5-CYL Horsepower Densities by Manufacturer  </b>  
  </summary>
  <img src="https://raw.githubusercontent.com/boogiedev/automotive-eda/master/focused_img/5cylhpmanufacturer.png">
  </img>
</details>

<details>
  <summary>
    <b> Power Densities by Cylinder  </b>  
  </summary>
  <img src="https://raw.githubusercontent.com/boogiedev/automotive-eda/master/focused_img/powdistbycyl.png">
  </img>
</details>

<details>
  <summary>
    <b> Power Densities by Cylinder  </b>  
  </summary>
  <img src="https://raw.githubusercontent.com/boogiedev/automotive-eda/master/focused_img/powdistbycyl.png">
  </img>
</details>

---
<sub>[  **[Back to Sections](#sections)** ]</sub>

## Hypothesis

After exploring the data, and thanks to the help of Tony and Andrew (my instructors) we saw that the MPG distribution of 5-Cylinder engines were Bimodal! This was interesting! Even having a bit of domain knowledge about cars, I couldn't exactly explain, or even prove why this was the case. 
<br>

> My initial thoughts: 

*5-Cylinder engine configurations are somewhat of a novelty engine, where the majority of car models who host this engine are coming from the same manufacturers who are grandfathering in this design choice as a statement of legacy, rather than practicality.*

<br>

**TLDR: 5-Cylinder Engine configurations offer _no advantages_ over more "Traditional" Engines (I-4, V-6)**

**Null :<br> 
![#f03c15](https://placehold.it/15/f03c15/000000?text=+) 5-Cyl Engine configs offer _no advantages_ over I-4, V-6 Engines configs in the categories below**<br>
**Alternative :<br>
![#c5f015](https://placehold.it/15/c5f015/000000?text=+) 5-Cyl Engine configs _do_ offer _advantages_ over I-4, V-6 Engines configs in the categories below**<br>

| Miles Per Gallon (MPG - Combined)  | Horsepower | Torque |
| ------------- | ------------- | ------------- |

<br>

---
<sub>[  **[Back to Sections](#sections)** ]</sub>

## Analysis
<br>

### MPG vs Cylinder Testing  <br>

```python
# Five Cylinder Car 5 Num Sum for MPG
five_cyl_desc = five_cyl_cars["Gas Mileage (Combined)"].describe()
five_cyl_desc
```
```python
# Four Cylinder Car 5 Num Sum for MPG
four_cyl_desc = four_cyl_cars["Gas Mileage (Combined)"].describe()
four_cyl_desc
```
<img src="https://raw.githubusercontent.com/boogiedev/automotive-eda/master/focused_img/4v5bootstrap.png">






---
<sub>[  **[Back to Sections](#sections)** ]</sub>

## Future
- Implement more Hypothesis Testing on other categories in Engine output -> Bonferroni Correction
- Actually Source 0-60 Data or Clean existing
- Source Data on Engine Dynamics
---
<sub>[  **[Back to Sections](#sections)** ]</sub>

## Shoutouts
- All the Galvanize DS 120 Instructors for the Guidance
- All the Galvanize DS 120 Instructors for listening to me stress
- All the Galvanize DS 120 Instructors for being with me through my ups and downs
- Pandas-Profiling for carrying me and my current lack of a statistical eye 
---
<sub>[  **[Back to Sections](#sections)** ]</sub>

## Takeaways
<img src="https://raw.githubusercontent.com/boogiedev/automotive-eda/master/img/saitamanervous.gif" width="220"></img>

---
