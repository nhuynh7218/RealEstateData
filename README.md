# Real Estate Market Analysis
The Real Estate Market has been skyrocketing the past year.
Using current sales data we can estimate the prices of current homes and see if there is an opportunity to invest.
![The-Ultimate-Guide-to-Real-Estate-Property-Analysis](https://user-images.githubusercontent.com/32362383/145609033-7a5824b4-8f65-48ef-8c6c-fc3af944f12f.jpeg)

Many real estate investors have been speculative of the recent growth in the real estate market, that makes many wonder if there will be an impending crash. At first I wanted to explore datasets and compare it to past datasets and use some statistics to see if the market was similar to when the housing market crashed in 2008, but the more I though about it, the more impossible the project seemed. It is hard to predict when something like this will crash because there are so many different factors that go into play. Since there has only been about 5 major market crashes in the US, it is hard to gather valuable data that can predict the future. We also don't have much data from before the housing crash in 2008, since the previous crash before was the great depression. I changed my project to then predict what current home prices are comparative to homes like it in its zipcode. By using current sales in the market, I clean the dataframe to include the data I need and want. I then had to remove any outliers so my model wouldnt be skewed and inaccurate. Then using machine learning with linear regression, I am able topredict the price of homes in the area. I focused on only brooklyn because thats where I lived and grew up and have a better understanding of the market.

The dataset I used is from tNew Yorks Department of Finance(https://www1.nyc.gov/site/finance/taxes/property-rolling-sales-data.page)
The Dataset orignally includes 21 columns, many of which I didn't need to do my analysis so i broke it down and just included the neccessary data I felt was useful such as the zipcode, number of units, square footage, and sales price.
<img width="817" alt="Screen Shot 2021-12-10 at 10 40 57 PM" src="https://user-images.githubusercontent.com/32362383/145662520-b377656f-1c1e-4ed3-9bf3-dc29af120e51.png">
From this dataset, I made a new column called "Price Per Square Foot" that takes the column "Sale Price" and divided it by "Gross Square Feet". We used "Gross Square Feet" instead of "Land Square Feet" because in the documentation of the dataset, it says "The total area of all the floors of a building as measured from the exterior surfaces of the outside walls of the building, including the land area and space within any building or structure on the property.
 meaning that it only counted the total livable space, which is used in real estate and not the land that isn't livable. I then plotted a histogram to see the distribution of homes price per square foot. I thought I would get a nice clean graph, but the data in the dataset had many outliers.
<img width="641" alt="Screen Shot 2021-12-10 at 11 17 31 PM" src="https://user-images.githubusercontent.com/32362383/145663500-aeddda11-7da5-4b2f-b80f-856d45c0a081.png">

These outliers were absurd, I noticed that there were many homes that had a sales price of 0, this is beacause there was a transfer of property without money present. This could be from someone inheriting a home, or from exchanging homes. So I had to remove all homes with a sale price of 0, but then there were still many homes that sold for ridiculously high prices. So I had a function that would take the mean PPSF{Price per square foot), and remove any homes that lie beyond 1 standard deviation from the mean. 

<img width="642" alt="Screen Shot 2021-12-10 at 11 24 57 PM" src="https://user-images.githubusercontent.com/32362383/145663636-90b403f7-ea87-493e-bd0d-5e14a984d7bf.png">

This gave me a better looking histogram but it was still skewed to the right, and I wanted a more normal distribution, so I removed any homes that exceeded $950 per Sqft.

"<img width="639" alt="Screen Shot 2021-12-10 at 11 15 13 PM" src="https://user-images.githubusercontent.com/32362383/145663675-f4cd3990-c83a-4d48-8c7f-9cd5cefd80d0.png">

a citations section with links to all data sources, code sources, publications used.

Given the current real estate market, this project evaluates a property against past and current data to see if there is an opportunity to invest.
-find price per square footage on house, how many bedrooms/bath and compare to other houses in the area with a similar composition.
-compare its historical price data against other compositions
