# yolov5_detection_fruit 


딥러닝 vision 입문기

yolo v5를 이용하여 토마토 및 파프리카의 완숙도 선별 모델을 만들고자 한다.

다음은 각 모델 테스트별 결과를 정리한 것이다.

***

## tom_test1 result

dataset을 이용함.

image size 224 x 224

batch 16 epoch 50

#### raw data set

|type|red tomato|green tomato|tomato blossom end rot|total|
|------|---|---|---|---|
|raw|100|100|100|300|

agumaentation total: 1109

colab 링크: https://colab.research.google.com/drive/1_AeNEQRcGnL5_m-uKQlX3vm7dPsboRCw#scrollTo=yy0VAiw2Wbmw

<p align = 'center'>
  <img src = 'https://github.com/EthanSeok/yolov5_detection_fruit/blob/main/tom_test1/results.png?raw=true'
       </p>

<p align = 'center'>
  <img src = 'https://user-images.githubusercontent.com/93086581/182602064-977bdc26-0c43-4cdf-900e-b2e632769cca.png'
       </p>
  동영상에 적용한 테스트 결과

### 리뷰
  학습은 이상적인 수치가 나왔음.
  
  분류결과도 비교적 정확.

  학습시 라벨별 training set과 validation set 이미지 갯수의 비율을 8:2로 나눔.
  
  
***
  
  

## pp_test1 result 

dataset2를 이용함.

image size 224 x 224
  
batch 16 epoch 50

#### raw data set

|type|check|pass|rot|total|
|------|---|---|---|---|
|raw|173|246|103|540|

agumentation total: 1331

colab 링크: https://colab.research.google.com/drive/1_AeNEQRcGnL5_m-uKQlX3vm7dPsboRCw#scrollTo=yy0VAiw2Wbmw

<p align = 'center'>
  <img src = 'https://github.com/EthanSeok/yolov5_detection_fruit/blob/main/pp_test1/result.png?raw=true'
       </p> 

  
tensorboard 링크
https://tensorboard.dev/experiment/xi5gafkqSquJJQuyrzC1Lw/#scalars
  
<p align = 'center'>
  <img src = 'https://user-images.githubusercontent.com/93086581/182566576-dabdcc59-6362-4f1c-b7c8-5b7b5eb16c7d.png'
       </p>
    동영상에 적용한 테스트 결과 
  
  
### 리뷰
  
  #### 문제점
1. 학습은 이상적인 수치가 나왔음. 
2. 동영상에 적용했을때 pass와 check가 서로 반대로 표현되는등 원하는 결과가 출력되지 않음.
3. 학습시 라벨별 training set과 validation set 비율을 나누지 않고 total 1331장의 이미지 갯수의 비율을 8:2로 나눔.
  
  #### 해결책
1. batch를 1로 줄이고, epoch를 100으로 늘림 --> 그래프의 수렴을 명확히 하고 학습을 더 정확히하기 위함.
2. 이미지 데이터셋을 늘림 --> 다각도로 보더라도 라벨이 정확히 나오도록 하기 위함.
3. 각 라벨별 training set과 validation set의 비율을 8:2로 나누고 각 라벨별 training set과 validation set을 train_img_list와 val_img_list에 넣음. --> 학습의 정확도를 높이기 위해서.
  
  
***
  
## pp_test_colab result
  
image size 224 x 224
  
batch 20 epoch 50 
  
#### dataset
  
<p align = 'center'>
  <img src = 'https://github.com/EthanSeok/yolov5_detection_fruit/blob/main/pp_test3_colab/labels.jpg?raw=true'
       </p>
  
augmentation total: 2037
  
colab 링크: https://colab.research.google.com/drive/1_AeNEQRcGnL5_m-uKQlX3vm7dPsboRCw#scrollTo=yy0VAiw2Wbmw
  
<p align = 'center'>
  <img src = 'https://github.com/EthanSeok/yolov5_detection_fruit/blob/main/pp_test3_colab/results.png?raw=true'
       </p> 
  
tensorboard 링크
https://tensorboard.dev/experiment/v7R8RGqLRdmSniqyfyNwmw/#scalars
  
<p align = 'center'>
  <img src = 'https://github.com/EthanSeok/yolov5_detection_fruit/blob/main/pp_test3_colab/%ED%99%94%EB%A9%B4%20%EC%BA%A1%EC%B2%98%202022-08-06%20212550.png?raw=true'
       </p> 
      
web cam에 적용한 결과

### 리뷰
  
  #### 문제점
1. 학습은 이상적인 수치가 나왔음. 
2. web cam에 적용했을때 pass와 check가 서로 반대로 표현되는등 원하는 결과가 출력되지 않는 빈도 적어짐.
  
  #### 해결책
1. 찾는중...
  
  
***
  
## pp_test3_local result 

dataset3를 이용함.

image size 224 x 224
  
batch 1 epoch 300

#### dataset

<p align = 'center'>
  <img src = 'https://github.com/EthanSeok/yolov5_detection_fruit/blob/main/pp_test3_local/labels.jpg?raw=true'
       </p> 

agumentation total: 2037

colab 링크: https://colab.research.google.com/drive/1_AeNEQRcGnL5_m-uKQlX3vm7dPsboRCw#scrollTo=yy0VAiw2Wbmw
  
<p align = 'center'>
  <img src = 'https://github.com/EthanSeok/yolov5_detection_fruit/blob/main/pp_test3_local/results.png?raw=true'
       </p> 

### 리뷰
  
  #### 문제점
1. 학습은 이상적인 수치가 나왔음. 
2. web cam에 적용했을때 pass와 check가 서로 반대로 표현되는등 원하는 결과가 출력되지 않음.
3. 학습시 라벨별 training set과 validation set 비율을 나누지 않고 total 2037장의 이미지 갯수의 비율을 8:2로 나눔.
4. batch를 1로 줄이고, epoch를 100으로 늘림 --> 하나를 100번 학습시킴 따라서 학습이 더 안됨(오개념이 있었음)
5. batch 20 epoch 50일때 보다 학습결과는 좋지만 테스트결과는 더 안좋음. --> batch 1로 학습시 당연한 결과.
  
  #### 해결책
1. 너무 deep 하게 학습한 결과 테스트시 결과가 더 좋지 않아지는 것같다고 판단됨. --> batch를 늘리고 epoch은 100으로 다시 시도해 보겠음.
