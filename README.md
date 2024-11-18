# Portfolio Website

This is the source code for my personal portfolio website. The site is hosted on **AWS S3**, with **Route 53** for DNS, and **CloudFront** for content delivery. The contact form uses **EmailJS** for handling form submissions.

## 🚀 Project Overview

- **Frontend**: HTML, CSS, and JavaScript.
- **Hosting**: AWS S3 with CloudFront and Route 53.
- **Domain**: Custom domain hosted on AWS.
- **Contact Form**: Integrated with EmailJS to handle form submissions.

---

## 🌐 Hosting on AWS

### How It Works
Here's a brief overview of how the different AWS services work together to host your portfolio site:

1. **S3 (Simple Storage Service)**:  
   Used to store your website files (HTML, CSS, JavaScript, images, etc.) and serve them as a static website.

2. **Route 53**:  
   Manages DNS settings for your custom domain, allowing your website to be accessible via a user-friendly URL (e.g., `www.yourdomain.com`).

3. **CloudFront (CDN)**:  
   Distributes your content globally, reducing latency and improving load times by caching your website’s files at edge locations around the world.

---

### 🌍 Deploying Your Site

#### Step 1: Upload Files to S3
1. Log in to the [AWS Management Console](https://aws.amazon.com/).
2. Go to **S3** and create a new bucket (if you don’t have one).
   - The bucket name should match your domain name (e.g., `www.yourdomain.com`).
3. Upload your website files (e.g., `index.html`, `contact.html`, `assets/`, etc.) to the bucket.
4. Configure your bucket for **Static Website Hosting**:
   - Go to the **Properties** tab.
   - Enable **Static website hosting**.
   - Set the **index document** to `index.html`.

#### Step 2: Set Up CloudFront
1. Go to the **CloudFront** console and create a new distribution.
2. Set the **Origin Domain** to your S3 bucket.
3. Configure the distribution settings to use **HTTPS**.
   - For **Cache Behavior**, set the default object to `index.html`.
   - Enable caching to improve load times.

#### Step 3: Configure Route 53
1. Go to **Route 53** and create a new hosted zone for your custom domain.
2. Create an **A record** pointing to your CloudFront distribution:
   - Choose **Alias** and select your CloudFront distribution.
3. If you're using a **www** subdomain, set up a **CNAME record** pointing to your main domain.

#### Step 4: SSL Certificate (Optional)
1. Go to the **AWS Certificate Manager** (ACM) to request an SSL certificate for your domain.
2. Use the certificate with your **CloudFront distribution** for secure HTTPS access.

---

## 🛠️ Additional Resources

- [AWS S3 Documentation](https://docs.aws.amazon.com/s3/)
- [AWS Route 53 Documentation](https://docs.aws.amazon.com/route53/)
- [AWS CloudFront Documentation](https://docs.aws.amazon.com/cloudfront/)
- [EmailJS Documentation](https://www.emailjs.com/docs/)

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).