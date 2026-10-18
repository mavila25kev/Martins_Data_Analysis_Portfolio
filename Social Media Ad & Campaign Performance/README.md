
# Social Media Ad/Campaign Performance Analysis + Dashboard

The goal of this analysis is to review the effectiveness of Ad types and their associated campaigns based on the conversions generated from the user interactions and translate the findings into insights displayed through a Power Bi dashboard. Additionally, demographic, date/time and user preference data will be used as context for how each of these categories may be influencing the aforementioned goal of the analysis. The datasets used for this project are synthetic and created to emulate that of actual Ad management platform models used by companies like Meta. 

Key Points/Goals:
- Determine the percentage of customer interactions with ads which are being converted into a purchase
- Analyze the level of engagement per ad (clicks, likes,etc.)
- Recognize trends within customer ages, locations, browsing times, etc. and their specific engagement habits. 


## Context, Data & Tools

Advertising & Social Media go hand in hand as essential parts of every business model and understanding the way users interact with ads can greatly help companies determine how they can align strategic planning to match consumer habits. 

After an initial look at the the datasets used in this project, the data is housed in several Excel files; the *ad_events* table serves as the fact table and relates  to the *users* dimension table and *ads* dimension table. The *campaigns* dimension table then serves as a dimension table with a relationship to the *ads* table.

The column names and row counts of each table are as follows:
<table>
<tr>
  <td width = "30%">  
    
*AD_EVENTS* (400,000)
- event_id
- ad_id,
- user_id 
- timestamp
- day_of_week
- time_of_day
- event_type
  </td>
  <td width = "30%">
  
*USERS* (10,000)
- user_id
- user_gender
- user_age
- age_group
- country
- location
- interests
  </td>
  <td width = "30%">  

*ADS* (200)
- ad_id
- campaign_id
- ad_platform
- ad_type
- target_gender
- target_age_group
- target_interests
  </td>
  <td width = "30%">  
  
*CAMPAIGNS* (50)
- campaign_id
- name
- start_date
- end_date
- duration_days
- total_budget 
  </td>
  </tr>
</table>

Data Sources:
- [Kaggle](https://www.kaggle.com/datasets/alperenmyung/social-media-advertisement-performance) All data used can be found on this page. According to the source, the data is synthetic and was creating in Python to mirror data models used in working with platforms like Meta Ads Manager.


Tools Used:
- MYSQL
- POWER BI

## Methodology 

1. First I loaded our datasets via MySQL's Data import wizard creating four separate tables with the columns mentioned above after creating our scheme titled 'social_media_ads'. Some modifications were done during the import setup to correct data types for a full import to be successful. Primarily the columns with DATETIME variables had to be adjusted in order to load properly as well as some TEXT variables being set to INT values. Below are the four tables that will be used and their columns as loaded into MySQL, all rows were included as expected.
<br></br>

<img width="215" height="173" alt="Image" src="https://github.com/user-attachments/assets/46725869-040b-4a33-8a7a-497124499ab7" />

<br></br>

2. I then wanted to review that each table has no duplicates and ran the following queries below, using CTEs and the row_number function to view the count of distinct values per table. Only the users table had duplicate values associated with the user_id for 50 rows.
<br></br>

 <img width="1265" height="1084" alt="Image" src="https://github.com/user-attachments/assets/cbdd7bfe-5eac-476b-a33c-996ed87eb3d4" />
 
<br></br>

Since these 50 user_id values have 50 other user_id duplicate values which each then have some duplicate and non-duplicate values for the other columns in each row, the best course of action would be to use the CTE below for all future joins and queries on the user table to eliminate these 100 rows without altering the original table. I used two CTEs and joined them rather using a sub-query due to the table containing over 10k rows in order to speed up the query time and ran a quick row count check to confirm we no longer have the 100 user_ids.
<br></br>

<img width="511" height="467" alt="Image" src="https://github.com/user-attachments/assets/724cdd81-c6c4-4473-a183-247151e68f68" />

<br></br>

3. Next, I ran the following queries specifically on columns from each table which could be used for grouping/aggregation related insights in order to check on data quality issues like duplicate values, misspellings and formatting issues. There were none found as was expecting from the dataset as it was generated synthetically. Normally this would not always be the case as real world data often does include the aforementioned quality issues. In this case, the data could have been checked in Excel using something like the filter option rather than the various queries which would be tedious depending on the size of the dataset but I opted for reviewing each with a query in this case as the data was already imported and available.
<br></br>

<img width="310" height="875" alt="Image" src="https://github.com/user-attachments/assets/d4d06eac-1ab5-4d73-9dd5-938248301ddb" />

<br></br>

4. 


```sql

```


## Limitations and Liabilities



## Final Notes


## Files for Re-Creation

The files used for this project can be found under the folder titled 'Social Media Ad & Campaign Performance'
