
# Deploying Wiki.js on Elastic Beanstalk


* Official documentation: https://wiki.js.org/

* Docker image: https://hub.docker.com/r/requarks/wiki/

* Steps to deploy in AWS: ( Beanstalk in particular ) 

(A) Create a postgres Database [1]. Make sure to create "initial database" in the "Additional Configuration" tab.
(B) Launch Sample beanstalk environment with a sample application. Make sure to choose platform as "single docker". ( Create this without a coupled Database )[2]
(C) Set the environment variables in Beanstalk and update[3]
-----------------------------------
DB_TYPE: postgres
DB_HOST: < your RDS endpoint >
DB_PORT: 5432
DB_NAME: < name of your initial database >
DB_USER: < name of your DB user >
DB_PASS: < DB passowrd >
DB_SSL: false
----------------------------------
(D) Have the contents in this repository in a directory => zip it => "Upload and deploy" on Beanstalk environment.

Links:
---------
[1]https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_CreateDBInstance.html
[2]https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/using-features.environments.html
[3]https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/environments-cfg-softwaresettings.html#environments-cfg-softwaresettings-console
