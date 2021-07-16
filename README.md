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

## How stop the containers
Inside the folder you cloned the repository run the next command:
```
docker-compose down
```

## Verify if the containers are running
After run the cantainers with **docker-compose up -d** verify the containers are runnig with:
```
docker ps
```
Output:
```
CONTAINER ID   IMAGE                                         COMMAND                  CREATED         STATUS         PORTS                                                                                      NAMES
725b752f716a   sonarqube                                     "bin/run.sh bin/sona…"   9 minutes ago   Up 9 minutes   0.0.0.0:9000->9000/tcp, :::9000->9000/tcp                                                  sonar_compose
71d053c315a1   postgres                                      "docker-entrypoint.s…"   9 minutes ago   Up 9 minutes   5432/tcp                                                                                   postgres_compose
ac33c5d2b12e   juniorrodriguez/multistage:junior.rodriguez   "flask run --port=88…"   9 minutes ago   Up 9 minutes   0.0.0.0:8888->8888/tcp, :::8888->8888/tcp                                                  python_app_compose
d80fa0d3b282   sonatype/nexus3                               "sh -c ${SONATYPE_DI…"   9 minutes ago   Up 9 minutes   0.0.0.0:8081->8081/tcp, :::8081->8081/tcp                                                  nexus_compose
7ccdecd595f7   jenkins/jenkins                               "/sbin/tini -- /usr/…"   9 minutes ago   Up 9 minutes   0.0.0.0:8080->8080/tcp, :::8080->8080/tcp, 0.0.0.0:50000->50000/tcp, :::50000->50000/tcp   jenkins_compose

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
To verify if the service is working correctly run the next commands.

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
Once you find the string try again in the web browser.