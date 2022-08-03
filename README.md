# yolov5_detection_fruit 


딥러닝 vision 입문기

yolo v5를 이용하여 토마토 및 파프리카의 완숙도 선별 모델을 만들고자 한다.

다음은 각 모델 테스트별 결과를 정리한 것이다.


***

## pp_test1 result 

dataset2를 이용함.

image size 224 x 224

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
1. 학습은 이상적인 수치가 나왔음. <br>
2. 동영상에 적용했을때 pass와 check가 서로 반대로 표현되는등 원하는 결과가 출력되지 않음.
3. 학습시 라벨별 traing set과 validation set 비율을 나누지 않고 total 1331장의 이미지 갯수의 비율을 8:2로 나눔.
  
  #### 해결책
1. batch를 1로 줄이고, epoch를 100으로 늘림 --> 그래프의 수렴을 명확히 하고 학습을 더 정확히하기 위함.
2. 이미지 데이터셋을 늘림 --> 다각도로 보더라도 라벨이 정확히 나오도록 하기 위함.
3. 각 라벨별 traing set과 validation set의 비율을 8:2로 나누고 각 라벨별 traing set과 validation set을 train_img_list와 val_img_list에 넣음. --> 학습의 정확도를 높이기 위해서.
