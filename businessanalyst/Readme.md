# Hands on Lab - Business Analyst
[<img src="https://github.com/WatsonDataPlatform/E2ELab/blob/master/Media/DataDiscovery.png">](https://github.com/ibmdataworks/datafirst/tree/master/businessanalyst/)

Perform these hands-on exercises using guided exploration capabilities with IBM Watson Analytics platform on customer transaction data to uncover unique insights about product affinities.
 

# Hands on Exercises...


1.  Logon to Watson Analytics by going to page “watsonanalytics.com” on a browser and clicking on “SIGN IN” text on the top right. 

 [<img src="https://github.com/WatsonDataPlatform/E2ELab/blob/master/Media/WatsonASignon.png">](https://github.com/WatsonDataPlatform/E2ELab/businessanalyst)

2.  If you completed the [Data Engineer Lab](https://github.com/WatsonDataPlatform/E2ELab/tree/master/dataengineer/) you should have the "Great Outdoor Customer Orders.csv" file in your "Personal" folder as shown in the image below. If this file does not exist or you do not wish to complete the Data Engineer lab, proceed to Step 3 to upload the file, otherwise move to Step 9. 

3. Download this file <https://github.com/WatsonDataPlatform/E2ELab/blob/master/GettingStarted/Great%20Outdoor%20Customer%20Orders.csv> to a local directory. 

4. From Watson Analytics, click on “+ New data” button towards the top left. 

 > <img src="./media/image9.png" />

5.  You should now be able to import the spreadsheet “Great Outdoor Customer Orders.csv” that that you downloaded in Step 3. Click on “Local file” to import the dataset into Watson Analytics.
    
 > <img src="./media/image10.png" />

6.  You can now either drag and drop the spreadsheet or click on “Browse” to select the file from the folder where you downloaded the dataset from Github.

 > <img src="./media/image11.png" />

7.  Next, you should see an icon for the file on the screen and now click on “Import” button on bottom right to upload the spreadsheet to Watson Analytics.

 > <img src="./media/image12.png" />

8.  In less than a minute (usually within 30 seconds), the input file is uploaded and processed and shows up as an entry in the Personal folder as shown below. Watson Analytics processes the file to measure its usefulness for analytics and computes a data quality score. The data quality score (77% for this file) is computed as an average of the score of all fields and is influenced by missing values, constant values, imbalance (skews and outliers). To read more about data loading and data quality, please check out: <https://community.watsonanalytics.com/discussions/storage/attachments/816-watson-analytics-intro-to-data-v-2-1.pdf>

 <img src="https://github.com/WatsonDataPlatform/E2ELab/blob/master/businessanalyst/media/WatsonAcsv.png"/>

9.  You are now all set to start looking at the interesting insights Watson Analytics automatically finds from the data. Just click on the dataset and you’ll be taken to a screen labelled as “New Discovery Set” as shown below. As “Starting points”, 6 different visualizations are automatically recommended for you to explore (you can click on “Show Next” on the top right to see the next set of guided visualizations), but you can create your own visualization selecting from the 20 different chart types in the bottom of the screen. You also have an option to type in a natural language question on the top and Watson Analytics will suggest an appropriate visualization that likely answers that question! 
 > <img src="./media/image14.png" />

10.  Let’s scroll back to the top and type in a question “Show the breakdown of Transactions by Product Line and Product Type” and hit enter. You will automatically be provided a set of starting points starting with the most relevant visualization that helps answer your question! Let’s click on the treemap on the top left (the first visualization listed as “Most relevant” under “Starting points”).

 > <img src="./media/image15.png" />

11.  Since each row of the spreadsheet is a customer transaction, the size of the rectangles in the treemap represents the number of transaction for each product type such as “Tents”, “Sleeping Bags”, “Eyewear” etc. We can clearly see that most popular item for Great Outdoors is “Eyewear” and if you hover your mouse over that brown rectangle under “Personal Accessories”, it tells you that there were a total of 8,264 transactions (out of a total of 62K transactions) for “Eyewear”! The next best selling items in terms of total volume are “Tents” and then “Sleeping Bags”.

 > <img src="./media/image16.png" />

12. Several other automatically generated “Discoveries” are drawn on the right, but let’s click on the “>” symbol to minimize that pane, to lay out the treemap across the entire screen and better visualize the chart. Now, let’s add a field to the “Multiplier” data slot as highlighted on the bottom right by clicking on the "+" symbol and selecting “Gender” from the pulldown list.

<img src="https://github.com/WatsonDataPlatform/E2ELab/blob/master/businessanalyst/media/WatsonAgender.png">

13. On the text box that pops up, make sure to click on arrow to the right of “Multiplier Mode” and select “Vertical”. This will lay out the treemaps for Females and Males, one below the other (versus the default “Horizontal” option, which is next to each other). This helps better use the screen space to see the treemap more clearly for each Gender and observe the similarities and differences.

 > <img src="./media/image18.png" />

14. Now comparing the treemaps for the Women and Men respectively, we can clearly see that the most popular item for Women is “Eyewear”, whereas for Men, it is “Tents”. In the “Camping Equipment” category, Women buy more “Sleeping Bags” and then “Cooking Gear”.

 > <img src="./media/image19.png" />

15. Let’s now add a title to this visualization by clicking on “Untitled 1” on the tab to the top left and then click on the rename pencil icon as shown below to type in a title “Product Type vs Gender”.

 > <img src="./media/image20.png" />

16. We will create a new visualization now to see the correlation of Age and Gender to Product Line. Click on the “+” button to the right of the title tab of the visualization you just created as shown below:

 > <img src="./media/image21.png" />

17. You will be prompted with 6 “Starting points” again and instead of typing in a natural language question, let’s create this new visualization by scrolling to the bottom and under “Create your own visualization”, pick the chart titled as “Bar” under “Comparison”. There are 20 different chart options categorized as “Comparison”, “Parts to whole”, “Trend and forecast”, “Relationships”, “Tables and Summary”, “Predictive …” and “Geospatial”.

 > <img src="./media/image22.png" />

18. First, dismiss the “Discoveries’ pane on the right by clicking on the “>” symbol, so as get more space to draw out the bar chart. You will see a sample “Bar Chart” and you have to now pick fields for the categories; “Bars”, “Length”, “Color” and “Multiplier”, as shown on the bottom of the chart as below:

 > <img src="./media/image23.png" />

19. At the bottom of the screen, click on "Bars" and choose "Age". Click on "Length" and choose "Transactions". Click on "Color" and choose "Product Line". 

 > <img src="./media/image24.png" />

20. Now click on “Format”, expand “Variations” and perform the following - select “Stacked” and de-select “Swap Axis”. That enables your bar chart to be stacked and presented in a horizontal fashion and enhances the overall visibility of the visualization.

 > <img src="./media/image25.png" />

21. Click on the "Multipler" option at the bottom right and choose "Gender". Also make sure your "Multiplier Mode" is set to "Horizontal".

 > <img src="./media/image26.png" />

22. As you compare these, you’ll notice that Females below 30 years of age buy more “Personal Accessories” (shown in purple) and those between 30 and 48 buy more “Camping Equipment” (shown in blue).

 > <img src="./media/image27.png" />

23. As for the Males below age 44, they mostly buy “Camping Equipment” (shown in blue) and those older buy “Golf Equipment” (shown in green).
 > <img src="./media/image28.png" />

24. You can now rename this tab as “Product Line by Age and Gender” and save the new discovery set you just created by clicking on the disk icon and selecting “Save As”, as shown below.

 <img src="https://github.com/WatsonDataPlatform/E2ELab/blob/master/businessanalyst/media/WatsonAsaveas.png" />

25. On the “Save As” text box that pops up, type “Great Outdoors Customer Insights” on the top for the file name and save it in the “Personal” folder by clicking on the “Save” push button on the bottom right.

 > <embed src="./media/image31.emf" />

26. We will create one last visualization that will show us the attributes that drive “Product Line”. Click on the “+” and type a question “What drives Product Line” on the top left as shown below and hit enter.
    Watson Analytics returns with 6 resulting insights for you to choose from. Click on the most relevant (top left) Spiral Visualization as shown below.
    
 > <img src="./media/image32.png" />

27. You will see a list of factors arranged in order of their predictive strengths. You should see the top predictor as “Product Type” with 100% strength (since each Product Line has a set of unique Product Types) right at the center of the bulls-eye and then the next relevant attributes are “Profession and Gender” and “Professional and Age” respectively, each with 50% predictive strength. Click on the “Untitled 1” tab label for this discovery and click on the rename “pencil” icon and type in the label “Drivers of Product Line”. You should now see the discovery as below:

 > <img src="./media/image33.png" />

28. The predictive insight gleaned from the “Spiral” chart says a Data Scientist can explore building machine learning models such as a decision tree using the same data with the “Data Science Experience” (DSX) too. There’s a separate lab exercise for the Data Scientist that does exactly that and you’re welcome to try that next!

29. Congratulations, you’re done with the lab exercise!
