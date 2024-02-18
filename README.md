# AWSWebsiteHostingProject
Creating the AWS Architecture for Hosting a static website on AWS using Amazon S3, Route 53,  CloudFront and SSL Certification (Certification Manager)

![Screenshot 2024-02-18 at 9 14 59 PM](https://github.com/keys7/AWSWebsiteHostingProject/assets/101874897/867ca192-768b-4b2d-9762-58a6fac60d84)


From the above Architecture we can clearly say's that we having a limites AWS Services in use like (AWS S3, AWS CloudFront, AWS Certification for SSL and AWS Route 53).

# AWS S3
This is the service is used to creat a bucket in which we uploading all the content of static website and enabling the public access to so that we can connect the index.html bucket url to the aws cloudfront and aws route 53. 

![Screenshot 2024-02-18 at 9 06 10 PM](https://github.com/keys7/AWSWebsiteHostingProject/assets/101874897/d9aee5f5-3936-48b1-b25c-98a1b836c692)

after uploading all the required file's in the bucket now we need to set the S3 policy:-

Amazon S3 Bucket Policy code:
{
    "Version": "2012-10-17",
    "Statement": [
       {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::yourdomainnamehere.com/*"
        }
    ]
}

edit the yourdomainnamehere.com accourding to your folder/bucket name.

# AWS Route 53
This is the service of aws that provides the connectivity and DNS servers accouding to the requirements and in this if you have your own Domain name hostel in any other third-party domain regist we need to edit the DNS Servers from aws to hosted domain platform.


# AWS CloudFront
This is the service tof aws for Content Delivery Service that help to deliver our content to all over the world by creating the Distribuation.

1. will request for the SSL Certification from Certification Manager for both Sub-Domain and Apex Domain.
2. there si the option for creating the CNAME Record in Route 53
3. now after creating the Distribuation in cloudFront we can copy the Domain Name from cloudFront and form the A Record in aws Route 53 (Alias Target).

# Final Website Hosted using AWS Services


https://github.com/keys7/AWSWebsiteHostingProject/assets/101874897/fabbd54d-d870-4d57-8154-1e0b007255c9





