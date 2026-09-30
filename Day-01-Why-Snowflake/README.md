# 30-Days-of-Snowflake
Day-01-Why-Snowflake/
    🥶30 DAYS OF SNOWFLAKE
🎬 Welcome to the Snowflake journey! 
 
<img width="938" height="481" alt="image" src="https://github.com/user-attachments/assets/dc1898de-cbee-4d16-a8f1-4b222c64bf74" />

DAY 1 — WHY DO WE NEED SNOWFLAKE?
 
Before we start writing:
SELECT *
FROM CUSTOMER;
Let's stop for a minute.
🤔 Why do we need Snowflake in the first place? (Kyu chahiyee bhaii??)
Because if we don't understand the WHY, we'll end up memorizing SQL like:
"SELECT... FROM... WHERE... GROUP BY..."
…and when the interviewer asks:

"Why Snowflake?"
We'll be like:
"Sir... because... it's... a cloud..." 😭😂
Not today.
Today we're going to understand the story behind Snowflake.

1️⃣ WHY DO MODERN ORGANIZATIONS NEED CLOUD DATA PLATFORMS?
🏪 Imagine a growing company
Let's say we have an e-commerce company called:
🛒 "AbbasKart" 😂 😂
Initially, AbbasKart has:
•	10,000 customers
•	50,000 orders
•	1 GB of data
Everything is peaceful. 😎
Then the company grows.
Month 1
Customers     10K
Orders            50K
Data                1 GB
Everyone:
"Easy!" 😎
Month 12
Customers      10 Million
Orders         100 Million
Data            10 TB
Everyone:
"Okay... still manageable." 😐
Month 36
Customers      100 Million
Orders              Billions
Data                   100+ TB
Everyone:
"WHO CREATED THIS COMPANY?!" 😭😂
 
Now the company needs to answer questions like:
Which products sell the most?
Which customers are most active?
Which region generates the most revenue?
What happened to sales last month?
What products should we recommend?
And all those questions require data.
2️⃣ THE OLD PROBLEM — TRADITIONAL DATA WAREHOUSES
Before modern cloud data platforms became popular, organizations often had to manage significant infrastructure themselves.
Imagine your company has its own data warehouse.
You need to think about:
🖥️ Servers
💾 Storage
⚡ Compute                                                 
🔧 Maintenance
📈 Scaling
🔐 Security
💰 Infrastructure cost
🔄 Upgrades
And then your manager says:
"We need 10x more data next year."
You: No Problem 😂 😂
 
Your infrastructure team:
 
Your wallet:
 
😂( pocket emptyyyyy)

3️⃣ THE REAL PROBLEM: STORAGE + COMPUTE
Here's an important concept.
Imagine you have:
🏭 Storage
Where your data lives.
And:
💪 Compute
The processing power used to run your queries.
In many traditional data warehouse architectures, storage and compute were more tightly coupled, making independent scaling more difficult So imagine:
        STORAGE
           +
        COMPUTE
           |
        MACHINE
Now your data grows.
You need more storage.
But your workload also grows.
You need more compute.
And suddenly you're managing infrastructure just to answer:
SELECT SUM(SALES)
FROM ORDERS;
😂
Data Engineer:
"I just wanted the sales number!"
Infrastructure:
"First let's discuss your CPU utilization." 💀

4️⃣ ENTER SNOWFLAKE ❄️
Snowflake's architecture is designed around an important idea:
💡 Separate storage from compute.
Think of it like this:
                 ❄️ SNOWFLAKE

              ───────────────  ┐
                    STORAGE            
                          🏭                     
         
                      
                      
             ──────────
                 COMPUTE          
                        ss💪                     
                     Virtual                    
                   Warehouse             
              
But Snowflake also has:
          ☁️ CLOUD SERVICES
which coordinates many platform functions.
Simple analogy:
🏭 Storage:
"I'll keep the data."
💪 Compute:
"I'll process the queries."
🧑‍💼 Cloud Services:
"Everyone calm down. I'll coordinate this." 😂
5️⃣ SO... WHAT PROBLEM DOES SNOWFLAKE ADDRESS?
Snowflake provides a cloud data platform designed to support workloads such as:
📊 Data warehousing
🔄 Data engineering
📈 Analytics
🤖 Data science
🔐 Data security & governance
🤝 Data sharing
And one of its major architectural advantages is the ability to manage storage and compute independently.
For example:
                     YOUR DATA
                               🏭
                                  │
        ┌─────────┼─────────┐
        │                         │                      │
        ▼                      ▼                   ▼
      BI Team      ETL Team       Data Science
        💻               💻                        💻
Different workloads can use compute resources without requiring separate copies of the underlying data.
________________________________________
6️⃣ BUT WAIT... WHAT DO I NEED TO KNOW BEFORE LEARNING SNOWFLAKE?
Good news:
You don't need to be a Snowflake expert to start learning Snowflake. 😂
Recommended prerequisites:
🧠 SQL
You should understand:
SELECT
WHERE
GROUP BY
ORDER BY
JOIN
CASE
CTE
WINDOW FUNCTIONS
You don't need to be a SQL wizard.
If you currently write:
SELECT *
FROM EMPLOYEE;
Congratulations.
You're already invited to the party. 😂
________________________________________
🗄️ Basic database concepts
Understand:
•	Database
•	Schema
•	Table
•	View
•	Rows
•	Columns
•	Primary key
•	Foreign key
________________________________________
☁️ Basic cloud concepts
Understand the difference between:
Storage → where data is kept
Compute → where processing happens
IAM/Security → who is allowed to do what
That's enough to get started.
________________________________________
7️⃣ CREATE YOUR SNOWFLAKE ACCOUNT
Now enough theory.
🎬 Let's enter the Snowflake movie.
Link: https://signup.snowflake.com/?referrer=snowsight
Free…… Freee……. Freeeee…….
Free trial? Freeeee... until the credits say otherwise. 😂💸"
 

If you’re rich and have credit card…. 😂😂 go for CoCo(Cortex Code) 
Create your Snowflake account and choose the appropriate:
•	Cloud provider (aws/azure/gcp)
•	Region 
•	Account configuration (Business/enterprise/standard) 
Once you log in, you'll work through the Snowflake interface.
And now...
🥁 The moment you've been waiting for...
Your first Snowflake environment!
________________________________________
8️⃣ CREATE YOUR FIRST WAREHOUSE
A Snowflake Virtual Warehouse provides compute resources for executing workloads.
Think of it as:
💪 Your Snowflake gym.
Small workload?
"Bro, X-Small is enough." 😎
Huge workload?
"We need more muscles." 💪😂
Let's create one:
CREATE WAREHOUSE  SNOWFLAKE_30_DAYS_WH 😂
WITH
WAREHOUSE_SIZE = 'XSMALL'  
AUTO_SUSPEND = 60
AUTO_RESUME = TRUE;
 
-----------------------------------------------
CREATE WAREHOUSE  WH_DEV  (Your wish… 😄 You can create it with any name you want, except your lover’s name, because I’ll get jealous. 😂❤️)

What did we just do?
WAREHOUSE_SIZE = 'XSMALL'
➡️ Started with a small compute size.
AUTO_SUSPEND = 60
➡️ Automatically suspends after the configured period of inactivity.
AUTO_RESUME = TRUE
➡️ Allows the warehouse to resume when needed for a query.
Important:
Suspending the warehouse does NOT mean:
"Delete everything." 😂
Your stored data remains stored.
Think:
Warehouse sleeps 😴
Data stays in the house 🏠
________________________________________
9️⃣ CREATE YOUR DATABASE
Now let's create our project database.
Eg: CREATE DATABASE SNOWFLAKE_30_DAYS;
Eg : create or replace database dev_db;

 
Think:
🏢 Database = Building
Inside that building, we can have different departments.
Those departments are our:
📁 Schemas
________________________________________
🔟 CREATE A SCHEMA
Eg: CREATE SCHEMA SNOWFLAKE_30_DAYS.RAW;
Eg: create schema dev_schema;
 
So now:
🏢 SNOWFLAKE_30_DAYS
        │
        └── 📁 RAW
Simple.
Database
Contains schemas.
Schema
Contains database objects such as:
•	Tables
•	Views
•	Stages
•	Procedures
•	Functions
•	etc.
________________________________________
1️⃣1️⃣ USE YOUR ENVIRONMENT
USE WAREHOUSE WH_DEV;

USE DATABASE dev_db;

USE SCHEMA dev_schema;;
Now Snowflake knows where we want to work.
Check your current environment:
SELECT CURRENT_USER();

SELECT CURRENT_ROLE();

SELECT CURRENT_DATABASE();

SELECT CURRENT_SCHEMA();

SELECT CURRENT_WAREHOUSE();
🎉
Congratulations.
You have just started building your Snowflake environment.
________________________________________




1️⃣2️⃣ SNOWFLAKE ARCHITECTURE
Now let's understand what is happening behind the scenes.
Snowflake architecture can be simplified into three major layers:
                  ❄️ SNOWFLAKE
                       
       
   STORAGE                  COMPUTE                                                    CLOUD SERVICES
      🏭                              💪                                        🧠    
       │                                 │                                            │
 Micro-partitions   Virtual                                     Metadata
                                       -Warehouses                                     Security
                                                    Authentication
                                       Query coordination


 
🏭 STORAGE LAYER
This is where Snowflake stores your data.
But Snowflake doesn't simply throw everything into one giant file.
Snowflake stores table data in optimized storage structures called:
Micro-partitions
We'll come back to this in detail.
For now, remember:
Micro-partition = Snowflake's way of organizing table data into smaller, optimized storage units.
________________________________________
💪 COMPUTE LAYER
This is where Virtual Warehouses come in.
A warehouse provides compute resources to execute SQL statements and other workloads.
Think:
Query
  ↓
Virtual Warehouse
  ↓
Compute
  ↓
Result
Funny version:
Storage: "I have the data." 🏭
Warehouse: "Give it to me. I'll process it." 💪
Cloud Services: "First, let's check whether you're allowed to do that." 👀😂
________________________________________
☁️ CLOUD SERVICES LAYER
This layer coordinates important
 Snowflake services.
Examples include:
🔐 Authentication
👮 Access control
📋 Metadata management
🧠 Query parsing and optimization
🎯 Query coordination
Think of Cloud Services as the:
🎬 Director
Storage is backstage.
Compute is the actor.
Cloud Services says:
"Lights! Camera! SELECT!" 😂🎬
________________________________________


1️⃣3️⃣ STORAGE VS COMPUTE — THE MOST IMPORTANT IDEA OF DAY 1
Remember this:
STORAGE
   ↓
Stores your data

COMPUTE
   ↓
Processes your data

And they are separated.





Why is that useful?
Because you can manage compute resources independently of stored data.
For example:

                                   DATA 🏭

    Warehouse   Warehouse   Warehouse
       💪                          💪                     💪
                                                                
      BI                        ETL                Analytics
One underlying data platform can support different workloads using different compute resources.
________________________________________
1️⃣4️⃣ MICRO-PARTITIONS — BABY VERSION 👶
Micro-partitions are automatically created and managed by Snowflake; you don't manually create them.
Don't worry.
We're NOT going into advanced optimization today. 😂
Imagine you have:
1 BILLION rows
And you put everything into one giant box:
📦 1 BILLION ROWS
Finding specific data could be painful.
Instead, Snowflake organizes table data into smaller chunks:
📦 📦 📦 📦 📦 📦 📦 📦
These are micro-partitions.
Snowflake can use metadata about these partitions to help avoid scanning unnecessary data in many queries.
For example:
SELECT *
FROM SALES
WHERE SALE_DATE = '2026-09-23';
Snowflake can potentially eliminate micro-partitions that cannot contain matching values.
This is called partition pruning.
We'll go much deeper into this later.
________________________________________
🎯 1️⃣5️⃣ YOUR FIRST HANDS-ON CHALLENGE
🚨 Don't copy-paste the SQL. Type it yourself.
Enough watching me.
Now YOU do it. 😈
Challenge 1
Create:
Database
   ↓
Schema
   ↓
Warehouse
Challenge 2
Create this table:
CREATE TABLE CUSTOMERS (
    CUSTOMER_ID NUMBER,
    FIRST_NAME VARCHAR,
    LAST_NAME VARCHAR,
    EMAIL VARCHAR,
    CITY VARCHAR,
    COUNTRY VARCHAR
);
Challenge 3
Insert at least 5 customers.
I know…. You are the best…..
but I can understand you
Let me give you insert queries to run 😂😂

INSERT INTO CUSTOMERS
(CUSTOMER_ID, FIRST_NAME, LAST_NAME, EMAIL, CITY, COUNTRY)
VALUES
(101, 'Sajid', 'Abbas', 'sajid.abbas@example.com', 'Hyderabad', 'India'),
(102, 'Rahul', 'Sharma', 'rahul.sharma@example.com', 'Mumbai', 'India'),
(103, 'John', 'Smith', 'john.smith@example.com', 'New York', 'USA'),
(104, 'Emily', 'Johnson', 'emily.johnson@example.com', 'London', 'UK'),
(105, 'Aisha', 'Khan', 'aisha.khan@example.com', 'Dubai', 'UAE'); 
 
Challenge 4
Run:
SELECT *
FROM CUSTOMERS;
Challenge 5
Find the number of customers:
SELECT COUNT(*) FROM CUSTOMERS;
 
Challenge 6
Find customers by country:
SELECT COUNTRY, COUNT(*) FROM CUSTOMERS
GROUP BY COUNTRY;
 
Challenge 7 😈
Run:
SELECT
    CURRENT_USER(),
    CURRENT_ROLE(),
    CURRENT_DATABASE(),
    CURRENT_SCHEMA(),
    CURRENT_WAREHOUSE();
 

This is your first Day 1 proof of work. 📸
________________________________________
😈 INTERVIEW TRAPS
Now let's see whether you actually understood the concept.
Q1. If I suspend a Snowflake warehouse, will my data be deleted?
❌ No.
The warehouse is compute.
Your stored data remains in Snowflake storage.
________________________________________
Q2. What is a Virtual Warehouse?
A Virtual Warehouse is a cluster of compute resources used to execute queries and other workloads.
________________________________________
Q3. Why separate storage and compute?
It allows compute resources to be managed independently from data storage and helps support different workloads with flexible compute.
________________________________________
Q4. What are the three major architectural layers?
Storage
Compute
Cloud Services
________________________________________
Q5. Where does Snowflake store table data?
In Snowflake-managed storage, organized into micro-partitions.
________________________________________
Q6. What is a micro-partition?
A small, immutable unit of storage used by Snowflake to organize table data.
________________________________________
Q7. What happens when a warehouse is suspended?
Its compute resources stop running. Stored data is not deleted.
________________________________________
Q8. Database vs Schema?
Think:
Database
   ↓
Schema
   ↓
Tables / Views / Stages / etc.
🏢 Database = Building
📁 Schema = Department
🗃️ Table = Filing cabinet
😂 Now hopefully you'll never forget it.
________________________________________
🧠 DAY 1 — WHAT YOU SHOULD REMEMBER
If you remember only these 7 things today, that's enough:
1️⃣ Snowflake is a cloud data platform.
2️⃣ Snowflake separates storage and compute.
3️⃣ Storage stores the data.
4️⃣ Virtual Warehouses provide compute.
5️⃣ Cloud Services coordinate important platform operations.
6️⃣ Snowflake organizes table data into micro-partitions.
7️⃣ A warehouse can be suspended without deleting your stored data.

Concept	Think of it as
Database	🏢 Building
Schema	📁 Department
Table	🗃️ Organized records
Storage	🏭 Where data lives
Warehouse	💪 Compute
Cloud Services	🧠 Coordinator
Then:
Warehouse ≠ where your data is stored.

 	 DAY 1 FINAL CHALLENGE
Close this document.
Don't look at your notes.
Now explain Snowflake to a friend in 2 minutes.
Start with:
"Imagine you work for a company with 100 TB of data..."
Then explain:
Problem → Snowflake → Storage → Compute → Cloud Services
If you can explain it without reading...
🎉 DAY 1 COMPLETE.
If you still need to read every line...
😂 No problem. That's exactly why we're doing 30 days.
________________________________________
🚀 TOMORROW
DAY 2 — DATABASES, SCHEMAS, TABLES & VIEWS
We'll answer:
"Okay... I created a database. Now where exactly do I put my data?" 😂
And we'll start building our project properly.
Learn → Practice → Break → Fix → Understand → Share.
🥶 30 Days. One Snowflake journey.

