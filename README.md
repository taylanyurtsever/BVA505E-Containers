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