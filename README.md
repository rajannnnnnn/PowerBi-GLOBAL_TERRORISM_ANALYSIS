# **Global Terrorism :** Terrorism Analysis for 1970-2010
## Introduction:
&nbsp;&nbsp;&nbsp;&nbsp;I found a really wonderfull dataset on Internet which got me into the workplace of PowerBi straight away. And here I am showcasing the overview of what i have done with it.
## Problem Statement:
&nbsp;&nbsp;&nbsp;&nbsp;Given the data, here are the problems to consider

* Split the data to optimize performance
* Transform it, to make it fit to analyse
* Define a Star Schema
* Create Report for these on your own custom:
  * Ransom paid, Hostages Kidnapped, Property Damaged over time
  * Understaning each Gang
## Data Sourcing:
&nbsp;&nbsp;&nbsp;&nbsp;The CSV file contained 113 columns and 181629 rows of single sheet (155mb). It contained every terrorisms happened between the year 1970 and 2010, giving informations about the
  
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
&nbsp;&nbsp;&nbsp;&nbsp;The data is first splitted into star schema to make it scalable, then further transformation took place including
* Making the **column multiples into single column** on gangs, weapons, attacktypes and also its sub-categories
* **Removing the columns** that is not necessary for analysis _eg. written notes, explaing the events_
* **Replacing** Numeric values with understandable replacements _eg. replacing -9,-99 with 'Unknown'_
* **Making Bridge tables** for colums with multiple entries _eg. multiple weapon types can be used in one event_
* **Appropriating Data Types** on columns of Date, Binary, Currency
* **Appending and Removing Duplicates** which happens on spliting the data
## Data Analysis Expression & Data Heirarchies:
* **Calculated Columns**:
  * _NoOf days to Execute_ which is the date difference between _Resolution Date(if available)_ and _Date of Event_
* **Measures**:
  * _Success Rate of Attack Type_: Percentage of Success of each type of Attack
* **Calculated Tables:**
  * _Gang Details_: Details of each gang includes their _NoOf Success, NoOf Failures, Success Rate %_
* **Data Hierarchies**:
  * Date Hierarchy: which is made automatic in nature for _Event Date, Resolution Date_
  * Gang Hierarchy: _Gang Name, Gang SubName_
  * Target Hierarchy: _Target, Target Subtype_
  * Weapon Hierarchy: _Weapon Type and Weapon Subtype_
  * Location Hierarchy: _country, region, prov_state, city_
## Data Modeling:
&nbsp;&nbsp;&nbsp;&nbsp;Since I prepared everything for Star Schema, I made relationship with fact table to all queries with _eventid_. Its finally 20 queries, and here how it looks like
![Screenshot (117)](https://github.com/user-attachments/assets/df54f5cb-c13b-4c03-ab36-bc86b37c72ec)
## Data Analysis and Visuals:
![image](https://github.com/user-attachments/assets/729bd046-5d76-48ec-9c8d-239c042adb69)
