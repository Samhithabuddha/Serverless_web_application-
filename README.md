# Greeting App with AWS Lambda View Counter

## Overview
This is a simple web application that greets the user by their name and tracks the total number of visits using AWS Lambda and DynamoDB. It demonstrates a serverless architecture with frontend interactivity and backend cloud integration.

- Users can enter their name in a form and receive a personalized greeting.
- The application tracks the number of views using a DynamoDB table updated via an AWS Lambda function.

## Features
- **Personalized Greeting:** Users receive a greeting message when they submit their name.
- **Serverless View Counter:** Total page views are stored and updated in DynamoDB via AWS Lambda.
- **Responsive UI:** Clean and simple design using HTML and CSS.
- **Asynchronous Updates:** Views counter updates dynamically without refreshing the page.

## Technologies Used
- **Frontend:** HTML, CSS, JavaScript
- **Backend:** AWS Lambda (Python)
- **Database:** AWS DynamoDB
- **Deployment:** Serverless API Gateway/Lambda URL

## File Structure
├── index.html # Main HTML file
├── style.css # CSS styling
├── script.js # Frontend JavaScript
├── lambdaFunction.py # AWS Lambda function to update and fetch views


## Installation & Setup

1. **Clone the Repository**
   ```bash
   git clone <repository-url>
   cd <repository-folder>
   
## Set Up DynamoDB

1. Create a DynamoDB table named `serverless-web-application-on-aws`.
2. Add a primary key `id` (String) and create an initial item:
```json
{
  "id": "0",
  "views": 0
}

## Set Up DynamoDB

1. Use the provided `lambdaFunction.py`.
2. Ensure it has access to the DynamoDB table.
3. Enable a Lambda URL to serve the frontend request.

## Connect Frontend

1. Update `script.js` with your Lambda URL:
```javascript
let response = await fetch("YOUR_LAMBDA_URL_HERE");

## **Run Locally**

1. Open `index.html` in a browser to test the greeting form and view counter.

## **How It Works**

### **1. User Interaction**
- The user enters their name in the form and clicks "Submit".
- JavaScript intercepts the form submission, prevents page reload, and displays a personalized greeting.

### **2. View Counter**
- On page load, `script.js` calls the AWS Lambda endpoint.
- Lambda fetches the current number of views from DynamoDB, increments it by one, and returns the updated count.
- The frontend dynamically updates the "Views" counter.

### **3. Serverless Backend**
- `lambdaFunction.py` interacts directly with DynamoDB using Boto3.
- No traditional server is required, making the application fully serverless.

## **Future Improvements**
- Add **input validation** to prevent empty names.
- Show **greeting history** for multiple users.
- Implement **persistent user sessions** for personalized experiences.
- Enhance styling and responsiveness for mobile devices.

## **Author**
**Samhitha Buddha**  
B.Tech Computer Science – 2026  
[GitHub](https://github.com/your-github-profile)
