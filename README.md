# **Global Terrorism :** Terrorism Analysis for 1970-2017
![1693140836538](https://github.com/user-attachments/assets/d9046d4d-c6cf-44e2-91e1-fdab0ae897a8)
## Introduction:
&nbsp;&nbsp;&nbsp;&nbsp;I found a really wonderfull dataset on Internet which got me into the workplace of PowerBi straight away. And here I am showcasing the overview of what i have done with it.
### Skills Demonstrated:
* **Transformation**: Splitting into queries, Cleaning
* **DAX**: Calculated Columns, Measures, Calculated Tables
* **Modeling**: SnowFlake Schema
* **Report Making**: Visuals, Slicers, Bookmarks
## Problem Statement:
&nbsp;&nbsp;&nbsp;&nbsp;Given the data, here are the problems to consider

* Split the data to optimize performance
* Transform it, to make it fit to analyse
* Define a SnowFlake Schema
* Create Report for these on your own custom:
  * Loss Over Time
  * Gang Summary
  * Attacks and Targets
## Data Sourcing:
**DataSet**: [_Global Terrorism_](https://www.kaggle.com/datasets/START-UMD/gtd)<br>
&nbsp;&nbsp;&nbsp;&nbsp;The CSV file contained 113 columns and 181629 rows of single sheet (155mb). It contained every terrorisms happened between the year 1970 and 2017, giving informations about the
  
  - pepetrators
  - gangs involved
  - targets
  - kills and wounds
  - kidnappings and releases
  - weapons
  - ransom demanded
  - locations
  - properties affected
  - internatinal supports
## Data Transformation/Cleaning:
&nbsp;&nbsp;&nbsp;&nbsp;The data is first splitted for the sake of snowflake schema and to make it scalable, then further transformation took place including
* Making the **column multiples into single column** on gangs, weapons, attacktypes and also its sub-categories
* **Removing the columns** that is not necessary for analysis _**eg**. written notes, explaing the events_
* **Replacing** Numeric values with understandable replacements _**eg**. replacing -9,-99 with 'Unknown'_
* **Making Bridge tables** for colums with multiple entries _**eg**. multiple weapon types can be used in one event_
* **Appropriating Data Types** on columns of Date, Binary, Currency
* **Appending and Removing Duplicates** which happens while spliting the data
## Data Analysis Expression & Data Heirarchies:
* **Calculated Columns**:
  * _'NoOf days to Execute'_ which is the date difference between _'Resolution Date'(if available)_ and _'Date of Event'_
  * _'Gang Label'_ to know the gang is recogniced or Unknown
  * _'NoOf SubGangs'_ each gang has
* **Measures**:
  * _'Success Rate of Attack Type'_: Percentage of Success of each type of Attack
  * _'International Support %'_: Percentage of International Support gained
* **Calculated Tables:**
  * _"Gang Summary"_: Details of each gang including their, success and failures, kills and wounds, kidnapping and ransom, etc
* **Data Hierarchies**:
  * Date Hierarchy: which is made automatic in nature for _'Event Date', 'Resolution Date'_
  * Gang Hierarchy: _'Gang Name', 'Gang SubName'_
  * Target Hierarchy: _'Target', 'Target Subtype'_
  * Weapon Hierarchy: _'Weapon Type', 'Weapon Subtype'_
  * Location Hierarchy: _'country', 'region', 'prov_state', 'city'_
## Data Modeling:
&nbsp;&nbsp;&nbsp;&nbsp;Since I prepared everything for SnowFlake Schema, I made relationship with fact table to all related queries with _'eventid'_. Its finally 21 queries, and here how it looks like
![Screenshot (125)](https://github.com/user-attachments/assets/9ef129b2-bf24-4364-b1df-c78664d43f55)
## Data Analysis and Visuals:
![Screenshot (122)](https://github.com/user-attachments/assets/53893094-8737-4e78-8151-15afcd69bbe2)
![Screenshot (124)](https://github.com/user-attachments/assets/21084f23-790f-4420-ac5a-25f6b6ce8972)
![image](https://github.com/user-attachments/assets/003ed667-500f-4813-bfd1-a45d97ca8fe8)
