
# Demo for visualizing CNNs using Guided_Grad_Gam and Grad_cam


#### Sivateja Gollapudi

Built on the work of  [utkuozbulak/pytorch-cnn-visualizations](https://github.com/utkuozbulak/pytorch-cnn-visualizations)

###### vis_grad file contains model_compare function which is used to visualize guided_gradcam_back_prop and model_compare_cam perfroms grad_cam


```python
from vis_grad import model_compare_cam , model_compare
```

###### import pretrained models using torch vision models (custom models can be used)


```python
from torchvision import models
```

###### using 3 models , alex net , dense net 121 and resnet 152 


```python
md=models.alexnet(pretrained=True)
md2=models.densenet121(pretrained=True)
md3=models.resnet152(pretrained=True)
md4 = models.vgg16(pretrained=True)
```

###### input image size used by the network


```python
size=[224,224]
```

###### create a list containing (model,'model name to print',[input image size,input image size]) for each model 


```python
list=[[md,'alexnet',size],[md2,'densenet121',size],[md3,'resnet152',size],[md4,'vgg',size]]
```

###### pass the list , class number , layer to visualize , input_image to visualize on 


```python
model_compare(list,56,6,'../input_images/snake.jpg')
```

    Grad cam completed
    Guided backpropagation completed
    Guided grad cam completed
    Grad cam completed
    Guided backpropagation completed
    Guided grad cam completed
    Grad cam completed
    Guided backpropagation completed
    Guided grad cam completed
    Grad cam completed
    Guided backpropagation completed
    Guided grad cam completed
    


![png](https://github.com/TejaGollapudi/pytorch-cnn-visualizations/blob/master/display/output_10_1.png?raw=true)



![png](https://github.com/TejaGollapudi/pytorch-cnn-visualizations/blob/master/display/output_10_2.png?raw=true)

###### Images are automatically saved in result folder

###### For visualizing grad_cam


```python
model_compare_cam(list,56,10,'../input_images/snake.jpg')
```

    Grad cam completed
    Grad cam completed
    Grad cam completed
    Grad cam completed
    


![png](https://github.com/TejaGollapudi/pytorch-cnn-visualizations/blob/master/display/output_13_1.png?raw=true)



![png](https://github.com/TejaGollapudi/pytorch-cnn-visualizations/blob/master/display/output_13_2.png?raw=true)



![png](https://github.com/TejaGollapudi/pytorch-cnn-visualizations/blob/master/display/output_13_3.png?raw=true)


