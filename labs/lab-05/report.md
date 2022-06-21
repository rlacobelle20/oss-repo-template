# CMake Tutorial
## Step 1
![Screenshot (998)](https://user-images.githubusercontent.com/44063772/174339051-84dd5bec-72bd-4ae8-92d6-63afae57b4ed.png)
![Screenshot (999)](https://user-images.githubusercontent.com/44063772/174339071-d755341b-45e6-44ce-80cf-5c6d41e20f91.png)
![Screenshot (1000)](https://user-images.githubusercontent.com/44063772/174339085-501507ee-c05a-4152-bc0c-cb1b78ac174f.png)
![Screenshot (1001)](https://user-images.githubusercontent.com/44063772/174338952-be4c2a0d-0181-43af-9394-958567c26e7d.png)

## Step 2
![Screenshot (1002)](https://user-images.githubusercontent.com/44063772/174460783-0cbf0d51-ea79-4ab9-a02d-b1b07b0d17af.png)
![Screenshot (1003)](https://user-images.githubusercontent.com/44063772/174460786-a239f43a-db9c-43f4-a98c-32e8b9943915.png)
![Screenshot (1007)](https://user-images.githubusercontent.com/44063772/174460800-02f3b99c-889a-43c3-91af-1c9b5bb4cad1.png)
![Screenshot (1004)](https://user-images.githubusercontent.com/44063772/174460789-58cb79f7-aed7-47e3-88b3-56f08d5f8bde.png)
![Screenshot (1009)](https://user-images.githubusercontent.com/44063772/174460805-692b4c92-6de8-46db-b907-635a66a10416.png)
![Screenshot (1010)](https://user-images.githubusercontent.com/44063772/174460806-0ca771ce-9145-4367-ad7c-6edae9a285f7.png)
![Screenshot (1011)](https://user-images.githubusercontent.com/44063772/174460842-60b7331e-53b6-465d-ab8c-156e1f508700.png)

## Step 3
![Screenshot (1012)](https://user-images.githubusercontent.com/44063772/174460878-5c95edc5-91a2-403c-b3d7-82ff92f7bca6.png)
![Screenshot (1014)](https://user-images.githubusercontent.com/44063772/174460882-0b21aff7-77bf-4405-bd92-2c62a6a26b1a.png)
![Screenshot (1013)](https://user-images.githubusercontent.com/44063772/174460887-a9787243-f773-4f16-90a5-72275c8d79ca.png)

## Step 4
![Screenshot (1015)](https://user-images.githubusercontent.com/44063772/174460920-433202de-9af1-430a-8da9-679204a00fd0.png)
![Screenshot (1016)](https://user-images.githubusercontent.com/44063772/174460924-65c5e9a4-cc02-4b41-aa7e-0ec14bfb7650.png)
![Screenshot (1017)](https://user-images.githubusercontent.com/44063772/174460929-fe7489d8-2c2d-4cf8-8e16-c37d9f95c08f.png)

## Step 5
![Screenshot (1018)](https://user-images.githubusercontent.com/44063772/174460975-df60af3e-9ace-46c5-bc70-17fbb7d08b09.png)
![Screenshot (1019)](https://user-images.githubusercontent.com/44063772/174460979-9a6ce572-bd65-4a2a-a993-86b320d45ef0.png)
![Screenshot (1020)](https://user-images.githubusercontent.com/44063772/174460981-5a27ff3d-78bb-4be6-9d0c-d85e9a4b3e6e.png)
![Screenshot (1021)](https://user-images.githubusercontent.com/44063772/174460984-920b3a8c-6ad0-4ab2-918d-d52ae82a5aac.png)

# Makefile
## Self-created Makefile
```
all:
        gcc -c source/block.c -o build/static_block
        gcc -c --shared source/block.c -o build/dynamic_block
        gcc program.c build/static_block -o build/static.out
        gcc program.c build/dynamic_block -o build/dynamic.out
```
![Screenshot (1026)](https://user-images.githubusercontent.com/44063772/174710534-4fa3c44d-46ff-468d-af33-3200fb8015eb.png)


## CMakeLists.txt
```
cmake_minimum_required (VERSION 3.2)
#set project name
project(CMake Example)

add_library(static_block STATIC source/block.c)
add_library(dynamic_block SHARED source/block.c)

add_executable(static_cmake static_block program.c)
add_executable(dynamic_cmake dynamic_block program.c)

target_link_libraries(static_cmake LINK_PUBLIC static_block)
target_link_libraries(dynamic_cmake LINK_PUBLIC dynamic_block)

```
## CMake Makefile
```
Does not output --> My terminal was giving me output, but it did not give me a makefile for this. I think something went wrong while it was compiling.
```
![Screenshot (1025)](https://user-images.githubusercontent.com/44063772/174710547-d1d43df5-97c6-4f08-8abf-b55953100f20.png)
![image](https://user-images.githubusercontent.com/44063772/174711539-155f732b-7aa4-47a2-a008-3780ec14f97c.png)



