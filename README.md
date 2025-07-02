## 📐 Serverless Rectangle Area Calculator (AWS)

This project is a fully **serverless web application** built on **AWS** that calculates the **area of a rectangle** based on user input. 
It demonstrates the use of AWS services such as **Lambda**, **API Gateway**, **S3**, and **IAM** to build a secure, scalable, and event-driven application.

## 🚀 Features

- 📦 **Frontend** hosted on **Amazon S3** with static website hosting.
- ⚙️ **Python-based AWS Lambda function** to calculate area from user-submitted JSON payload.
- 🔁 **API Gateway REST API** triggers Lambda function on HTTP POST requests.
- 🔐 **IAM roles and permissions** configured for secure integration between services.
- 🌐 Global accessibility with low-cost, high-availability serverless architecture.

## 🧰 Tech Stack

- **AWS Lambda** (Python 3.9)
- **Amazon API Gateway** (REST API)
- **Amazon S3** (Static Website Hosting)
- **IAM Roles and Policies** (Least Privilege Access)
- **HTML, CSS, JavaScript** (Frontend)

## 🖼️ Architecture Diagram

```plaintext
User ➜ S3 (Frontend) ➜ API Gateway ➜ Lambda ➜ JSON Response
```



📂 Project Structure

```
├── index.html             # Frontend UI (S3 hosted)
├── lambda_function.py     # Lambda function to calculate area
├── README.md              # Project documentation
└── images/                # Screenshots, architecture diagrams, etc.
    ├── architecture.png
    ├── demo-ui.png
    └── *.png


```


## ⚙️ Deployment Instructions
1️⃣ **Set Up the Lambda Function**
Go to AWS Console → Lambda → Create Function → Author from scratch

Runtime: Python 3.9

Paste your function code into the lambda_function.py editor

Save and deploy the function


![App Screenshot](https://github.com/AvinashSaxena17/Area-of-rectangle-app/blob/main/images/lambda%20function.png)




![App Screenshot](https://github.com/AvinashSaxena17/Area-of-rectangle-app/blob/main/images/Testing-1.png)


![App Screenshot](https://github.com/AvinashSaxena17/Area-of-rectangle-app/blob/main/images/Testing-2.png)



2️⃣ **Create API Gateway (REST API)**
Go to AWS Console → API Gateway → Create API → REST API

Create a POST method and integrate it with your Lambda function

Enable CORS for the POST method (POST + OPTIONS)

Deploy the API to a new stage (e.g., production)

Copy the Invoke URL and paste it into your index.html file:



![App Screenshot](https://github.com/AvinashSaxena17/Area-of-rectangle-app/blob/main/images/API%20Gateway%20architecture.png)




![App Screenshot](https://github.com/AvinashSaxena17/Area-of-rectangle-app/blob/main/images/POST%20methods.png)

3️⃣ **Host Frontend on Amazon S3**
Go to AWS Console → S3 → Create Bucket

Uncheck "Block all public access"

Go to Properties → Enable Static Website Hosting

Upload your index.html file

Set public access via Bucket Policy:

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicRead",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}

```

4️⃣ **Access the Application**
Visit the S3 static website endpoint URL to access your live web app.


![App Screenshot](https://github.com/AvinashSaxena17/Area-of-rectangle-app/blob/main/images/Static%20website%20hosting.png)



5️⃣ ✅ **Application is Live**

Your serverless web application is now live and fully functional.
Test it by entering values on the web page — the Lambda function will calculate the area and return results instantly via API Gateway.

![App Screenshot](https://github.com/AvinashSaxena17/Area-of-rectangle-app/blob/main/images/App%20run.png)





## 🚀 Future Enhancements
💾 Store calculation history using Amazon DynamoDB

🔧 Implement CI/CD pipeline using GitHub Actions or AWS CodePipeline

🔐 Add rate limiting or authentication for API access


