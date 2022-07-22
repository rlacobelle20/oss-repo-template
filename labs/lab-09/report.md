## example00
```docker run docker/whalesay cowsay boo```
![image](https://user-images.githubusercontent.com/44063772/180462379-3c0ced5f-0771-4f64-ac10-4dec230dd634.png)

## example01
```docker run -it ubuntu bash```
![image](https://user-images.githubusercontent.com/44063772/180463974-e641f1b0-188f-4b08-a47b-2537642b8864.png)
```
apt install vim
vim --version
```
![image](https://user-images.githubusercontent.com/44063772/180464276-d800aed1-c7ac-45cd-862a-2db4d2a095e9.png)
``` sudo apt install cowsay ```
![image](https://user-images.githubusercontent.com/44063772/180464861-4ebfbd8e-8622-4661-896a-04ae69d0ddea.png)
![image](https://user-images.githubusercontent.com/44063772/180465877-f3692f21-5a5e-409b-aaba-c74ab1b7f5c8.png)

## example 02
```
docker run --name db -d mongo:3.2 mongod --smallfiles
docker run --name rocketchat -p 3000:3000 --env ROOT_URL=http://localhost --link db:db -d rocket.chat:0.62
docker ps
docker images
```
![Screenshot (1061)](https://user-images.githubusercontent.com/44063772/180467373-84d05d69-295c-4fbf-aaa1-249a2a5a17ff.png)
![image](https://user-images.githubusercontent.com/44063772/180467332-0f5c3e40-8e58-44ed-b1cd-854cf5ee87c6.png)


## example 03
```
# Comments in Dockerfiles
FROM python:3.5

# Update and install dependencies
RUN apt-get update
RUN pip install Flask

# Add code
ADD . /opt/webapp/

# Set the working directory
WORKDIR /opt/webapp

# Set environment variables
ENV FLASK_APP=hello.py

# Expose the application's port
EXPOSE 5000

# Run the application
CMD ["flask", "run", "--host=0.0.0.0"]
```
![image](https://user-images.githubusercontent.com/44063772/180468231-679ea139-e0e4-42bf-bef5-2377c079d9cf.png)
```
docker build -t hello.py .
```
![image](https://user-images.githubusercontent.com/44063772/180469282-973a3a10-cfb3-41d0-a2ca-bd4a8d71c354.png)
```
docker run -p 5000:5000 hello.py
```
![image](https://user-images.githubusercontent.com/44063772/180469550-f741432b-265f-4c73-a59d-9b3f9f1a0e2c.png)

## example 04
```
cd messageApp
touch Dockerfile
```
![image](https://user-images.githubusercontent.com/44063772/180471339-24c83093-3756-44f4-a0f5-2b084543dcdf.png)
```
vi Dockerfile
FROM node:10.15.3
ENV LAST_UPDATED 20190325T175400
COPY . /app
WORKDIR /app
RUN npm install
RUN npm audit fix
EXPOSE 1337
CMD ["node","app.js"]
```
![image](https://user-images.githubusercontent.com/44063772/180471631-b06a5015-c5dd-4f80-ae38-8d3b15892083.png)
```
docker build -t message-app .
```
![image](https://user-images.githubusercontent.com/44063772/180472082-616f5a64-72bb-490c-ade1-870f26a7c517.png)
```
docker images
```
![image](https://user-images.githubusercontent.com/44063772/180472202-21859c87-4f31-44ee-9923-e3616617fb90.png)
```
docker run message-app
```
![image](https://user-images.githubusercontent.com/44063772/180472306-34b5fe3d-8707-486c-9e00-b5a305f8e16c.png)
```
vim docker-compose.yml

version: '3'
services:
  mongo:
    image: mongo:4.0.7
    volumes:
      - mongo-data:/data/db
    expose:
      - "27017"
  app:
    build: .
    ports:
            - "1337:1337"
    links:
      - mongo
    depends_on:
      - mongo
    environment:
      - MONGO_URL=mongodb://mongo/messageApp
volumes:
  mongo-data:
```
![image](https://user-images.githubusercontent.com/44063772/180473632-5df6eeac-514c-4d05-bb3b-cf39178cbaf2.png)
```
docker-compose build
```
![image](https://user-images.githubusercontent.com/44063772/180473848-bfda0b77-febc-4026-b6e0-071c3f25598f.png)
```
docker-compose up
```
![Screenshot (1073)](https://user-images.githubusercontent.com/44063772/180474069-183477cd-700c-412b-b5e1-f9337b569b9f.png)
![image](https://user-images.githubusercontent.com/44063772/180474041-c86defa5-8c1e-4bda-a1c3-3b6035e585b3.png)
```
cd -
curl http://localhost:1337/message
```
