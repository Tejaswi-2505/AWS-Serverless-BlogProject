# AWS Serverless Blog

This is a simple serverless blog application built using AWS services including DynamoDB, Lambda, API Gateway, IAM, and S3 for static website hosting.

## Features
- Create and store blog posts using DynamoDB.
- Retrieve blog posts using API Gateway and Lambda.
- Host the frontend on S3.
- Secure API access with IAM roles.

## Architecture
1. **Frontend:** HTML, JavaScript hosted on S3.
2. **Backend:** AWS Lambda with Node.js using the AWS SDK.
3. **Database:** Amazon DynamoDB for storing blog posts.
4. **API Gateway:** Exposes RESTful endpoints for the frontend.
5. **IAM:** Provides necessary permissions.

## Setup & Deployment

### 1. Clone the repository
```sh
git clone https://github.com/yourusername/aws-serverless-blog.git
cd aws-serverless-blog
```

### 2. Deploy the backend
- Create a DynamoDB table (`BlogDB`) with `id` as the primary key.
- Deploy Lambda function with the provided code.
- Configure API Gateway to trigger the Lambda function.
- Ensure IAM roles allow Lambda to access DynamoDB.

### 3. Deploy frontend to S3
- Enable static website hosting on S3.
- Upload `index.html` and related files to the S3 bucket.
- Update the API URL in `index.html`.

### 4. Optional: Set up CloudFront for CDN
- Create a CloudFront distribution pointing to the S3 bucket.

## Usage
- Open the S3-hosted URL in a browser.
- Write a blog post and submit it.
- View existing posts dynamically fetched from DynamoDB.

## Troubleshooting
- Ensure IAM roles have correct permissions.
- Check API Gateway logs if Lambda is not responding.
- Verify S3 bucket policy allows public access (if needed).
