# DSA210 Term Project: Correlation Between Obesity, Socioeconomic Status, and Coastal Regions Based on Regions of Turkey
## Project Overview and Motivation 
I am a student iin Sabancı University, Aslı Koturoğlu. I have thought that over the years, due to many developments in biology, technology, agriculture and etc. human's body and health have been affected in bad way. Even though many research have been done, I have wondered if human beings are informed sufficiently. In my opinion, one of the problems which humans are facing is obesity. Additionaly, it seems to me that in different cities that I had visit, people's weight are changing due to their region, availability to access to coasts and socioeconomic status.

My project is trying to find answers to
  - Does socioeconomic level of people have an impact on obesity? 
  - Does the distance to sea affecting people on socioeconomic levels?
  - Does the distance to sea affecting people on facing obesity?

## Hypothesis
  **1)** **Null Hypothesis:** Socioeconomic status have no impact to people with not getting weight and become obese based on regions of Turkey.

  **Alternative Hypothesis:** Socioeconomic status have positive impact to people with not getting weight and become obese based on regions of Turkey.
  
  -----------------------------------------------------------------------------------------------
  
  **2)** **Null Hypothesis:** Regions which are nearby the sea have no impact to people with not getting weight and become obese.
  
**Alternative Hypothesis:** Regions which are nearby the sea have positive impact to people with not getting weight and become obese.
   
  -----------------------------------------------------------------------------------------------
  
**3)** **Null Hypothesis:** Regions that are located near the sea have no significant difference in their impact on people’s socioeconomic status compared to regions that are not near the sea.

**Alternative Hypothesis:** Regions that are located near the sea have a more positive impact on people’s socioeconomic status compared to regions that are not near the sea.

## Data Collection 
I will collect data from three different sources:
  1. **Obesity Percentages in Different Regions in Turkey:** From The Ministry of Health of Turkey
     - _Region_Obesity_Level__
     - Importing the Excel records into a Pandas DataFrame and process the data.
     - This sources gives the information of 12 different regions' obesity percentages who are the people older than 15 years old.
     - Data was ready to use, I only combined some parts to each other since there are only 7 regions in Turkey.
     - _https://hsgm.saglik.gov.tr/tr/obezite_
       
       -----------------------------------------------------------------------------------------------
  2. **Socioeconomic status:** From The Ministry of Industry and Technology
     - _City_Region_Socioeconomic_Level__
     - Importing the Excel records into a Pandas DataFrame and process the data.
     - Importing 6 levels of socioeconomic levels for each city. Class 1 is presenting the highest socioeconomic level, and class 6 is presenting the lowest socioeconomic level.
     - To find the regions' socioeconomic level; first I have calculated cities' socioeconomic level , then I have combined and calculated the regions socioeconomic level with making the cities as groups.
     - The calculation of one specific city's socioeconomic level:
       - Score of Rates = 6xRate Class 1 + 5xRate Class 2 + 4xRate Class 3 + 3xRate Class 4 + 2xRate Class 5 + 1xRate Class 1
     - since I am calculating a score (not rate at this point), I needed to give the highest point to the highest socioeconomic level class
       
       - RATE = Score of Rates / 6
       - #since there are 6 classes
     - Later, I have calculated the regions' rate with adding the score of every city that the region contains, then divided the score to 6*number of cities.
     - Additionaly, I have added the data which contains the answer to the question "Is the city nearby the sea?".
     - With these steps, I have cleaned and organized my data.
  
     - Later, I have cleaned data with only taking the regions' socioeconomic rates: _TheR_Regions_Rate_Last_
     - _https://www.sanayi.gov.tr/assets/pdf/birimler/2022-ilce-sege.pdf_
       
        -----------------------------------------------------------------------------------------------
  3. **Coastal Cities and Regions:** From the Wikipedia Turkey Map
     - _City_Region_Socioeconomic_Level__
     - Importing the Excel records into a Pandas DataFrame and process the data.
     - This sources has a picture of Turkey map.
     - I have written "1" for cities with coast, and "0" with cities does not have coast.
     - _https://tr.m.wikipedia.org/wiki/Dosya:Turkey_map.svg_
     
## Data Analysis

  **Exploratory Data Analysis (EDA)**
  
  - Identifying peak obesity levels, regions with number of coasts, and socioeconomic levels based on cities and regions based on Turkey.

-----------------------------------------------------------------------------------------------
  **Correlation Analysis**
  
  - Measuring correlation between obesity and socioeconomic status.
  - Measuring correlation between obesity and coastal regions.
  - Measuring correlation between coastal regions and socioeconomic status.

-----------------------------------------------------------------------------------------------
    
 **Visualization**
   - Using line plots, bar charts, scatter plots, pie charts, correlation matrixes and histograms
   -  Visiualizing the datas with:
       - matplotlib.pyplot
       - matplotlib.patches
       - seaborn
  
## Findings
**Obesity Rates by Regions in Turkey**

The grapghs below showes the distribution of obesity based on seven regions in Turkey.
- x-axis shows the regions
- y-axis shows the obesity rate

As can be seen in the graph, Turkey's east sides are the least likely to be an obese, and middle side is the most likely to be an obese in Turkey.

  ![image](https://github.com/user-attachments/assets/32bd5bbb-0b74-4ace-aba0-8c5917deff3f)

  ![image](https://github.com/user-attachments/assets/aa1b611b-e48d-457a-83cc-b10c234d7056)


----------------------------------------------------------------------------------------------------------------
**Socioeconomic Levels in Turkey**

The bar chart below representing the distribution of the socioeconomic levels in 81 cities in Turkey. Cities are grouped based on regions.
- x-axis shows the cities
- y-axis shows the socioeconomic level rate

As can be seen in the graph, there is an decline of socioeconomic status.

 ![image](https://github.com/user-attachments/assets/fc43c85e-ddf1-4f7d-b200-5bd4b1933661)

Additionaly the frequency of the socioeconomic level is represented in below as histogram.

 ![image](https://github.com/user-attachments/assets/1d931092-c47c-4b93-9215-6ad2f9f7a34c)


Furthermore,the bar chart below is showing the distribution of socioeconomic levels in seven regions.
- x-axis shows the regions
- y-axis shows the socioeconomic level rate

As can be seen, the region with the best socioeconomic level is Marmara, then Aegean is coming; and the region with the least socioeconomic level is Southeastern Anatolia, then Eastern Anatolia is coming.

 ![image](https://github.com/user-attachments/assets/292a1e89-b7b3-4466-883f-d57e63767c85)

 ----------------------------------------------------------------------------------------------------------------
 **Coastal vs Non-Coastal Cities and Regions in Turkey**
 
 The bar chart shows the distribution of Coastal vs Non-Coastal Cities in Turkey
 - x-axis shows the cities
 - y-axis show is the cith is neaby the sea or not. If the city is near by the sea than te result is 1, if not result is 0.

 ![image](https://github.com/user-attachments/assets/a070f165-9c2d-4da1-99e1-d91e181c8301)


 Moreover, this pie chart shows the rate of cities with having a coast or not.

  ![image](https://github.com/user-attachments/assets/a6125668-bba4-4530-beee-0cad5ce02e52)

 Distribution of Coastal Cities in Turkey Based on _Regions_
  ![image](https://github.com/user-attachments/assets/d00bc130-9962-48cc-906c-9e8b6746da91)

 Total Sea Count based on Regions
  ![image](https://github.com/user-attachments/assets/702dc36d-555f-40e5-b816-a91fc9ef016c)

 
## Hypothesis Testing

   1) **Null Hypothesis:** Socioeconomic status have no impact to people with not getting weight and become obese based on regions of Turkey.
      
      **Alternative Hypothesis:** Socioeconomic status have positive impact to people with not getting weight and become obese based on regions of Turkey.
      
      - Obesity Level and Cities' Socioeconomic Levels with Classment of Regions' in Turkey
         ![image](https://github.com/user-attachments/assets/6aa0b5aa-7892-4542-9ff5-90192aa4f356)

      - Correlation Matrix: Socioeconomic status and Obesity based on Regions
         ![image](https://github.com/user-attachments/assets/6188f1bd-bed7-48b2-b8dc-4d7b81a66d47)

      - Mann-Whitney U: 1064.00
      - p-value: 0.0192

      As can be seen, there is **correlation** detected between socioeconomic status and obesity levels. By the Pearson's Correlation method, the correlation they have is **0.66** which is a number quite trustworthy and there is a direct proposition .

      However, we decide that is a null or alternative hypothesis with the p-value.
      Since p-value is 0.0192 smaller than 0.05, we **reject null hypothesis**.

      Therefore, _socioeconomic status have positive impact to people with not getting weight and become obese based on regions of Turkey._

  -----------------------------------------------------------------------------------------------

  2)  **Null Hypothesis:** Regions which are nearby the sea have no impact to people with not getting weight and become obese.
     
      **Alternative Hypothesis:** Regions which are nearby the sea have positive impact to people with not getting weight and become obese.
        
   - Obesity Level and Coastal Regions in Turkey
     ![image](https://github.com/user-attachments/assets/5ccba4e1-bec8-4c40-960f-1b96df418fe0)

   - Correlation Matrix: Coastal Cities and Obesity based on Regions
     ![image](https://github.com/user-attachments/assets/3ce66264-3d48-49c8-a407-6f0c84307d32)

   - Mann-Whitney U: 1011.00
   - p-value: 0.0069

   As can be seen, there is **correlation** detected between being nearby sea and obesity levels. By the Pearson's Correlation method, the correlation they have is **0.39** which is a number not very strong but it is direct proposition.

   However, we decide that is a null or alternative hypothesis with the p-value.
   Since p-value is 0.0069 smaller than 0.05, we **reject null hypothesis**.

   Therefore, _regions which are nearby the sea have positive impact to people with not getting weight and become obese._

   -----------------------------------------------------------------------------------------------
  
   3) **Null Hypothesis:** Regions that are located near the sea have no significant difference in their impact on people’s socioeconomic status compared to regions that are not near the sea.
      
      **Alternative Hypothesis:** Regions that are located near the sea have a more positive impact on people’s socioeconomic status compared to regions that are not near the sea.

   - Distribution of Coastal and Non-Coastal Regions in Turkey with Socioeconomic status
     ![image](https://github.com/user-attachments/assets/a9c29fee-e2db-4132-9340-c267201cea81)

   - Correlation Matrix: Socioeconomic status and Coastality based on Regions
     ![image](https://github.com/user-attachments/assets/1d0a2e1d-38c4-4c1a-853d-62c74d8d8144)

   - Mann-Whitney U: 1317.50
   - p-value: 0.0000

   As can be seen, there is **correlation** detected between being nearby sea and obesity levels. By the Pearson's Correlation method, the correlation they have is **0.58**, it is direct proposition.

   However, we decide that is a null or alternative hypothesis with the p-value.
   Since p-value is 0.0000 smaller than 0.05, we **reject null hypothesis**.

   Therefore, _Regions that are located near the sea have a more positive impact on people’s socioeconomic status compared to regions that are not near the sea.._

## Machine Learning Techniques
- Regression: Predicting Obesity Rates

- Objective: The goal of this analysis was to predict obesity rates based on socioeconomic status.

**Lineplot**

![image](https://github.com/user-attachments/assets/b0b69a62-bc85-4d3b-ad06-17783b98890c)

- x-axis: Regions
- y-axis: Obesity Rates

Yellow line stands for real rates, and the green line stands for predicted rates. As can be seen, it looks like it has a linear regression.

----------------------------------------------------------------------------------------------------------------------------------------------------

**Bar Chart**

![image](https://github.com/user-attachments/assets/2373b175-a137-4527-a579-95f9777243b8)

- x-axis: Regions
- y-axis: Obesity Rates

Yellow bars stands for real rates, and the green bars stands for predicted rates. As can be seen, the differences between prection and real rates are more clear.

We can claim that Aegean and Mediterranean have the closest prediction among the others, while Black Sea has the the widest prediction.

----------------------------------------------------------------------------------------------------------------------------------------------------

**Bar Chart About The Errors**

The aim is to find how did machine learning predicted. Every region had a prediction and a real rate. Therefore there are 3 levels of errors for seven regions:
- Low Difference: The difference between the prediction and the real rates is between 0% and 1% (including).
- Medium Difference: The difference between the prediction and the real rates is between 1% (not including) and 4% (including).
- High Difference: The difference between the prediction and the real rates is higher than 4%.

![image](https://github.com/user-attachments/assets/faf2881a-6c27-4c9e-a17f-ac8f663b12ca)

- x-axis: The error category
- y-axis: The count of categories which are occured.

As can be seen from the graph, there are **2 low difference, 4 medium difference,** and **1 high difference**. 

----------------------------------------------------------------------------------------------------------------------------------------------------

**Pie Chart About The Errors**

The aim is same with _bar chart about errors_, to check how close is the prediction. The same levels of errors are used which are:
- Low Difference: The difference between the prediction and the real rates is between 0% and 1% (including).
- Medium Difference: The difference between the prediction and the real rates is between 1% (not including) and 4% (including).
- High Difference: The difference between the prediction and the real rates is higher than 4%.

![image](https://github.com/user-attachments/assets/78a52dd9-7942-45c9-ad7d-21bb164d6bf7)

As can be seen from the graph, **57.1% has medium level of errors**. In the conclusion of this graph, more than the half of the predictions have error of 1% to 4%.

## Technologies and Tools
- **Python:** For statistical analysis
- **Pandas:** To process data
- **Machine Learning Model:** Linear Regression

## Limitations and Future Work
**Limitations**

  **- Limited data on obesity rates:** Obesity rate datasets was just for regions, therefore the correlations between obesity and socioeconomic levels or coastal cities may not be the right answer due to this problem.
  
  **- Lack of Variable Control:** Socioeconomic status and obesity rates are influenced by multiple factors such as education level, urbanization, and cultural habits. These variables were not specifically controlled for in this analysis.

-----------------------------------------------------------------------------------------------

**Future Work**

  **- Using More Detailed Data:** Future studies could incorporate data at the household level—such as income, education, and physical activity—to better analyze the causes of obesity.
  
  **- Application of Machine Learning:** With larger and more detailed datasets, machine learning techniques could uncover hidden patterns that are not visible through traditional analysis.
  
  **- Temporal Analysis:** Analyzing changes in socioeconomic structures and obesity rates over time could help understand long-term trends and impacts.
  
  **- Expanding Health Indicators:** Beyond obesity, this research could be enriched by including other health indicators such as diabetes prevalence or life expectancy.
  
  **- Collaborations with Field Experts:** Collaborating with local governments or healthcare institutions could enable the collection of primary data, leading to more accurate and impactful findings.
