# yolov5_detection_fruit 


딥러닝 vision 입문기

yolo v5를 이용하여 토마토 및 파프리카의 완숙도 선별 모델을 만들고자 한다.

다음은 각 모델 테스트별 결과를 정리한 것이다.


***

## pp_test1 result 

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
  
  #### 해결책
1. 배치를 1로 줄이고, epoch를 100으로 늘림 --> 그래프의 수렴을 명확히 하고 학습을 더 정확히하기 위함.
2. 이미지 데이터셋을 늘림 --> 다각도로 보더라도 라벨이 정확히 나오도록 하기 위함.
