# Static-Website-Host
This repository is about hosting a static website from AWS S3 bucket using AWS Cloudfront  service.By the end of this project you will be able to see your website using your domain.

# Prerequisites
1. Have a registered Domain.
2. Knowledge about AWS S3 bucket.
3. Knowledge about AWS Cloudfront.
4. Knowledge about AWS ACM (Amazon Certificate Manager).
5. Knowledge about AWS Route 53.

# First Step
1. Go to your favourite domain provider and purchase a damain as per your need.
2. Now create a AWS account and under that go to ACM or CM (Certificte Manager) service , request a certificate for you domain.
3. After request , It will show you pending status. Now under the certificate Id , click on the create records into route 53. It will still show you pending status untill we make hosted zone for our domain in the Route 53.
4. Next go to Route 53 and create a hosted zone for your domain . After creating it, copy the "ns" records to your domain provider dns nameserver and save changes. Remember to delete the already existing dns records.
