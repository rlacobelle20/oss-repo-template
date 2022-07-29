## Step 1
```sudo -i -u couchdb /opt/couchdb/bin/couchdb ```
![image](https://user-images.githubusercontent.com/44063772/181786843-217d9799-b480-434d-826d-25ca8c21c0b8.png)

## Step 2
### Part 1
```curl http://127.0.0.1:5984/```
![image](https://user-images.githubusercontent.com/44063772/181789339-bfc27fb1-20ba-4970-b057-ea98952aeb0a.png)
``` http://admin:admin@127.0.0.1:5984/_all_dbs```
![image](https://user-images.githubusercontent.com/44063772/181794972-4c7eb9dd-7e9f-4e4e-a26b-3e6b2f8503c4.png)
```curl -X PUT http://admin:admin@127.0.0.1:5984/baseball```
![image](https://user-images.githubusercontent.com/44063772/181795274-4ba63615-8cee-49c7-b447-b301e279d2ce.png)
```curl -X GET http://admin:admin@127.0.0.1:5984/_all_dbs```
![image](https://user-images.githubusercontent.com/44063772/181795399-b10d4c65-224a-4435-b2c9-4f0424dc8ddf.png)
```curl -X PUT http://admin:admin@127.0.0.1:5984/baseball```
![image](https://user-images.githubusercontent.com/44063772/181795606-fbda56e7-9438-4c5d-b578-9c641f6f10e1.png)
```curl -X PUT http://admin:admin@127.0.0.1:5984/plankton```
![image](https://user-images.githubusercontent.com/44063772/181795809-199f40e6-bb8e-4f4d-b676-6a069cc7a140.png)
```curl -X GET http://admin:admin@127.0.0.1:5984/_all_dbs```
![image](https://user-images.githubusercontent.com/44063772/181796003-496cb071-e0bb-41f2-b452-73f4fd418b39.png)
```curl -X DELETE http://admin:admin@127.0.0.1:5984/plankton```
![image](https://user-images.githubusercontent.com/44063772/181796119-fd6cdf0b-1046-4f7c-8169-557b95d44389.png)
```curl -X GET http://admin:admin@127.0.0.1:5984/_all_dbs```
![image](https://user-images.githubusercontent.com/44063772/181796241-aff19fe3-74bd-45e6-906c-9f3261bbddce.png)
### Part 2
```http://127.0.0.1:5984/_utils/```
![image](https://user-images.githubusercontent.com/44063772/181796528-c93f8db6-b52b-4c61-a2b8-8944ba47a6e3.png)
![image](https://user-images.githubusercontent.com/44063772/181797223-2a96b2c7-4220-4712-8400-0b21941a7ec8.png)
### Part 3
![image](https://user-images.githubusercontent.com/44063772/181797890-411812e3-ba29-4787-ac68-c9993ace7b91.png)
![image](https://user-images.githubusercontent.com/44063772/181798504-3b74b7df-6af1-4fbb-a885-c9d86ba537f8.png)
![image](https://user-images.githubusercontent.com/44063772/181798583-2dd5a27c-c587-4ac4-995e-7fa66d58b1b7.png)
### Part 4

## Step 3

## Step 4
