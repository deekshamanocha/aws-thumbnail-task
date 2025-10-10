# Using an AWS S3 trigger to create thumbnail image

We create and configure a Lambda function that resizes images added to an Amazon Simple Storage Service (Amazon S3) bucket. When you add an image file to your bucket, Amazon S3 invokes your Lambda function. The function then creates a thumbnail version of the image and outputs it to a different Amazon S3 bucket.

In order to set up the workflow, you need to have the following:

1. An AWS Account 
2. Terraform is installed on the machine.

To complete this project, we need to carry out the following steps:

1. Create source and destination Amazon S3 buckets and upload a sample image.
2. Create a Lambda function that resizes an image and outputs a thumbnail to an Amazon S3 bucket.
3. Configure a Lambda trigger that invokes your function when objects are uploaded to your source bucket.
4. Test your function, first with a dummy event, and then by uploading an image to your source bucket.

By completing these steps, we’ll learn how to use Lambda to carry out a file processing task on objects added to an Amazon S3 bucket. 

First create two Amazon S3 buckets. The first bucket is the source bucket we will upload your images to. The second bucket is used by Lambda to save the resized thumbnail when you invoke your function.
Later we’ll test our Lambda function by invoking it using the AWS CLI or the Lambda console. To confirm that our function is operating correctly, our source bucket needs to contain a test image. This image can be any JPG or PNG file we choose.
