# BVA505E-Containers
Container environments for Database Management and Big Data (BVA505E) course @ ITU


## Usage

### MySQL

1. Install Docker. Instructions can be found in the given links.
- [Docker Desktop for MAC](https://docs.docker.com/desktop/install/mac-install/)
- [Docker Desktop for Windows](https://docs.docker.com/desktop/install/windows-install/)
- [Docker Desktop for Ubuntu](https://docs.docker.com/desktop/install/ubuntu/)
- [Docker Engine for Ubuntu](https://docs.docker.com/engine/install/ubuntu/)

In order to execute Docker commands without root privileges add your host computer user to the docker group.

2. Download or copy the corresponding docker compose yaml file.

3. Create a folder for persistant storage of MySQL database.

4. Edit the docker compose file according to instructions given in the comments.

5. Using the cli (terminal) execute the following command in the same directory as the docker compose file **only for the first time**.

For X86 systems:
```
docker compose -f mysql_docker_compose_x86.yml up -d
```

For ARM systems:
```
docker compose -f mysql_docker_compose_arm.yml up -d
```

6. Using the cli access the created container using the following command:
```
docker exec -it mysql_bva505e bash
```

7. After the initial setup to restart the container execute the following:
```
docker start mysql_bva505e
```

#### Adding an existing database

1. To add an existing database for access inside the MySQL server, copy the database file from the host computer to the container using the following command:
```
docker cp /path/to/existing/database.sql mysql_bva505e:/var/lib/mysql/
```

2. Then add the file to the MySQL server while inside the container shell using the next command:
```
mysql -h localhost -P 3306 -p < /var/lib/mysql/database.sql
```

3. You will be prompted to enter a password, which was specified in the docker compose file during the setup process.

#### Connecting to the MySQL server using a local instance of DBeaver

1. Click on the plug icon with a plus sign on the top left corner of the window and specify the connection as a MySQL connection.

2. Use the following to fill out the required fields:

+ **Server Host:** localhost
+ **Port:** 3306
+ **Database:** Name of the database uploaded
+ **Username:** root
+ **Password:** password specified inside the docker compose file (by default: password)

**Optional** - Click on connection details button to specify a unique name for the connection.

3. In the driver properties section set the **allowPublicKeyRetrieval** value to **true**.

4. Click on finish to complete the setup process. The database should be available on the database connection directory on the left.
