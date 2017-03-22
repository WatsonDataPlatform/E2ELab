
## Before You Begin

> The "Watson Data Platform" lab is done using the IBM cloud. It uses a set of fully managed cloud services; Cloudant, dashDB for Analytics and Data Connect that are available in Bluemix, IBM’s cloud platform as a service (PaaS), Watson Analytics, IBM’s smart data discovery service on the cloud, IBM's Data Science Experience, an interactive, collaborative, cloud-based environment where data scientists can use multiple tools to activate their insights and a few files that are supplied that you will be used as source datasets.

## Workflow

> On the following pages are a series of steps you will need to perform before you perform any of the labs. Each step outlines an easy to follow set of instructions that prepare your environment. It has been designed as a serial process so it’s important that you follow each step in sequence and do not deviate from the workflow or skip any steps in the process.

### Getting Started Steps

Step | Description
------------ | -------------
1 ! Create a Bluemix Account
2 ! Create a Watson Analytics Account
3 | Login to Bluemix
4 | Create a Bluemix Space
4	| Create a Cloudant Service
5	| Create a dashDB for Analytics
6 | Create a Data Connect Service
7 | Create a Node.js Application
8 | Download Data Files

1. **Download** the Great Outdoor Customer Orders CSV file from the GitHub location below and save the file to a location of your choice on your workstation:

 > https://github.com/WatsonDataPlatform/E2ELab/blob/master/dataengineer/Great%20Outdoor%20Customer%20Orders.csv

2. You will need a Bluemix account. If you don't have an account, click on the URL below to register for one:

  > https://console.ng.bluemix.net/registration
  >
  > Fill in all information on the right side panel and then click on the *Create Account* button on the bottom of    the right side panel.

3. You will need a Watson Analytics account. If you don't have an account, click on the URL below to create one:

  > https://watson.analytics.ibmcloud.com/product
  >
  > Click on the “TRY IT FOR FREE” button. You have the option to click on “View pricing and buy” from the next screen. Watson Analytics provides 2 paid editions “Plus” and “Professional” with monthly license charges of $30 and $80, with included storage of 2GB and 100GB respectively. For now, you will go with the “Free” license and click on “Try free edition”.

## Step 1: Register for a Bluemix Account

## Step 2: Register for a Watson Analytics Account

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
