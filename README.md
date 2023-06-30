# BPI_BuyDirect_2023  
Analysis of the event data related to the customer suppport process of an online retailer called BuyDirect.  

References documentations  
*https://academy.celonis.com/*  
*https://docs.celonis.com/en/getting-started.html*  
*https://www.youtube.com/watch?v=dPCtRYpsO1I&t=114s*  


# 1 - The Data  
Read bpi_projet.pdf

# 1.2 - Tools  / Methods
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

# 2 - Exploring the Event Data  
1 - Create a new Process Analysis (select the data model created in the previews steps)
![image](https://github.com/Cristianfllc3/BPI_BuyDirect_2023/assets/72107370/ffb59745-7ace-4dde-b007-46c0ab35cdfd)
..  
![image](https://github.com/Cristianfllc3/BPI_BuyDirect_2023/assets/72107370/f8b2f304-5566-416b-8237-b070f7045859)  

Add a new App  
  
![image](https://github.com/Cristianfllc3/BPI_BuyDirect_2023/assets/72107370/8ae3a616-3883-4fdb-9ac8-c92cf4ee8a38)

1a - Process Explorer component to create a Directly-Follows Graph (DFG) with activities as nodes. (If we move both sliders up (to 100% ) so that the
DFG shows all (seven) activities and arcs obtained from the data.)  
  
![image](https://github.com/Cristianfllc3/BPI_BuyDirect_2023/assets/72107370/4cb2adbe-c89a-4bfe-b093-e30461a08f86)

## Exploring the Event Data: Graphics 📊  

   ### 1. Subscriptions distribution  
   *( Using a Pie Chart component, visualize the distribution of the values for the case attribute Subscription )*     
![image](https://github.com/Cristianfllc3/BPI_BuyDirect_2023/assets/72107370/aa6462d6-cebd-4ea4-bdce-076c862641eb)
    
   ### 2. Component distribution  
   *(Using a Pie Chart component, visualize the distribution of the values for the case attribute Component)*
![image](https://github.com/Cristianfllc3/BPI_BuyDirect_2023/assets/72107370/353992a2-6032-4ad0-9626-627124727bbd)  
      
   ### 3. Subscription-Component distribution  
   *(Using a Pie Chart component, visualize the distribution of the combined values for the case attributes Subscription and Component together.)*     
   **Option 1** - (With two dimensions in the visual)  
   **Option 2** - CONCAT("case-table"."SUBSCRIPTION", '- ', "case-table"."COMPONENT")  
   **Note**: Keep in mind to configure the maximum number of elements shown in the general graph options, by default it only shows 4.*  

![image](https://github.com/Cristianfllc3/BPI_BuyDirect_2023/assets/72107370/354dd5af-15cd-4e48-8cf7-a9e3744c623c)

   ### 4. Total number of activities by resources  
   *(Using a Column Chart component, show for each resource (x-axis), the total number of activities handled by that resource in the process (y-axis).)*  
   **Note**: Sorted descendently by the number of activities*  
     
   ![image](https://github.com/Cristianfllc3/BPI_BuyDirect_2023/assets/72107370/eac9ebb5-af3a-48b3-a2f8-885bf8965b0d)

   ### 5. Distribution of ITSupport - resources  
   *(Using a Pie Chart component, visualize the distribution of the ITSupport responsibility over the resources throughout the different weeks. I.e., each
pie portion shows the fraction of the weeks for which a particular resource takes over the IT-Support responsibility. Provide the PQL code lines required for the dimension(s) and KPI(s) of the component..)*  
   **PQL dimensions**:"activity-table"."RESOURCE"  
   **PQL KPI**:"COUNT("activity-table"."RESOURCE")"  
   
   *In the OLAP table graph, the PQL codes were used:*  
   
   **PQL dimensions**:"ROUND_WEEK("activity-table"."TIMESTAMP")" **AND** "activity-table"."RESOURCE"   
   **PQL KPI**:"COUNT("activity-table"."RESOURCE")" **AND**  PU_COUNT(DOMAIN_TABLE(ROUND_WEEK("activity-table"."TIMESTAMP")), "activity-table"."ACTIVITY")    
     
   ![image](https://github.com/Cristianfllc3/BPI_BuyDirect_2023/assets/72107370/057cc6a1-3cef-4eed-bde3-d03a30674781)

   **Note:** Each fraction, ratio can be viewed on the pie chart by applying a filter by week.  

   
   ### 6. Executions of activity "Register" by Resources  
   *(Using a Pie Chart component, visualize how the executions of activity "Register" are split among the corresponding resources.)*  
   **Note**: *KPI PQL: SUM(CASE WHEN "activity-table"."ACTIVITY" = 'Register' THEN 1 ELSE 0 END)*  
   **Visual Editor**  
   *KPI PQL: SUM(CASE WHEN "activity-table"."ACTIVITY" = 'Register' THEN 1 ELSE 0 END)*  
   ![image](https://github.com/Cristianfllc3/BPI_BuyDirect_2023/assets/72107370/bbba28f4-cd72-4eff-bbff-6724518bcd60)  

   ![image](https://github.com/Cristianfllc3/BPI_BuyDirect_2023/assets/72107370/1a872331-6695-4116-a143-3830ca029f35)

   ### 7. Component distribution  
   *(Using a Pie Chart component, visualize how the executions of activity "Register" are split among the corresponding resources .)*  
   **Note**: *  
   ![image](https://github.com/Cristianfllc3/BPI_BuyDirect_2023-CELONIS-EMS-/assets/72107370/cbb029e2-2ec6-4f65-8156-5a19a1ed047c)

   ![image](https://github.com/Cristianfllc3/BPI_BuyDirect_2023-CELONIS-EMS-/assets/72107370/8ec7a83e-059b-48f6-92e9-6ad4a9145e6f)

   


   ### 8. Component distribution  
   *( .)*  
   **Note**: *  

   
   ### 9. Component distribution  
   *( .)*  
   **Note**: *  

   ### 10. Component distribution  
   *( .)*  
   **Note**: *  

   ### 11. Component distribution  
   *( .)*  
   **Note**: *  
 


# 3 - Conformance Checking  

# 4 - Decision Mining

# 5 - Performance  

# 6 - Organizational Mining  
