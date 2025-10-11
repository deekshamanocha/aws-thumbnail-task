# Using  AWS S3 trigger to create thumbnail image

We create and configure a Lambda function that resizes images added to an Amazon Simple Storage Service (Amazon S3) bucket. When you add an image file to your bucket, Amazon S3 invokes your Lambda function. The function then creates a thumbnail version of the image and outputs it to a different Amazon S3 bucket.

In order to set up the workflow, you need to have the following:

1. An AWS Account 
2. Terraform is installed on the machine.

To complete this project, we need to carry out the following steps:

1. Create source and destination Amazon S3 buckets and upload a sample image.
2. Create a Lambda function that resizes an image and outputs a thumbnail to an Amazon S3 bucket.
3. Configure a Lambda trigger that invokes your function when objects are uploaded to your source bucket.
4. Test your function, first with a dummy event, and then by uploading an image to your source bucket.

By completing these steps, we’ll learn how to use Lambda to carry out a file processing task on objects added to an Amazon S3 bucket:

1. First create two Amazon S3 buckets. The first bucket is the source bucket we will upload your images to. The second bucket is used by Lambda to save the resized thumbnail when you invoke your function.

2. Later we’ll test our Lambda function by invoking it using the AWS CLI or the Lambda console. To confirm that our function is operating correctly, our source bucket needs to contain a test image. This image can be any JPG or PNG file we choose.

3. We'll start by defining a permissions policy that allows our Lambda function to interact with other AWS resources. In this setup, the policy provides read and write access to specific Amazon S3 buckets and grants permission to write logs to Amazon CloudWatch.

4. Next, we'll create an IAM execution role for our Lambda function. This role defines what actions our function can perform on AWS services. 

5. We'll prepare a deployment package containing our function’s source code and all necessary dependencies. For the image resizing functionality, include the required image-processing library.

5. We can deploy the function using either the AWS Command Line Interface (CLI) or the AWS Management Console. We'll use the deployment package we created in the previous step to define our Lambda function.

6. To automatically run Lambda function when a new image is uploaded, configure an Amazon S3 trigger. This trigger can also be set up via the AWS CLI or console and links our source S3 bucket with the Lambda function.

7. Before testing the full setup, invoke Lambda function manually with a sample event to ensure it runs as expected. Lambda events are JSON documents that include key details such as the bucket name, ARN, and object key.

8. Once the function works correctly, upload an image to the source S3 bucket to test the complete workflow. The upload should automatically invoke the Lambda function, which will generate a resized version of the image and store it in the target S3 bucket.
