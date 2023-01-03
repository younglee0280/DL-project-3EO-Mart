# DL-finalproject-3EO-Mart
### "No Barcode! Just Scan!"
딥러닝 모델을 활용한 객체 탐지 편의점
<br></br>


## :soccer: Trouble Shooting :running:
#### 1. 데이터 찾기
1)마트에서 판매하는 품목들의 데이터를 수집하고자 공공데이터, AI Hub, kaggle 등 다양한 사이트를 방문했지만 우리 팀의 조건에 맞는 데이터(1. 모델에게 학습시킬 사진이 다방면으로 찍혀있는 데이터 2. 마트에서 흔히, 대표적으로 볼 수 있는 품목의 데이터 3. 한 품목당 30장 이상의 화질이 좋은 데이터)를 찾을 수 없었고 있다고 해도 78GB나 되는 양의 그것도 한쪽 방면으로만 찍혀있는 데이터였기에 사용할 수 없었다. 외국 마트 사이트(Amazon)의 경우 우리나라에서 파는 품목과 맞는 데이터가 있지 않았고 미국 본사에서 허가를 받아야만 사용할 수 있는 데이터였다. (게다가 달러 지불)</br>
2)고민끝에 직접 우리나라 마트에서 살 수 있는 품목들의 사진을 촬영해 학습 데이터로 활용했다.
#### 2. roboflow - tfrecord
1)tfrecord가 필요한 이유? - 
tfrecord 파일은 텐서플로우 학습 데이터를 효율적으로 저장하기 위한 포맷, tfrecord 파일이 없으면 CNN으로 학습 시 이미지와 라벨을 별도로 읽어와야 하는데 여기서 성능 저하가 발생할 수 있으며 코드도 복잡해진다. </br>
1-1)pytorch가 아닌 tensorflow 기반의 데이터셋을 쓰고 싶어 roboflow에서 tensorflow tfrecord zip파일로 다운받았으나 이미지와 라벨링이 되어있는 상태라 헤맸고, 파일을 불러오는 경로도 맞지 않는 등 시간이 소요됐다. </br>
1-2)roboflow의 문제 - 데이터를 라벨링하거나 증강시키는 역할과 roboflow안에서의 모델로 학습시켜 단편적인 결과를 보는 데에는 사용하기 편리했으나 직접 층을 만들어 모델을 만들어야 하는 우리 팀에서의 목표와 서로 방향이 달라 어려움이 있었다.

#### 3. 모델 선정
#### 4. 모델 해석
