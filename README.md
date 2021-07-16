# docker-compose Example
This is a repository with one example about docker-compose

In this repository is setted the next services:

- Jenkins
- Nexus
- Pythonapp
- Postgres
- Sonarqube

## Requirements
Is a prerequisite the next:
- docker
- docker-compose

## Verivy the requirements
Run the next commands:

Input:
```
docker --version
```
Output:
```
Docker version 20.10.7, build f0df350
```

Input:
```
docker-compose -version
```
Output:
```
docker-compose version 1.29.2, build 5becea4c
```
## How run the containers
Only clone the repository and run the command:
```
docker-compose up -d
```

## Verify if the containers are running
After run the cantainers with **docker-compose up -d** verify the containers are runnig with:
```
docker-compose up 
```
Output:
```
```

## Verify the applications in the browser
Open your web browser and enter the following URLs:
- Jenkins:
```
localhost:8080
```
- Nexus:
```
localhost:8081
```
- Pythonapp:
```
localhost:8888
```
- EndPoint of Python App:
```
localhost:8888/docker
```
- Sonarqube:
```
localhost:9000
```

# Troubleshooting Nexus
Sometimes the container of Nexus is up but the service is down when try to see the service in a web browser.
To verify if the service is working correctly run the next commands:
To see the logs of container:
```
docker logs nexus_compose
```
In the output should be see the next string:
```
-------------------------------------------------

Started Sonatype Nexus OSS 3.32.0-03

-------------------------------------------------
```
After that try again in the web browser.