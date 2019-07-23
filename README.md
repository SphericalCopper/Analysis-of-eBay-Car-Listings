# Analysis of eBay Car Listings
eBay Car Listings were cleaned and then organized to glean insight as to the demographics of the cars being sold, and the correlations between variables like the brand of a car and its price. 

The [dataset](https://www.kaggle.com/orgesleka/used-cars-database/data) used was available on Kaggle.

## Data Cleaning 
- Some columns were re-named to be shorter and more appropriately named, making them more intuitive to work with.
- Dataframe was explored to look at what values were missing, and whether it would be appropriate to simply delete them. 
- Columns that were not useful (such as those that only contained 1-2 values that we didn't need) were dropped.

The `price` and `odometer` columns contained numeric data stored as strings. One of the reasons they were stored as strings is because the unit they described, in this case `$` and `km` respectively, were included in the column's values.

- These units were removed to convert the columns to numeric types, and the info about `km` or `$` was added to column anme instead.

## Data Analysis

- Upon inspection of the mileage registered in the `odometer` column, we realized there were only 13 unique values, meaning sellers probably had to pick from a list of values rather than keying in their precise mileage.
- `price` column was analyzed, and cars listed at price $0, or for an unrealistic amount (> 10 mil) were removed.
- Due to noticing that car price variations only spike after 350,000, car prices above this amount were removed.
- Incorrect rows in the `registration_year` column were cleaned. 

![registration year anomalies](https://i.gyazo.com/8efa38d0c9edc4ff961255a2b41d956a.png)

- Since an overwhelming majority of our data points fell within the 1900-2016 registration year range, by dropping the rows that don't belong to that range, we lost less than 4% of our data points. As such, we decided to drop them.

From the rows that remained in the dataset, we selected the 9 most popular car brands, and determined the mean price and mean mileage for each brand:

![popular car brand info](https://i.gyazo.com/baf91a6ddba47b74814d76a0e4e03d8e.png)

## Conclusions
The first thing that stuck out to us about brand popularity was that cars made by European Automobile makers were most popular, representing at least 60% of the total car listings.

We also noted that the most popular brand of car, Volkswagen, had average listing prices that were in the middle of the "higher-tier" and "lower-tier" cars. We deduced that a large number of people might be drawn to the Volkswagen brand due to perceiving it as a "best of both worlds" option. **It possibly satisfies people's latent desire for a luxury brand of car, while also being much more affordable compared to some of the other options like BMW and Audi.**

We also gathered that across most brands listed, the average mileage of cars is very uniform, and has no clear correlation to variables like brand and their corresponding average prices.
