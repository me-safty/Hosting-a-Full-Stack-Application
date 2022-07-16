# Pipeline process

we use in the environment :
- node@5.0.2
- aws-cli@3.1.1
- aws-elastic-beanstalk@2.0.1

jobs :
  we need for jobs node-version: '14.15'
  and we have tow jobs :
  - build
    in the build we run scripts that install the dependencies and build for front-end and api
  - deploy
    in the deploy we run scripts that deploy front-end and api

workflows :
  we need for workflows :
  - node-version: '14.15' 
  - aws-cli/setup
  - eb/setup  

  the workflows we have :
  - build 
    the build with filter that allow for main branche only to build 
  - hold 
    the hold of type approval with filter that allow for main branche only to run it and require build
  - deploy
    the deploy that require hold to run deploy job 

### get started

create `.circleci/config.yml` file
and make the configuration steps for install dependencies, build for front-end and api and Deploy the app
then push it in github repo and open circle ci for deploy the app

and see the screenshots in screenshots dir
