# project_child_detection

### 주제: 어린이 존재여부 파악 후, 운전자에게 먼저 알러주는 서비스

[프로젝트 과정]

1. 데이터 수집 : AIhub 사이트에서 데이터를 가져옴.
https://www.aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&aihubDataSe=realm&dataSetSn=169
2. 전처리
   - 데이터 용량이 커서 주제에 가장 관련이 있는 데이터만 남기고 모두 삭제하여 용량 최소화 진행
   - 분석을 하기 위해 json 파일에 있는데 영상데이터의 정보들을 frame단위로 캡쳐
   - frame에 맞는 json 정보를 가져와서 child를 1, adult를 0으로 하여 encoding을 진행.

분석하는 도중 이미지 mapping 확인하는 결과값(jupyter에서 생략된 부분. 업로드 용량으로 인해)

<img width="534" alt="image" src="https://user-images.githubusercontent.com/49609175/203236377-ec423138-fabe-4b79-a61d-f2b3c09caaa0.png" width="500" height="300">

3. 분석 & 결과
  
(SSD- Single Shot multibox Detector)
  - import libraries
  - 데이터 경로 작성
  - make vgg
  - make extras
  - loc 및 conf 모듈 구현
  - L2 Norm
  - DBox
  - Detect
  - SSD 모델 설립
  - Decode
  - nm_supperession
  - Multi Box Loss : 평가지표 결과 추출
  - 어린이 어른 데이터셋 구현
  - 신경망 구현
  - 손실함수 구현 및 학습
  - inference 실시
  
(Yolo v5 - You only look once)
  - 모델을 진행하기 전에 Yolo 좌표로 변환해주는 과정 진행
  - yaml 파일 작성
  - 모델 구현
  - tensorboard로 결과값 확인
  - webcam으로 분석 결과 확인

yolo 좌표로 변환한 값들이 잘 이미지에 그려지는지 확인하는 코드(jupyter에서 생략된 부분, 업로드 용량으로 인해)

<img width="672" alt="image" src="https://user-images.githubusercontent.com/49609175/203236613-38003ea7-44fc-4b3b-8c8e-880624747eb4.png" width="500" height="300">


# 프로젝트 기말 진행 현황


SSD 모델을 학습시키고 모델 평가지표인 loss값도 구하여 학습이 완료되었다.

하지만 이제 모델을 다른 사진에 활용하는 inference과정에서 shape문제가 계속 발생하여 방학때 계속해서 이 에러를 해결해 나가야할 것같다.

yolo 모델을 학습하고 싶었지만, 계속해서 data load과정에서 문제가 있는건지

train과정에서 객체를 인식하지 못하고 background로 인식한다. 이부분도 추후에 보완하여

yolo모델과 SSD 모델의 평가지표를 비교해보고 성능을 비교분석해보겠다.
