# star-agile-insurance-project

This project will help you to understand various concept related to Insurace domain. Please read the Insurace-domain.pdf to get more functional knowledge on 
Insurace domain. 

This project front is based on simple HTML, CSS and Angular Js ad Backend is Java Spring Boot.

In order to run the application use port 8081..
# InsureMe

Spring Boot Insurance Application with MySQL and Docker.

## Technologies

- Java 11
- Spring Boot 2.7.4
- Maven
- MySQL 8
- Docker
- GitHub

## Docker Image

sourav16031998/insure-me:1.3

## Database

Database: insuredb

Tables:
- policy
- contact
- hibernate_sequence

## Run MySQL

docker network create insure-network

docker volume create mysql-data

docker run -d `
  --name mysql `
  --network insure-network `
  -e MYSQL_ROOT_PASSWORD=root `
  -e MYSQL_DATABASE=insuredb `
  -e MYSQL_USER=insure `
  -e MYSQL_PASSWORD=insure123 `
  -v mysql-data:/var/lib/mysql `
  -p 3306:3306 `
  mysql:8.0

## Run Application

docker run -d `
  --name insure `
  --network insure-network `
  -p 8080:8081 `
  -e SPRING_DATASOURCE_URL="jdbc:mysql://mysql:3306/insuredb" `
  -e SPRING_DATASOURCE_USERNAME="insure" `
  -e SPRING_DATASOURCE_PASSWORD="insure123" `
  sourav16031998/insure-me:1.3

## Access

http://localhost:8080

## Contact API

POST /contact

GET /contacts
docker exec -it mysql mysql -u insure -p

Password:

insure123

Then:

USE insuredb;

SELECT * FROM contact;
