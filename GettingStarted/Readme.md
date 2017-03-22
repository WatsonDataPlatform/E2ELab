
## Before You Begin

The "Watson Data Platform" lab is done using the IBM cloud. It uses a set of fully managed cloud services; Cloudant and dashDB for Analytics to persist data and Data Connect to ingest data. These services are available in Bluemix, IBM’s cloud platform as a service (PaaS). It also uses Watson Analytics, IBM’s smart data discovery service on the cloud and the IBM Data Science Experience, an interactive, collaborative, cloud-based environment where data scientists can use multiple tools to activate their insights. Lastly, you will be required to download a few files that are supplied that you will use as source datasets.

## Workflow

On the following pages are a series of steps you will perform before you do any of the labs. Each step outlines an easy to follow set of instructions that will prepare your cloud environment so you can do any of the labs you choose. It has been designed as a serial process so it’s important that you follow each step in sequence and do not deviate from the workflow or skip any steps in the process.

Step | Description
------------ | -------------
1 | Register for a Bluemix Account
2 | Register for a Watson Analytics Account
3 | Login to Bluemix
4 | Create a Bluemix Space
5	| Create a Cloudant Service
6	| Create a dashDB for Analytics Service
7 | Create a Data Connect Service
8 | Create a Node.js Application
9 | Download Source Data Files

1. **Download** the Great Outdoor Customer Orders CSV file from the GitHub location below and save the file to a location of your choice on your workstation:

 > https://github.com/WatsonDataPlatform/E2ELab/blob/master/dataengineer/Great%20Outdoor%20Customer%20Orders.csv

## Step 1: Register for a Bluemix Account

You will need a Bluemix account. If you don't have an account, click on the URL below to create one:

  > https://console.ng.bluemix.net/registration
  >
  > Fill in all information on the right side panel and then click on the *Create Account* button on the bottom of    the right side panel.

<img src="https://github.com/ibmdataworks/datafirst/blob/master/appdeveloper/media/image4.png" width="237" height="219" />

You will see a page asking you to check your email for next steps. Check your email account that you used when you registered for your Bluemix account.

<img src="https://github.com/ibmdataworks/datafirst/blob/master/appdeveloper/media/image5.png" width="396" height="330" />

Click on the “confirm your account” link.

## Step 2: Register for a Watson Analytics Account

You will need a Watson Analytics account. If you don't have an account, click on the URL below to create one:

  > https://watson.analytics.ibmcloud.com/product
  >
  > Click on the “TRY IT FOR FREE” button. You have the option to click on “View pricing and buy” from the next screen. Watson Analytics provides 2 paid editions “Plus” and “Professional” with monthly license charges of $30 and $80, with included storage of 2GB and 100GB respectively. For now, you will go with the “Free” license and click on “Try free edition”.


1.  Open a browser and go to “watsonanalytics.com”. This will redirect you to the URL: <https://watson.analytics.ibmcloud.com/product> and click on “TRY IT FOR FREE” button as shown below:
 > <img src="./media/image1.png" width="378" height="257" />
   
2.  You have the option to click on “View pricing and buy” from the next screen. Watson Analytics provides 2 paid editions “Plus” and “Professional” with monthly license charges of $30 and $80, with included storage of 2GB and 100GB respectively. For now, let’s go with the “Free” license and click on “Try free edition”. To read more about the editions, please check out: <https://www.ibm.com/analytics/watson-analytics/us-en/solution/editions>
 > <img src="./media/image2.png" width="382" height="260" />

3.  You will be taken to the “Purchase” page, from where click on “Try free edition”. This will set up a “Free” account that supports 1MB of storage for a single user for an indefinite period and a 30-day trial of the Professional single user account. The “Free” account only allows text files to be uploaded into Watson Analytics, whereas from Professional Account you can bring in a variety of data sources on the cloud and on-premise with up to 100GB of storage (additional storage can be purchased at $50 per month per 50GB).
 > <img src="./media/image3.png" width="382" height="217" />

4.  You will now be prompted to setup an IBMid using the sign-up form as shown below. However, if you already have an IBMid, you can click on “Already have an IBMid” as highlighted below and sign-on with those credentials to request Watson Analytics account setup.
 > <img src="./media/image4.png" width="381" height="232" />

5.  To activate your IBMid, you will be sent an email by ibmacct@us.ibm.com with a “Confirmation code” (7 digit number), that you can retrieve from your email box and type it on the sign-up page as shown below.
 > <img src="./media/image5.png" width="382" height="197" />

6.  At this point, you will see a status screen saying “Your services are being setup” but within a few seconds your account will be setup and you’ll see a page as below confirming your 30-day trial subscription to “IBM Watson Analytics Professional Single User”!
 > <img src="./media/image6.png" width="597" height="323" />

7.  You can now login to Watson Analytics by clicking on “Launch” button or directly go to Watson Analytics sign-on site from the homage watsonanalytics.com. After you login, you should see the page below and you are now ready to upload data for an amazing experience of guided self-service analytics!
 > <img src="./media/image7.png" width="382" height="217" />

## Step 3: Login to Bluemix

Using your preferred web browser, go to URL https://console.ng.bluemix.net

<img src="./media/Step1-image-1.png"/>

1. **Select** the "Log In" button. When prompted, enter your Bluemix ID and password.

## Step 4: Create a Bluemix Space

<img src="./media/Step2-image-1.png"/>  

1. **Select** the Account information area in the top right corner of your Bluemix account home page.
2. **Select** the "Create a Space" link next to “Manage Organizations” below the Space drop down list box.

  <img src="./media/Step2-image-2.png"/>

3. **Enter** “Watson Data Platform” (without quotes) for the space name.  
4. **Select** the “Create” button.  

> Your space will be created and you will be taken into your new space. You should now see, in the top right corner, that you are in the “Watson Data Platform” space in your Bluemix organization. You will use this space to house the Data Connect service that you will be creating in the following section.

## Step 3: Create a Data Connect Service

<img src="./media/Step3-image-1.png" />

1. **Select** the "Catalog" menu at the top of the Bluemix home page.  
2. **Select** the "Data and Analytics" category from the categories on the left.  
3. **Click on** the “Data Connect” service from the list of services on the right.  

<img src="./media/Step3-image-2.png" />

4. **Enter** "Data Connect” (without quotes) for the Service name.  
5. **Enter** “Data Connect” (without quotes) for the Credential name.  
6. **Select** the “Starter” plan from the Pricing Plans section (it is typically selected by default).  
7. **Select** the the "CREATE" button. The service will be created and the launch page is displayed.  

<img src="./media/Step3-image-3.png" />

8. **Select** the “LAUNCH” button to start using Bluemix Data Connect - It will open in a new tab in your browser.

<img src="./media/Step3-image-4.png"/>

> The Data Connect user interface provides easy access to all functions from a main menu located on the left side and a few primary functions that are displayed in the middle of the home page that allow you to navigate to the different areas of the interface.

> **Notice** that there is a menu control button to the right of the Data Connect logo. It controls the appearance of the menu on the left side. By selecting this button you can hide or view the left side menu. Also, clicking on the service name you can always get back to the home page. Let’s experiment with these controls.

1. **Select** the menu control button. The menu will disappear. Select it again and the menu will reappear.  
2. **Select** the Activities menu item. It will take you to the Activities section of the interface.  
3. **Select** the Data Connect service name to get back to the home page.
