## YouTube 📺 Data Mining & NLP: Automated 📈 ETL for scraping, processing, text analytics, insights via Aws, Python, Firebase & Streamlit

### ✨ Demo app Link: &nbsp; <a href="https://yt-comments-sentiment-analyzer.streamlit.app/"><img src="https://github.com/KunalAnand2907/Youtube_DataMining_Analysis-End-End-Data-Engineering-Data-Science-Project/assets/46574881/4f490ebc-1c79-4b10-b869-cf319682598e"></a>

#

### 📌 Dataset Overview:

This project utilizes data collected through two different sources:

<ul> <li> <b>1. Trending YouTube Video Statistics</b> — sourced from Kaggle <br>
 
<b>🔗 Dataset Link:</b> [YouTube Trending Video Dataset](https://www.kaggle.com/datasets/datasnaek/youtube-new) 
 <ul> <li><b>CSV Files:</b> Each region’s dataset is stored separately and contains attributes such as <i>video title, video ID, category ID (1–41), channel title, publish time, tags, views, likes, dislikes, description,</i> and <i>comment count.</i></li> <li><b>JSON Files:</b> Structured in key-value pairs for each region, with an <code>id</code> acting as the primary key. Each record includes a <code>snippet</code> object containing nested fields like <code>channelId</code> and <code>categoryName</code>—categorizing videos into domains such as <i>Music, Sports, Technology, Entertainment,</i> and more.</li> </ul> </li> 
<br>
<li> <b>2. YouTube Data Scraped via YouTube Data API</b> — collected dynamically based on user-defined search terms. For this project, data was extracted using the keyword <b>"Data Science"</b>. </li> </ul>

#

### 🚀 Key Features:

-- In Making

#

### 📦 Project Structure: 

-- In Making

#

### 🎯 The Project is divided into 3 Parts:

---

 **1️⃣ Real-Time Auth & Interactive User Posts with Firebase + Firestore on Streamlit App**

🔥 This module powers a secure, real-time user experience using Firebase Authentication and Firestore Database, seamlessly integrated into the Streamlit App ⇢ [Visit Streamlit_App Folder](https://github.com/KunalAnand2907/Youtube-Data-Mining-Analytics-End-End-Data-Engineering-Data-Science-Project/tree/master/Part1_Streamlit_App)

**⚙️ Key Functionalities**

1️. User Authentication & Authorization:
 <ul> 
 <li> New users can Sign Up using an email, password, and unique username, and later Log In securely via Firebase Authentication. </li>
 <li> Each user’s credentials are validated to ensure uniqueness of both email and username, enabling a personalized session and secure data access. </li>
 </ul>
 
2️. Dynamic Post Management via Firestore:
<ul> 
 <li> Authenticated users can create, view, and delete there own posts in a collaborative Post Notes Space & can view other's & owner post on Home Page. </li>
 <li> All posts are stored in Firestore (NoSQL Real-Time Database) under each user’s unique document ID. </li>
 <li> Data is organized into collections per user, where posts are ordered by User_ID, ensuring fast retrieval and real-time updates directly reflected in the Streamlit interface. </li>
 </ul>

---

**2️⃣ Analytic Platform with end - end ETL Data Pipeline For Trending YouTube Video Statistics via AWS** ⇢ [Visit ETL_AWS Folder]

#### 📚 Overview

A fully automated ETL Data Pipeline designed to extract, clean, and analyze YouTube trending video data from multiple regions/Countries — leveraging AWS services for scalable processing, schema handling, and real-time analytics.
The platform securely handles structured and semi-structured data (JSON, CSV, Parquet) to uncover insights across key metrics such as ideo categories (Entertainment, Science and fiction, etc), Video Tile and desc, Channel Name & ID, Likes & Description, comments & its count.

#### 🧩 Workflow Summary:

Built from scratch using AWS serverless architecture:

1️⃣ Raw Data Ingestion → Uploaded regional/Diff. Countries JSON and Partitioned CSV files based on Regional Tag (Ind.csv, eng.csv, etc.) into 2 S3 Raw Bucket. <br>
2️⃣ Schema Discovery → Created AWS Glue Catalog; handled nested JSON struct arrays via preprocessing. <br>
3️⃣ Automated Cleansing → Used AWS Lambda triggers on S3 PUT events to clean and append data into S3 (Cleansed Bucket). <br>
4️⃣ Data Transformation → Executed PySpark Glue Jobs with Glue Bookmarks for schema normalization, null handling, and outlier's treatment. <br>
5️⃣ Data Integration/ Combining → Performed inner joins on category IDs and stored curated datasets into S3 (Analytic Bucket). <br>
6️⃣ Query & Analysis → Queried partitioned data with Athena, storing query output & metadata into 2 different named as : a.) S3 (Athena Output Bucket), b.) S3 (Logs Athena Query Bucket) <br>
7️⃣ Visualization & Insights → Leveraged QuickSight Dashboards to track KPIs like mentioned below, & create diff. data driven dashboards including various Graphs & Charts. <br>

**➔ Top/Bottom 10 trending videos by region**

**➔ Category-wise views, likes, and comment counts**

**➔ Global vs. regional performance trends**

### [🔗 View Detailed Architecture & Workflow →](https://drive.google.com/drive/u/0/folders/19idDsEe7xafxWRVmEaYkRSfAbbYlmCbb)

#

### 🏗️ Architecture Diagram

![ETL_AWS](https://github.com/user-attachments/assets/eafba805-cdb6-400d-a208-f061ee1ee643)

#

📚 **Tech Stack:**

➔ **Languages --** SQL, Python3 |
➔ **File Formats --** Json, Parquet, Csv

➔ **Services:**
<ul>
<li><b>S3:</b> Amazon S3 is an object storage service that provides manufacturing scalability, data availability, security, and performance.
<li><b>IAM (Users, Groups & Role):</b> This is nothing but identity and access management which enables us to manage access to AWS services and resources securely.
<li><b>QuickSight:</b> Amazon QuickSight is a scalable, serverless, embeddable, machine learning-powered business intelligence (BI) service built for the cloud.
<li><b>Glue (Crawler, Studio & Glue Catlog):</b> A serverless data integration service that makes it easy to discover, prepare, and combine data for analytics, machine learning, and application development.
<li><b>Lambda:</b> Lambda is a computing service that allows programmers to run code without creating or managing servers.
<li><b>Athena:</b> Athena is an interactive query service for S3 in which there is no need to load data it stays in S3.
<li><b>SNS:</b> A distributed publish/subscribe solution used for application-to-application (A2A) and application-to-person (A2P) communication. SNS topics are used to enable communication: producers publish messages to topics, and consumers subscribe to these topics to receive messages. You can deliver messages to various types of subscribers, such as AWS SQS queues, AWS Lambda functions, and HTTP endpoints. You can also use SNS to send SMS messages, email, and push notifications to end-user devices.
<li><b>Cloudwatch & Logs:</b> It enables you to monitor your complete stack (applications, infrastructure, network, and services) and use alarms, logs, and events data to take automated actions and reduce mean time to resolution (MTTR). This frees up important resources and allows you to focus on building applications and business value.
</ul>

---
**3️⃣ YouTube Data Scraping, Transformation, Preprocessing, EDA, and NLP-based Text Mining with RAG ⇢** [ Visit DataScrapping_Viz_Nlp_Tasks Folder ]

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
<li> Topic Categorization: At the end map the Category_id to 16 different Category Name s.a [ Film & Animations, Sports, Science & Technology, Entertainment, Music, News, Daily Vlogs ] etc.
</ul>

# 
### Watch the Below Video for working of the App

[![Main_Page_ss](https://github.com/KunalAnand2907/Youtube_DataMining_Analysis-End-End-Data-Engineering-Data-Science-Project/assets/46574881/b480838d-991b-4387-994c-bb3c90e9a081)](https://youtu.be/GaeUzR9szVM)
