## Step 1
![Screenshot (1045)](https://user-images.githubusercontent.com/44063772/179435288-319e8583-d272-4191-8e39-e26473dd2614.png)

## Step 2
1. Find the Nightly and Experimental sections and look at some of the submissions. How can you see what tests were run for a particular submission?
    - You can click on the build name and you can see the type of test that was run.
3. Find a submission with errors. Can you see what the error condition was? How does this help you debug the failure?
    - Nightly expected --> gcc119.fsffrance.org CTestTestTimeout
    - You can see what tests were passed and what failed if you click into the test. This can help with debugging because it says exactly what failed.
5. Find a system that is close to your specific configuration in the Nightly, Nightly Expected or one of the Masters sections. How clean is the dashboard? Are there any errors that you need to be concerned with?
    - merge-requests
    - dashboard is mostly clean
    - need to be concerned with downloads
![Screenshot (1046)](https://user-images.githubusercontent.com/44063772/179444741-2bf7fd03-aecc-4be3-ae84-76fd0b960d98.png)
![Screenshot (1047)](https://user-images.githubusercontent.com/44063772/179444749-d6abb469-8412-457e-a945-6ed68006fa89.png)



## Step 3
![Screenshot (1049)](https://user-images.githubusercontent.com/44063772/179445179-96fdaf15-92d3-4f2a-84a8-a37936aac218.png)
What does -VV do? It gives specific outputs for tests.


## Step 4
![cmake-step5 repo](https://github.com/rlacobelle20/cmake-step5)

## Step 5
