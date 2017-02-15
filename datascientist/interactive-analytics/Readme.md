#Data Scientist 
#Part 1 - Root Cause Analysis..
[<img src="https://github.com/WatsonDataPlatform/E2ELab/raw/master/datascientist/media/DSE2E1.png">](https://github.com/WatsonDataPlatform/E2ELab/raw/master/datascientist/interactive-analytics/)

This lab exercise uses an IPython Notebook in Data Science Experience to connect with dashDB, explores sales, product data and analyze sales performance for a specific product line. Pixiedust, a Python based visualization package is used to visualize the results.

![overview](https://github.com/WatsonDataPlatform/E2ELab/raw/master/datascientist/interactive-analytics/media/overview.gif.gif)

Lab Video: https://youtu.be/sHm4IHHZq2w
 > [<img src="https://github.com/WatsonDataPlatform/E2ELab/raw/master/datascientist/media/DS Video.png" width="382">](https://youtu.be/sHm4IHHZq2w "Data Science")

#Step 1. Provision dashDB

1.	Login to IBM Bluemix

  a.	For existing accounts use  https://new-console.ng.bluemix.net/login

  b.	Sign-up for a free trial account at https://console.ng.bluemix.net/registration/

2.	Provision dashDB

  a.	From the Bluemix catalog menu search for “dashdb”

  b.	Click on the "dashDB for Analytics" Icon

  c.	Accept the default values and rename “Service name:” to ‘DS_Sales_DataStore’

  d.	Select “Entry Pricing Plan” (default) and click “Create” on the right hand panel.

The dashDB service is provisioned along with sample database and lab exercise will use the sample database.

---
#Step 2. Create a project and a connection to DashDB

1.	Login to IBM Data Science Experience @ http://datascience.ibm.com/

2.	Create a new project

        You may have to come back to creating a project a few times if you need to 
        create a Spark service and an ObjectStore repository.

  a.	Click on the "+" sign in the upper right of the screen and select "Create project”

    ![start project](https://github.com/WatsonDataPlatform/E2ELab/raw/master/datascientist/interactive-analytics/media/dsxCreateProject.png)

  b.	If, under "Spark Service", you see "No Spark instances found.", click on:
	"Create a new IBM Analytics for Apache Spark instance"
	- Give the service named "IA_Lab_Spark" and click on "Create Instance".
	- Click on the "CXD" logo in the upper left of your screen to go back
	  to creating a new project
           
  c.	If, under "Storage Type" you see: "No object storage instances found",
	click on: "Create a new instance"
	- Select the free plan and click on "Buy IBM Object Storage",
	  then give it a name such as "IA_Lab_ObjectStorage"
	- Click on Add a container names "IA_project"
	- Click on the "CXD" logo in the upper left of your screen to go back
	  to creating a new project

  d.	Use the project name "IA_project", give any description you want and click "Create"

---
#Step 3. Load Notebook and Perform Analysis

1. Click on "add notebooks"

<img src="https://github.com/WatsonDataPlatform/E2ELab/raw/master/datascientist/interactive-analytics/media/createnew.png" width="750"> 
 
2. Type ‘IA_Lab_Notebook’ as Notebook name, click on ‘from URL’ link and specify:  https://raw.githubusercontent.com/WatsonDataPlatform/E2ELab/master/datascientist/interactive-analytics/DSX_IA_Lab.ipynb

 ![start notebook](https://github.com/WatsonDataPlatform/E2ELab/raw/master/datascientist/interactive-analytics/media/createNotebook.png)

  a.	 Click on ‘Create Notebook’
  
1. Once the notebook is created, add dashDB as a data asset for the project

  a.	Click on the '1001' icon (upper right corner), then Connections -> project page

	Note that it opens a new tab that you'll close when done.
  

  b.	Select the "connections" -> "create connection", then key in ‘dashDB’ as connection name

  c.	From drop down list of ‘Target Service Instance’ select ‘DS_Sales_DataStore’, the dashDb service you provisioned in Bluemix.

  d.	Select ‘Database’ as ‘BLUDB’.

  e.	Click ‘Create’.

  f.	Close this tab to return to your notebook


1.	Back to the notebook with the connections tab open


1.	From the Notebook, connect to the sample sales database in dashDB

  a.	Place the cursor in the first cell. This should be empty, if not clear the contents.

  b.	Click on ‘Insert Code’  to insert credentials for the data source ‘dashDB’

    ![insert to code](https://github.com/WatsonDataPlatform/E2ELab/raw/master/datascientist/interactive-analytics/media/addSource.png)

  c.	Rename the inserted array variable ‘credentials_1’  to ‘credentials’

    ![credentials](https://github.com/WatsonDataPlatform/E2ELab/raw/master/datascientist/interactive-analytics/media/credentials.gif)

  d.	To execute code in any notebook cell, place cursor in cell and click the arrow icon in toolbar

  ![execute in notebook](https://github.com/WatsonDataPlatform/E2ELab/raw/master/datascientist/interactive-analytics/media/notebookNav.gif)

  e.	Place cursor in cell1, execute code to capture dashDB database credentials

  f.	Place cursor in cell2, execute code to connect, load tables from dashDB
3.	Query, join and group data using SparkSQL Data frame API to build aggregated sales for the product line ‘Outdoor Protection’.

  a.	Place cursor in cell3 and execute code to build aggregated sales data frame

  b.	Place cursor in cell4 and execute code to install or update Pixiedust package

  c.	Place cursor in cell5 and execute code to  visualize SparkSQL Data frame

  ![execute in notebook](https://github.com/WatsonDataPlatform/E2ELab/raw/master/datascientist/interactive-analytics/media/finalViz.gif)

7.	You can move the mouse over the visual to see data points on each bar. The chart shows a steady decline in sales for ‘Outdoor Protection’ product line.
8.	Pixiedust is an open source visualization package developed by IBM labs. You can visualize SparkSQL data frames with a single API call and interactively access raw data, pick visual options and stow data away to files or IBM Cloudant or Object Storage.

--- 
#### End of Lab

##### [Next Steps: Build your next Spark Analytics project using IBM Data Science Experience.](https://github.com/WatsonDataPlatform/E2ELab/raw/master/datascientist/machinelearning)
