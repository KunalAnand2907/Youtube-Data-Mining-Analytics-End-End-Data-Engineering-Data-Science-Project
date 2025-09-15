## Youtube 📺 Data Mining & Analysis 📈 End-End Data Engineering & Data Science Project 

### 📌 Demo app Link 

<a href="https://youtu.be/GaeUzR9szVM"><img src="https://github.com/KunalAnand2907/Youtube_DataMining_Analysis-End-End-Data-Engineering-Data-Science-Project/assets/46574881/4f490ebc-1c79-4b10-b869-cf319682598e"></a>


### 📌 Dataset Overview:
For this Project, I have used 2 Types of Data as mentioned below:
<ul>
<li> <b>Trending YouTube Video Statistics Data</b> which is taken from Kaggle.

**Dataset Link:** https://www.kaggle.com/datasets/datasnaek/youtube-new

<b>1. Csv File - </b>Each region’s data is in a separate file. Data includes the video title, video id, category_id [ranging from 1-41], channel title, publish time, tags, views, likes and dislikes, description, and comment count. <br>
<b>2. Json File -</b> Is in Key-Value format, where for each Region it has 30 nested K-V Pairs which included in the items Array, here for each Key we have id act as a Primary Key/ Joining Key and Snippet Struct Array which has nested k:v which includes Channel_id & Category Name where the videos are categorized into different categories like Film & Animations, Sports, Science & Technology, Entertainment, Music & Many More etc. 

<li> <b>Youtube Data Scrapped via Youtube Data API </b> according to the search word entered by the user, for our case I have used as 'Data Science'
</ul>

### 🎯 The Project is divided into 3 Parts:

---

 🧩 **1. Real-Time User Authentication & Authorization via Firebase & Show/Post Posts via Firestore on Streamlit App** ⇢ [ Visit Streamlit_App Folder ]
<ul>
<li>Any User can First Sign Up with an Email, Password, and unique Username and then log in to the Web App - Make Sure that the Email and username are different for each User - at the Backend I have used Firebase.
<li>Users has the option to post their thoughts or Queries in Post Notes Space, also they can see other People's Posts & can delete their Posts according to their Need. I have used Firestore (No SQL Real Time Database) which stores the data in Documents [ Unique Username ] and it includes a Collection that has Post's ordered w.r.t User_ID for each User.
</ul>

---

🧩 **2. Analytic Platform with end - end ETL Data Pipeline For Trending YouTube Video Statistics via Aws Services** ⇢ [Visit ETL_AWS Folder]

#### 📚 Overview

This part aims to securely manage, streamline, and perform analysis on the Structured and Semi-Structured YouTube video data based on the many trending metrics such as video categories (Entertainment, Science and fiction, etc), Video Tile and desc, Channel Name & ID, Likes & Description, Comments & its Count.

####  📚 Brief Workflow

For this, Have built the ETL Data Pipeline from Scratch, where I loaded raw .json Files & .csv Files w.r.t different regions in **1.** Raw_S3_Bucket ➡️ Created a Glue Catalog while running the crawler on raw JSON file ➡️ Got an error as it had a struct Array Items ➡️ Pre-Processed Data for all. Json Files converted into Tabular/ Parquet Format & stored into a new cleansed S3 -- **2.** S3_Cleansed_Bucket by automatically triggering the Lambda Function on every S3 Json Put & doing append operation - pre-processing & then storing it in cleansed S3 [Automating the Process] ➡️ Again Created a Glue Catalog on partitioned CSV Files w.r.t Regions ➡️ Similarly Created a Glue Catalog by running Glue Crawler on all the .csv files by partitioning them w.r.t regions ➡️ In btw runing the Glue Job (Pyspark Script) - doing the schema (DT Types Changes), dropping null Rows & Handling Outliers - then storing it to table & then storing in the nex cleansed s3 ➡️ then Join the 2 Catalog's by Inner Join on Category_Id Col [PK & Fk] & ran the Glue Spark Job and stored the Queried Data in new **3.** S3_Analytic_Bucket ➡️ For Querying the Data present in different S3 Bucket used Athena and stored the metaand & Output Table in new **4.** S3_Query_Athena_Output Bucket ➡️ At the end used the Data from the Analytic S3 Bucket to create Interactive Dashboards having Imp KPIs and various Graphs and charts answering Question such as Top 10/ Bottom 10 Trending videos w.r.t Region and all around the Globe, Total Views/ Total Likes/ Total Comment Count w.r.t Different Categories etc.

**⇢** <a href="https://drive.google.com/drive/u/0/folders/19idDsEe7xafxWRVmEaYkRSfAbbYlmCbb" target="_blank">**Detailed Workflow Link**</a>

#

### 🚀 Architecture Diagram

![ETL_AWS](https://github.com/user-attachments/assets/c8efa182-ca19-4680-b121-d2709c8c1d9f)

📚 **Tech Stack:**

➔ **Languages --** SQL, Python3

➔ **File Formats --** Json, Parquet, Csv

➔ **Services:**
<ul>
<li>Amazon S3: Amazon S3 is an object storage service that provides manufacturing scalability, data availability, security, and performance.
<li>AWS IAM (Users, Groups & Role): This is nothing but identity and access management which enables us to manage access to AWS services and resources securely.
<li>QuickSight: Amazon QuickSight is a scalable, serverless, embeddable, machine learning-powered business intelligence (BI) service built for the cloud.
<li>AWS Glue (Crawler, Studio & Glue Catlog): A serverless data integration service that makes it easy to discover, prepare, and combine data for analytics, machine learning, and application development.
<li>AWS Lambda: Lambda is a computing service that allows programmers to run code without creating or managing servers.
<li>AWS Athena: Athena is an interactive query service for S3 in which there is no need to load data it stays in S3.
<li>AWS SNS: A distributed publish/subscribe solution used for application-to-application (A2A) and application-to-person (A2P) communication. SNS topics are used to enable communication: producers publish messages to topics, and consumers subscribe to these topics to receive messages. You can deliver messages to various types of subscribers, such as AWS SQS queues, AWS Lambda functions, and HTTP endpoints. You can also use SNS to send SMS messages, email, and push notifications to end-user devices.
<li>AWS Cloudwatch & Logs: It enables you to monitor your complete stack (applications, infrastructure, network, and services) and use alarms, logs, and events data to take automated actions and reduce mean time to resolution (MTTR). This frees up important resources and allows you to focus on building applications and business value.
</ul>

---
🧩 **3. Youtube Data Scrapping & Performing Data Wrangling, Pre-Processing, EDA & Text Mining -** NLP Tasks on the Youtube Data to predict to which Category the Video Belongs!! **⇢** [ Visit DataScrapping_Viz_Nlp_Tasks Folder ]

This Section is further divided into 2 Parts:

▶️ **Scrapping Youtube data, Pre-Processing, Wrangling, and Visualizing Data via different Charts & Graphs.**

⇢ Youtube data is scrapped by using Youtube Data API according to search Data Science & we have Attributes such as:
<ul>
<li> <b> For Different Channel's Data:</b>
Attributes s.a. Channel Name, subscribers, Total Views, Total Videos, Playlist ID
<li> <b> For each Channel Data:</b>
Attributes s.a. Video title, Video id, Video Description, Published date, Likes, Dislikes, Views, Comments
<li> After that I Performed Data Processing, Wrangling operations on the Data mentioned above & then Performed EDA (uni, Bi, Tri) Variate Data Visualization on the Cleaned Data
</ul>

📄🔍 **Text Mining - Performing NLP Tasks on the Youtube Statistics Data**

⇢ Predict the Category_id (Y) Based on Video_Title (X)
<ul>
<li> <b>Text Pre Processing 1 --</b> Tokenize [Sentences, Words] ➡️ Text Cleaning { Regex - remove Punctuations, Special Chars, extra white spaces} ➡️ Remove StopWords ➡️ Stemming & Lemmatization ➡️ POS Tagging ➡️ NER
<li> <b>Text Pre Processing 2 --</b> Word Embeddings { Ml Embeddings - BOW, TF-IDF, Word2Vec, DL Embeddings - LSTM/ Bi - Dir LSTM with Word Embeddings }
<li> Model Building & Training
<li> Evaluation and tuning of Parameters
<li> Comparing all the Word Embeddings Model
<li> At the end map the Category_id to 16 different Category Name s.a [ Film & Animations, Sports, Science & Technology, Entertainment, Music, News, Daily Vlogs ] etc.
</ul>

# 
### Watch the Below Video for working of the App

[![Main_Page_ss](https://github.com/KunalAnand2907/Youtube_DataMining_Analysis-End-End-Data-Engineering-Data-Science-Project/assets/46574881/b480838d-991b-4387-994c-bb3c90e9a081)](https://youtu.be/GaeUzR9szVM)
