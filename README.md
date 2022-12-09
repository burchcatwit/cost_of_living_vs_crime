# Global Cost of Living vs. Crime Index Analysis

## Introduction 
This project was undertaken in further exploration of the best cities/countries to travel to around the world, while working remote. The group project focussed on which countries have modern internet speeds despite a low GDP, allowing a remote worker to comfortably complete modern work while maximizing their high (compared to global) salaray. However, as an international traveler, we also want to remain as safe as possible from crime ridden countries or specific cities. Thus, this personal project aims to find countries with the lowest cost of living, while remaing safest (according to a global crime index).

## Selection of Data
Two datasets were used in this project. The first dataset was a global cost of living dataset scraped from Numbeo and found on 
![Kaggle.com](https://www.kaggle.com/datasets/mvieira101/global-cost-of-living?select=cost-of-living_v2.csv).
The second dataset was a crime index data set also found on 
![Kaggle.com](https://www.kaggle.com/datasets/6611a4648856d3dd2b8cd9fbc67b3195e9af52ef2dc36c9b66f1ef8ea89cf18c).

The first dataset had a lot of nan values, so those had to be dropped. Most rows with at least one nan value had more than one nan value, so all rows with nan vlaues were dropped instead of focusing on underrepresented columns. The last column also indicated rows which may have inadequate data quality, so those rows were filtered out as well. Lastly, all 55 cost of living features were normalized and averaged into one cost of living (COL) index to make comparison between crime index easier later on. Below, in results, is the top and bottom 20 cities for a few COL features, in comparison to the created COL Index. You will notice a lot of overlap, which is a simple marker of the metric's efficacy.

The second dataset required its location be stripped, as it was originally one string of "city,state,country". This was split into three columns and the state column was dropped, as we are more interested in global destinations than United States-based locations. This dataset also had no nans to remove.

## Methods 
NumPy was used in conjunction with Pandas, to read in the data and perform all data cleaning/munging. 

Matplotlib was then used to create the visualizations. 

## Results 

### Top/Bottom 20 Plots
![top20_cheap_1meal.png](https://github.com/burchcatwit/cost_of_living_vs_crime/blob/main/figs/top20_cheap_1meal.png)
![bot20_cheap_1meal.png](https://github.com/burchcatwit/cost_of_living_vs_crime/blob/main/figs/bot20_cheap_1meal.png)
![top20_cheap_2meal.png](https://github.com/burchcatwit/cost_of_living_vs_crime/blob/main/figs/top20_cheap_2meal.png)
![bot20_cheap_2meal.png](https://github.com/burchcatwit/cost_of_living_vs_crime/blob/main/figs/bot20_cheap_2meal.png)
![top20_cheap_beef.png](https://github.com/burchcatwit/cost_of_living_vs_crime/blob/main/figs/top20_cheap_beef.png)
![bot20_cheap_beef.png](https://github.com/burchcatwit/cost_of_living_vs_crime/blob/main/figs/bot20_cheap_beef.png)
![top20_cheap_1bed.png](https://github.com/burchcatwit/cost_of_living_vs_crime/blob/main/figs/top20_cheap_1bed.png)
![bot20_cheap_1bed.png](https://github.com/burchcatwit/cost_of_living_vs_crime/blob/main/figs/bot20_cheap_1bed.png)
![bot20_cheap_1bed_adj.png](https://github.com/burchcatwit/cost_of_living_vs_crime/blob/main/figs/bot20_cheap_1bed_adj.png)

Unsurprisingly, some of the poorest Middle-Eastern and Southeast Asian countries populate the bottom lists whereas Switzerland, United States, and Norwegian countries populate the top lists. There are a couple Indonesian cities as well as Fiji, which have cheap food and are known to be beautiful. These could potentially be looked into as ideal vacationing locations if their crime index is low as well. Switzerland is also well known for being one of the most expensive countries to visit globally, so its no surprise to see if top the lists.

### COL Index Plots
![top20_col.png](https://github.com/burchcatwit/cost_of_living_vs_crime/blob/main/figs/top20_col.png)
![bot20_col.png](https://github.com/burchcatwit/cost_of_living_vs_crime/blob/main/figs/bot20_col.png)

Both the COL Index plots have a large overlap with the previous COL metric plots, which helps justfiy its use a metric similar to crime index!

### World Crime Index Plots
![top20_wci.png](https://github.com/burchcatwit/cost_of_living_vs_crime/blob/main/figs/top20_wci.png)
![bot20_wci.png](https://github.com/burchcatwit/cost_of_living_vs_crime/blob/main/figs/bot20_wci.png)

Switzerland and the Norwegian countries top the plot for crime index as well. So, while they may not be cheap to visit, they are some of the safest countries on the planet. On the other hand, Brazil and South Africa are among the most crime ridden countries. There are also a couple US states on the bottom list, such as Baltimore and Detroit. One could argue that they are comparable to the Brazilian or South African cities. Given these cities reputations, though, that is likely not going to be make anyone eager to visit a city with nearly as much crime.

### 
![top50_safe_col.png](https://github.com/burchcatwit/cost_of_living_vs_crime/blob/main/figs/top50_safe_col.png)

Eastern European countries seem to be a standout, as they are among the top 50 safest countries while often having some of the lowest cost of living. Let's adjust for COL Index to filter out some of the safe cities with wildly high cost of living.

![top50_safe_col_adj.png](https://github.com/burchcatwit/cost_of_living_vs_crime/blob/main/figs/top50_safe_col_adj.png)

With the adjustment, the Eastern European countries become the standouts. Romania has the most cities on the list, with Armenia, Croatia, and Turkey having a couple a piece. A few interesting cities to find on this list were Tokyo, Seoul, Taipei, and Tampere (Finland). Tokyo, Seoul, and Tampere belong to notably rich countries, so to see them both this safe and somewhat affordable (under 30 COL Index) makes them prime targets to travel to. Taipei was interesting because it happened to be one of the absolute safest countries, while have a cost of living below 25 COL Index which means its both safer and cheaper than the other three mentioned!

![top50_cheap_wci_adj.png](https://github.com/burchcatwit/cost_of_living_vs_crime/blob/main/figs/top50_cheap_wci_adj.png)

Looking at the cheapest countries adjusted to be under crime index of 30, the Eastern European countries get bolstered even further. Slovakian cities are added to list, as well as more from the afforementioned countries, like Romania. There are also a couple cities from Belgium and the Netherlands among the ranks, although near the higher end of the list (close to 30 COL Index, which is "affordable" but above the mean COL Index).

## Discussion 
The best area to visit in terms of low cost of living and low crime index are the eastern European countries. Notably, Romania, Armenia, Turkey, Croatia, and Czech Republic. All these countries had multiple cities with low cost of living and low crime index. A few other notable cities include Merida, Mexico, Abu Dahbi, UAE, Doha Qatar, and Taipei, Taiwan. This gives a travel hungry remote worker plenty of options to explore worldwide, while remaining safe and stretching their dollar as far as possible. Countries to avoid without adequate research, protection, and guidance would definitely be Brazil and South Africa. The Middle-East and most of India, do not seem worth the risk even though your dollar will go quite far there, although, Mangalore seems to be a potential exception to this.

Many of the cheapest or most expensive cities fall in line with what we know about global GDP and word of mouth, such as Switzerland being notably lavish. Still, the cost vs. safety of Eastern European countries is often overlooked in the public eye. Future research could delve deeper into Eastern European countries or a collection of ideal cities to further assertain both safety as well as tourist pulls, such as attractions, food quality, recreational experiences, accessible hobbies, etc. to eventually find "diamonds in the rough" or the definitive best affordable cities to visit.

## Reference 
AHMAD JALAL MASOOD (2022-11). World Crime Index, Version 1. Retrieved: 2022-12-8 from (https://www.kaggle.com/datasets/6611a4648856d3dd2b8cd9fbc67b3195e9af52ef2dc36c9b66f1ef8ea89cf18c).
MIGUEL PIEDADE (2022-12). Global Cost of Living, Version 2. Retrieved: 2022-12-8 from 
(https://www.kaggle.com/datasets/mvieira101/global-cost-of-living?select=cost-of-living_v2.csv).
