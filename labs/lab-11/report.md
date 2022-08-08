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
```
# TensorFlow and tf.keras
import tensorflow as tf

# Helper libraries
import numpy as np
import matplotlib.pyplot as plt

print(tf.__version__)
```
![image](https://user-images.githubusercontent.com/44063772/183336100-592612e1-b5d7-4bef-8581-ad7fd3f48597.png)

```
fashion_mnist = tf.keras.datasets.fashion_mnist
(train_images, train_labels), (test_images, test_labels) = fashion_mnist.load_data()
```
![image](https://user-images.githubusercontent.com/44063772/183338826-432f7a55-8e26-4f97-a4ad-c0cee68cfa25.png)

```
class_names = ['T-shirt/top', 'Trouser', 'Pullover', 'Dress', 'Coat',
               'Sandal', 'Shirt', 'Sneaker', 'Bag', 'Ankle boot']
train_images.shape
len(train_labels)
train_labels
train_images.shape
len(train_labels)
```
![image](https://user-images.githubusercontent.com/44063772/183338992-f3a89613-92cb-468a-bfa6-8c7576b328e9.png)

```
plt.figure()
plt.imshow(train_images[0])
plt.colorbar()
plt.grid(False)
plt.show()
```
![image](https://user-images.githubusercontent.com/44063772/183339196-bc34f48b-5bb4-4494-860e-fa6d4542e5a8.png)
![image](https://user-images.githubusercontent.com/44063772/183339261-39d3a759-a935-49f2-9b9e-560dc0ab11b3.png)

```
train_images = train_images / 255.0
test_images = test_images / 255.0
plt.figure(figsize=(10,10))
for i in range(25):
    plt.subplot(5,5,i+1)
    plt.xticks([])
    plt.yticks([])
    plt.grid(False)
    plt.imshow(train_images[i], cmap=plt.cm.binary)
    plt.xlabel(class_names[train_labels[i]])
plt.show()
```


```
model = tf.keras.Sequential([
    tf.keras.layers.Flatten(input_shape=(28, 28)),
    tf.keras.layers.Dense(128, activation='relu'),
    tf.keras.layers.Dense(10)
])
model.compile(optimizer='adam',
              loss=tf.keras.losses.SparseCategoricalCrossentropy(from_logits=True),
              metrics=['accuracy'])
model.fit(train_images, train_labels, epochs=10)
```
![image](https://user-images.githubusercontent.com/44063772/183340316-c5720799-3457-483c-b30b-3e0151b98fba.png)

```
test_loss, test_acc = model.evaluate(test_images,  test_labels, verbose=2)
print('\nTest accuracy:', test_acc)
```
![image](https://user-images.githubusercontent.com/44063772/183340356-dfa8e028-b504-428e-9b9a-fa4bd15336b8.png)

```
probability_model = tf.keras.Sequential([model, 
                                         tf.keras.layers.Softmax()])
predictions = probability_model.predict(test_images)
predictions[0]
```
![image](https://user-images.githubusercontent.com/44063772/183340435-0f5788b4-35ab-4b80-801e-22ee40b0aaf9.png)

```
np.argmax(predictions[0])
test_labels[0]
```
![image](https://user-images.githubusercontent.com/44063772/183340570-7b23bdd3-832e-44b8-b1c2-3db371cf1405.png)

```
def plot_image(i, predictions_array, true_label, img):
  true_label, img = true_label[i], img[i]
  plt.grid(False)
  plt.xticks([])
  plt.yticks([])
  plt.imshow(img, cmap=plt.cm.binary)
  predicted_label = np.argmax(predictions_array)
  if predicted_label == true_label:
    color = 'blue'
  else:
    color = 'red'
  plt.xlabel("{} {:2.0f}% ({})".format(class_names[predicted_label],
                                100*np.max(predictions_array),
                                class_names[true_label]),
                                color=color)

def plot_value_array(i, predictions_array, true_label):
  true_label = true_label[i]
  plt.grid(False)
  plt.xticks(range(10))
  plt.yticks([])
  thisplot = plt.bar(range(10), predictions_array, color="#777777")
  plt.ylim([0, 1])
  predicted_label = np.argmax(predictions_array)
  thisplot[predicted_label].set_color('red')
  thisplot[true_label].set_color('blue')
```

```
i = 0
plt.figure(figsize=(6,3))
plt.subplot(1,2,1)
plot_image(i, predictions[i], test_labels, test_images)
plt.subplot(1,2,2)
plot_value_array(i, predictions[i],  test_labels)
plt.show()
```
![image](https://user-images.githubusercontent.com/44063772/183341845-dfa56d45-db1e-47b5-a6b2-f07ed19efbdc.png)

```
i = 12
plt.figure(figsize=(6,3))
plt.subplot(1,2,1)
plot_image(i, predictions[i], test_labels, test_images)
plt.subplot(1,2,2)
plot_value_array(i, predictions[i],  test_labels)
plt.show()
```
![image](https://user-images.githubusercontent.com/44063772/183341885-5970d56c-06df-406b-98a7-7021678f40f7.png)

```
# Plot the first X test images, their predicted labels, and the true labels.
# Color correct predictions in blue and incorrect predictions in red.
num_rows = 5
num_cols = 3
num_images = num_rows*num_cols
plt.figure(figsize=(2*2*num_cols, 2*num_rows))
for i in range(num_images):
  plt.subplot(num_rows, 2*num_cols, 2*i+1)
  plot_image(i, predictions[i], test_labels, test_images)
  plt.subplot(num_rows, 2*num_cols, 2*i+2)
  plot_value_array(i, predictions[i], test_labels)
plt.tight_layout()
plt.show()
```

```
# Grab an image from the test dataset.
img = test_images[1]
print(img.shape)
# Add the image to a batch where it's the only member.
img = (np.expand_dims(img,0))
print(img.shape)
predictions_single = probability_model.predict(img)
print(predictions_single)
```
![image](https://user-images.githubusercontent.com/44063772/183342221-a5d3f7b4-95c9-4eda-83ef-1af9c466b7bb.png)

```
plot_value_array(1, predictions_single[0], test_labels)
_ = plt.xticks(range(10), class_names, rotation=45)
plt.show()
```
![image](https://user-images.githubusercontent.com/44063772/183342248-8d31c02e-831a-4139-b74f-d7c5d467fea0.png)

```
np.argmax(predictions_single[0])
```
![image](https://user-images.githubusercontent.com/44063772/183342313-d9234cc9-efe2-499a-9517-2195ea2fc774.png)

```
# Plot the first X test images, their predicted label, and the true label
# Color correct predictions in blue, incorrect predictions in red
num_rows = 5
num_cols = 3
num_images = num_rows*num_cols
plt.figure(figsize=(2*2*num_cols, 2*num_rows))
for i in range(num_images):
  plt.subplot(num_rows, 2*num_cols, 2*i+1)
  plot_image(i, predictions, test_labels, test_images)
  plt.subplot(num_rows, 2*num_cols, 2*i+2)
  plot_value_array(i, predictions, test_labels)
plt.show()
```
![image](https://user-images.githubusercontent.com/44063772/183342633-11aa40c2-2b20-4549-9310-4d3a17ec4d77.png)



## CHeckpoint 3
