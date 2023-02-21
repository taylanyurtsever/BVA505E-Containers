# BVA505E-Containers
Container environments for Database Management and Big Data (BVA505E) course @ ITU


## Usage

### MySQL

1. Install Docker. Instructions can be found in the given links.
- [Docker Desktop for MAC](https://docs.docker.com/desktop/install/mac-install/)
- [Docker Desktop for Windows](https://docs.docker.com/desktop/install/windows-install/)
- [Docker Desktop for Ubuntu](https://docs.docker.com/desktop/install/ubuntu/)
- [Docker Engine for Ubuntu](https://docs.docker.com/engine/install/ubuntu/)

2. Download or copy the corresponding docker compose yaml file.

3. Using the cli (terminal) execute the following command in the same directory as the docker compose file:
```
docker compose -f mysql-compose.yml up
```
