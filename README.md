# Using an AWS S3 trigger to create thumbnail image

We’ll set up and configure a Lambda function that automatically resizes images uploaded to an Amazon S3 bucket. Whenever a new image is added, Amazon S3 triggers the Lambda function, which then generates a thumbnail version of the image and saves it to another S3 bucket.
