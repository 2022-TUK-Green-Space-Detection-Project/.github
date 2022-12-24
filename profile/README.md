# 2022 TUK Green Space Detection Project

## Subject

Development the green space detection module using vggnet11 at Google Earth

## Problem Statement

Our goal is making module using vggnet11 to detect the portion of green space at input image captured in Google Earth 
and improving performance of existing module described in previous studies
(Youn, Y.-S., Kim, K.-B. and Park, H.-J. (2020) “Measurements of Green Space Ratio in Google Earth using Convolutional Neural Network,” Journal of the Korea Institute of Information and Communication Engineering. 한국정보통신학회, 24(3), pp. 349–354. doi: 10.6109/JKIICE.2020.24.3.349.
).

## Dataset

To collect the data, we captured images from Google Earth and collected a total of 200 images of size 224 by 224. (Altitude fixed at 1 km)

Additionally, to increase the size of the dataset, we augmented the data to a total of 3200 images.

[Kaggle Link](https://www.kaggle.com/datasets/choemarco/green-space-dataset)

## Model

* Model Architectur : VGGNET11

<img width="643" alt="image" src="https://user-images.githubusercontent.com/57928967/209422260-46593051-151c-4e25-bfe7-2698104cc01c.png">


## Training

Due to the lack of memory, we conducted transfer learning on the model three times with 800 copies of the data.

### Train Dataset & Test Dataset
<img width="885" alt="image" src="https://user-images.githubusercontent.com/57928967/209421924-5615563c-d954-47ad-9ea8-a9132e07cbb1.png">

### Loss Graph
#### Otimizer Comparison
<img width="1382" alt="image" src="https://user-images.githubusercontent.com/57928967/209422034-e5eb2c99-44b3-4b2e-836d-63cbb9495e3a.png">

#### Learing Rate Comparison
<img width="1271" alt="image" src="https://user-images.githubusercontent.com/57928967/209422101-d8569b20-eb4e-4d80-a7b2-02724ba62141.png">

### Transfer Learning
<img width="1288" alt="image" src="https://user-images.githubusercontent.com/57928967/209422009-9dc16ec7-0c74-4da8-b5bc-85691cffcec0.png">


## Results

### Best Hyperparameter

* Optimizer : Adagrad

* Criterion : CrossLossEntropy

* Learning Rate : 0.0001

* Batch Size : 256

* Epoch : 100

### Test

<img width="1271" alt="image" src="https://user-images.githubusercontent.com/57928967/209422133-d90bd73b-857f-48bc-8e57-a869bbd6cb3a.png">
<img width="1270" alt="image" src="https://user-images.githubusercontent.com/57928967/209422136-a0016d54-940c-4b15-9e66-b5879468602b.png">

## Conclusion

It showed an improved error than the 13.71% error suggested in the paper. However, it is a result that has not been sufficiently tested, so supplementation is required later.

# Reference

[합성곱 신경망을 이용한 구글 어스에서의 녹지 비율 측정](https://scienceon.kisti.re.kr/srch/selectPORSrchArticle.do?cn=JAKO202005653789633)
