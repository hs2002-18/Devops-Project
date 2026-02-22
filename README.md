# Static Website Hosting on AWS S3 using GitHub Actions

This project demonstrates how to automatically deploy a static website to an AWS S3 bucket using a GitHub Actions CI/CD pipeline. The website consists of HTML, CSS, and JavaScript files, and deployment is triggered whenever changes are pushed to the repository.

## Features

* Static website hosting on AWS S3
* Automated deployment using GitHub Actions
* Secure AWS credential management using GitHub Secrets
* Continuous Integration and Continuous Deployment (CI/CD)
* Fast and cost-effective hosting solution

## Technologies Used

* AWS S3 (Static Website Hosting)
* GitHub Actions (CI/CD)
* YAML
* HTML
* CSS
* JavaScript
* Linux

## Architecture

Developer → GitHub Repository → GitHub Actions → AWS S3 Bucket → Website

## Prerequisites

* AWS Account
* S3 Bucket configured for static website hosting
* IAM User with S3 permissions
* GitHub Repository
* Git installed

## Setup Instructions

1. Clone the repository

git clone https://github.com/your-username/repository-name.git

2. Create an S3 bucket

* Enable static website hosting
* Upload permissions for public access (if required)

3. Configure GitHub Secrets

Go to:

Repository → Settings → Secrets → Actions

Add the following secrets:

* AWS_ACCESS_KEY_ID
* AWS_SECRET_ACCESS_KEY

4. Update Bucket Name

Modify the bucket name inside the workflow YAML file:

aws s3 sync . s3://your-bucket-name --delete

5. Push Code

git add .
git commit -m "Deploy website"
git push origin master

The website will automatically deploy to S3.

## CI/CD Workflow

The GitHub Actions workflow performs the following steps:

1. Checks out repository code
2. Configures AWS credentials securely
3. Syncs project files to the S3 bucket
4. Deletes old files from the bucket if removed from repo

## Project Structure

.
├── index.html
├── style.css
├── script.js
└── .github/workflows/deploy.yml

## Future Improvements

* Add CloudFront CDN
* Add custom domain with Route 53
* Add HTTPS using ACM
* Add automated testing before deployment

## Author

Harsh
