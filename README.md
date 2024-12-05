# Purchasing Power Parity Analytics

## Purchasing Power Parity Explained
Purchasing power parity (PPP) is an econmic analytical tool that is used to compare the economic productivity of different countries.

The PPP is essentially an atypical exchange rate used to compare the value of different currencies in different nations. Purchasing Power parity is the strength a currency has when purchasing goods. If you have currency in one country and exchange it in another, how much can that value you get you of the same good. A standard example to easily understand this is the McDonald's Big Mac. According to the PPP if you buy a Big Mac in the United States then fly to a country in Europe that uses Euros , you should be able to buy a Big Mac with your converted US Dollar and the Euro should have relatively the same worth. Of course, due to many external factors affecting the currency in other countries this is not always the case. This leads to a fluctuation in prices in differenct countries

## The Chosen Product 🍎
The product we have chosen are apples. Countries from all across the globe consume a substantial amountof apples. So this provides a wide dataset from many different currencies, regions and lifestyles around the world! 


## External Factor
Apples were selected as the product for this analysis due to their status as a staple fruit with global availability and relatively standardized pricing, making them an ideal product for comparison across different countries. For the external factor analysis, exchange rates were examined, as they significantly influence the cost of imported goods. According to Investopedia, an exchange rate is the value of one currency for the purpose of conversion to another, essentially determining how much of one currency is needed to purchase another. Exchange rates fluctuate based on economic factors such as interest rates, inflation, and political stability, affecting the cost of goods and services between countries ("Exchange Rates," 2024). Fluctuations in exchange rates can result in substantial price differences for the same product in different countries. By comparing apple prices across various countries and incorporating exchange rate data, insights about the global market, intercontinental poltics and relations even the enviroment!


## The Apples Index

### 1. Retrieving Cost of Apples
Numbeo.com shows the price of apples by country per one kilogram. Our group scraped this data from the website as the foundational building block to create our apples index. Next we used the html parser to find the relevant section and table on the webpage. 

### 2. Creating a Table
First we added the correct place and ID. Next we took 15 countries; Kazakhstan, Portugal, Greece, Lativa, Iran, Morocco, Panama, Iraq, Chile, Nepal, Argentina, Ukraine, India, Canada and added them to a table by country and price. During this process we also converted the price numbers to float values as this will make it easier to manipulate them in the future. The countries we chose were from many different regions with different lifestyles around the world which should provide us with a nice data spread.

### 3. Converting Currencies
In this step we created a function to convert the currencies. Using the currency

### 4. VAT Rate and Application
VAT stand for value-added tax (rate) is a consumption tax that is levied on goods at each stage of the supply chain. Different countries have different rates of vat tax. Using the Canada Revenue Agency site and taxsummaries.pwc.com our group found the VAT of each country and added it to the table. Next we used a function to apply each tax rate to the price of apples in each country **apply_tax(price, tax_rate)**. This was then applied to the table using **df.apply** and **lamda function**.

### 5. Doing Some Cleaning
In this section our group dropped the currency symbols so we could begin the math.

### 6. Calculations and Visualizations
First we calculated the price difference in CAD by subtracting the 'Price with Tax' column by 8.55 the canadian price. Then we filtered out Canada's date due to it always being zerio as we subtracting from Canada. After this, we created a bar chart from this data and added a red line for Canada's price difference. For this we used **plt.()**. The result is shown below:
![image](https://github.com/user-attachments/assets/bea91f0f-beab-432e-8cf9-7bb33ddc1bce)

### 7. Applying Our External Factor
In this next section we applied our extrernal factors of exchange rates which was discussed in the external factors section above. We then used **.drop** to drop the domain code, domain, area code and all other sections in the table we sourced from the FAO website. We also replaced 'Iran (Islamic Republic of)' with just 'Iran' using a **for** loop.

### 8. Bringing it All Together
In these penultimate sections using **.join** we joined the table from our 'Calculations and Visualizations' section with the table from 'Applying Our External Factor' This can be seen below:

We then created a table with country and apple production which can be seen below:
![image](https://github.com/user-attachments/assets/e323401e-469f-4eee-b3ec-b9fc48e73f0b)

Finally we created a scatter plot of Price Difference vs Apple Production to show the correlation. This is shown below:
![image](https://github.com/user-attachments/assets/81877f84-72aa-4a28-acc5-b85d2c6c7b94)

### 9. Calculating Z Score
Using a function we converted the array to standard units and then calculated the Z score which was -0.16 (rounded to 2 decimal places)

## Conclusion

## Citations
Numbeo. (n.d.). Cost of living country price rankings. Numbeo. 
  Retrieved December 1, 2024, from https://www.numbeo.com/cost-of-living/country_price_rankings?itemId=110

The Economist. (2024, September 21). The Big Mac index. The Economist. 
  Retrieved December 1, 2024, from https://www.economist.com/interactive/big-mac-index

Investopedia. (2024, November 12). Purchasing power parity (PPP). Investopedia. 
  Retrieved December 1, 2024, from https://www.investopedia.com/updates/purchasing-power-parity-ppp/

 Exchange Rates: What They Are, How They Work, and Why They Fluctuate. (2024). Investopedia. https://www.investopedia.com/terms/e/exchangerate.asp

