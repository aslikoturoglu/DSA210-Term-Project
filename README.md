# DSA210 Term Project: Correlation Between Obesity, Socioeconomic Status, and Coastal Regions Based on Regions of Turkey
## Project Overview and Motivation 
I have thought that over the years, due to many developments in biology, technology, agriculture and etc. human's body and health have been affected in bad way. Even though many research have been done, I have wondered if human beings are informed sufficiently. In my opinion, one of the problems which humans are facing is obesity. Additionaly, it seems to me that in different cities that I had visit, people's weight are changing due to their region and socioeconomic status.

My project is trying to find answers to
  - Does socioeconomic level of people have an impact on obesity? 
  - Does the distance to sea affecting people on socioeconomic levels?
  - Does the distance to sea affecting people on facing obesity?

## Hypothesis
  - **1. Null Hypothesis:** Socioeconomic status have no impact to people with not getting weight and become obese based on regions of Turkey.
  - **1. Alternative Hypothesis:** Socioeconomic status have positive impact to people with not getting weight and become obese based on regions of Turkey.
    
  - **2. Null Hypothesis:** Regions which are nearby the sea have no impact to people with not getting weight and become obese.
  - **2. Alternative Hypothesis:** Regions which are nearby the sea have positive impact to people with not getting weight and become obese.
    
  - **3. Null Hypothesis:** Regions that are located near the sea have no significant difference in their impact on people’s socioeconomic status compared to regions that are not near the sea.
  - **3. Alternative Hypothesis:** Regions that are located near the sea have a more positive impact on people’s socioeconomic status compared to regions that are not near the sea.
    
## Project Goal and Plan
I will create grades for socioeconomic levels based on regions, then I will make a correlation between socioeconomic level and obesity level. So that, I can see how are they correlated. Additionally, I will search the hypothesis that coastal regions' impact on obesity and socioeconomic statues with comparing the datas that I will be working on.

## Data Collection 
I will collect data from two different sources:
  1. **Obesity Percentages in Different Regions in Turkey:** From The Ministry of Health of Turkey
     - This sources gives the information of 12 different regions' obesity percentages who are the people older than 15 years old.
     - _https://hsgm.saglik.gov.tr/tr/obezite_
       
  2. **Socioeconomic Levels:** From The Ministry of Industry and Technology
     - This sources gives the information of all citys' townships' level of socioeconomic level in 6 levels.
     - I will give each city and region a score, because the data is for township.
     - _https://www.sanayi.gov.tr/assets/pdf/birimler/2022-ilce-sege.pdf_
       
  3. **Coastal Cities and Regions:** From the Wikipedia Turkey Map
     - This sources has a picture of Turkey map.
     - I have written "1" for cities with coast, and "0" with cities does not have coast.
     - _https://tr.m.wikipedia.org/wiki/Dosya:Turkey_map.svg_
     
## Data Analysis
1. **Data Collection**
1) _Socioeconomic Statues:_
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
       
  2) _Coastal Cities and Regions_
     - _City_Region_Socioeconomic_Level__
     - Importing the Excel records into a Pandas DataFrame and process the data.
     - I have written "1" for coastal cities, and "0" for non-coastal cities to column called "Sea" based on Turkey Map.
    
  3) _Obesity Level_
     - _Region_Obesity_Level__
     - Importing the Excel records into a Pandas DataFrame and process the data.
     - Data was ready to use, I only combined some parts to each other since there are only 7 regions in Turkey.

2. **Visualization**
   - Visiualizing the datas:
     - with:
       - matplotlib.pyplot
       - matplotlib.patches
       - seaborn
     - some examples: 
     - Obesity Rates by Regions in Turkey
       ![image](https://github.com/user-attachments/assets/32bd5bbb-0b74-4ace-aba0-8c5917deff3f)

     - Socioeconomic Levels of Cities in Turkey
       ![image](https://github.com/user-attachments/assets/fc43c85e-ddf1-4f7d-b200-5bd4b1933661)

     - Distribution of Coastal vs Non-Coastal Cities in Turkey
       ![image](https://github.com/user-attachments/assets/a6125668-bba4-4530-beee-0cad5ce02e52)

     - Socioeconomic Status by Regions in Turkey
       ![image](https://github.com/user-attachments/assets/292a1e89-b7b3-4466-883f-d57e63767c85)

     - Distribution of Coastal Cities in Turkey Based on Regions
       ![image](https://github.com/user-attachments/assets/d00bc130-9962-48cc-906c-9e8b6746da91)

     - Distribution of Coastal and Non-Coastal Cities in Turkey with Socioeconomic Statues
       ![image](https://github.com/user-attachments/assets/5eae69c6-3922-4122-85bf-1db55b0d47cf)

     - Coastal Cities in Each Region (For instance: Marmara Region)
       ![image](https://github.com/user-attachments/assets/71fa2ed5-8165-41ab-b4c2-474cf835e627)

     - Distribution of Coastal and Non-Coastal Regions in Turkey with Socioeconomic Statues
       ![image](https://github.com/user-attachments/assets/a9c29fee-e2db-4132-9340-c267201cea81)

     - Correlation Matrix: Socioeconomic Statues and Coastality based on Regions
       ![image](https://github.com/user-attachments/assets/1d0a2e1d-38c4-4c1a-853d-62c74d8d8144)
       
3. **Hypothesis Testing**
   - Test hypotheses:
       1) **Null Hypothesis:** Socioeconomic status have no impact to people with not getting weight and become obese based on regions of Turkey.
          **Alternative Hypothesis:** Socioeconomic status have positive impact to people with not getting weight and become obese based on regions of Turkey.
          
          - Obesity Level and Cities' Socioeconomic Levels with Classment of Regions' in Turkey
             ![image](https://github.com/user-attachments/assets/6aa0b5aa-7892-4542-9ff5-90192aa4f356)

          - Correlation Matrix: Socioeconomic Statues and Obesity based on Regions
             ![image](https://github.com/user-attachments/assets/6188f1bd-bed7-48b2-b8dc-4d7b81a66d47)

          As can be seen, there is **correlation** detected between socioeconomic statues and obesity levels. By the Pearson's Correlation method, the correlation they have is **0.66** which is a number quite trustworthy and there is a direct proposition .

          However we cannot decide is it a null or alternative hypothesis since we do not have the p value.

      2)  **Null Hypothesis:** Regions which are nearby the sea have no impact to people with not getting weight and become obese.
          **Alternative Hypothesis:** Regions which are nearby the sea have positive impact to people with not getting weight and become obese.
          
     - Obesity Level and Coastal Regions in Turkey
       ![image](https://github.com/user-attachments/assets/5ccba4e1-bec8-4c40-960f-1b96df418fe0)

     - Correlation Matrix: Coastal Cities and Obesity based on Regions
       ![image](https://github.com/user-attachments/assets/3ce66264-3d48-49c8-a407-6f0c84307d32)

     As can be seen, there is **correlation** detected between being nearby sea and obesity levels. By the Pearson's Correlation method, the correlation they have is **0.39** which is a number not very strong but it is **direct proposition **.
     Since 0.39 is very small, 

     Therefore it is a _alternative hypothesis_.

4. **Trend Analysis**
   - Identifying peaks and plateus
   - Analyze how region and socioeconomic status are related to obesity.

## Technologies and Tools
- **Python:** For statistical analysis
- **Pandas:** To process data
- **Machine Learning Model:** Linear Regression
