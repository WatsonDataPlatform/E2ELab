#Hands on Lab - Data Engineer
[<img src="https://github.com/ibmdataworks/datafirst/raw/master/datascientist/media/DEE2E.png">](https://github.com/ibmdataworks/datafirst/tree/master/dataengineer)

As a Data Engineer, you are constantly challenged with the expediated task of delivering quality, trusted data to business users, data scientists and application developers. Time is always of the essence, so you need the ablity to quickly and easily find, access, combine, cleanse, standardize and prepare the data and then deliver it to those who need it when they need it in support of analytical and business application use cases. 

The IBM Bluemix Data Connect service, an intergral part of the Watson Data Platform, help solves these challenges.

Bluemix Data Connect is a fully managed, self-service, data preparation and integration service which enables you to easily put data to work. It provides instant access to your data wherever it resides, on the cloud or on-premises. You can blend data together from multiple relevant data sources to create powerful insights and then transform the data by refining and cleansing it, using a robust catalog of transformation operations and then deliver it with confidence to one of many supported cloud or on-premises targets.

Data Connect is fully managed by IBM in the cloud, so you can sleep better at night, with Pay-as-you-go and subscription pricing options to get started quickly. It’s powered by Spark for a speedy and responsive experience and can easily integrate data across different platforms and is seamlessly integrated with Watson Analytics. Bluemix Data Connect empowers non-technical and technical users to simply put data to work.

With Data Connect, Data Engineers can enable self-service data access to end users using elastic deployment through the cloud and delver the data faster while maintaining important controls such as data governance and security. This allows them to break free from routine data requests and focus on additional value for an organization such as implementing and enforcing corporate standards, security, data governance and complex requirements. Data Connect saves time and resources by reducing the effort to provision trusted data and make it fit for use.

This lab will demonstrate how a data engineer can utilize the following capabilities of the Data Connect service: 

* Creating and Working with the Bluemix Data Connect service
*	Creating and Working with Bluemix Data Connect Connections
*	Visualizing and Understanding Data Quality and Content
*	Transforming and Standardizing Data
*	Executing and Monitoring Data Activities
* Persiting data into the Watson Analytics repository

##Before You Begin

> This lab will be done exclusively from the web using Bluemix, IBM’s Platform-As-a-Service and Watson Analytics, IBM’s premiere analytical SaaS. It will also use an Excel file that you will you use as your source data. Perform the following steps before you proceed any further:

1. Download the Great Outdoor Customer Orders Excel file from the github.com location below and save the file to a location of your choice on your workstation:

 > https://github.com/WatsonDataPlatform/E2ELab/blob/master/dataengineer/Great%20Outdoor%20Customer%20Orders.xlsx

2. You will need a Bluemix account. If you don't have an account, click on the URL below to create one:

  > https://console.ng.bluemix.net/registration
  >
  > Fill in all information on the right side panel and then click on the *Create Account* button on the bottom of the right side panel

3. You will need a Watson Analytics account. If you don't have an account, click on the URL below to create one:

  > https://watson.analytics.ibmcloud.com/product
  >
  > Click on the “TRY IT FOR FREE” button. You have the option to click on “View pricing and buy” from the next screen. Watson Analytics provides 2 paid editions “Plus” and “Professional” with monthly license charges of $30 and $80, with included storage of 2GB and 100GB respectively. For now, you will go with the “Free” license and click on “Try free edition”.

##Workflow

> On the following pages are a series of steps required to complete this lab sucessfully. Each step outlines an easy to follow work flow to instruct and demonstrate the capabilities of the Data Connect service. It has been designed as a serial process and it’s important that you follow each step in sequence and do not deviate from the workflow or skip any steps in the process.

###Step 1: Prepare Your Bluemix Environment

Step | Description
------------ | -------------
1 | Login to Bluemix
2	| Create a Bluemix Space
3	| Create a Data Connect Service

###Step 2: Create Data Connect Connections

Step |	Description
------------ | -------------
 1	| Create a Watson Analytics Connection
 
###Step 3: Refine and Copy Results to Watson Analytics

Step |	Description
------------ | -------------
1	| Add the Source Data File
2	| Access the Source Data File
3	| Review Data Quality and Content
4	| Transform the Data
5	| Review History
8	| Complete the Activity
9	| Validate the Results

###Step 1. Prepare Your Bluemix Environment

1.  Log in to your IBM Bluemix account <https://console.ng.bluemix.net/login?state=/home/onboard/>

> NOTE: If you already have a Bluemix account then skip these steps:

1.  Go to [www.bluemix.net](https://www.bluemix.net)

2.  Click the signup button on the top right

 > <img src="https://github.com/ibmdataworks/datafirst/blob/master/appdeveloper/media/image2.png" width="624" height="171" />

3.  On the next page fill in the corresponding fields and click “Create Account”

 > <img src="https://github.com/ibmdataworks/datafirst/blob/master/appdeveloper/media/image3.png" width="624" height="300" />

4.  You will see a page asking you to check your email for next steps. Check your email that you used to sign up for Bluemix

 > <img src="https://github.com/ibmdataworks/datafirst/blob/master/appdeveloper/media/image4.png" width="237" height="219" />

5.  Click on the “confirm your account” link

 > <img src="https://github.com/ibmdataworks/datafirst/blob/master/appdeveloper/media/image5.png" width="396" height="330" />

Step 2. Initialize Source Data Repository: Object Storage Service
=========================================================

1.  From the Bluemix dashboard catalog menu search for “Object Storage”

2.  Click on the Object Storage Icon <img src="./media/image2.png" width="57" height="50" />

3.  Choose the default pre-filled values in the fields (optionally rename the “Service name:” to DE-DataIngest-ObjStorage), select the “Free Pricing Plan” and click “Create” at the bottom of the page.

4.  Click on “Actions-&gt;Add Container” and enter “datafirst" as the container name.

 > NOTE: Once a new container is created, you get this message "There are no files in the container you selected. Add files or view Object Storage documentation."

5.  Click on “Add files”.

6.  Select and add the files previously downloaded (GOProductDim, GOSalesFact) to this Container.

 > NOTE: Your data files are now moved to the Object Storage into the Bluemix.

7.  From the Object Storage Service menu (scroll up the browser page), click on “Service Credentials” option.

8.  Select the Key Name for your service (e.g. Credentials-1) and select the “View Credentials” down triangle (<img src="./media/image3.png" width="157" height="31" /> ) under the ACTIONS column.

 > It will show the credential details similar to the following:
 >
 > { <br />
 > "auth\_url": "https://identity.open.softlayer.com", <br />
 > "project": "object\_storage\_abcd12e3\_4f56\_7a89\_1bc2\_3de45fa67bcd", <br />
 > "projectId": "ab12c3456d7891ef2345a6789bc1d23e", <br />
 > "region": "dallas", <br />
 > "userId": "123a4567890123456b789012cde34f56", <br />
 > "username": "admin\_123a4567890123455a67ce456b789012cde34f56", <br />
 > "password": "ANUP&3NaZiR4PD&r=", <br />
 > "domainId": "cc421938a87348739a6bdc374424273d", <br />
 > "domainName": "1531219", <br />
 > "role": "admin" <br />
 > }

9.  Copy the credentials by clicking on the blue square (<img src="./media/image4.png" width="30" height="36" />) on the top right corner of the window and paste it into a notepad (Windows) / textedit (Mac) / vi (Linux). This information will be needed later for use in DataWorks Forge to create and establish the connection to the object store.

 > From the credential details above, only the values from the following tokens ( as highlighted in blue) will be needed in DataWorks Forge to establish connection to the Object Store: "auth\_url", "projectId", "region", "userId", "password"

10.  The source data repository to be used with DataWorks Forge later is now ready. Let’s create a target data repository.

11.  From the top of the browser page click on the “Catalog” option. This will take you back to the Bluemix dashboard catalog menu.

Step 3. Initialize Target Data Repository: dashDB Service
=================================================

1.  From the Bluemix dashboard catalog menu search for “dashdb”

2.  Click on the dashDB Icon <img src="./media/image5.png" width="41" height="40" />

3.  Choose the default pre-filled values in the fields (optionally rename the “Service name:” to DE-DataIngest-dashDB), select the “Entry Pricing Plan” (default) and click “Create” at the bottom of the page.

4.  From the dashDB Service menu (scroll up the browser page), click on “Service Credentials” option (you may have to click on the double arrow button on the “Back to Dashboard for…” option).

 > It will show the credential details similar to the following:
 >
 > { <br />
 > "credentials": { <br />
 > "port": 50000, <br />
 > "db": "BLUDB", <br />
 > "username": "dash999999", <br />
 > "ssljdbcurl": "jdbc:db2://awh-yp-small99.services.dal.bluemix.net:50001/BLUDB:sslConnection=true;", <br />
 > "host": "awh-yp-small99.services.dal.bluemix.net", <br />
 > "https\_url": "https://awh-yp-small99.services.dal.bluemix.net:8443", <br />
 > "dsn": "DATABASE=BLUDB;HOSTNAME=awh-yp-small99.services.dal.bluemix.net;PORT=50000;PROTOCOL=TCPIP;UID=dash999999;PWD=ANupNAirAjxy1;", <br />
 > "hostname": "awh-yp-small99.services.dal.bluemix.net", <br />
 > "jdbcurl": "jdbc:db2://awh-yp-small99.services.dal.bluemix.net:50000/BLUDB", <br />
 > "ssldsn": "DATABASE=BLUDB;HOSTNAME=awh-yp-small99.services.dal.bluemix.net;PORT=50001;PROTOCOL=TCPIP;UID=dash999999;PWD=ANupNAirAjxy1;Security=SSL;", <br />
 > "uri": "db2://dash999999:ANupNAirAjxy1@awh-yp-small99.services.dal.bluemix.net:50000/BLUDB", <br />
 > "password": "ANupNAirAjxy1" <br />
 > }

5.  Copy the credentials by clicking on the blue square (<img src="./media/image4.png" width="30" height="36" />) on the top right corner of the window and paste it into a notepad (Windows) / textedit (Mac) / vi (Linux). This information will be needed later for use in DataWorks Forge to create and establish the connection to dashDB.

 > From the credential details above, only the values from the following tokens ( as highlighted in blue) will be needed in DataWorks Forge to establish connection to dashDB: "host", "db", "username", "password"
 >
 > NOTE: You can also retrieve the connection information by Opening the dashDB console (Manage-&gt;Open from dashboard) and within the console clicking on “Connect-&gt; Connection information”. You get the information screen similar to the following:
 >
 > <img src="./media/image6.png" width="559" height="162" />

6.  The target data repository to be used with DataWorks Forge later is now ready. Let’s work with DataWorks Forge to transform and migrate data.

 > NOTE: Although we have created the database service, it is optional to port the source schema to this target database. More information about this in the next section.

7.  From the top of the browser page click on the “Catalog” option. This will take you back to the Bluemix dashboard catalog menu.

Step 4. Transform and Migrate Data: DataWorks Forge Service
===================================================

1.  From the Bluemix dashboard catalog menu search for “dataworks”

2.  Click on the DataWorks Icon <img src="./media/image7.png" width="47" height="52" />

3.  Choose the default pre-filled values in the fields (optionally rename the “Service name:” to DE-DataIngest-DataWorks), select the “Starter Pricing Plan” (default) and click “Create” button on the side panel.

 > NOTE: Once the service is provisioned it will invoke the DataWorks Forge Service dashboard where you can explore additional resources like IBM DataWorks™ APIs, Learning Center, Discussion forums etc.

4.  To launch the DataWorks Forge service just created, click the arrow icon (<img src="./media/image8.png" width="61" height="63" />) in the IBM DataWorks™ section on the provisioning dashboard. This brings you to the DataWorks Forge dashboard which looks like this:

 > <img src="./media/image9.png"/>

DataWorks Forge Service Introduction
------------------------------------

 > <img src="./media/DE Image9.png"/>
 >
 > NOTE: The Bluemix Secure gateway can be used to retrieve data hosted in a secure enterprise environment through a secure network tunnel. Configuring a Secure Gateway service and connecting using a secure tunnel is a simple and intuitive process (the dashboard walks you through the steps). As it was indicated earlier, getting access to a data hosted in an enterprise infrastructure can be a compliance and privacy issue for this lab, we will be using a sample datasets hosted in the IBM Object Storage that would be used as a source data set. This doesn’t need the use of a secure gateway.
 >
 > The flow diagram for creating a data migration process in DataWorks Forge is as shown below: 

#Step 5. Create Data Connections

### Create Source Data Connection

1.  From the DataWorks Forge dashboard click on “Tasks”-&gt;““Create Connection”

 > This will take you to the list of all available connection drivers.

2.  Select the “Bluemix Object Storage” icon (<img src="./media/image11.png" width="82" height="77" />)

3.  Enter the following information in the data entry dashboard

 > Connection Name: SourceDB
 >
 > Description: Data Stored in Bluemix Object Storage

4.  Retrieve the values for the parameters "auth\_url", "projectId", "region", "userId", "password" from the Bluemix Object Storage service that was created earlier (section titled “Initialize Source Data Repository: Object Storage Service” step 8) and enter it in the dashboard.

 > You entry would look similar to the following:
 >
 > Auth URL: https://identity.open.softlayer.com
 >
 > Project ID: ab12c3456d7891ef2345a6789bc1d23e
 >
 > Region: dallas
 >
 > User ID: 123a4567890123456b789012cde34f56
 >
 > Password: ANUP&3NaZiR4PD&r

5.  Click on the “CREATE CONNECTION”

6.  You will be seeing the **SourceDB** icon in the Connections dashboard.

 > <img src="./media/image12.png" width="105" height="72" />

### Create Target Data Connection

1.  From the DataWorks Forge dashboard click on “Tasks”-&gt;“Create Connection”

 > This will take you to the list of all available connection drivers.

2.  Select the “IBM dashDB” icon (<img src="./media/image13.png" width="86" height="84" />)

3.  Enter the following information in the data entry dashboard

 > Connection Name: TargetDB
 >
 > Description: Data Stored in IBM dashDB

4.  Retrieve the values for the parameters "host", "db", "username", "password" from the dashDB service that was created earlier (section titled “Initialize Target Data Repository: dashDB Service” step 4) and enter it in the dashboard.

 > You entry would look similar to the following:
 >
 > Hostname or IP Address: awh-yp-small99.services.dal.bluemix.net
 >
 > Database: BLUDB
 >
 > Username: dash999999
 >
 > Password: ANupNAirAjxy1

5.  Click on the “CREATE CONNECTION”

6.  You will be seeing the **TargetDB** icon in the Connections dashboard.

> <img src="./media/image14.png" width="121" height="96" />

Create Data Flow (Activity)
---------------------------

1.  From the DataWorks Forge dashboard click on “Tasks”-&gt;“Refine and Copy”

2.  Click and select the source database: SourceDB

3.  Click and select the Container: datafirst

4.  Click and select the files (checkbox) from the container: GOProductDim, GOSalesFact

 > At this point you have the options of either **copying/migrating the selected data files as-is** to the target OR **refine the data** from the selected files and then copy/migrate it.

### Copy data as-is

5.  Edit the activity name by clicking the pencil icon (<img src="./media/image15.png" width="33" height="36" />) on top of the dashboard. Name the activity “LoadDataAsIs”. Click <img src="./media/image16.png" width="34" height="34" /> when done with editing.

6.  Click on “COPY TO TARGET”

7.  Click and select the target database: TargetDB

8.  Select the database schema to which the data needs to be copied to.

 > NOTE: Since we are using an entry plan dashDB for this lab exercise the schema name would look similar to the dashDB userid (e.g., DASH99999)

9.  In the “Table Action” column you are prompted with 4 options “Append to the table”, “Recreate the table”, “Replace the table contents” and “Merge with the table”. Since this is the first time we are copying data, select “Recreate the table”

 > NOTE: If the table does not exist, it will be created and data will be appended.

10.  Now you can either “SCHEDULE” this activity for a later run or “RUN” this activity immediately. Click on “RUN” to execute it immediately

11.  The activity is executed immediately. An icon is added to the activity list dashboard. We will revisit this icon in the later section.

> <img src="./media/image17.png" width="193" height="71" />
>
> **IMPORTANT**: You would have noticed that while creating the target database we never ported the schema. This is because, if the schema doesn’t exist in the target database, it is created automatically from the source data type. This feature enhances and expedites the overall project productivity.

### Refine data (OPTIONAL)

> NOTE: Skip to next section titled “**Validate Data Flow Run Activity** “ if you don’t want to refine the data before copying else continue.

1.  Repeat steps 1 to 4. **Come back to this step once complete**.

2.  Edit the activity name by clicking the pencil icon (<img src="./media/image15.png" width="33" height="36" />) on top of the dashboard. Name the activity “RefineAndLoadData”. Click <img src="./media/image16.png" width="34" height="34" /> when done with editing.

3.  Click on “REFINE DATA”

4.  This brings you to the refine dashboard where you can do various operations on the selected table.

 > For the tables, it provides you a histogram and statistics of the data quality for each of the table columns. You can cleanse the data (standardize values, remove rows/columns, change value, filter and sort rows etc.)
 >
 > You are at liberty to explore and act on these options. Once complete click on “NEXT”

5.  Continue steps 7 to 10. **Come back to this step once complete**.

6.  The activity is executed immediately and an icon is added to the activity list dashboard.

 > <img src="./media/image18.png" width="235" height="87" />

Validate Data Flow Run Activity
-------------------------------

1.  From the DataWorks Forge dashboard click on “Browse”-&gt;“Activities”

2.  Click on the three dots (<img src="./media/image19.png" width="17" height="37" />) on the right-top corner for the activity titled “LoadDataAsIs”. This will pop up additional sub-activity icons

 > <img src="./media/image20.png" width="267" height="157" />
 > 
 > You can Run (<img src="./media/image21.png" width="43" height="42" />), Schedule (<img src="./media/image22.png" width="45" height="45" />), delete (<img src="./media/image23.png" width="42" height="42" />) the activity OR find more details (<img src="./media/image24.png" width="41" height="42" />) about the run.

3.  Let find out about the detailed status of the run. Either click on the activity name icon “LoadDataAsIs“ or click on the expanded details (<img src="./media/image24.png" width="41" height="42" />) icon.

 > <img src="./media/image25.png" width="559" height="349" /><img src="./media/image26.png" width="559" height="379" />
 >
 > It will show you an information screen (similar to the figure above). Here, check if the activity details match with the information it was created with and whether the activity was run successfully. You can also rerun or schedule a run of the activity without having to recreate it again. You can see the detailed **runlog** of the activity by clicking on the named “Activity Runs” (circled in the earlier figure).

Validate Migrated Data
----------------------

1.  Go to the main Bluemix portal and click on DASHBOARD (Top of the browser)

 > NOTE: You may already have a browser tab open from where you invoked the DataWorks Forge service (<img src="./media/image27.png" width="278" height="42" />). Go to that tab and click on <img src="./media/image28.png" width="121" height="28" />. This will take you back to the provisioned services dashboard.

2.  Under the Services section on this browser page click on the dashDB service that was created in section titled “Initialize Target Data Repository: dashDB Service “.

3.  This will open up the dashDB launch board. Click on the “OPEN” button. This will launch the dashDB dashboard.

4.  To verify the data you have 2 Options

> **Option 1**

1.  Click on “Run SQL” and execute the “SELECT COUNT(\*) FROM *&lt;SchemaName.TableName&gt;”* SQL commands against the GOProductDim and GOSalesFact table name. The resultant row counts should be 274 and 10000 rows respectively.

2.  You can also run other SELECT commands to check if the resultant data is valid especially if you have refined the incoming data.

> NOTE: For this lab the *SchemaName would be the* username as indicated in section titled Initialize Target Data Repository: dashDB Service step 4.
>
> **Option 2**

1.  Click on “Tables”

2.  Select the Schema

3.  For each table GOProductDim and GOSalesFact verify the schema and also browse the data.

Delete All Provisioned Services (Optional)
------------------------------------------

1.  Go to the main Bluemix portal and click on DASHBOARD (Top of the browser)

 > NOTE: You may already have a browser tab open from where you invoked the dashDB service (<img src="./media/image27.png" width="278" height="42" />). Go to that tab and click on <img src="./media/image28.png" width="121" height="28" />. This will take you back to the provisioned services dashboard.

2.  Under the Services section you will see the three services you had created (Object Storage, DataWorks Forge and dashDB)

3.  To delete the service click on the three dots (<img src="./media/image19.png" width="17" height="37" />) under the actions column and click “Delete Service”. This will pop up a confirmation dialog box that says:

 > *Deleting the service will remove it from all apps that are using it. In addition, all of its data will be permanently deleted. Are you sure you want to delete the &lt;service name&gt; service?*

4.  Click “Delete” to remove the service.

5.  Repeat steps 3 and 4 above until all services are deleted.

***End of Lab***

