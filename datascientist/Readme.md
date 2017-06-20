#Hands on Lab - Data Scientist
[<img src="https://github.com/WatsonDataPlatform/E2ELab/blob/master/Media/MachineLearning.png">](https://github.com/WatsonDataPlatform/E2ELab)

As a Data Scientist, you have to turn raw data into meaning using state-of-the-art techniques leveraging open source and enterprise applications. Data Science Experience (DSX) brings together the data science development experience accumulated in R, Python, Scala, and Java, along with the intuitive data connectivity and processing capabilities of Spark, and displays the outcomes using state-of-art dynamic visualization technology such as; Brunel, Pixiedust, and RStudio.

In this lab, we will create a notebook that contains steps and code to get data from the community, create a predictive model and start scoring new data. This notebook introduces commands for getting data and commands for basic data cleansing and exploration, pipeline creation, model training, model persistance to Watson Machine Learning repository, model deployment and scoring. Some familiarity with Python is recommended.

You will use publicly available data "GoSales Transactions for Naive Bayes Model" about anonymous outdoor equipment purchase to predict clients' interests in terms of product line like: golf accessories, camping equipement and others.

Learning Goals:
- Load a CSV file into a Spark DataFrame
- Explore data
- Prepare data for training and evaluation
- Create spark ml pipeline
- Train and evaluate model
- Persist pipeline and model in Watson Machine Learning repository
- Deploy model for online scoring using Wastson Machine Learning API
- Score sample scoring data using Watson Machine Learning API
- Explore and visualize prediction result using the plotly package.</font>


Setup
1. You need a Bluemix ID to get started. Please visit the Step 2 in the [Getting Started](https://github.com/WatsonDataPlatform/E2ELab/tree/master/GettingStarted) section if you have not created your Bluemix ID.


1. Goto [http://datascience.ibm.com/](http://datascience.ibm.com/)

2. Click the Log In button on the DSX landing page to sign in with your Bluemix credentials. Type in your Bluemix email address and password, then click Sign In.

 > <img src="https://github.com/watsondataplatform/e2elab/raw/master/datascientist/media/DSX Sign On.png">

 > You are now in the Data Science Experience. Depending on the plan you chose, your environment is automatically set up with at least one Apache Spark instance and at least 5 GB of object storage. From here you can create a new project, notebook, or connection. You can also explore any of the tutorials, videos, sample notebooks or articles in the community.

 > <img src="https://github.com/watsondataplatform/e2elab/blob/master/datascientist/media/DSX%20Landing.png">

You are now ready to start the hands-on excercises:

[Excercise 1. Root Cause Analysis (Interactive Analytics) Start Here](https://github.com/watsondataplatform/e2elab/raw/master/datascientist/interactive-analytics/)
This lab exercise uses an IPython Notebook in DSX to connect with dashDB, explores sales, product data and analyze sales performance for a specific product line. Pixiedust, a Python based visualization package is used to visualize the results.

[Excercise 2. Create Resolution (Machine Learning) Start Here](https://github.com/watsondataplatform/e2elab/raw/master/datascientist/machinelearning/)
This lab we will explore how a data scientist utilizes DSX and IBM Bluemix cloud services to easily analyze data using machine learning techniques and to visualize the outcomes using DSX, R, and Brunel. For the lab, we have chosen two algorithms to demonstrate supervised and unsupervised machine learning in DSX. Decision tree-based classification is one of the domains that allowed scientists to have direct insights into the reasoning behind classification choices. Association rules algorithms support market basket analysis.



