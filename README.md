# Dockerfile---Build-image-with-MySQL-schema
Steps to solve this assignment  -> 
1> Create a test.sql file and dockerfile in a folder.
2> Open terminal and type command.
    1. docker build -t dockerfile 	
       (This command builds Docker image from docker file)
    2. docker images 
       (Using this command check the docker image is created or not)
    3. docker run -itd assignment2
       (This command is used for launch docker container)
    4. docker ps
       (Using this command we can see which containers are in running state)
    5. docker exec -it 1624dfc27e02 bash
       (Using this command we can execute commands in running container)
    6. mysql -upucsd -ppucsd
       (Using this command we can open mysql shell)
    7. On MySQL Shell  : 
       1. show databases;
       2. use pucsdStudents;
       3. show tables;
       4. select * from studentData;

DockerFile 

FROM mysql
-> (it is the first command inside dockerfile. It defines image to start the build 	process.)
ENV MYSQL_ROOT_PASSWORD=swapnil77
ENV MYSQL_DATABASE=pucsdStudents
ENV MYSQL_USER=pucsd 
ENV MYSQL_PASSWORD=pucsd
-> (ENV command is used to set envoirment variables for docker container.)

COPY ./mysql/ /docker-entrypoint-initdb.d/
-> (This command copies local files into docker container.in our case it copies 	mysql file to docker container.)
