# infrastructure

## RDS infrastructure

Amazon Relational Database Service (Amazon RDS) is a collection of managed services that makes it simple to set up, operate, and scale databases in the cloud.

### get started

first create database,
the type of database is postgres
and make templates free tier

## S3 infrastructure

Amazon Simple Storage Service (Amazon S3) is an object storage service that offers industry-leading scalability, data availability, security, and performance. 

### get started

first create bucket from cli
make aws configure and run the following command

```
aws s3api create-bucket --bucket my-bucket --region us-east-1
```

then edit bucket Policy like the following json file

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": [
                "s3:GetObject"
            ],
            "Resource": [
                "arn:aws:s3:::safty-bucket-1/*"
            ]
        }
    ]
}
```

## Elastic Beanstalk infrastructure

AWS Elastic Beanstalk is an easy-to-use service for deploying and scaling web applications and services developed with Java, .NET, PHP, Node.js, Python, Ruby, Go, and Docker on familiar servers such as Apache, Nginx, Passenger, and IIS.

You can simply upload your code and Elastic Beanstalk automatically handles the deployment, from capacity provisioning, load balancing, auto-scaling to application health monitoring.

### get started

first create a repository with the eb init command

```
eb init aws-circle-ci-api --platform node.js --region us-east-1
```

then create an environment running a sample application with the eb create command

```
eb create aws-circle-ci-api-dev
```