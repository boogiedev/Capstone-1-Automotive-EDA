# Automotive-EDA
EDA on Automotive Dataset Scraped from www.theCarConnection.com, ~~www.0-60Specs.com~~, and ~~www.zeroto60times.com~~
![Automotive EDA Header](https://raw.githubusercontent.com/boogiedev/automotive-eda/master/img/automobiles.jpg)

![GitHub](https://img.shields.io/github/license/boogiedev/automotive-eda?style=flat-square)
![GitHub repo size](https://img.shields.io/github/repo-size/boogiedev/automotive-eda?style=flat-square)
![GitHub commit activity](https://img.shields.io/github/commit-activity/m/boogiedev/automotive-eda?style=flat-square)

---
## Sections:
 |  **[Introduction](#introduction)**  |
 **[Data Cleaning](#data-cleaning)**  |
 **[Hypothesis...?](#Hmm...Hypothesis?)**  |
 **[Exploration](#exploration)**  |
 **[Hypothesis](#hypothesis)**  |
 **[Analysis](#analysis)**  |
 **[Future](#future)**  |
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
## Hmm...Hypothesis?
Going into this EDA originally, I was set on trying to compare common features of cars with 0-60 times on a continuous scale, but I soon realized that I was biting off much more than I could chew. I also found out that some of the sources that I was preparing to scrape (crossed out above) had pieces of data in it that were extremely incorrect. 

> Sub 2.0 seconds to 60? On a MANUAL Combustion Engine Car, that's stock??  Source: [0-60 Specs](https://www.0-60specs.com/0-60-times/)
![weird 0-60 times](https://raw.githubusercontent.com/boogiedev/automotive-eda/master/img/0-60bunk.png)

---

## Exploration
### Graphs/Visualizations:
 |  **[Averge MPG by Manufacturer](#Average-MPG-by-Manufacturer)**  |
 **[Horsepower to MPG](#MPG-to-Horsepower-Scatter-Plot)**  |
 **[Torque to MPG](#MPG-to-Torque-Scatter-Plot)**  |
 **[Weight to MPG](#MPG-to-Weight-Scatter-Plot)**  |
 **[Passenger Door to MPG](#MPG-to-Passenger-Doors-Density-Plot)**  |
 **[Cylinders to MPG](#MPG-to-n_Cylinders-Density-Plot)**  |

 
> The rabbit hole of exploration

#### Average MPG by Manufacturer
![avgMPGbyBrand](https://raw.githubusercontent.com/boogiedev/automotive-eda/master/img/avgmpgbrand.png)
#### MPG to Horsepower Scatter Plot
![mpgbyhp](https://raw.githubusercontent.com/boogiedev/automotive-eda/master/img/mpgbyhp.png)
#### MPG to Torque Scatter Plot
![mpgbytq](https://raw.githubusercontent.com/boogiedev/automotive-eda/master/img/mpgbytq.png)
#### MPG to Weight Scatter Plot
![mpgbyweight](https://raw.githubusercontent.com/boogiedev/automotive-eda/master/img/mpgbyweight.png)
#### MPG to Passenger Doors Density Plot
> Getting a little desperate to find something meaningful...
![mpgbydoors](https://raw.githubusercontent.com/boogiedev/automotive-eda/master/img/mpgbydoorsDensity.png)

<br><br><br>
> Untill...
#### MPG-to-n_Cylinders-Density-Plot
![mpgbycyldense](https://raw.githubusercontent.com/boogiedev/automotive-eda/master/img/mpgbycyldense.png)

---
## Hypothesis
After exploring the data, and thanks to the help of Tony and Andrew (my instructors) we saw that the MPG distribution of 5-Cylinder engines were Bimodal! This was interesting! Even having a bit of domain knowledge about cars, I couldn't exactly explain, or even prove why this was the case. So here we go! 



---
## Analysis




---
## Future
- Implement more Hypothesis Testing on other categories in Engine output -> Bonferroni Correction
- Actually Source 0-60 Data or Clean existing
- Source Data on Engine Dynamics
---
## Shoutouts
- All the Galvanize DS 120 Instructors for the Guidance
- All the Galvanize DS 120 Instructors for listening to me stress
- All the Galvanize DS 120 Instructors for being with me through my ups and downs
- Pandas-Profiling for carrying me and my current lack of a statistical eye 
---


