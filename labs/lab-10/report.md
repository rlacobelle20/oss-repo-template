## Step 1
```sudo -i -u couchdb /opt/couchdb/bin/couchdb ```
![image](https://user-images.githubusercontent.com/44063772/181786843-217d9799-b480-434d-826d-25ca8c21c0b8.png)

## Step 2
### Part 1
```curl http://127.0.0.1:5984/```
![image](https://user-images.githubusercontent.com/44063772/181799769-7f627dc4-7a18-4b70-9fff-0a15809078dd.png)
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

### Part 3
![image](https://user-images.githubusercontent.com/44063772/181797223-2a96b2c7-4220-4712-8400-0b21941a7ec8.png)

### Part 4
![image](https://user-images.githubusercontent.com/44063772/181797890-411812e3-ba29-4787-ac68-c9993ace7b91.png)
![image](https://user-images.githubusercontent.com/44063772/181798504-3b74b7df-6af1-4fbb-a885-c9d86ba537f8.png)
![image](https://user-images.githubusercontent.com/44063772/181798583-2dd5a27c-c587-4ac4-995e-7fa66d58b1b7.png)

### Part 5
![image](https://user-images.githubusercontent.com/44063772/181798986-9dc43e33-15c2-439e-b799-2968af032ae3.png)
![image](https://user-images.githubusercontent.com/44063772/181799030-5247a125-3fed-412d-8c6e-47b4491d44ec.png)
![image](https://user-images.githubusercontent.com/44063772/181799081-7811541a-e0ac-4c31-b758-490e91fcc8a4.png)
![image](https://user-images.githubusercontent.com/44063772/181799141-43b0023b-833e-440e-9781-9507d904605b.png)

### Part 6
Moved to next step

## Step 3

### Part 7
#### Section 1
```curl http://127.0.0.1:5984/```
![image](https://user-images.githubusercontent.com/44063772/181799769-7f627dc4-7a18-4b70-9fff-0a15809078dd.png)

#### Section 2
```curl -X PUT http://admin:admin@127.0.0.1:5984/albums```
![image](https://user-images.githubusercontent.com/44063772/181800326-48419477-b121-402b-8706-f4b786739c9a.png)
```curl -X PUT http://admin:admin@127.0.0.1:5984/albums```
![image](https://user-images.githubusercontent.com/44063772/181800465-3c34185b-85cb-4a02-b055-309e5098afca.png)
```curl -vX PUT http://admin:admin@127.0.0.1:5984/albums-backup```
![image](https://user-images.githubusercontent.com/44063772/181800570-246481e0-dc03-4c0b-8269-5a21018e7d57.png)
```curl -vX DELETE http://admin:admin@127.0.0.1:5984/albums-backup```
![image](https://user-images.githubusercontent.com/44063772/181800878-89dc1976-c3eb-4cc2-9a87-d4529ad767e5.png)

#### Section 3
```curl -X PUT http://admin:admin@127.0.0.1:5984/albums/6e1295ed6c29495e54cc05947f18c8af -d '{"title":"There is Nothing Left to Lose","artist":"Foo Fighters"}'```
![image](https://user-images.githubusercontent.com/44063772/181801044-0d5d6209-ecfd-4140-b62d-d34d40663ae0.png)
```curl -X GET http://admin:admin@127.0.0.1:5984/albums/6e1295ed6c29495e54cc05947f18c8af```
![image](https://user-images.githubusercontent.com/44063772/181801151-81cd9f67-f071-4278-befa-559d4f6e5933.png)
```curl -X PUT http://admin:admin@127.0.0.1:5984/albums/6e1295ed6c29495e54cc05947f18c8af \ -d '{"title":"There is Nothing Left to Lose","artist":"Foo Fighters","year":"1997"}'```
![image](https://user-images.githubusercontent.com/44063772/181801304-4d48299b-aa76-449d-af51-653384320328.png)
```curl -X PUT http://admin:admin@127.0.0.1:5984/albums/6e1295ed6c29495e54cc05947f18c8af \ -d '{"_rev":"1-2902191555","title":"There is Nothing Left to Lose","artist":"Foo Fighters","year":"1997"}'```
![image](https://user-images.githubusercontent.com/44063772/181801541-1b2fe591-2691-4418-9514-6ab5f9893a8e.png)
```curl -vX PUT http://admin:admin@127.0.0.1:5984/albums/70b50bfa0a4b3aed1f8aff9e92dc16a0 \ -d '{"title":"Blackened Sky","artist":"Biffy Clyro","year":2002}'```
![image](https://user-images.githubusercontent.com/44063772/181801744-3443dd09-db49-4188-8f95-f2ff334a2ed0.png)
```curl -vX PUT http://admin:admin@127.0.0.1:5984/albums/6e1295ed6c29495e54cc05947f18c8af/artwork.jpg?rev=2-2739352689 \ --data-binary @artwork.jpg -H "Content-Type:image/jpg"```
![image](https://user-images.githubusercontent.com/44063772/181801944-0089a6bd-eed7-4cd3-95ff-d9cddb9512d1.png)
```curl http://admin:admin@127.0.0.1:5984/albums/6e1295ed6c29495e54cc05947f18c8af```
![image](https://user-images.githubusercontent.com/44063772/181802179-3ad18829-7d52-4b6e-a0be-c0947941e36b.png)
#### Section 4
```curl -X PUT http://admin:admin@127.0.0.1:5984/albums-replica```
![image](https://user-images.githubusercontent.com/44063772/182038781-37c0c3df-03c2-4b3e-b802-61fa131a2c2d.png)
```curl -vX POST http://admin:admin@127.0.0.1:5984/_replicate \
     -d '{"source":"http://127.0.0.1:5984/albums","target":"http://127.0.0.1:5984/albums-replica"}' \
     -H "Content-Type: application/json"```
## Step 4
