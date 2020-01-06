# The effect of the Swedish amortization requirement on house prices - A descriptive analysis

## 1. Introduction 

In this notebook I will scrape a Swedish website called “Hemnet”. Hemnet is the largest property portal in Sweden for buying and selling apartments, houses, summer houses etcetera. It includes the majority of housing ads in Sweden. I do research in macroeconomics and I am specifically interested in monetary policy, housing markets, debt and economic inequality. My dissertation is currently focused on monetary policy but for my last paper I have been thinking about doing something on the Swedish housing market. In order to get novel housing market data, I want to scrape Hemnet. Hemnet not only report most of the properties for sale in Sweden, it also list all closing prices together with the information on the properties all the way back to 2010. Hence, it is possible to retrieve historical data from the site. The information provided for each listing includes the address, city, area in city, number of square meters, monthly fee, number of rooms, price per square meter, date of sale and how many percent the closing price has increased or decreased from the asked price. There are other sources to retrieve this data (such as Statistics Sweden), however it is not public. On Statistics Sweden's website you can find data on property prices but this will only be on an aggregate level for regional comparison or similar. Hence, there are no publically available data on all the properties sold. Hence, I believe there is a valid reason to collect this data. 

The Swedish housing market has been under hard scrutiny for the last couple of years. In 2015, the Riksbank lowered the interest rate to negative territories and implemented bond purchases, in order to increase inflation that was well under the target of 2 %. At the same time, the housing market was booming with a ratio of household debt to disposable income being one of the higest in the world at more than 180 percent in 2016 (Milne, 2016). In addition, house prices increased dramatically with a 20 % increase in the two biggest cities Stockholm and Gothenburg in 2015 (Turk, 2015). Many researchers warned that the financial stability of Sweden was threatend (Andersson and Jonung, 2016). In 2016, Sweden's financial supervisory authority and the agency in charge of macroprudential policy, Finansinspektionen, implemented an amortization requirement to curb indebtedness and reduce the demand for housing. The amorization requirement stated that new mortgages have to be amortised down to 50 per cent of the value of the residential property (Finansinspektionen, 2016). 

Almost two years has passed since the requirement was implemented and there is still little research on the effects of the requirement. Hull (2017) evaluate the effect on debt using an incomplete markets model with three types of debt and a novel mortgage contract specification that is calibrated using Swedish micro and macro data. He finds that the policy effect in the fully-specified model is small. The debt-to-income ratio drops, but only by 4.79–4.99%. On the other hand, Chen and Columba (2016) estimate a dynamic stochastic general equilibrium (DSGE) model and find that demand-side macroprudential measures are more effective in curbing household debt ratios than monetary policy, and they are less costly in terms of foregone consumption. Every year, Finansinspektionen publish a report on the Swedish Mortgage Market. In the report from 2018, they conclude that the amortization requirement has reduced the rate of growth of new mortgages and resulted in households buying less expensive homes. As a whole, the amortisation requirement slowed the growth of house prices by 2 per cent and debt-to-income ratios by almost 8 per cent (Finansinspektionen, 2018). However, the analysis is limited to the annual change from 2016 and there is little information provided on how the effect differs between cities, types of properties and if the increase/decrease from the asked price is affected. Therefore, further research is called for.   

The goal of this project is to understand how the amortization requirement affected house prices in Sweden. As far as I know, there are no paper on this yet. Even though the main objective of the reform was to halt indebtedness, I believe it is important to look at the effects on housing prices as well to understand how this reform impacts the broader economy. An important extension would be to also look at the effects on borrowing and housedhold debt, but due to lack of data I will not do that in this short analysis. Rising house prices and debt levels is also a global issue and so far the impact and effectiveness of macroprudential policies is unclear, as there is little research on the subject (Bernanke, 2015). Hence, I want to provide information on the short-term impacts of the requirement, which can be a guideline for future research. I will collect data from Hemnet and run a descriptive analysis on the final prices. Since I also have information on city and type of property, I can divide the data into subgroups to search for heterogenous effects. I also want to study whether there is an effect on the percentage increase/decrease from the asked price after the requirement. The hypothesis is that after the amortization requirement, individuals may be less prone to pay more than the asked price, since the amount of amortization depends on the sales price of the property.

## 2. Data

The data I want to obtain is all closing prices on properties in Sweden found on hemnet.se. On the website they list all the residences sold in Sweden and also report information on the sale price, address, city, area in city, number of square meters, monthly fee, number of rooms, price per square meter, date of sale and how many percent the closing price has increased or decreased from the asked price. The list of closing prices goes as far back as 2010. However, the number of listings are few in 2010-2012, and hence I will use data from 2013 and forward. I collect data for both co-operative appartments and villas since those types of properties are the largest and most common. 

The data I am scraping is found on the following link: https://www.hemnet.se/salda/bostader?item_types%5B%5D=bostadsratt&page=2&sold_age=all.  

## 3. Descriptive evidence

Find full code for the analysis in Amortization requirement and house prices.ipynb.

I will divide the data into subgroups based on city and type of property and simply plot the sale prices between 2014-2018. I want to see if there are trend breaks in sale prices comparing the period before and after the implementation of the amortization requirement on June 1st 2016. I also want to see of the percentage increase in sale price from the asked price is effected or not. Of course, we cannot say whether the possible trend break is due to the amortization requirement since I do not control for anything else. In addition, the number of years after the requirement was implemented is few so we can only get a general picture of the price development.

![Saleprice](https://user-images.githubusercontent.com/59476324/71809191-d74ef300-306f-11ea-8272-dbc8f799d5ba.png)


## 4. Conclusions
