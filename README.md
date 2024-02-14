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
### Developed By:
### Register Number: 


## Output:

### i) Read and display the image
```
    import cv2
    image=cv2.imread('dip.exp 1.jpg',1)
    image=cv2.resize(image,(300,300))
    cv2.imshow('SIVA CHANDRAN',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
## Output:
![image](https://github.com/SivaChandranR07/COLOR_CONVERSIONS_OF-IMAGE/assets/113497395/1b3f0636-cfac-4ff5-915c-4ae7a8807085)

<br>
<br>

### ii)Write the image
```
    import cv2
    image=cv2.imread('demos.jpg',0)
    cv2.imwrite('demos.jpg',image)
```
## Output:
![image](https://github.com/SivaChandranR07/COLOR_CONVERSIONS_OF-IMAGE/assets/113497395/76f62091-59e4-4823-85c2-84e379b6f20c)


<br>
<br>

### iii)Shape of the Image
```
   import cv2
    image=cv2.imread('dip.exp 1.jpg',1)
    print(image.shape)
```
## Output:

![image](https://github.com/SivaChandranR07/COLOR_CONVERSIONS_OF-IMAGE/assets/113497395/59729427-e3f0-4860-9030-194f93a0d732)

<br>
<br>

### iv)Access rows and columns
```
import random
import cv2
image=cv2.imread('dip.exp 1.jpg',1)
image=cv2.resize(image,(500,500))
for i in range (250,500):
    for j in range(image.shape[1]):
            image[i][j]=[random.randint(0,255),
                       random.randint(0,255),
                       random.randint(0,255)] 
    cv2.imshow('part image',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
## Output:
![image](https://github.com/SivaChandranR07/COLOR_CONVERSIONS_OF-IMAGE/assets/113497395/97671429-72fc-4a8e-bc27-cc1903441259)


<br>
<br>

### v)Cut and paste portion of image
```
import cv2
image=cv2.imread('dip.exp 1.jpg',1)
image=cv2.resize(image,(300,300))
tag =image[150:200,110:160]
image[110:160,150:200] = tag
cv2.imshow('image1',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![image](https://github.com/SivaChandranR07/COLOR_CONVERSIONS_OF-IMAGE/assets/113497395/dc4cb6ed-45d7-4d10-bf86-1419fd3e41a4)

<br>
<br>

### vi) BGR and RGB to HSV and GRAY
```
```
## Output:
![image](https://github.com/SivaChandranR07/COLOR_CONVERSIONS_OF-IMAGE/assets/113497395/389538f9-5f27-4d3a-927c-dbc446fcad85)

<br>
<br>

### vii) HSV to RGB and BGR
```
import cv2
img = cv2.imread('dip.exp 1.jpg')
img = cv2.resize(img,(200,200))

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
![image](https://github.com/SivaChandranR07/COLOR_CONVERSIONS_OF-IMAGE/assets/113497395/852b8bfe-1c04-4989-a4e3-cea2a70e3cc0)

<br>
<br>

### viii) RGB and BGR to YCrCb
```
import cv2
img = cv2.imread('dip.exp 1.jpg')
img = cv2.resize(img,(200,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![image](https://github.com/SivaChandranR07/COLOR_CONVERSIONS_OF-IMAGE/assets/113497395/d36697cb-6e5f-47a6-8e12-8c2724ceb371)

<br>
<br>

### ix) Split and merge RGB Image
```
import cv2
img = cv2.imread('dip.exp 1.jpg',1)
img = cv2.resize(img,(200,200))

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
![image](https://github.com/SivaChandranR07/COLOR_CONVERSIONS_OF-IMAGE/assets/113497395/39ab8cd6-b474-42de-aa7b-bf52c8a3f9fe)

<br>
<br>

### x) Split and merge HSV Image
```
import cv2
img = cv2.imread("dip.exp 1.jpg",1)
img = cv2.resize(img,(200,200))
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
![image](https://github.com/SivaChandranR07/COLOR_CONVERSIONS_OF-IMAGE/assets/113497395/ec971e7d-016f-44f2-afdc-4d5973196b83)

<br>
<br>




## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







