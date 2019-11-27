# Wordpress Deployment with Docker & AWS Elastic Beanstalk

> mkdir ~/wordpress/
> cd ~/wordpress/
#### :whale: Wordpress with Docker 
##### :unicorn: Download and run Mariadb latest on docker 
`docker run -e MYSQL_ROOT_PASSWORD=(dbpassword) -e MYSQL_DATABASE=wordpress --name wordpressdb -v "$PWD/database":/var/lib/mysql -d mariadb:latest`

##### :unicorn: Download wordpress image and run on docker 
`docker run -e WORDPRESS_DB_PASSWORD=(dbpassword) --name wordpress --link wordpressdb:mysql -p 80:80 -v "$PWD/html":/var/www/html -d wordpress`

---
#### :whale: Wordpress with Docker Compose
`cd ~/wordpress/`
##### :unicorn: Docker compose up & down  
`docker-compose up -d`

`docker-compose down --volume`

---
#### :whale: Wordpress with AWS Elastic Beanstalk 
###### :unicorn: Install/Configure AWSCLI and EBCLI

`cd ~/wordpress/`
###### :unicorn: Prepare eb environment and **Dockerrun.aws.json** file
`eb init`

`eb create wordpress-eb-env`





