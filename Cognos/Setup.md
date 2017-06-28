## Step 1: Setup Cognos

Launch [Cognos Free Trial](https://www.ibm.com/analytics/us/en/technology/products/cognos-analytics/)
and SIGN IN to bring up the login page.

<img src="./cmedia/image2.png" >

You will be taken to the Welcome page.

<img src="./cmedia/image3.png" >

### Create a Data server connection

![](/media/CA/ca1.png)

1. On the Welcome screen, select Manage on the bottom left side. 

<img src="./cmedia/image3b.png" >

1. Select Data server connections to create a new data server.

![](/media/CA/ca2.png)

1. Create a new data server connection by selecting the ‘+’

<img src="./cmedia/image3b.png" >

Select dashDB as the typeIA

![](/media/CA/ca3.png)

1. Rename the connection name from New data server connection to IA_Bank Customers

1. Enter your dashDB JDBC URL from your dashDB service credentials you created and obtained earlier during the dashDB service setup. Copy the "jdbcurl" (NOT the "ssljdbcurl") and paste into Cognos Analytics. Your JDBC URL might look something like this (do not paste the quotes):  **"jdbc:db2://dashdb-entry-yp-dal09-08.services.dal.bluemix.net:50000/BLUDB"**

1. You need to specify the sign in credentials for the dashDB user to use each time you connect to this database. Select the Use the following signon check mark  

1. Select the  ‘+’ icon 

![](/media/CA/ca5.png)


1. Enter the your dashDB User ID

1. Enter your password and confirm your password

1. Click on the Test Button to verify your new connection.  If it tests successfully, then

1. Click Save

If the test fails, check the userID, password, etc. and re-test.


Now we need to select the database schema (table owner) that we will use in this exercise. 

![](cmedia/image25.jpg)

1. Select the Schema tab for the IA_Bank Customers data server connection

1. Select the schema associated to your userid and select

1. Select Load metadata. 

 When the schema is successfully loaded, the status button next to the schema will turn green

![](cmedia/image26.jpg)


### Create a Data Module

With Cognos Analytics, users are not restricted to only using existing enterprise data sources. Users can blend perosnal data or external data with enterprise data to gain deeper insight. Users can connect to enterprise data directly, or they can import other data sets from from files or other data sources into Cognos Analytics. These data sources can be blended, cleansed and joined together to create a reusable **data module** for use in dashboards and reports, and/or shared with other users in the organization. Although this lab has only one data source, we will still create a data module.

To create a new data module, select New from Navigation Bar on the left side of the Cognos Analytics screen and then select Data module

![](cmedia/image27.png)

This will take you to the Create data module screen and provide a list of options you can choose from. 

![](cmedia/image28.png)

1. Select Data servers (because we are going to connect to the ‘IA_Bank Customers’ data server connection you created earlier.

1. Select IA_Bank Customers from the list. This will display the schema we created earlier. 

1. Select the ‘Schema’ associated with your dashDB instance, ours is **DASH106554** in this instance.


Your schema will now be added to Selected sources list. Again ours is **DASH106554**.

![](cmedia/image29.png)

Click on the Start button.

### Data modeling

Once a data source is selected, users can enter their desired search term(s) and click on Go to look for tables with data related to that search term. Cognos Analytics will analyze the data source and present table(s) that have some relation to the term you entered that you can add to your data module. Since we want to look into our Bank customers to analyze satisfaction and churn data,  

![](cmedia/image30.png)

1. In the intent panel, type Customers

1. Click on Go

1. While we show multiple tables here, you should only see a single table, named **Bank Customers**.  Select the Bank Customers table

1. Click on Add this proposal


Your data module should look like this

![](cmedia/image35.png)


We will save our data module now.

![](cmedia/image36.png)
1. Click Save.

1. Select My Content.

1. Type ‘Bank Customers Module’ for the name.

1. Click Save

Expand the Bank Customers table in the Data Module View

![](cmedia/image37.png)

You have told us that your Data Scientists have found some interesting correlations between the number of late payments a customer has had in the past and their propensity to churn. Because this has been identified as an interesting factor for further analysis, we will divide the data into groups based on how many late payments they have had. 

Select the Number of Late Payments column and click on more options (the 3 dots, one above the other)

Select Create custom groups

![](cmedia/image38.png)

We can see that Cognos Analytics suggests creating an equal distribution of the late payment values into 10 groups distributed evenly.

![](cmedia/image39.png)


However, we will create 3 groups based on the findings of your Data Scientists.

1. Change the Group name to Group Late Payments

1. Change How many groups? from 10 to 3

1. Select Custom

1. Change the lowest value to 1

1. Change the middle value to 21

1. Change the highest value to 3000

1. Click on Create

![](cmedia/image40.png)

The data scientists have also observed a correlation between the number of credit applications a customer has submitted and their tendency to churn. So we will also create a another Custom group for the number of credit applications. Create a
new custom group based on the Number of Credit Applications.

Again, we will create 3 groups.

Select the Number of Credit Applications column and click on more options

1. Change the Group name to Group Credit Applications (Note, we mis-spelled this, but you can spell it correctly if you wish)

1. Change How many groups? from 10 to 3

1. Select Custom

1. Change the lowest value to 5

1. Change the middle value to 26

1. Change the highest value to 3000

1. Click on Create

![](cmedia/image41.png)

**Save the data module**

### Create Navigation Group

Navigation groups allow drill downs that align with how users want or need to analyze their business. In this case the Bankid column identifies whether the data is from "K Bank" or "N Bank". 

![](cmedia/image42.png)

Go back to your Data module

- Scroll to the Bankid column in the Bank Customers table and select it

- Select more options for the Bankid column

- Select Create navigation group. 

The default name will be Bankid since that is the name of the column we selected first.

![](cmedia/image43.png)

In our Analysis we want to look at information by Originating Bank, churn, customer type, branch location and customer.

1. Rename the Navigation Group to Bank Churn Drill Path

1. Drag the Churn column below Bankid

1. Drag the Customer Type column below Churn

1. Drag the Home Branch State column below Customer Type

1. Drag the Customer column below Home Branch State

1. Click on Apply

![](cmedia/image44.png)

There are many more things we could do in this data module, but for now let's **save** the data moduleand start looking for insight.
