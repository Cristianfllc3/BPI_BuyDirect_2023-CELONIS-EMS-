# BPI_BuyDirect_2023  
Analysis of the event data related to the customer suppport process of an online retailer called BuyDirect.  

References documentations  
*https://academy.celonis.com/*  
*https://docs.celonis.com/en/getting-started.html*  
*https://www.youtube.com/watch?v=dPCtRYpsO1I&t=114s*  


# The Data  
Read bpi_projet.pdf

# Tools  
Celonis, Prom and RapidMiner  
#### Conecting data in Celonis  
![image](https://github.com/Cristianfllc3/BPI_BuyDirect_2023/assets/72107370/2ddd0fb2-4caa-4fdb-9338-4c89bb445127)  

#### Update schema
![image](https://github.com/Cristianfllc3/BPI_BuyDirect_2023/assets/72107370/5021144d-e2c2-4b56-b899-b8659870a5e5)  

#### Import data (from csv files)
![image](https://github.com/Cristianfllc3/BPI_BuyDirect_2023/assets/72107370/d7c0b4f4-4380-4389-91e3-7908fc0b7d46)  

#### Data Jobs (ETL)  
If necessary, transformations can be created in the Data Jobs.  
*https://docs.celonis.com/en/data-jobs.html*

#### Data Model  
1 - Define the activity table and event attributes  
![image](https://github.com/Cristianfllc3/BPI_BuyDirect_2023/assets/72107370/00fe031b-6649-427a-b000-9f1d44eaaa19)

2 - Create a data model  
*https://docs.celonis.com/en/data-model-definition.html*
![image](https://github.com/Cristianfllc3/BPI_BuyDirect_2023/assets/72107370/1714c7ee-1049-4b61-b638-282a7e19ea61)

![image](https://github.com/Cristianfllc3/BPI_BuyDirect_2023/assets/72107370/5edfae02-745d-43d5-ba72-e29a3d434157)

3 - Loaded Data Model  
![image](https://github.com/Cristianfllc3/BPI_BuyDirect_2023/assets/72107370/ca4f5f3a-a378-4897-b8b0-bf5192ce0889)
Stats (click in details)
![image](https://github.com/Cristianfllc3/BPI_BuyDirect_2023/assets/72107370/0ebfa4b6-6892-4b15-bd8b-a68aa0f872b0)

5 - Create and execute a schedule  
![image](https://github.com/Cristianfllc3/BPI_BuyDirect_2023/assets/72107370/1f3e5525-ae58-4ed9-be3d-99bac0a24db2)
   
 *Execute*  
![image](https://github.com/Cristianfllc3/BPI_BuyDirect_2023/assets/72107370/fd618328-7ce6-48b7-a59e-cd3cedcea83e)

# Exploring the Event Data  
1 - Create a new Process Analysis (select the data model created in the previews steps)
![image](https://github.com/Cristianfllc3/BPI_BuyDirect_2023/assets/72107370/ffb59745-7ace-4dde-b007-46c0ab35cdfd)
..  
![image](https://github.com/Cristianfllc3/BPI_BuyDirect_2023/assets/72107370/f8b2f304-5566-416b-8237-b070f7045859)  

Add a new App  
![image](https://github.com/Cristianfllc3/BPI_BuyDirect_2023/assets/72107370/8ae3a616-3883-4fdb-9ac8-c92cf4ee8a38)

1a - Process Explorer component to create a Directly-Follows Graph (DFG) with activities as nodes. (If we move both sliders up (to 100% ) so that the
DFG shows all (seven) activities and arcs obtained from the data.)  
![image](https://github.com/Cristianfllc3/BPI_BuyDirect_2023/assets/72107370/4cb2adbe-c89a-4bfe-b093-e30461a08f86)






# Conformance Checking  

# Conformance Checking  

# Performance  

# Organizational Mining  
