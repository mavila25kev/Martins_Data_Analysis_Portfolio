
# Social Media Ad/Campaign Performance Analysis + Dashboard

The goal of this analysis is to review the effectiveness of Ad types and their associated campaigns based on the conversions generated from the user interactions and translate the findings into insights displayed through a Power Bi dashboard. Additionally, demographic, date/time and user preference data will be used as context for how each of these categories may be influencing the aforementioned goal of the analysis. The datasets used for this project are synthetic and created to emulate that of actual Ad management platform models used by companies like Meta. 


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
- EXCEL
- POWER BI

## Methodology 

1. First I loaded our datasets via MySQL's Data import wizard creating four separate tables with the columns mentioned above after creating our scheme titled 'social_media_ads'. Some modifications were done during the import setup to correct data types for a full import to be successful. Primarily the columns with DATETIME variables had to be adjusted in order to load properly as well as some TEXT variables being set to INT values. Below are the four tables that will be used and their columns as loaded into MySQL, all rows were included as expected.




2. 

```sql

```

## Limitations and Liabilities



## Final Notes


## Files for Re-Creation

The files used for this project can be found under the folder titled 'Social Media Ad & Campaign Performance'
