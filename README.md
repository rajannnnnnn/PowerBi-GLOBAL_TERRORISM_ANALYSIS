# **Global Terrorism :** Terrorism Analysis for 1970-2017
## Introduction:
&nbsp;&nbsp;&nbsp;&nbsp;I found a really wonderfull dataset on Internet which got me into the workplace of PowerBi straight away. And here I am showcasing the overview of what i have done with it.
## Problem Statement:
&nbsp;&nbsp;&nbsp;&nbsp;Given the data, here are the problems to consider

* Split the data to optimize performance
* Transform it, to make it fit to analyse
* Define a Star Schema
* Create Report for these on your own custom:
  * Loss Over Time
  * Gang Summary
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
&nbsp;&nbsp;&nbsp;&nbsp;The data is first splitted for the sake of star schema and to make it scalable, then further transformation took place including
* Making the **column multiples into single column** on gangs, weapons, attacktypes and also its sub-categories
* **Removing the columns** that is not necessary for analysis _**eg**. written notes, explaing the events_
* **Replacing** Numeric values with understandable replacements _**eg**. replacing -9,-99 with 'Unknown'_
* **Making Bridge tables** for colums with multiple entries _**eg**. multiple weapon types can be used in one event_
* **Appropriating Data Types** on columns of Date, Binary, Currency
* **Appending and Removing Duplicates** which happens while spliting the data
## Data Analysis Expression & Data Heirarchies:
* **Calculated Columns**:
  * _'NoOf days to Execute'_ which is the date difference between _'Resolution Date'(if available)_ and _'Date of Event'_
* **Measures**:
  * _'Success Rate of Attack Type'_: Percentage of Success of each type of Attack
* **Calculated Tables:**
  * _"Gang Details"_: Details of each gang includes their _'NoOf Success', 'NoOf Failures', 'Success Rate %'_
* **Data Hierarchies**:
  * Date Hierarchy: which is made automatic in nature for _'Event Date', 'Resolution Date'_
  * Gang Hierarchy: _'Gang Name', 'Gang SubName'_
  * Target Hierarchy: _'Target', 'Target Subtype'_
  * Weapon Hierarchy: _'Weapon Type', 'Weapon Subtype'_
  * Location Hierarchy: _'country', 'region', 'prov_state', 'city'_
## Data Modeling:
&nbsp;&nbsp;&nbsp;&nbsp;Since I prepared everything for Star Schema, I made relationship with fact table to all other queries with _'eventid'_. Its finally 20 queries, and here how it looks like
![Screenshot (122)](https://github.com/user-attachments/assets/582f7024-d64d-493b-a286-4e3a45009d8c)

## Data Analysis and Visuals:
![Screenshot (122)](https://github.com/user-attachments/assets/53893094-8737-4e78-8151-15afcd69bbe2)

