[Back to main guide](../README.md)
___

## Appendix B

### Step 1: Crawl and Catalog data in AWS Glue

a) From **Glue Console → Add tables using a Crawler**

<img alt="" src="images/b-1.png" width="70%" height="70%" >

b) Specify the **crawler name** as **patient-dedup-data-cr**

<img alt="" src="images/b-2.png" width="70%" height="70%" >

c) Select **Crawler source type** as **Data stores**

<img alt="" src="images/b-3.png" width="70%" height="70%" >

d) Choose **S3** as a data store and select the **transformresult** folder under **S3 bucket**

<img alt="" src="images/b-4.png" width="70%" height="70%" >

e) Choose **No** for **Add another data store**

<img alt="" src="images/b-5.png" width="70%" height="70%" >

f) **Choose Existing IAM Role** from the drop down – **AWSGlueServiceRole-LF-MLLab**

<img alt="" src="images/b-6.png" width="70%" height="70%" >

g) Select **Run on Demand**

<img alt="" src="images/b-7.png" width="70%" height="70%" >

h) Select **patientdb** as a **Database**

<img alt="" src="images/b-8.png" width="70%" height="70%" >

i) Review the information and click **Finish**

<img alt="" src="images/b-9.png" width="70%" height="70%" >

j) **Run** the crawler

<img alt="" src="images/b-10.png" width="70%" height="70%" >


### Step 2: Login as Data Lake Administrator and grant dlanalyst permission to the table

a) Login as data lake administrator – **dladmin**

b) Navigate to **Lake Formation Console → select Data Permissions → Grant**

c) Grant user **dlanalyst** permission on **transformresult** table

<img alt="" src="images/b-11.png" width="70%" height="70%" >


### Step 3: Modify Table Definition to remove quotes

a) Login as **dlanalyst**

b) Navigate to **AWS Glue Console → Databases → Tables** → Select the **transformresult** table and click on **Edit table details**

<img alt="" src="images/b-12.png" width="70%" height="70%" >

c) Change the **Serde Serialization lib** to **org.apache.hadoop.hive.serde2.OpenCSVSerde** and the **Serde Parameters** as shown below since the transformed result csv files contains the data values enclosed in double quotes **(“)**. You can set the Serde parameters as per your requirements based on the type of datasets you have. For our dataset, we will set below values

<img alt="" src="images/b-13.png" width="70%" height="70%" >

d) Click on the tablename **transformresult** and select **Edit schema**

<img alt="" src="images/b-14.png" width="70%" height="70%" >

e) Edit the Schema of the table by setting the data types of **all** columns to **“String”**. You can choose to retain the inferred data types by Glue Crawler as per your requirements as well. For this case, we will set all to String datatype for the sake of simplicity **except match_id column** datatype set as **“bigint”**.

<img alt="" src="images/b-15.png" width="70%" height="70%" >

f) Select **View data** option which will take you to **Amazon Athena** to query the data from a data lake

<img alt="" src="images/b-16.png" width="70%" height="70%" >



## Congratulations!! You have successfully completed the lab.

___

[Back to main guide](../README.md)
