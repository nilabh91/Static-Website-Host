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

# Second Step
1. It's time to create S3 bucket , remember to create a S3 with your domain like it is domain.com
2. Here do not allow public access.
3. After you can upload your static website file.
4. <img width="696" alt="Screenshot 2024-04-25 at 8 14 14 PM" src="https://github.com/nilabh91/Static-Website-Host/assets/153995859/107b7409-d560-4ec0-88ed-a30c0b2bba03">

5. Here under the properties section , you will find out static web hosting part:

6. <img width="696" alt="Screenshot 2024-04-25 at 11 02 24 PM" src="https://github.com/nilabh91/Static-Website-Host/assets/153995859/bdd8d4fd-2208-4f0f-aae9-4b1e1671a47b">

7. Make changes as , Enable static web hosting , put document root file like index.html and make changes.
8. Under Static website hosting, note the Endpoint.The Endpoint is the Amazon S3 website endpoint for your bucket.


# Third Step
1. Go to AWS Cloudfront Service.
2. Choose Create distribution Option.
3. Here Hoose your S3 bucket option in origin domain.
4. For Origin access, select Legacy access identities. For the Origin access identity, you can choose from the list, or choose Create new OAI (both will work).
   For Bucket policy, select Yes, update the bucket policy.
5. Under Viewer, set Viewer protocol policy to Redirect HTTP to HTTPS.
6. Under Cname give like www.domain.com if you want . Select the SSL certificate that we created . Remember to add default root object as index.html . Create distribution .
7. Wait for its deployment as it will around each and every edge location at every region.
8. After deployment , can use DNS of cloudfront to check whether your site is accessable or throwing error like 404 or 403. If yes then rectify it.

# Fourth step
1. This is the last step where we can create a record in ROUTE 53 for our Cloudfront DNS.
2. <img width="1064" alt="Screenshot 2024-04-25 at 11 32 58 PM" src="https://github.com/nilabh91/Static-Website-Host/assets/153995859/955c9cfd-4ad1-4a6e-b1c4-e61dfa6e8140">
Choose your distribution and create records.
3. Now access your website through your domain name.


# REFERENCE
[
](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/getting-started-cloudfront-overview.html)
