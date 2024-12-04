# Purchasing Power Parity Analytics

## Purchasing Power Parity Explained
Purchasing power parity (PPP) is an econmic analytical tool that is used to compare the economic productivity of different countries.

The PPP is essentially an atypical exchange rate used to compare the value of different currencies in different nations. Purchasing Power parity is the strength a currency has when purchasing goods. If you have currency in one country and exchange it in another, how much can that value you get you of the same good. A standard example to easily understand this is the McDonald's Big Mac. According to the PPP if you buy a Big Mac in the United States then fly to a country in Europe that uses Euros , you should be able to buy a Big Mac with your converted US Dollar and the Euro should have relatively the same worth. Of course, due to many external factors affecting the currency in other countries this is not always the case. This leads to a fluctuation in prices in differenct countries

## The Chosen Product
The product we have chosen are apples. Over more than 50% consume a substantial amount of apples from many different parts of the globe. So this provides a wide dataset from many different currencies, regions and lifestyles around the world! 


## External Factor
Apples were selected as the product for this analysis due to their status as a staple fruit with global availability and relatively standardized pricing, making them an ideal product for comparison across different countries. For the external factor analysis, exchange rates were examined, as they significantly influence the cost of imported goods. According to Investopedia, an exchange rate is the value of one currency for the purpose of conversion to another, essentially determining how much of one currency is needed to purchase another. Exchange rates fluctuate based on economic factors such as interest rates, inflation, and political stability, affecting the cost of goods and services between countries ("Exchange Rates," 2024). Fluctuations in exchange rates can result in substantial price differences for the same product in different countries. By comparing apple prices across various countries and incorporating exchange rate data, insights can be gained into how currency fluctuations impact the affordability of apples in different markets.


## The Apples Index

### 1. Retrieving Cost of Apples
Numbeo.com shows the price of apples by country per one kilogram. Our group scraped this data from the website as the foundational building block to create our apples index. Next we used the html parser to find the relevant section and table on the webpage. 

### 2. Creating a Table
First we added the correct place and ID. Next we took 15 countries; Kazakhstan, Portugal, Greece, Lativa, Iran, Morocco, Panama, Iraq, Chile, Nepal, Argentina, Ukraine, India, Canada and added them to a table by country and price. During this process we also converted the price numbers to float values as this will make it easier to manipulate them in the future.

## Citations
Numbeo. (n.d.). Cost of living country price rankings. Numbeo. 
  Retrieved December 1, 2024, from https://www.numbeo.com/cost-of-living/country_price_rankings?itemId=110

The Economist. (2024, September 21). The Big Mac index. The Economist. 
  Retrieved December 1, 2024, from https://www.economist.com/interactive/big-mac-index

Investopedia. (2024, November 12). Purchasing power parity (PPP). Investopedia. 
  Retrieved December 1, 2024, from https://www.investopedia.com/updates/purchasing-power-parity-ppp/

 Exchange Rates: What They Are, How They Work, and Why They Fluctuate. (2024). Investopedia. https://www.investopedia.com/terms/e/exchangerate.asp

