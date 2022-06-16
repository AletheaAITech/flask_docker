
# _Dockerizing a Flask application with a MySQL Database_

## Technologies Used

* Python
* docker
* docker-compose

# _Setup/Installation Requirements_

# You can run the code by using any one of the following ways:

## 1.Using docker

- Download or clone the code: https://github.com/ajayjatav777/flask_docker.git
- Install the dependencies.
- build docker image:
	- sudo docker build -t flask-mysql-docker-api -f Dockerfile .
- run docker image:
	- sudo docker run --rm -d --network mysqlnet --name rest-server -p 8000:5000 flask-mysql-docker-api
- configure and run a database in a container by using the following commands:
	- sudo docker volume create mysql
	- sudo docker volume create mysql_config
	- sudo docker network create mysqlnet
	- sudo docker run --rm -d -v mysql:/var/lib/mysql -v mysql_config:/etc/mysql -p 3306:3306 --network mysqlnet --name mysqldb -e MYSQL_ROOT_PASSWORD=p@ssw0rd1 mysql	

- Now you can browse here:
  - http://localhost:8000/dbinit
  - http://localhost:8000/getdata
	
## 2.Using docker-compose

- Download or clone the code: https://github.com/ajayjatav777/flask_docker.git
- Install the dependencies.
- build and run containers:
	- sudo docker-compose -f docker-compose.dev.yml up --build

## 3. Pull our image from the docker hub

- to pull an image write the following command in terminal
	- sudo docker pull webtunixdc/flask-mysql-docker-api:latest
- run docker image:
	- sudo docker run --rm -d --network mysqlnet --name rest-server -p 8000:5000 flask-mysql-docker-api
- configure and run a database in a container by using the following commands:
	- sudo docker volume create mysql
	- sudo docker volume create mysql_config
	- sudo docker network create mysqlnet
	- sudo docker run --rm -d -v mysql:/var/lib/mysql -v mysql_config:/etc/mysql -p 3306:3306 --network mysqlnet --name mysqldb -e MYSQL_ROOT_PASSWORD=p@ssw0rd1 mysql	

- Now you can browse here:
  - http://localhost:8000/dbinit
  - http://localhost:8000/getdata


	
