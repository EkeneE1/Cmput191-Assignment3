# Purchasing Power Parity Analytics

## Purchasing Power Parity Explained
Purchasing power parity (PPP) is an econmic analytical tool that is used to compare the economic productivity of different countries.

The PPP is essentially an atypical exchange rate used to compare the value of different currencies in different nations. Purchasing Power parity is the strength a currency has when purchasing goods. If you have currency in one country and exchange it in another, how much can that value you get you of the same good. A standard example to easily understand this is the McDonald's Big Mac. According to the PPP if you buy a Big Mac in the United States then fly to a country in Europe that uses Euros , you should be able to buy a Big Mac with your converted US Dollar and the Euro should have relatively the same worth. Of course, due to many external factors affecting the currency in other countries this is not always the case. This leads to a fluctuation in prices in different countries

## The Chosen Product 🍎
The product we have chosen are Apples. Countries from all across the globe consume a substantial amount of apples. So this provides a wide dataset from many different currencies, regions and lifestyles around the world! 


## External Factor

Apples were selected as the product for this analysis due to their status as a staple fruit with global availability and relatively standardized pricing, making them an ideal product for comparison across different countries. We chose the quantity of Apples grown and produced in the countries as our external factor. Naturally, the production of any item in a country directly influences the prices and sale of that item in that country. If a country produces more apples, they will have to import less, and hence, prices should be lower as compared to that of a country that imports most of its apples. Apple trees require a specific environment to grow and many countries do not have that kind of soil, weather, moisture and other factors which can help them grow apples.


## The Apples Index

### 1. Retrieving Cost of Apples
Numbeo.com shows the price of apples by country per kilogram. Our group scraped this data from the website as the foundational building block to create our Apple index. The data on prices of apples in each country was scraped from this website using BeatifulSoup. Next, we used the HTML parser to find the relevant section and table on the webpage. 

### 2. Creating a Table
First, we added the correct place and ID. Next, we scraped 15 countries: Kazakhstan, Portugal, Greece, Latvia, Iran, Morocco, Panama, Iraq, Chile, Nepal, Argentina, Ukraine, India, and Canada and added them to a table by country and price. During this process, we also converted the price numbers to float values as this will make it easier to manipulate them in the future. The countries we chose were from many different regions with different lifestyles around the world which should provide us with a nice data spread.

### 3. Converting Currencies
In this step, we created a function to convert the currencies. Here we defined a dictionary and assigned the currency codes. Then we used a function to convert it from CAD to the country's respective currency. For this, the table was mapped with the Currency Codes and then each country was applied with the conversion function.

### 4. VAT Rate and Application
VAT stands for Value-Added Tax (rate), it is a consumption tax that is levied on goods at each stage of the supply chain. Different countries have different rates of VAT tax. Using the Canada Revenue Agency site and taxsummaries.pwc.com our group found the VAT of each country and added it to the table. Next, we used a function to apply each tax rate to the price of apples in each country **apply_tax(price, tax_rate)**. This was then applied to the table using **df.apply** and **lambda function**.

### 5. Doing Some Cleaning
We cleaned the data by removing the unwanted countries and removing extra spaces from the values.

### 6. Calculations and Visualizations
First, we calculated the price difference in CAD by subtracting the 'Price with Tax' column by 8.55, which is the Canadian price. Then we filtered out Canada's data due to it always being zero as we take references from Canada. After this, we created a bar chart from this data and added a red line for Canada's price difference. For this we used **plt.()** function. The result is shown below:
      ![image](https://github.com/user-attachments/assets/bea91f0f-beab-432e-8cf9-7bb33ddc1bce)

### 7. Applying Our External Factor
In this next section, we imported data on Apple production in each country in units of tonnes. This was chosen as the external factor as we have extensive data on it which can be correlated with prices of Apples. The csv file for the Production Quantity data was imported from the Food and Agricultural Organization of the United Nations website.  We then used **.drop** to drop the domain code, domain, area code and all other sections in the table that were not required for analysis. We also replaced 'Iran (Islamic Republic of)' with just 'Iran' to correctly join the table with our original table.

### 8. Bringing it All Together
In these penultimate sections using **.join** we joined the table from our 'Calculations and Visualizations' section with the table from 'Applying Our External Factor' This can be seen below:
![Screenshot 2024-12-04 214804](https://github.com/user-attachments/assets/ac776534-e11a-4c82-bb49-b34a3e5630da)

We then created a bar graph to join the price differences:
![image](https://github.com/user-attachments/assets/bc5c5456-92ed-4936-8206-6aa42034f0f5)


We then created a table with country and apple production which can be seen below:
![image](https://github.com/user-attachments/assets/e323401e-469f-4eee-b3ec-b9fc48e73f0b)

Finally, we created a scatter plot of Price Difference vs Apple Production to show the correlation. This is shown below:
![image](https://github.com/user-attachments/assets/81877f84-72aa-4a28-acc5-b85d2c6c7b94)

### 9. Calculating Z Score
Using the Correlation function we converted the array to standard units and then calculated the Z score which was obtained as -0.16 (rounded to 2 decimal places).


## Conclusion 🍎
Our analysis compared apple prices across 15 countries we explored how exchange rates affect price differences. We did this by scraping data from Numbeo and including VAT rates, we standardized prices for comparison. The results highlight the influence of Production quantity on global prices and show how factors like local production and taxes impact the affordability of products in countries.

## Citations
Numbeo. (n.d.). Cost of living country price rankings. Numbeo. 
  Retrieved December 1, 2024, from https://www.numbeo.com/cost-of-living/country_price_rankings?itemId=110

The Economist. (2024, September 21). The Big Mac index. The Economist. 
  Retrieved December 1, 2024, from https://www.economist.com/interactive/big-mac-index

Investopedia. (2024, November 12). Purchasing power parity (PPP). Investopedia. 
  Retrieved December 1, 2024, from https://www.investopedia.com/updates/purchasing-power-parity-ppp/

 Exchange Rates: What They Are, How They Work, and Why They Fluctuate. (2024). Investopedia. https://www.investopedia.com/terms/e/exchangerate.asp

