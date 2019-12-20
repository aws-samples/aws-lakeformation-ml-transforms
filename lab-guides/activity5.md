[Back to main guide](../README.md) | [Next](activity6.md)
___

## 5. Crawl and catalog Patient data in AWS Glue
FindMatches ML Transform that we would be using, operates on tables defined in the AWS Glue Data Catalog. Use AWS Glue crawlers to discover and catalog the patient data.

a) Login as **dlanalyst**

b) Navigate to Lake Formation Console **→ Data Catalog → Tables → Create Table using a crawler**

<img alt="" src="images/5-1.png" width="70%" height="70%" >

Click on **Get Started** in case you are prompted.

<img alt="" src="images/5-2.png" width="70%" height="70%" >

c) Select **Add tables using a crawler**

d) Give Crawler name as **patient-raw-ds-cr** and click **Next**

<img alt="" src="images/5-3.png" width="70%" height="70%" >

  
e) Select Data stores on the next page

<img alt="" src="images/5-4.png" width="70%" height="70%" >

f) Select **S3** in **Choose Data Store** dropdown

g) Select **\<S3Bucket\>/patientdata/rawdata** as Include path

<img alt="" src="images/5-5.png" width="70%" height="70%" >

h) Click **Next**

<img alt="" src="images/5-6.png" width="70%" height="70%" >

i) Select **Choose an existing IAM role** and select **AWSGlueServiceRole-LF-MLLab**

<img alt="" src="images/5-7.png" width="70%" height="70%" >

j) Click **Next**

<img alt="" src="images/5-8.png" width="70%" height="70%" >

k) Select **Database** as **patientdb** and click **Next**

<img alt="" src="images/5-9.png" width="70%" height="70%" >

<img alt="" src="images/5-10.png" width="70%" height="70%" >

l) Click **Finish** button, select the crawler and click **Run Crawler**

<img alt="" src="images/5-11.png" width="70%" height="70%" >


Once the crawler is run successfully, it would create the table under AWS Glue Data Catalog Database. As a next step, Data Lake User would want to query the data in a data lake through data catalog tables. In order to do this, they would need permission from Lake Formation. In the next step, we login as a Data Lake Administrator and give ‘dlanalyst’ the permission to Select, Insert, Update, Delete data from a table in AWS Glue Data Catalog.

___

[Back to main guide](../README.md) | [Next](activity6.md)


