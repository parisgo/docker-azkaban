1: Build the image executor

    docker build --rm -t azkaban-executor .

2: Build the image webserver

    docker build --rm -t azkaban-webserver .

3: Start containers

    docker-compose up -d

![](https://raw.githubusercontent.com/parisgo/docker-azkaban/master/docs/images/Capture00.JPG)

4: Copy and initialize database (azkaban-db-3.57.0.tar.gz / create-all-sql.sql)

    docker cp create-all-sql.sql mysql:/
    mysql -uroot -ptest azkaban < create-all-sql.sql

5: Access the web UI :
[https://127.0.0.1:8443](https://127.0.0.1:8443)  
username: azkaban  
password: azkaban

![](https://raw.githubusercontent.com/parisgo/docker-azkaban/master/docs/images/Capture01.JPG)

6: Create project for test

    #command.job
    type=command
    command=echo 'hello azk'

![](https://raw.githubusercontent.com/parisgo/docker-azkaban/master/docs/images/Capture02.JPG)

![](https://raw.githubusercontent.com/parisgo/docker-azkaban/master/docs/images/Capture03.JPG)