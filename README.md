<p align="center">
  <a href="https://www.youtube.com/watch?v=jnX28Kt8u5w" target="_blank">
  <img src="https://upload.wikimedia.org/wikipedia/commons/0/09/YouTube_full-color_icon_%282017%29.svg" alt="YouTube Logo" width="90">
</p>

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

<ul>
<li>An interactive chatbot that makes exploring the <code>project | any related questions | its features | workflow | understanding tech stack</code> effortless
<li>Automated scraping of <code>YouTube metadata | comments | channel insights</code> using Python-based ETL
<li>Serverless ingestion pipeline built with <code>AWS (Lambda | S3 | CloudWatch)</code> for scalable execution
<li>Real-time text preprocessing <code>(tokenization | regex cleaning | stopwords | stemming | lemmatization)</code>
<li>Advanced NLP analytics including <code>sentiment analysis | topic modeling | NER | word embeddings</code>code>
<li>Firebase backend for structured <code>data storage and quick retrieval</code>
<li>Interactive plotly dashboards for <code>visual insights | KPIs | deep comment analytics</code>
<li>Modular pipeline design enabling plug-and-play <code>ML/DL models like TF-IDF | Word2Vec | LSTM/Bi-LSTM</code>
<li>Error-tolerant ETL workflow with <code>batch retries | logging | monitoring</code>
</ul>

#

### 📦 Project Structure: 

-- In Making

#

### ⚙️ Tech Stack:

| Category | Technology Used |
|-----------|-----------------|
| **Frontend** | Streamlit 🎈, HTML, CSS, JavaScript |
| **Backend / Scripting** | Python 🐍 |
| **Data Handling** | Pandas, NumPy 📊 |
| **Visualization** | Plotly, Matplotlib, WordCloud 📈 |
| **NLP & ML** | Hugging Face (Transformers 🤗) |
| **Security & Database / NoSQL** | IAM, Firebase (Firestore) 🔥 |
| **ETL – Compute** | Glue & Lambda ⚙️ |
| **ETL – Storage** | S3 🪣 |
| **Workflow Orchestration** | Step Functions 🔄  |
| **Monitoring & Logging** | CloudWatch, Cognito, CloudTrail & Config 📡 |
| **Notification/Msgs.** | SNS, SQS, MSK  |
| **APIs** | YouTube Data API v3 🔑 |
| **DevOps & Deployment** | Streamlit Cloud ☁️, Git, Github |
| **Caching** | Streamlit `@st.cache_data` ⚡ |
| **Editors** | Jupyter / VS Code 💻 |

#

### 🎯 The Project is divided into 5 Verticals:

---

 **1️⃣ Real-Time Auth & Interactive User Posts with Firebase + Firestore on Streamlit App**

🔥 This module powers a secure, real-time user experience using Firebase Authentication and Firestore Database, seamlessly integrated into the Streamlit App ⇢ [Visit Streamlit_App Folder](https://github.com/KunalAnand2907/Youtube-Data-Mining-Analytics-End-End-Data-Engineering-Data-Science-Project/tree/master/Part1_Streamlit_App)

**⚙️ Key Functionalities**

**1️. User Authentication & Authorization:**
 <ul> 
 <li> New users can Sign Up using an email, password, and unique username, and later Log In securely via Firebase Authentication. </li>
 <li> Each user’s credentials are validated to ensure uniqueness of both email and username, enabling a personalized session and secure data access. </li>
 </ul>
 
**2️. Dynamic Post Management via Firestore:**
<ul> 
 <li> Authenticated users can create, view, and delete there own posts in a collaborative Post Notes Space & can view other's & owner post on Home Page. </li>
 <li> All posts are stored in Firestore (NoSQL Real-Time Database) under each user’s unique document ID. </li>
 <li> Data is organized into collections per user, where posts are ordered by User_ID, ensuring fast retrieval and real-time updates directly reflected in the Streamlit interface. </li>
 </ul>

---

**2️⃣ Analytic Platform with end - end ETL Data Pipeline For Trending YouTube Video Statistics via AWS** ⇢ [Visit ETL_AWS Folder](https://github.com/KunalAnand2907/Youtube-Data-Mining-Analytics-End-End-Data-Engineering-Data-Science-Project/tree/master/Part2_ETL_Aws)

#### 📚 Overview

A fully automated ETL Data Pipeline designed to extract, clean, and analyze YouTube trending video data from multiple regions/Countries — leveraging AWS services for scalable processing, schema handling, and real-time analytics.
The platform securely handles structured and semi-structured data (JSON, CSV, Parquet) to uncover insights across key metrics such as ideo categories (Entertainment, Science and fiction, etc), Video Tile and desc, Channel Name & ID, Likes & Description, comments & its count.

#### 🧩 Workflow Summary:

Built from scratch using AWS serverless architecture:

1️⃣ **Raw Data Ingestion →** Uploaded regional/Diff. Countries JSON and Partitioned CSV files based on Regional Tag (Ind.csv, eng.csv, etc.) into 2 S3 Raw Bucket. <br>
2️⃣ **Schema Discovery →** Created AWS Glue Catalog; handled nested JSON struct arrays via preprocessing. <br>
3️⃣ **Automated Cleansing →** Used AWS Lambda triggers on S3 PUT events to clean and append data into S3 (Cleansed Bucket). <br>
4️⃣ **Data Transformation →** Executed PySpark Glue Jobs with Glue Bookmarks for schema normalization, null handling, and outlier's treatment. <br>
5️⃣ **Data Integration/ Combining →** Performed inner joins on category IDs and stored curated datasets into S3 (Analytic Bucket). <br>
6️⃣ **Query & Analysis →** Queried partitioned data with Athena, storing query output & metadata into 2 different named as: <code>a. S3 (Athena Output Bucket)</code>, <code>b.) S3 (Logs Athena Query Bucket)</code> <br>
7️⃣ **Visualization & Insights →** Leveraged QuickSight Dashboards to track KPIs like mentioned below, & create diff. data driven dashboards including various Graphs & Charts. <br>

**➔ Top/Bottom 10 trending videos by region** &nbsp; **➔ Category-wise views, likes, & comment counts** &nbsp; **➔ Global vs. regional performance trends**

### [🔗 View Detailed Architecture & Workflow](https://drive.google.com/drive/u/0/folders/19idDsEe7xafxWRVmEaYkRSfAbbYlmCbb)

#

### 🏗️ Architecture Diagram

![ETL_AWS](https://github.com/user-attachments/assets/eafba805-cdb6-400d-a208-f061ee1ee643)

#

📚 **Services:**

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
**3️⃣ YouTube Data Scraping → Transformation → Preprocessing → EDA → NLP-based Text Mining (with RAG) ⇢** [Visit DataScrapping_Viz_Nlp_Tasks Folder](https://github.com/KunalAnand2907/Youtube-Data-Mining-Analytics-End-End-Data-Engineering-Data-Science-Project/tree/master/Part3_DataScrapping_Viz_Nlp_Tasks)

#

This module is split into two major components:

**▶️ Part 1: Automated YouTube Data Extraction, Cleaning & Insightful Visual Analytics**

⇢ Using the YouTube Data API, the pipeline scrapes topic-specific content (e.g., Data Science) and captures rich metadata::
<ul>
<li> <b> Channel-level attributes: </b>
Channel Name, Subscribers, Total Views, Video Count, Playlist ID
<li> <b> Video-level attributes: </b>
Title, Description, Video ID, Publish Date, Likes, Dislikes, Views, Comments
<li> After data collection, extensive data wrangling + preprocessing operations are performed, followed by univariate, bivariate, and multivariate EDA using interactive charts and visualizations.
<li> This part essentially turns raw YouTube metadata into clean, structured insights—ready for downstream NLP tasks.
</ul>

# 

📄🔍 **Part 2: NLP-Powered Text Mining & Category Prediction (RAG Enhanced)**

⇢ A full end-to-end text analytics workflow is built on YouTube video statistics and metadata:

#### 🔤 Text Preprocessing Pipeline
<ol>
<li>Tokenization (sentence, word)
<li>Regex cleaning (remove punctuation, special chars, extra whitespaces)
<li>Stopword removal
<li>Stemming & Lemmatization
<li>POS Tagging & Named Entity Recognition
</ol>

#### 🧠 Word Embeddings based on MTEB Research Paper

<ul>
<li>Frequency based: Bag of Words, TF-IDF
<li>Prediction/ DL-based: Word2Vec, Glove
<li>Transformers/ LSTM Based: Open AI Embedder, Ollama, Gemini, Hugging Face, Elmmo, Qdrant 
</ul>

#### 🏗️ Model Development & 🔄 Evaluation
<ul>
<li>Training supervised models to predict Category_ID (Y) from Video Title (X)
<li>Hyperparameter tuning and performance comparison across multiple embedding strategies
<li>Final mapping of Category_ID to 16 YouTube content categories (e.g., Music, Sports, Tech, Entertainment, Vlogs, News, etc.)
</ul>

**✨ Section Focus:**
This section showcases the full lifecycle—from raw YouTube data → structured analytics → deep NLP modeling—demonstrating how to extract knowledge, classify content, and power intelligent search/RAG systems on top of unstructured YouTube data.

---

**4️⃣ YouTube Comments Sentiment Analyzer**

> 🔥 *Analyze, visualize, and understand YouTube audience sentiment for your videos in one click!*
This Streamlit app uses a multilingual BERT (transformer) model to classify YouTube comments as Positive, Neutral, or Negative, while automatically filtering spam and generating insights through charts, word clouds, and top comment (top 5 +ve, -ve & neutral) highlights with a <code> Download csv File </code> button to store sentiment insights locally.

> **[🔗 Watch the Workflow & Demo in Action](https://github.com/KunalAnand2907/Youtube-Comments-Sentiment-Analyzer/)**

---

**5️⃣ KunBot AI Assistant! 🤖 -** Interactive Conversational Bot that makes exploring the project, related queries, features, workflow, & understanding tech stack effortless ....

> 🌨️ Ask questions related to the project to the bot, uses an efficient low latency & high 
performant bot answering questions after understanding semantic, contextual meanings & 
applying added LLM intelligence on top of it.  

# 

**🚀 Future Initiatives** ~ What lies ahead:🌟

1. A personal assistant for generating Multilingual Video Timestamps
2. Personalized GIF Maker: Converting video to animated GIF Images [based on duration, speed playback, resolution scaling, image specs, fps, etc.] 

#
### ⚡ Experience the app in action—watch the video below!

[![Landing_Page](https://github.com/KunalAnand2907/Youtube-Data-Mining-Analytics-End-End-Data-Engineering-Data-Science-Project/blob/master/Landing_Page.png)](https://www.youtube.com/watch?v=jnX28Kt8u5w)
