# Histogram equalization 

> is the way we choose to equalize the intensity of the images, [OpenCV](https://docs.opencv.org/3.4/d4/d1b/tutorial_histogram_equalization.html) has Implementation of it which handles gray images, so according to this  [StackoverFlow post](https://stackoverflow.com/questions/31998428/opencv-python-equalizehist-colored-image#38312281) in RGB images each Chanel represents the **intensity of the related color,** so we saturated the **Brightness** of the image, By using **standardized** colors paces that encode brightness and color **separately** like (YCbCr, HSV, ect ). 
![](https://github.com/AbdoAli05/Scene-Understanding-in-Low-Light-Conditions/blob/main/Images/mermaid-diagram-20220531011520.png?raw=true)
and then **Apply simple Histogram**, because Histogram lacking results, due to its lack of rag rad to outliers and the location of the pixel, we chose to implement Contrast Limited Adaptive HE witch have better slightly better RESTPlus.

## results 


>![before](https://github.com/AbdoAli05/Scene-Understanding-in-Low-Light-Conditions/blob/main/Images/befortype3.png?raw=true)

>![After](https://github.com/AbdoAli05/Scene-Understanding-in-Low-Light-Conditions/blob/main/Images/befortype3.png?raw=true)

>![before](https://github.com/AbdoAli05/Scene-Understanding-in-Low-Light-Conditions/blob/main/Images/type3befor2.png?raw=true)

>![after](https://github.com/AbdoAli05/Scene-Understanding-in-Low-Light-Conditions/blob/main/Images/type3after2.png?raw=true)

--- 

## techniques used in each task

--- 

> task 1 --> Contrast Limited Adaptive HE
> 
> task 2 --> (resnet50 - imageNet)
> 
> task 3 --> yolov5 
> 
> task 4 --> k-mean, mean shift 


### Training and Testing times. 

---

```mermaid
graph TD
    1(fa:fa-image Object detection task ) --> Y(YOLOV5) --> t[Train]-->T([Test])-->if{MSE > 50} -->|yes| t
    if -->|no| det[( detect fa:fa-water Iamges)] 
   
    2(fa:fa-image image Classification)--> res(ResNet50)-->t1[Train]
    2-->Image(net)-->t1[train] 
    t1 --> w{while acc <90 } -->|yes|t1
    w-->|no| f(Finsh)
    
    
```
 > **YOLOV5** --> 18
> 
> **ImageNEt** 5
> 
> **ResNet50** 4
> 
 > k-means and mean shift --> 5
 > 

---

## Accuracy 

---
- Image Net --> 91 acc
- YOLO5
>![](Images/photo_2022-05-31_06-57-30.jpg)
> ![](Images/photo_2022-05-31_06-58-06.jpg)
> ![](Images/photo_2022-05-31_06-58-44.jpg)
> ![](Images/Mse.jpg)
>
- segmentation 
> Results
> ![](Images/seg/3index.png)
> ![](Images/seg/33index.png)
> ![](Images/seg/5index.png)
> ![](Images/seg/55index.png)
> 
- Object detection 
>![](Images/dog1.png)
> ![](Images/2.png)
> ![](Images/3.png)
> ![](Images/4.png)
> ![](Images/5.png)