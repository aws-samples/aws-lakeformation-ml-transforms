[Back to main guide](../README.md)|[Next](sct.md)
___

## 7. Observe the data pattern and duplicates in data

You can now query data in Data Lake using Amazon Athena. Perform the below steps:

a) Login as **dlanalyst** if not already

b) Navigate to **Lake Formation Console → Data Catalog → Tables**

c) Select the **rawdata** table → **Actions → View data**

d) In the **Athena console** → select database as **patientdb → tables rawdata → options Preview**

e) You can download the csv by removing the **limit** clause in the select statement and clicking on the **Download the results** icon in the Results section


NOTE:
After landing on Athena console, if you get an error or query doesn’t run, click on the **Set up a query result location in Amazon S3** link and enter the value as **s3://\<\<S3BucketName\>\>/query/**

___

[Back to main guide](../README.md)|[Next](sct.md)
