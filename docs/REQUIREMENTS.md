# infrastructure

## App dependencies

- bcryptjs
- jsonwebtoken
- dotenv
- email-validator
- express
- pg
- sequelize
- angular
- jasmine
- eslint
- codelyzer
- karma

## RDS infrastructure

first create database,
the type of database is postgres
and make templates free tier

## S3 infrastructure

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

first create a repository with the eb init command

```
eb init aws-circle-ci-api --platform node.js --region us-east-1
```

then create an environment running a sample application with the eb create command

```
eb create aws-circle-ci-api-dev
```

## Pipeline infrastructure

create `.circleci/config.yml` file
and make the configuration steps for install dependencies, build for front-end and api and Deploy the app
then push it in github repo and open circle ci for deploy the app

and see the screenshots in screenshots dir
