# ETL Midterm Project

## 📌 Project Overview
This ETL project extracts raw and incremental sales data, applies transformations like cleaning, enrichment, structural changes, categorization and loads the final data into Parquet databases.
screenshots are added to allow visualization of the codes used and their respective outputs 

## 🧪 ETL Phases
### **Extract**:
-Loaded and inspected raw/incremental data, checked for missing values and duplicates.
- ![image](https://github.com/user-attachments/assets/88d29bd5-3817-4472-b6b5-ffc81aa97d1f)
- ![image](https://github.com/user-attachments/assets/99b7476a-de0e-4e17-92f2-b2cd03770ac1)
- this shows the loaded datasets given and their top values
- ![image](https://github.com/user-attachments/assets/0e1a2f23-a65b-43d7-94c1-43e3caa4fbde)
- ![image](https://github.com/user-attachments/assets/c05d7ac5-279f-4528-9d6d-c7b9665a4774)
- this shows the .info of the datasets hence we are able to see the columns of the datasets, the number of entries and their respective data types
- ![image](https://github.com/user-attachments/assets/9947435b-cb78-41c3-92b1-4289d68f68cf)
- we were also able to see that their were some missing values and duplicates in the datasets that we were able to handle in the transformation stage
  
### **Transform**: 
-Cleaned nulls, removed duplicates, added a `total_price` column and a `customer_type` column, and converted date fields.
- we started by handling the missing values
- ![image](https://github.com/user-attachments/assets/af035f94-5d5e-4416-8dc2-3f23eb1fbd4e)
- ![image](https://github.com/user-attachments/assets/2bf8fd9e-0e2f-4717-9412-2af78f89cf8c)
-  before we cleaned it we saw that it has several missing values in several columns in both the raw and incremented datasets
-  ![image](https://github.com/user-attachments/assets/7e612423-8038-4f68-a8dd-1d166c15664c)
-  ![image](https://github.com/user-attachments/assets/d41a4c0e-7564-46e0-ba65-c717010f51c7)
-  l decided to deal with the missing values in each column individually. l calculated the mean in the columns that had a numeric type and replaced the missing values in them with the mean. In the columns that were of an object type, l decided to replace the missing value with the value that is most occuring in the column(mode)
-  missing values need to be handled because they cause errors in trying to get detailed results from the datasets
-![image](https://github.com/user-attachments/assets/1c406795-cbc0-4f45-be15-163e1b1a686f)
- after we were able to see that no more missing values were present
- ![image](https://github.com/user-attachments/assets/d2282dd7-936a-4dc6-8037-c15d5e90741c)
- l saw that there was a duplicated recored in the raw dataset that l dropped so that it removes redundancy
- ![image](https://github.com/user-attachments/assets/cce76a00-8420-4a71-a8b0-0120243f5473)
- No duplicates were found in the incremented dataset
- ![image](https://github.com/user-attachments/assets/1e021ec4-4fbc-4015-abca-2df57dec43f7)
- ## Enrichment of the dataset
- ![image](https://github.com/user-attachments/assets/5ed0321f-af9f-4b9b-9f11-95ccbf6d7c1b)
- ![image](https://github.com/user-attachments/assets/5496d6d7-1f6d-4674-877a-7d1f7ed13ee9)
- we added another column in both of the datasets called `total_price` which is gotten by unit_price*quantity. This shows the total price each customer paid in their purchases
- ## Structural change
- ![image](https://github.com/user-attachments/assets/6fdca40b-9796-4cd8-95b3-06aeee2438b6)
- ![image](https://github.com/user-attachments/assets/63b1b246-7512-49af-98b0-0a6816655c56)
- l was able to see that the column called `order_date` in both the datasets were of type object which l was able to change into datetime format so that it can help in the date-time analysis
- ## Categorization
- ![image](https://github.com/user-attachments/assets/91028cb8-7b78-43cf-bc75-e405a8f67086)
- ![image](https://github.com/user-attachments/assets/59ba9818-4c35-4dd8-9651-4d1a6621dab3)
- l was able to add another column called `customer_type` which is used to classify customers based on how much they have spent. Customers who have spent >1000 are classified as VIP and those who have spent less are Regulars. This allows the shop to know who to give discounts in the future
  
 ### **Load**: Stored data into Parquet databases and previewed results.
- ![image](https://github.com/user-attachments/assets/0f64167c-32ec-4479-bb33-de52beaafe69)
- l was able to load the transformed data using parquet which is in the pandas library and saved it in the loaded folder
- ![image](https://github.com/user-attachments/assets/ab436ebd-26cc-4ff9-811b-14c9a7308311)
- this shows the preview of the already loaded datasets



## 🛠️ Tools Used
- Python
- Pandas
- Jupyter Notebook
- GitHub

## ▶️ How to Run
1. Clone the repo
2. Run each notebook in order: `etl_extract.ipynb` → `etl_transform.ipynb` → `etl_load.ipynb`
3. Check `transformed/` and `loaded/` for final outputs


