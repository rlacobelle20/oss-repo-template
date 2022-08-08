## Checkpoint 1
```
mkdir lab11
docker run -it -p 8888:8888 -v "$PWD"/lab11:/home/tensorflow -e "DISPLAY"=host.docker.internal:0 \
   wdturner/tensorflow_oss:latest
```
![Screenshot (1124)](https://user-images.githubusercontent.com/44063772/183307232-48a420a5-284c-4359-b9b4-962829967138.png)

```
from __future__ import absolute_import, division, print_function

# TensorFlow and tf.keras
import tensorflow as tf
from tensorflow import keras
from PIL import Image
from PIL import ImageOps
from tkinter import *

# Helper libraries
import numpy as np
import matplotlib.pyplot as plt

print(tf.__version__)
plt.plot((-2,4),(-6,6))
plt.show()
```
![image](https://user-images.githubusercontent.com/44063772/183335525-38fd1afd-69a5-4659-9e79-8b87a3ed3527.png)
![image](https://user-images.githubusercontent.com/44063772/183335553-ee00d7da-4fce-4ca4-aee6-7a286003bee6.png)


## Checkpoint 2

## CHeckpoint 3
