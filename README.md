# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image

##### Program:
### Developed By: M.SAKTHIVEL
### Register Number: 212222240088


### i) Read and display the image
```
import cv2
image=cv2.imread('p-3.jpg',1)
image=cv2.resize(image,(400,300))
cv2.imshow('sakthivel',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![dip out 1](https://github.com/Sakthimurugavel/COLOR_CONVERSIONS_OF-IMAGE/assets/118707246/fd9d22eb-daea-41a6-a803-bc3ee8f4226a)

### ii)Write the image
```
image=cv2.imread('p-3.jpg',0)
cv2.imwrite('d.jpg',image)
```
## Output:
![dip out 2](https://github.com/Sakthimurugavel/COLOR_CONVERSIONS_OF-IMAGE/assets/118707246/4c4aa88f-5754-4806-980c-30dff4333c3f)

### iii)Shape of the Image
```
image=cv2.imread('p-3.jpg',1)
print(image.shape)
```
## Output:
![dip out 3](https://github.com/Sakthimurugavel/COLOR_CONVERSIONS_OF-IMAGE/assets/118707246/0bc08f5b-dde2-4876-89a6-ae143e80f10c)

### iv)Access rows and columns
```
import cv2
import random
image=cv2.imread('p-3.jpg',1)
image=cv2.resize(image,(400,400))
for i in range (150,200):
    for j in range(image.shape[1]):
        image[i][j]=[random.randint(0,255),
                     random.randint(0,255),
                     random.randint(0,255)] 
cv2.imshow('part image',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![dip out 4](https://github.com/Sakthimurugavel/COLOR_CONVERSIONS_OF-IMAGE/assets/118707246/047533c0-90c2-4473-87f8-2279536f7c82)

### v)Cut and paste portion of image
```
image=cv2.imread('p-3.jpg',1)
image=cv2.resize(image,(400,400))
tag =image[130:200,110:190]
image[110:180,120:200] = tag
cv2.imshow('partimage1',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![dip out 5](https://github.com/Sakthimurugavel/COLOR_CONVERSIONS_OF-IMAGE/assets/118707246/13a78f44-957d-4e78-80c9-51e8cb218c94)


### vi) BGR and RGB to HSV and GRAY
```
img = cv2.imread('p-3.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)
hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('BGR2HSV',hsv1)
hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)
gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('BGR2GRAY',gray1)
gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![dip out 6-1](https://github.com/Sakthimurugavel/COLOR_CONVERSIONS_OF-IMAGE/assets/118707246/d95cc079-7011-403b-a29a-61fcf07bd109)![dip out 6-2](https://github.com/Sakthimurugavel/COLOR_CONVERSIONS_OF-IMAGE/assets/118707246/3cd32ef5-e17a-46d8-a6e3-9ae5edeb1023)![dip out 6-3](https://github.com/Sakthimurugavel/COLOR_CONVERSIONS_OF-IMAGE/assets/118707246/71e9bda1-b3f6-4aa1-a9ca-7d2c7d7ca295)![dip out 6-4](https://github.com/Sakthimurugavel/COLOR_CONVERSIONS_OF-IMAGE/assets/118707246/4779b557-2e08-4eda-a8f0-c918619a0679)
![dip out 6-5](https://github.com/Sakthimurugavel/COLOR_CONVERSIONS_OF-IMAGE/assets/118707246/22fdef7c-e109-4d5c-9104-cb56c39e91e0)


### vii) HSV to RGB and BGR
```
img = cv2.imread('p-3.jpg')
img = cv2.resize(img,(300,200))
img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)
RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)
BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![dip out 7-1](https://github.com/Sakthimurugavel/COLOR_CONVERSIONS_OF-IMAGE/assets/118707246/ea57819d-4a61-4f1e-a900-1fd8af705a7f)![dip out 7-2](https://github.com/Sakthimurugavel/COLOR_CONVERSIONS_OF-IMAGE/assets/118707246/6b305332-04ee-4370-bc6a-0b8cdbc55fca)![dip out 7-3](https://github.com/Sakthimurugavel/COLOR_CONVERSIONS_OF-IMAGE/assets/118707246/0a270b60-3a78-4ded-95ff-ee62b82ffe72)

### viii) RGB and BGR to YCrCb
```
img = cv2.imread('p-3.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)
YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)
YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![dip out 8-1](https://github.com/Sakthimurugavel/COLOR_CONVERSIONS_OF-IMAGE/assets/118707246/65a2e4ba-7ea0-4ea7-bbcb-c55b639632c1)![dip out 8-2](https://github.com/Sakthimurugavel/COLOR_CONVERSIONS_OF-IMAGE/assets/118707246/d9f891dd-03cf-4048-8e1f-9a40e4ae7aa9)![dip out 8-3](https://github.com/Sakthimurugavel/COLOR_CONVERSIONS_OF-IMAGE/assets/118707246/306c1d4d-e616-435a-a095-9bbbbcccce33)


### ix) Split and merge RGB Image
```
img = cv2.imread('p-3.jpg',1)
img = cv2.resize(img,(300,200))
R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]
cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)
merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![dip out 9-1](https://github.com/Sakthimurugavel/COLOR_CONVERSIONS_OF-IMAGE/assets/118707246/0669fd41-d63a-4440-be6e-eeadbb39e70f)![dip out 9-2](https://github.com/Sakthimurugavel/COLOR_CONVERSIONS_OF-IMAGE/assets/118707246/6f7b5353-87e8-4098-9541-01c0e28d3476)![dip out 9-3](https://github.com/Sakthimurugavel/COLOR_CONVERSIONS_OF-IMAGE/assets/118707246/875d0e1a-4fa1-43b4-8c31-1fd34216efda)![dip out 9-4](https://github.com/Sakthimurugavel/COLOR_CONVERSIONS_OF-IMAGE/assets/118707246/a84b0133-5872-4edd-9373-49965ef2bb83)

### x) Split and merge HSV Image
```
img = cv2.imread("p-3.jpg",1)
img = cv2.resize(img,(300,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
H,S,V=cv2.split(img)
cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)
merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![dip out 10-1](https://github.com/Sakthimurugavel/COLOR_CONVERSIONS_OF-IMAGE/assets/118707246/c0428718-76bc-4f70-b80a-83b46b6d6568)![dip out 10-2](https://github.com/Sakthimurugavel/COLOR_CONVERSIONS_OF-IMAGE/assets/118707246/de32907a-de4a-451e-b885-5090914a1b16)![dip out 10-3](https://github.com/Sakthimurugavel/COLOR_CONVERSIONS_OF-IMAGE/assets/118707246/45aeae38-2323-4cf5-9f7e-de796dbec6fc)![dip out 10-4](https://github.com/Sakthimurugavel/COLOR_CONVERSIONS_OF-IMAGE/assets/118707246/edd3db6b-ac05-4514-b77f-219802433f67)

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







