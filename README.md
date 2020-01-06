# The effect of the Swedish amortization requirement on house prices - A descriptive analysis

## 1. Introduction 

The main purpose of this notebook is to learn how to scrape. I do that by scraping the largest property portal in Sweden, for buying and selling apartments and houses, called Hemnet. It includes the majority of housing ads in Sweden and provides novel housing market data. Hemnet not only report most of the properties for sale in Sweden, it also list all closing prices together with the information on the properties back to 2010. The Swedish housing market has been under scrutiny for the last couple of years. In 2015, the Riksbank lowered the interest rate to negative territories and implemented bond purchases, in order to increase inflation that was well under the target of 2 %. At the same time, the housing market was booming with a ratio of household debt to disposable income being one of the higest in the world (Milne, 2016) and house prices soaring (Turk, 2015). In 2016, Sweden's financial supervisory authority and the agency in charge of macroprudential policy, Finansinspektionen, implemented an amortization requirement to curb indebtedness and reduce the demand for housing. The amorization requirement stated that new mortgages have to be amortised down to 50 per cent of the value of the residential property (Finansinspektionen, 2016). 

Three years has passed since the requirement was implemented and there is still little research on the effects of the requirement. The literature has so far focused on the impact of the requirement on debt (see e.g. Hull, 2017 and Chen and Columba, 2016). Finansinspektionen's report from 2018, concludes that the amortisation requirement slowed the growth of house prices. However, the analysis is limited to the annual change from 2016 and there is little information provided on how the effect differs between cities, types of properties and if the increase/decrease from the asked price is affected.   

The goal of this project is to understand how the amortization requirement affected house prices in Sweden. Even though the main objective of the reform was to halt indebtedness, I believe it is important to look at the effects on housing prices as well to understand how this reform impacts the broader economy. So far the impact and effectiveness of macroprudential policies is unclear (Bernanke, 2015). I collect data from Hemnet and run a descriptive analysis on final prices. Since I also have information on the city the property was sold in and the type of property, I can divide the data into subgroups to search for heterogenous effects. Last, I study whether there is an effect on the percentage increase/decrease from the asked price after the requirement. The hypothesis is that after the amortization requirement, individuals may be less prone to pay more than the asked price, since the amount of amortization depends on the sales price of the property.

## 2. Data

The data I want to obtain is all closing prices on properties in Sweden found on hemnet.se. On the website they list all the residences sold in Sweden and also report information on the sale price, address, city, area in city, number of square meters, monthly fee, number of rooms, price per square meter, date of sale and how many percent the closing price has increased or decreased from the asked price. The list of closing prices goes as far back as 2010. However, the number of listings are few in 2010-2012, and hence I will use data from 2014 and forward. I collect data for both co-operative apartments and villas since those types of properties are the most common ones. 

The data I am scraping is found on the following link: https://www.hemnet.se/salda/bostader?item_types%5B%5D=bostadsratt&page=2&sold_age=all.  

## 3. Descriptive evidence

Find full code for the analysis in Amortization requirement and house prices.ipynb.

I divide the data into subgroups based on the city of sale and the type of property and simply plot the sale prices between 2014-2018. I want to see if there are trend breaks in sale prices comparing the period before and after the implementation of the amortization requirement on June 1st 2016. Of course, I cannot say whether the possible trend break is due to the amortization requirement only since I do not control for anything else. In addition, the number of years after the requirement was implemented is few so I can only get a general picture of the price development.

The descriptive evidence indicate that there is a small trend break in sales prices approximately one year after the requirement was implemented. The verticle red line indicates the amortization requirement. The black line shows a moving average (using 6 lagged terms and the current observation in the filer) and the dashed line shows a HP-filer (using a smoothing parameter of 1600). Even though the findings are only suggestive, the cyclical pattern in the MA-serie shows that prices generally increase during the first half of the year. However, this is not the case in the beginning of 2018, which further suggests that there is a trend break in mid 2017. Results are the same using six month averages.

<img src="https://user-images.githubusercontent.com/59476324/71809191-d74ef300-306f-11ea-8272-dbc8f799d5ba.png" width="400" height="300">

The same holds when plotting the price per square metres.

<img src="https://user-images.githubusercontent.com/59476324/71819327-e348ae00-308b-11ea-8ff5-267babb0e5a3.png" width="400" height="300">

The decreasing trend in house prices seems to be driven by a decreasse in house prices in Stockholm and by a decrease in prices for apartments. 

<img src="https://user-images.githubusercontent.com/59476324/71819986-f52b5080-308d-11ea-9eef-94823d34516d.png" width="400" height="300">
<img src="https://user-images.githubusercontent.com/59476324/71820022-112ef200-308e-11ea-8a9b-048fccdfff61.png" width="400" height="300">

An interesting finding is that buyers seems to be less willing to pay more than the asked price after the amortization requirement. The mean percentage increase from the asked prices decreases a lot after the requirement was implemented. This can perhaps capture that buyers became more cautious when the housing market became regulated. It can also capture that the real estate agents started to price the properties more "correctly". In summary, sales prices of properties do not increase from the asked prices equally much as prior to 2016.

<img src="https://user-images.githubusercontent.com/59476324/71820078-489d9e80-308e-11ea-8b31-b0d25d2f1fc2.png" width="400" height="300">

## 4. Summary

In this project I study the development of Swedish house prices in relation to an amortization requirement implemented in June 2016. I use novel data, scraped from the Swedish largest property portal called Hemnet. Using a descriptive analysis, I plot the house prices for the whole country, the three largets cities, apartments and villas, and the percentage increase in sale price from the asked price between 2014-2018. There seems to be a trend break in mid 2017, where prices start to decrease. The findings suggests that it is driven by a price decrease in Stockholm and for apartments. There is a clear trend break when it comes to the increase of final prices from asked prices. The percentage increase has dereased from 13% in 2016 to only 5 % in August 2018. Hence, buyers are less willing to pay more than the asked price now compared to prior to the requirement. In conclusion, this is a simple and broad analysis of a complex issue, however it may give an overview to the development of house prices in Sweden between 2014-2018 and in connection to the amortization requirement implemented in 2016.  

## References

Bernanke, B., 2015. "Should monetary policy take into account risks to financial stability?", retrieved at: https://www.brookings.edu/blog/ben-bernanke/2015/04/07/should-monetary-policy-take-into-account-risks-to-financial-stability/. 

Chen, J., Columba, F., 2016. Macroprudential and Monetary Policy Interactions in a DSGE Model for Sweden. IMF Working Paper, WP/16/74.

Finansinspektionen, 2016. "Amortisation requirement for new mortgages", retrieved at: https://www.fi.se/en/published/press-releases/2016/amortisation-requirement-for-new-mortgages/. 

Finansinspektionen, 2018. "The Swedish Mortgage Market", retrieved at: https://www.fi.se/contentassets/e50ed7ac94454af191625a898190073b/bolan_2018_eng_ktt.pdf

Milne, R., 2016. "Sweden’s central bank chief says negative rates ‘undramatic’", Financial Times, October 17 2016, retrieved at: https://www.ft.com/content/b5c03c3e-936b-11e6-a1dc-bdf38d484582.  

Turk, R., 2015. Housing prices and household debt interactions in sweden. IMF Working Paper 15/276.
