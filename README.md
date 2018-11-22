# AWS Photobucket
[Advanced] AWS-sdk, s3, API Gateway, Lambda, Serverless, and ES6 Methods

## Prerequisites
  - Basic understanding of JSON data.
  - Basic understanding of AWS Lambda
  - Basic understanding of Amazon S3
  - Basic understanding of Amazon API Gateway
  - Basic understanding of Serverless 

## Objective

You will be creating a Lambda function that makes a request to a public S3 bucket that is full of random images. From there, you will be creating a client-side scripts to render the images when your Lambda function is executed. 

## Flow of Data
![AWS Diagram](https://i.imgur.com/wxx5zw2.png)

## Setup
 - Fork & clone repo.
 - Create file structure:
 ```
+ --public
    |
    +-- index.html
    +-- styles.css
    +-- app.js
```
 - Create Serverless boilerplate/template 
 - Run command to create `package.json` file
 - Install aws-sdk


## Instructions
1. Build AWS Lambda function that makes a GET request to S3 bucket `treasure-chest-capstone`.

2. Look for the correct aws-sdk s3 service in [documentation](https://docs.aws.amazon.com/AWSJavaScriptSDK/latest/AWS/S3.html#getBucketWebsite-property) method in your lambda function to list contents of public S3 bucket.

3. Allow CORS in your `serverless.yml`

4. Create header in your lambda function to allow CORS

5. You will be using the `Key` value from your API response to dynamically display all the images from public S3 bucket in your app.js

6. Use public S3 bucket image path to help you display all images `https://s3-us-west-2.amazonaws.com/treasure-chest-capstone/YOUR_RENDERED_KEY_HERE`.

7. Create a button. When user clicks the button, it should initiate an Axios GET request to your specific Lambda URL, which then triggers your specific lambda to make a request to the `treasure-chest-capstone` S3 bucket, then will dynamically display all the images from the public S3 bucket on to the client-side.

8. Use the aws-cli commands referenced below to enable static website hosting on ***YOUR*** S3 bucket. Then run appropriate command to sync your client-side files to your bucket(ie. html, css, js files). Your public url will be in the format of ```http://YOUR_BUCKET_NAME.s3-website-region.amazonaws.com/```. Test url in browser

**Create a bucket**
- Create a bucket using aws-cli https://docs.aws.amazon.com/cli/latest/reference/s3api/create-bucket.html
- Give your bucket a name `i-found-the-treasure-YOUR_NAME`

**Make Bucket A Static Website**
- Make your bucket static using aws-cli https://docs.aws.amazon.com/cli/latest/reference/s3/website.html

**Sync client-side files to Static Website Bucket**
```
aws s3 sync ./public s3://YOUR_BUCKET_NAME --acl public-read
```

### Resources
[AWS.S3 — AWS SDK for JavaScript](https://docs.aws.amazon.com/AWSJavaScriptSDK/latest/AWS/S3.html#getBucketWebsite-property)
