##  1. Business Understanding:

This small research project sets out to answer the following main questions: 
1. What are the top 5 and bottom 5 countries in terms of corruption? 
2. What are the top 5 and bottom 5 countries with regard to ease of doing business?
3. Is there a relationship between corruption and ease of doing business?
4. Are there outliers, i.e. countries that don't correspond to the overall relationship between corruption and doing business?

##  2. Data Understanding: 

To answer the above questions, two datasets are used:
1. 2019 dataset of the Corruption Percept Index available from:
https://images.transparencycdn.org/images/2019_CPI_FULLDATA.zip

2. Ease of Doing Business Index. 2019 data for all countries was been retrieved at the following web page:
https://www.doingbusiness.org/en/custom-query

## 3. Data Preparation:

Both datasets were saved as comma delimited text file (csv). 

For Ease of Doing Business Index dataset, I first preprocessed the data. It involved the following steps: retaining columns that contain score values (these variables have names starting with the string "Sco"), shortening the variable names, and dropping columns that contain NaNs. Next, set the index as the "Country" variable. I the cleaned the "Country" variable by keeping the first part of the names separated by a comma, and also removing city values, which contain string "-".

For Corruption Perception Index dataset, I retained only the country variable and 'CPI score 2019', which contains the index rating value. I dropped all other variables from the dataset, since they represent the indicators that go into the calculation of CPI index score, thus not relevant for my analysis.  

I merged the above datasets into "df_merged", using the default "inner" method. This retains only the countries that contain values for both indices in question. 

## 4. Modeling:

To answer question 1 and 2, I used bar plots to show top 5 and bottom 5 countries according to both the CPI and EDBI. 

To answer question 3, I used scatter plot with a linear regression fit. I also calculated the Pearson correlation coefficient.

To answer question 4, I divided the countries into three categories according to both CPI and EDBI rankings. To do this, I used percentiles based on the distribution of the ranks. Next, I identified countries that fall under the bottom 33% percentile of one index, and simultanously upper 33% of the other index. 

## 5. Evaluation:

The scope of my analysis didn't require evaluation of the results. As next steps, I recommend further research to identify factors that may result countries not following the general positive relationship between the two indices studied in this project. 



**Author
Umrbek Allakulov**
